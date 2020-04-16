---
title: " グラフの作成、取得、更新、削除 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、ユーザーが所有するビジュアル化の作成、取得、更新、削除の方法を示します。
ms.custom: ''
ms.date: 12/20/2019
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
ms.openlocfilehash: 7c05e2b8618e4b1a542d3657bf822bd44e5e0287
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155867"
---
# <a name="create-retrieve-update-and-delete-a-chart"></a>ダッシュボードの作成、取得、更新、および削除

このサンプルでは、次のメソッドを使用してユーザーが所有するビジュアル化の作成、取得、更新、削除をする方法を示します:

- [IOrganizationService.Create](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.create?view=dynamics-general-ce-9)
- [IOrganizationService.Retrieve](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.retrieve?view=dynamics-general-ce-9)
- [IOrganizationService.Update](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.update?view=dynamics-general-ce-9)
- [IOrganizationService.Delete](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.delete?view=dynamics-general-ce-9)

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CRUDOperationsChart) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`IOrganizationService` メッセージは、組織のメタデータおよびデータにプログラムからアクセスする方法を提供するデータを含むシナリオで使用するものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `CreateRequiredRecords` メソッドは、サンプルに必要な エンティティ レコード を作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `presentationXml` メソッドは、プレゼンテーション XML 文字列を設定します。 
2. `dataXml` メソッドは、データ XML 文字列を設定します。
3. `newUserOwnedVisualization` メソッドは、ビジュアル化 エンティティ インスタンス を作成します。
4. `retrievedOrgOwnedVisualization` メソッドは、ビジュアル化を取得します。
5. `newDataXml` メソッドは、名前とデータの記述文字列を更新します。


### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。