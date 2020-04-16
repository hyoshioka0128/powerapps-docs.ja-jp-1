---
title: 'サンプル: Web リソースとしてファイルをインポート (Common Data Service) | Microsoft Docs'
description: このサンプルは、Web リソースとしてファイルをインポートする方法を示します
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
ms.openlocfilehash: c4f17c771242505941780b16c53ad3defd763c08
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155751"
---
# <a name="sample-import-files-as-web-resources"></a>サンプル: Web リソースとしてファイルをインポート 

このサンプルは、Web リソースとしてファイルをインポートする方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ImportWebResources) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルでは、 `SolutionUniqueName` オプション パラメーターを使用して Web リソースを作成時に特定のソリューションに関連付ける方法を示します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` クラスは、Web リソースを追加するときに、サンプルに必要な発行者およびソリューションを作成します。


### <a name="demonstrate"></a>実際にやってみます

1. `XDocument` メソッドは、XML ファイルから記述データを読み取ります。 
1. `WebResource` は、Web リソースのプロパティを設定するために使用されます。
1. `CreateRequest` メソッドは、オプションのパラメーターを追加するために使用されます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

