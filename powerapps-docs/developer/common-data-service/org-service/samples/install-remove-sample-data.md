---
title: 'サンプル: サンプル データのインストールと削除 (Common Data Service) | Microsoft Docs'
description: このサンプルは、サンプル データをインストールおよび削除する方法を示しています。
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
ms.openlocfilehash: 977025209c4fa4abac37ad99c6644cba6e846902
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956336"
---
# <a name="install-or-remove-sample-data"></a>サンプル データのインストールまたは削除

このサンプルでは、[InstallSampleDataRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.installsampledatarequest?view=dynamics-general-ce-9) メッセージを使用して、組織用のサンプル データをインストールまたはアンインストールする方法を示します。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`InstallSampleDataRequest` メッセージは、サンプル データベースをインストールするために必要なデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. ユーザーにサンプル データをインストールまたは削除するよう促します。
2. ユーザーがサンプル データのインストールを選択した場合、`InstallSampleDataRequest` メッセージはサンプル データをインストールします。
3. ユーザーがサンプル データのアンインストールを選択した場合、`UninstallSampleDataRequest` メッセージはサンプル データを削除します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でレコードを削除するためのオプションを表示します。 サンプルで作成されたエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。