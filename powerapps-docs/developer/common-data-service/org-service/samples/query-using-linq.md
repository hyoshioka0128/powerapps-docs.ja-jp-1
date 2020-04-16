---
title: LINQ を使用したデータのクエリ (Common Data Service) | Microsoft Docs
description: このサンプルではチームにレコードを割り当てる方法を示します。
ms.custom: ''
ms.date: 02/05/2020
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: samples
author: phecke
ms.author: pehecke
manager: KumarVivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 00717d61a34fa600c7dd6139f2c1d7bc3ca9d8f4
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155683"
---
# <a name="sample-query-data-using-linq"></a>サンプル: LINQ を使用したデータのクエリ

これらのサンプルは、[統合言語クエリ (LINQ)](https://docs.microsoft.com/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq-queries) を使用してビジネス データをクエリする方法を示しています。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/QueriesUsingLINQ) からダウンロードできます。 

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

このサンプルの実行方法については、[サンプルの実行方法](https://github.com/microsoft/PowerApps-Samples/blob/master/cds/README.md) をご覧ください。 ソリューションには複数のプロジェクトがあります。 各プロジェクトは、LINQ クエリのいくつかの側面を示しています。

## <a name="what-this-sample-does"></a>このサンプルの概要

各サンプルのコメントを読んで、各サンプルの機能を確認してください。 以下のサンプルがあります:
* 単純な LINQ クエリの作成
* エンティティ遅延バインディングを使用して LINQ クエリを作成する
* 条件演算子を使用して複数のレコードを取得する
* 複雑なクエリ - さまざまな LINQ の例

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

各 `Main`() メソッドの `Demonstrate` 領域に必要なエンティティ インスタンスを作成します。

### <a name="demonstrate"></a>実際にやってみます

`Main`() メソッドの `Demonstrate` 領域のコードは、1 つ以上の LINQ クエリを実行します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。

サンプルで作成されたエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。