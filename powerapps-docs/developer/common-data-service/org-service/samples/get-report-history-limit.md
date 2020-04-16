---
title: 'サンプル: レポートの履歴制限の取得 (Common Data Service) | Microsoft Docs'
description: このサンプルは、レポートの履歴制限を取得する方法を示しています。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
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
ms.openlocfilehash: 80dc150533914c64983aa6ec4450fde23dbb6b0a
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155759"
---
# <a name="get-report-history-limits"></a>レポートの履歴制限の取得

このサンプルは、[GetReportHistoryLimitRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.getreporthistorylimitrequest?view=dynamics-general-ce-9) メッセージを使用してレポートの履歴制限を取得する方法を示しています。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/GetReportHistoryLimit) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`GetReportHistoryLimitRequest` メッセージは、レポートの履歴制限を検出する必要があるデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `QueryByAttribute` メソッドは、既存のレポートを照会します。
2. `GetReportHistoryLimitRequest` メソッドは、履歴制限データを取得します。

### <a name="clean-up"></a>クリーンアップ

このサンプルにはクリーンアップは不要です。
