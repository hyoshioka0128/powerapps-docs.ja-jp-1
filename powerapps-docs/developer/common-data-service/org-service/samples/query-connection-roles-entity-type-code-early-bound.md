---
title: 'サンプル: エンティティの種類コードによるつながりロールの照会 (Common Data Service) | Microsoft Docs'
description: このサンプルは、接続ロールのクエリ方法を説明します。
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
ms.openlocfilehash: d4354e2a861f6b0f68916c2c9ca2104429c2b443
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155695"
---
# <a name="sample-query-connection-roles-by-entity-type-code-early-bound"></a>サンプル: エンティティの種類コードによるつながりロールのクエリ (事前バインド)

このサンプルは、クエリを使用し、エンティティ タイプ コードを指定して、アカウント エンティティの接続ロールを検索する方法を示します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/QueryRoleByEntityType) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルは、クエリを使用し、エンティティ タイプ コードを指定して、アカウント エンティティの接続ロールを検索する方法を示します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>使用方法

1. いくつかの匿名型を定義し、可能なつながりプロパティ値の範囲を定義します。
2. `ConnectionRole` はつながりロールを作成します。
3. `QueryExpression` により、すべてのつながりロールを照会します。
4. `ConnectionRoleObjectTypeCode` は、取引先企業エンティティに対するつながりロールのオブジェクトの種類のレコードを作成します。 

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でレコードを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
