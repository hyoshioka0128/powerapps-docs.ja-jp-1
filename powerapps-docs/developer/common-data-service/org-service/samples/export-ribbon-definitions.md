---
title: 'サンプル: リボンの定義をエクスポートする (Common Data Service) | Microsoft Docs'
description: このサンプルには、リボンの定義をエクスポートする方法を説明します
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: samples
author: mayadumesh
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 49d48cd432fb2b45395bbcff558a98378b889d40
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956337"
---
# <a name="export-ribbon-definitions"></a>リボン定義のエクスポート

このサンプルでは、リボンの定義をエクスポートする方法を説明します。 ここでは、 [RetrieveApplicationRibbonRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrieveapplicationribbonrequest?view=dynamics-general-ce-9) と [RetrieveEntityRibbonRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrieveentityribbonrequest?view=dynamics-general-ce-9) メッセージを使用します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ExportRibbonDefinitions) からダウンロードできます。


## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RetrieveApplicationRibbonRequest` メッセージは、アプリケーション リボンの内容と動作を定義するデータを取得するために必要なデータが含まれているシナリオで使用することを目的としています。 `RetrieveEntityRibbonRequest` メッセージは、エンティティに関するリボンの定義を取得するために必要なデータが含まれているシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `RetrieveApplicationRibbonRequest` メソッドは、アプリケーションのリボンを取得します。
2. `RetrieveEntityRibbonRequest` メソッドは、システム エンティティのリボンを取得します

### <a name="clean-up"></a>クリーンアップ

このサンプルにはクリーンアップは不要です
