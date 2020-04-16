---
title: サービス保護 API の制限 (Common Data Service) | Microsoft Docs
description: API 要求に対するサービス保護制限について理解します。
ms.custom: ''
ms.date: 11/23/2019
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f46360623cd3cf530f9d6b2a0c7c1aecd3c66c0c
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3156483"
---
# <a name="service-protection-api-limits"></a>サービス保護の API 制限

すべてのユーザーに一貫した可用性とパフォーマンスを確実に提供するために、API の使用方法にいくつかの制限を適用します。 ユーザー アカウントごとのコンカレント接続の数、接続ごとの API 要求の数、および各接続に使用できる実行時間を制限します。 これらは、5 分間のスライド枠内で評価されます。 これらの制限のひとつを超えると、例外がプラットフォームによってスローされます。

サービス保護 API 制限は、アプリケーションを実行しているユーザーがリソースの制約に基づいて互いに干渉できないようにします。 これらの制限はプラットフォームの標準ユーザーに影響しません。 影響を受ける可能性があるのは多数の API 要求を実行するアプリケーションのみです。 この制限は、Common Data Service プラットフォームの可用性とパフォーマンス特性に対する脅威となる、ランダムに発生する予期しない要求数の急増に備えて一定レベルの保護を提供します。

プラグインとカスタム ワークフロー活動はログオンしているユーザーから独立してサーバー上で実行されるため、プラグイン コードからの API 呼び出しはサービス保護 API 制限にはカウントされません。 

## <a name="limits"></a>制限

> [!IMPORTANT]
> これらの制限は Web サーバーごとに適用されます。 各スケール グループには、負荷分散に応じて各要求を処理する複数の Web サーバーがあります。 これらの数値は単一の Web サーバーを表しているため、これらの制限により可能な限り低いスループット レベルを示しています。 実際のスループットはより高くなるはずです。
> 
> 試用環境と運用環境には大きな違いがあります。 試用環境に割り当てられるリソースは少ないため、運用環境よりも簡単にこれらの制限に遭遇します。
> 
> この数値にあまり注意を向けないでください。 理解しておくべき重要なことは、大量のデータ操作に依存するアプリケーションは、サーバーが送信する信号に応答して、制限に達したときにサーバーがそれを知らせるよう設計する必要があるということです。 この数字に基づいてソリューションをハードコーディングしようとしないでください。 代わりに、以下で説明する手法を使用して、サービスが送信する信号に応答することにより、可能な限り最高のスループットを取得します。

サービス保護の制限は、アプリケーションがパフォーマンスを最大化するために複数のスレッドを使用することを想定しています。 各スレッドは個別の接続を表し、各接続は 5 分間 (300 秒) のスライド枠で評価されます。

5 分間のスライド枠内には、次のテーブルで説明するように測定される 3 つの側面があります。

|メジャー|説明|Web サーバーごとの制限|
|--|--|--|
|要求の数|接続ごとに行われた実際の要求の数。|6000|
|実行時間|同じユーザーアカウントを使用するすべての接続の合計期間| 20 分 (1200 秒)|
|接続の数|同じユーザー アカウントを使用する接続の数|52|

**要求の数**および**実行時間**の組み合わせは、一部の操作が他の操作よりも多くのシステム リソースを必要とするという事実を説明しています。 複雑なクエリを実行するには、単一のレコードを作成または更新するより多くのシステム リソースが必要です。

プラグイン コードから行われた API 呼び出しは要求の数に対してカウントされませんが、それらの呼び出しの実行時間は発信元の呼び出しに適用されます。

ImportSolution などのすでに知られている一部の長時間のシステム操作では、制限の計算に完全な実行時間が含まれていません。 実際の実行時間がより長い場合、制限の計算に対するこれらの呼び出しの寄与は 5 分に制限されます。

アプリケーションがその制限を超える可能性がある場合は、以下の [アプリケーションが制限を超える場合に実行する内容](#what-should-i-do-if-my-application-exceeds-the-limit) セクション内で指定されたガイダンスを適用してください。

処理しているデータの性質に応じて、コンカレント接続の数を調整して最大スループットを取得できます。 各操作が比較的速い場合、より多くの接続を使用します。

## <a name="what-happens-when-the-limit-is-exceeded"></a>制限を超えると何が発生しますか

制限を超えると、同じ接続へのすべての要求に対してエラー応答が返されます。

.NET SDK アセンブリを使用している場合、プラットフォームは `FaultException<OrganizationServiceFault>` WCF エラーで応答します。  

| エラー コード | メッセージ |
|------------|-------------------------------------|
|`-2147015902`|`Number of requests exceeded the limit of 6000, measured over time window of 300 seconds.`|
|`-2147015903`|`Combined execution time of incoming requests exceeded limit of 1,200,000 milliseconds over time window of 300 seconds. Decrease number of concurrent requests or reduce the duration of requests and try again later.`|
|`-2147015898`|`Number of concurrent requests exceeded the limit of 52`|

Web API で HTTP 要求を使用する場合、応答には同じメッセージと下記が含まれます。<br />
`StatusCode` : `429`

API 要求の量が制限を下回るまで、すべての要求に対してこれらのエラー応答が返されます。 これらの応答を受ける場合、要求量が制限を下回るまで、アプリケーションは API 要求の送信を停止する必要があります。

> [!TIP]
> Web API で HTTP 要求を使用している場合、次の HTTP 応答ヘッダーで残りの制限値を追跡できます。
> 
> |[ヘッダー]  |値の説明  |
> |---------|---------|
> |`x-ms-ratelimit-burst-remaining-xrm-requests` |この接続の残りの要求の数|
> |`x-ms-ratelimit-time-remaining-xrm-requests`  |同じユーザー アカウントを使用するすべての接続の残りの合計期間|

## <a name="what-should-i-do-if-my-application-exceeds-the-limit"></a>アプリケーションが制限を超える場合何をする必要がありますか

アプリケーションが制限を超えるとき、サーバーからのエラー応答により、さらに要求を送信するまで待機する必要がある時間量が指定される可能性があります。 Web API で SDK アセンブリまたは HTTP 要求を使用する場合、応答オブジェクトは少し異なります。

ベスト プラクティスの詳細については、[Azure アーキテクチャ ベスト プラクティスでの一時的なエラー処理](/azure/architecture/best-practices/transient-faults)を参照してください

[Polly Project](https://www.thepollyproject.org/) は、実行ポリシーを使用して一時的なエラーを処理する機能を含むライブラリです。

### <a name="http-requests-with-the-web-api"></a>Web API での HTTP 要求

エラー コード 429 が発生した場合は、エラー応答に含まれる `Retry-After` HTTP ヘッダーを検索できます。 これには、フォローアップ要求を実行するまで待機する必要がある時間を示す秒単位の値が含まれます。 詳細 [MDN Web ドキュメントの後に試行](https://developer.mozilla.org/docs/Web/HTTP/Headers/Retry-After)

### <a name="sdk-assemblies"></a>SDK アセンブリ

> [!NOTE]
> 次の場合、これらのパターンを適用する必要はありません。
>
>  - コードはプラグインまたはカスタム ワークフロー活動内で実行されます。 これらの場合、サービス保護の制限は適用されないため、これらのパターンを適用する必要はありません。
>  - <xref:Microsoft.Xrm.Tooling.Connector>.<xref:Microsoft.Xrm.Tooling.Connector.CrmServiceClient> を使用します。 これらのパターンは、そのクライアントに組み込まれています。 これは、クライアント アプリケーションに使用する推奨プロキシ クラスです。
>
> <xref:Microsoft.Xrm.Sdk.Client>.<xref:Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy>を使用する場合は、これらのパターンを適用する必要があります。 または <xref:Microsoft.Xrm.Sdk.WebServiceClient>.<xref:Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient>  プロキシ クラス。

もし <xref:Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy>または<xref:Microsoft.Xrm.Sdk.WebServiceClient.OrganizationWebProxyClient> プロキシ クラスで SDK アセンブリを使用している場合は、<xref:Microsoft.Xrm.Sdk.OrganizationServiceFault>.<xref:Microsoft.Xrm.Sdk.BaseServiceFault.ErrorDetails> の `Retry-After` 遅延値を検索できます。 プロパティ内で検索するには、`"Retry-After"` キーを使用することができます。 返される値は [TimeSpan](/dotnet/api/system.timespan) オブジェクトです。

## <a name="net-sdk-assembly-example"></a>.NET SDK アセンブリの例

次の例は以下で説明される [Retry クラス](#retry-class)を使用して、<xref:Microsoft.Xrm.Sdk.IOrganizationService>.<xref:Microsoft.Xrm.Sdk.IOrganizationService.RetrieveMultiple*>  メソッドを使用するアカウントを取得します。 API 制限を超えたために要求が失敗する場合、`Retry` クラスはサーバーが指定する遅延に応じて待機してから再試行します。

```csharp
var qe = new QueryExpression("account") { TopCount = 1 };
EntityCollection result = Retry.Do(() => service.RetrieveMultiple(qe));
```

### <a name="retry-class"></a>Retry クラス

`Retry` クラスは、既知の <xref:Microsoft.Xrm.Sdk.OrganizationServiceFault> エラー コードに基づき、一時的エラーのために失敗する要求を再試行する方法を示します。 `Retry` クラスは再試行まで待機します。 エラーが再試行遅延を指定する場合、サーバーが指定する遅延に基づき待機します。 それ以外の場合、急激なバックオフを使用して、実行された再試行の数に応じて遅延が計算されます。

```csharp
using System;
using System.ServiceModel;
using System.Threading;

public class Retry
{
    private const int RateLimitExceededErrorCode = -2147015902;
    private const int TimeLimitExceededErrorCode = -2147015903;
    private const int ConcurrencyLimitExceededErrorCode = -2147015898;

    public static TResult Do<TResult>(Func<TResult> func, int maxRetries = 3)
    {
        int retryCount = 0;

        while (true)
        {
            try
            {
                return func();
            }
            catch (FaultException<Microsoft.Xrm.Sdk.OrganizationServiceFault> ex) 
                when (IsTransientError(ex))
            {
                if (++retryCount >= maxRetries)
                {
                    throw;
                }

                if (ex.Detail.ErrorCode == RateLimitExceededErrorCode)
                {
                    // Use Retry-After delay when specified
                    delay = (TimeSpan)ex.Detail.ErrorDetails["Retry-After"];
                }
                else
                {
                    // else use exponential backoff delay
                    delay = TimeSpan.FromSeconds(Math.Pow(2, retryCount));
                }

                Thread.Sleep(delay);
            }
        }
    }

    private static bool IsTransientError(FaultException<Microsoft.Xrm.Sdk.OrganizationServiceFault> ex)
    {
        // You can add more transient fault codes to retry here
        if (ex.Detail.ErrorCode == RateLimitExceededErrorCode ||
            ex.Detail.ErrorCode == TimeLimitExceededErrorCode ||
            ex.Detail.ErrorCode == ConcurrencyLimitExceededErrorCode)
        {
            return true;
        }

        return false;
    }
}
```

### <a name="see-also"></a>関連項目

[Power Platform の管理 / ライセンスとライセンス管理 / 要求の制限と割り当て](/power-platform/admin/api-request-limits-allocations)<br />
[Common Data Service API 制限の概要](../../maker/common-data-service/api-limits-overview.md)<br />
[Common Data Service Web API を使用する](webapi/overview.md)<br />
[Common Data Service 組織サービスを使用する](org-service/overview.md)
