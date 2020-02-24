---
title: " レポート定義のダウンロード (Common Data Service) | Microsoft Docs"
description: このサンプルでは、レポートの定義をダウンロードする方法を解説します
ms.custom: ''
ms.date: 12/20/2019
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
ms.openlocfilehash: 6498fd0db4a65c5664cff8c4ffc03f1ff477fc78
ms.sourcegitcommit: cb533c30252240dc298594e74e3189d7290a4bd7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020096"
---
# <a name="download-report-definition"></a>レポート定義のダウンロード

このサンプルでは、 [DownloadReportDefinitionRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.downloadreportdefinitionrequest?view=dynamics-general-ce-9) メッセージを使用してレポートの定義 (.rdl) ファイルをダウンロードする方法を説明します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DownloadReportDefinition) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`DownloadReportDefinitionRequest` メッセージは、レポート定義のダウンロードが必要となるデータを含む場合に使用することを想定しています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `QueryByAttribute` メソッドは、既存のレポートを照会します。
2. `DownloadReportDefinitionRequest` メソッドはレポート定義をダウンロードします。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。