---
title: 'サンプル: ソリューションの使用（Common Data Service）| Microsoft Docs'
description: このサンプルは、ソリューションに関する作業方法を説明します
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
ms.openlocfilehash: 6a85a4643b5cc15f2c258893e538de96ef95231b
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155491"
---
# <a name="sample-work-with-solutions"></a>サンプル: ソリューションに関する作業

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/sample-work-solutions -->

このサンプルでは、ソリューションで次のアクションを実行する方法を示します。

- 発行元を作成します。
- 既定の発行元を取得します。
- ソリューションを作成します。
- ソリューションを取得します。
- 既存のソリューション コンポーネントを追加します。
- ソリューション コンポーネントを削除します。
- ソリューションをエクスポートまたはパッケージ化します。
- ソリューションをインストールまたはアップグレードします。
- ソリューションを削除します。

サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/WorkwithSolutions) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルは、ソリューションに関する作業方法を説明します。 このサンプルは、発行元の作成方法、ソリューションの作成、ソリューションのエクスポートとインポート、さらにソリューションの削除方法も扱います。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `Publisher` メソッドは、新しい発行元を定義します。 
1. `Solution` メソッドは、新しいソリューションを作成します。
1. `OptionSetMetadata` メソッドは、ソリューション コンポーネントを追加します。
1. `ExportSolutionRequest` メソッドは、[セットアップ](#setup) で作成されたソリューションをエクスポートします。
1. `DeleteSolutionRequest` メソッドは、ソリューションとコンポーネントを削除します。

### <a name="demonstrate"></a>使用方法

1. `querySDKSamplePublisher` メソッドは、発行元がシステムに既に存在するかどうかを調べます。
1. `querySampleSolutionResults` メソッドは、ソリューションがシステムに既に存在するかどうかを調べます。
1. `ExportSolutionRequest` メソッドは、ソリューションをエクスポートします。
1. `ImportSolutionRequest` メソッドは、ソリューションをインポートします。

### <a name="clean-up"></a>クリーン アップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。
