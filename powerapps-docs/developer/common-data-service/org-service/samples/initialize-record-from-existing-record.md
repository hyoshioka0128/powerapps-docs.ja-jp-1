---
title: " 既存レコードのレコードを初期化 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、既存のレコードから新しいレコードを作成する方法を示します。
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
ms.openlocfilehash: dbc1e734459ccfdd1a541e850d9c798f45297eee
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934569"
---
# <a name="initailize-a-record-from-existing-record"></a>既存レコードからレコードを初期化する

このサンプルは、 [IOrganizationService.InitializeFromRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9) メッセージを使用して、既存レコードから新しいレコードを作成する方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/InitializeRecordFromExisting) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`IOrganizationService.InitializeFromRequest` メッセージは、既存レコードから新規レコードを初期化するために必要なデータが含まれているシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドを活用すれば、このサンプルに必要なすべてのエンティティ レコードを作成できます。


### <a name="demonstrate"></a>実際にやってみます

1. `InitializeFromRequest` メソッドは、リクエストを作成し、リクエスト オブジェクトのプロパティを設定します。 
2. この要求は `InitializeFromResponse`  メソッドで実行されます。


### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

