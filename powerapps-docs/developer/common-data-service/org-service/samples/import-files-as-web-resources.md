---
title: 'サンプル: Web リソースとしてファイルをインポート (Common Data Service) | Microsoft Docs'
description: このサンプルは、Web リソースとしてファイルをインポートする方法を示します
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
ms.openlocfilehash: d73d2d7fa70998ceedc2cf9f833201a92c32c7e4
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934570"
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

