---
title: プラグインおよびワークフロー活動でバッチ要求の種類の使用を回避する | MicrosoftDocs
description: プラグインまたはワークフロー活動では ExecuteMultipleRequest または ExecuteTransactionRequest メッセージ要求クラスを使用すべきではありません。
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/06/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 6e1f27c68b020e7b22728d1c8e80c65f82e94d90
ms.sourcegitcommit: adfad395aab302fb71b56d8b7a7490265bbdaaae
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2019
ms.locfileid: "2899504"
---
# <a name="avoid-usage-of-batch-request-types-in-plug-ins-and-workflow-activities"></a>プラグインおよびワークフロー活動でバッチ要求の種類の使用を回避する

**カテゴリ**: 使用、信頼性、パフォーマンス

**影響の可能性**: 中程度

<a name='symptoms'></a>

## <a name="symptoms"></a>現象

これは長時間実行される特性を持っているため、プラグイン あるいは ワークフロー アクティビティーのコンテキスト内で <xref:Microsoft.Xrm.Sdk.Messages.ExecuteMultipleRequest> または <xref:Microsoft.Xrm.Sdk.Messages.ExecuteTransactionRequest> メッセージ要求クラスを使用すると、サンドボックス で分離された プラグイン の タイプが 2分 (12000ミリ秒) の チャネル タイムアウト例外 にさらされ、同期登録の ユーザー エクスペリエンス が低下する可能性があります。


<a name='guidance'></a>

## <a name="guidance"></a>ガイダンス

ネットワークの遅延によってスループットが低下し、大規模な一括操作の期間が長くなる可能性がある統合シナリオなど、プラットフォーム実行パイプラインの外部でコードが実行されている場合はこれらのバッチ メッセージを使用します。

さらに具体的には、次のようなシナリオで使用します:

- 長時間の操作（2 分以上）の実行を意図したデータまたは外部プロセスを一括ロードするには <xref:Microsoft.Xrm.Sdk.Messages.ExecuteMultipleRequest> を使用します。

- <xref:Microsoft.Xrm.Sdk.Messages.ExecuteMultipleRequest> を使用してユーザー定義のクライアントと Dynamics 365 サーバー間のラウンド トリップを最小限に抑え、発生する累積遅延をこれにより短縮します。

- 操作のバッチを単一のアトミック データベース トランザクションとしてコミットし、例外が発生した場合はロールバックする必要があるクライアントに <xref:Microsoft.Xrm.Sdk.Messages.ExecuteTransactionRequest> を使用します。 長期実行トランザクションの間はデータベースがブロックされる可能性に注意してください。

<a name='problem'></a>

## <a name="problematic-patterns"></a>問題となるパターン

以下はプラグインのコンテキストにおける <xref:Microsoft.Xrm.Sdk.Messages.ExecuteMultipleRequest> の使用例です。

> [!WARNING]
> このシナリオを回避する必要があります。

```csharp
public class ExecuteMultipleRequestInPlugin : IPlugin
{
    public void Execute(IServiceProvider serviceProvider)
    {
        IPluginExecutionContext context = (IPluginExecutionContext)serviceProvider.GetService(typeof(IPluginExecutionContext));
        IOrganizationServiceFactory factory = (IOrganizationServiceFactory)serviceProvider.GetService(typeof(IOrganizationServiceFactory));
        IOrganizationService service = factory.CreateOrganizationService(context.UserId);

        QueryExpression query = new QueryExpression("account")
        {
            ColumnSet = new ColumnSet("accountname", "createdon"),
        };

        //Obtain the results of previous QueryExpression
        EntityCollection results = service.RetrieveMultiple(query);

        if (results != null && results.Entities != null && results.Entities.Count > 0)
        {
            ExecuteMultipleRequest batch = new ExecuteMultipleRequest();
            foreach (Entity account in results.Entities)
            {
                account.Attributes["accountname"] += "_UPDATED";

                UpdateRequest updateRequest = new UpdateRequest();
                updateRequest.Target = account;

                batch.Requests.Add(updateRequest);
            }

            service.Execute(batch);
        }
        else return;

    }
}
```

この例は `Execute` メソッドで直接型を使用することを含みます。 プラグインまたはワークフロー活動の実行コンテキスト内のどこでも使用できます。 これは同一もしくは個別のクラスに含まれるメソッド内である可能性もあります。 それは `Execute` メソッド定義に直接含まれることに限定されません。

<a name='additional'></a>

## <a name="additional-information"></a>追加情報

`ExecuteMultiple` および `ExecuteTransaction` メッセージはバッチ要求メッセージとみなされます。 高遅延の接続でクライアントとサーバー間のラウンドトリップを最小限に抑えることが目的です。 プラグインはアプリケーション プロセスで直接実行されるか、サンドボックスで隔離されている場合はすぐに近接して実行され、これは遅延はほとんど問題にならないことを意味します。 タイムアウトしきい値の超過を回避し、同期シナリオの対応システムを確保するために、プラグインコードは迅速に実行されブロッキングを最小限に抑える非常に重点を置いた操作である必要があります。

サーバー側では、バッチ要求に含まれる操作は順次実行され、並列には実行されません。 これは次のような場合です <xref:Microsoft.Xrm.Sdk.ExecuteMultipleSettings>.<xref:Microsoft.Xrm.Sdk.ExecuteMultipleSettings.ReturnResponses> プロパティが false に設定されます。 開発者は並列処理が可能と想定してこの方法でバッチ要求を使用する傾向があります。 バッチ要求はこの目的を達成しません。 もうひとつの一般的な動機は、各操作がトランザクションに含まれるようにすることです。 プラグインは多くの場合データベース、 トランザクションのコンテキスト内ですでに実行されており、`ExecuteTransaction` メッセージを使用する必要がないため、これは必要ありません。

<a name='seealso'></a>

### <a name="see-also"></a>関連項目

[イベント フレームワーク](../../event-framework.md)<br />
[ランタイムの制限](../../org-service/execute-multiple-requests.md#run-time-limitations)<br/>
[組織サービスを使用して複数の要求を実行する](../../org-service/execute-multiple-requests.md)<br/>
[単一のデータベース トランザクションでメッセージを実行する](../../org-service/use-executetransaction.md)
