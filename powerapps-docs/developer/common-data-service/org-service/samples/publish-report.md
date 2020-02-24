---
title: 'サンプル : レポートの発行 (Common Data Service) | MicrosoftDocs'
description: 'このサンプルは、レポートの公開方法を示します:'
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
ms.openlocfilehash: dbf928c13e80ed0f95e1b0c84b4e51452d6f8607
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956334"
---
# <a name="publish-reports"></a>レポートの公開

このサンプルは、**レポート** レコードと、それを表示可能にする関連レコードを作成することによってレポートを公開する方法を示しています。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/PublishReport) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

上述のシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `Report` メソッドはレポート オブジェクトをインスタンス化します。
2. `ReportCategory` メソッドは、レポートが属するべきレポート カテゴリを設定します。
3. `ReportEntity` メソッドは、このレポートが使用するエンティティを定義します。
4. `ReportVisibility` メソッドはレポートの可視性を設定します。

### <a name="clean-up"></a>クリーンアップ

このサンプルにはクリーンアップは不要です。