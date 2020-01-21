---
title: " ダッシュボード の作成、取得、更新、削除 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、ユーザーが所有するダッシュボードの作成、取得、更新、削除の方法を示します。
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
ms.openlocfilehash: 0efb3e9b29f23e3d24fbaeb938751c20fe69566c
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934359"
---
# <a name="create-retrieve-update-and-delete-a-chart"></a>ダッシュボードの作成、取得、更新、および削除

このサンプルでは、次のメソッドを使用してユーザーが所有するダッシュボードの作成、取得、更新、削除をする方法を示します:

- [IOrganizationService.Create](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.create?view=dynamics-general-ce-9)
- [IOrganizationService.Retrieve](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.retrieve?view=dynamics-general-ce-9)
- [IOrganizationService.Update](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.update?view=dynamics-general-ce-9)
- [IOrganizationService.Delete](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.delete?view=dynamics-general-ce-9)

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CRUDOperationsDashboard) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`IOrganizationService` メッセージは、組織のメタデータおよびデータにプログラムからアクセスする方法を提供するデータを含むシナリオで使用するものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `mySavedQuery` メソッドは、営業案件の既定のパブリックビューを取得します。 
2. `visualizationQuery` メソッドは、システムからビジュアル化を取得します。 このサンプルでは、 **上位の営業案件** の例を示しています。 
3. `dashboard` メソッド は ダッシュボード を設定し、FormXml を指定します。
4. `chartPicker` メソッドは、チャート の チャートピッカー を有効にします。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。