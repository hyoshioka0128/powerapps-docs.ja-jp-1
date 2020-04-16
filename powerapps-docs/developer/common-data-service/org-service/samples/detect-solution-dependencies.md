---
title: 'サンプル: ソリューションの依存関係の検出 (Common Data Service) | Microsoft Docs'
description: このサンプルはソリューションの依存関係を検出する方法を示します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: samples
author: shmcarth
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 8f84ecba9af675d6027276bc307621a71476735a
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155835"
---
# <a name="sample-detect-solution-dependencies"></a>サンプル: ソリューションの依存関係の検出

このサンプルは、ソリューション コンポーネントを削除する前に依存関係を検出する方法を示します。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RetrieveDependentComponentsRequest`、`RetrieveDependenciesForDeleteRequest` メッセージはソリューションの依存関係を検出するためのデータを含んでいるシナリオで使用するためのものです。 サンプルは[ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/SolutionDependencies) からダウンロードできます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `Publisher` メソッドは、 2 つのソリューションを `own` するサンプルの発行元を作成します。
1. `Solution` メソッド主要なソリューションを作成します。
1. `OptionSetMetadata` はグローバル オプション セットを作成し、ソリューションに関連付けます。
1. `ExportSolutionRequest` は後でインポートできるように、ソリューションをマネージドとしてエクスポートします。
1. `DeleteOptionSetRequest` 以前に作成したオプション セットを削除するので、管理ソリューションでインポートできます。
1. `ImportSolutionRequest` はソリューションをマネージドとして再インポートします。

### <a name="demonstrate"></a>使用方法

1. `QueryByAttribute` はすべてのソリューションをソリューションにクエリします。
1. `RetrieveDependentComponentsRequest` はコンポーネントのすべての依存関係を取得します。 依存関係がない場合は、このコンポーネントを無視できます。 このソリューション コンポーネントに依存関係があり、ソリューション自体がマネージドの場合は、ソリューションを削除できなくなります。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup)で作成されたソリューションを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
