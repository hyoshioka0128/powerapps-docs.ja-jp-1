---
title: " 関連するレコードを使用したレコードの作成と更新 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、関連するレコードを使用したレコードの作成と更新について説明します。
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
ms.openlocfilehash: 4cbe34abef35224b4fc1eaf93a5f2307e9f4b8f6
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155839"
---
# <a name="create-and-update-records-with-related-records-early-bound"></a>関連するレコードを使用したレコードの作成と更新 (事前バインド)

このサンプルでは、次のメソッドを使用して、1回の呼び出しでレコードと関連レコードを作成および更新する方法を説明します:

- [IOrganizationService.Create](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.create?view=dynamics-general-ce-9)
- [IOrganizationService.Update](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.update?view=dynamics-general-ce-9)

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CreateUpdateRecordsWithRelatedRecords) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`IOrganizationService` メッセージは、組織のメタデータおよびデータにプログラムからアクセスする方法を提供するデータを含むシナリオで使用するものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `Account` メソッドは、レターを追加するアカウント レコードを作成します。 
1. `Relationship` メソッドは、レターとアカウント間の参照を作成します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。


