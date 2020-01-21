---
title: 'サンプル: エンティティのメタデータを作成、更新する (Common Data Service) | Microsoft Docs'
description: このサンプルでは、エンティティ の メタデータ の 作成と更新方法を示します。
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
ms.openlocfilehash: 394bd033c7664542c58286c117f0fce679040066
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934571"
---
# <a name="create-and-update-entity-metadata"></a>エンティティ メタデータ の作成と更新

このトピックでは、ユーザーが所有する **Bank Account** (銀行口座) という名前のユーザー定義エンティティをプログラムで作成し、そのエンティティに対して 4 種類の属性を追加する方法について説明します。

組織所有のカスタム エンティティも作成できます。 詳細情報: [エンティティの所有権](https://docs.microsoft.com/dynamics365/customerengagement/on-premises/developer/introduction-entities#entity-ownership)。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CreateUpdateEntityMetadata) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`CreateEntityRequest` メッセージは、カスタムエンティティの作成に必要なデータが含まれるシナリオで使用することを目的としています。任意で、指定されたアンマネージド ソリューションに追加することもできます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `createrequest` メソッドは、ユーザー定義の エンティティ を作成します。 
2. `Entity` メソッドは、エンティティの定義に使用されます。
3. `StringAttributeMetadata` エンティティのプライマリ属性を定義します。
4. `CreateBankNameAttributeRequest` メソッドは、エンティティ の文字列属性を作成します。
5. `CreateBalanceAttributeRequest` メソッドは、エンティティ の通貨列属性を作成します。
6. `CreateCheckedDateRequest` メソッドは、エンティティ の日付属性を作成します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
