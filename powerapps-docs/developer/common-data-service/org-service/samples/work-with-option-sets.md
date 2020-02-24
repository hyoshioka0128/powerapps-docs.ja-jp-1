---
title: 'サンプル: オプション セットに関する作業 (Common Data Service) | Microsoft Docs'
description: このサンプルでは、グローバル オプション セットの使用方法を示します
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: samples
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: d9319235820f973a760784c140e445f0835b0356
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956332"
---
# <a name="work-with-option-sets"></a>オプション セットに関する作業

このサンプルでは、オプション セットの使用方法を示します。 通常、グローバル オプション セットでフィールドを設定するのは、さまざまなフィールドを同じオプション セットで共有して、それらを 1 つの場所でメンテナンスできるようにするためです。 特定の属性に対してのみ定義されるローカル オプション セットとは異なり、グローバル オプション セットは再利用できます。 要求パラメーターの中で列挙体のときと同じように使われる例もあります。

[CreateOptionSetRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.createoptionsetrequest?view=dynamics-general-ce-9) でグローバル オプション セットを設定するときは、値の設定をシステムに任せることをお勧めします。 具体的には新規の `OptionMetadata` インスタンスを作成するとき、引数として NULL 値を渡します。 オプションを変更すると、そのオプション セットが作成されたソリューションに設定されている発行者のコンテキストに固有の接頭辞がオプション値に含められます。 この接頭辞は、マネージド ソリューションや、マネージド ソリューションのインストール先の組織で定義されている任意のオプション セットの中で、オプション セットの重複が生じる可能性を減らす効果があります。 詳細については、[オプション セット オプションのマージ](https://docs.microsoft.com/powerapps/developer/common-data-service/understand-managed-solutions-merged#merge-option-set-options) を参照してください。

次のメッセージ要求クラスを使って、グローバル オプション セットを操作します。

- [CreateOptionSetRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.createoptionsetrequest?view=dynamics-general-ce-9)
- [DeleteOptionSetRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.deleteoptionsetrequest?view=dynamics-general-ce-9)
- [RetrieveAllOptionSetsRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest?view=dynamics-general-ce-9)
- [RetrieveOptionSetRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrieveoptionsetrequest?view=dynamics-general-ce-9)
- [UpdateOptionSetRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.updateoptionsetrequest?view=dynamics-general-ce-9)

次のメッセージ要求クラスを使って、グローバル オプション セットとローカル オプション セットを操作します。

- [DeleteOptionValueRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.deleteoptionvaluerequest?view=dynamics-general-ce-9)
- [InsertOptionValueRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.insertoptionvaluerequest?view=dynamics-general-ce-9)
- [InsertStatusValueRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.insertstatusvaluerequest?view=dynamics-general-ce-9)
- [OrderOptionRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.orderoptionrequest?view=dynamics-general-ce-9)
- [UpdateOptionValueRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.updateoptionvaluerequest?view=dynamics-general-ce-9)
- [UpdateStateValueRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.updatestatevaluerequest?view=dynamics-general-ce-9)

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/WorkWithOptionSets) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`CreateOptionSetRequest`、`DeleteOptionSetRequest`、`RetrieveOptionSetRequest`、および `UpdateOptionSetRequest` メッセージは、オプション セットを使用するために必要なデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `CreateOptionSetRequest` メソッドは、グローバル オプション セットを作成します。 `IsGlobal=true` パラメーターを設定する必要があります。  
2. `CreateAttributeRequest` メソッドは、オプション セットにリンクされた選択リストを作成します。
3. `UpdateOptionSetRequest` メソッドは、オプション セットの基本情報を更新します。
4. `PublishXmlRequest` メソッドはオプション セットを公開します。
5. `InsertOptionValueRequest` メソッドは、新しいオプションをグローバル オプション セットに挿入します。
6. `RetrieveOptionSetRequest` メソッドは、その名前でグローバル オプション セットを取得します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
