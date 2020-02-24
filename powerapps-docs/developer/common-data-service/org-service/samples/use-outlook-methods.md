---
title: " Outlook メソッドの使用 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、Outlook メソッドの使用方法を紹介します。
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
ms.openlocfilehash: b1609c29dde65e77c6cecda39f9f1b651847dae6
ms.sourcegitcommit: cb533c30252240dc298594e74e3189d7290a4bd7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020095"
---
# <a name="sample-use-dynamics-365-for-outlook-methods"></a>サンプル: Dynamics 365 for Outlook メソッドの使用

このサンプルは、[Microsoft.Crm.Outlook.Sdk.dll](https://docs.microsoft.com/dotnet/api/microsoft.crm.outlook.sdk?view=dynamics-outlookclient-ce-9) アセンブリで利用可能なメソッドの使用方法を示しています。 サンプルは [ここ]() からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`Microsoft.Crm.Outlook.sdk` アセンブリは、オフライン アクセス対応 Microsoft Dynamics 365 for Outlook および Microsoft Dynamics 365 for Microsoft Office Outlook とのプログラム的な対話を提供する型が含まれるシナリオで使用されます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

上述のシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `CrmOutlookService` メソッドはサービスを設定します。
2. `CrmOutlookService.IsCrmClientOffline` メソッドは、クライアントがオフラインかどうかを確認します。
3. `CrmOutlookService.GoOnline()` メソッドはクライアントをオンラインにします。 このメソッドは自動的にデータベースと同期します。`Sync()` メソッドを呼び出す必要はありません。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。