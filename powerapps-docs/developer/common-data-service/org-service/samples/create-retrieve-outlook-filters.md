---
title: " Outlook フィルターの作成と取得 (Common Data Service) | Microsoft Docs"
description: この例では、 Outlook のフィルターの作成と取得方法を示します。
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
ms.openlocfilehash: 7835bd8552a19e5440380a470acc700f2280e1f5
ms.sourcegitcommit: cb533c30252240dc298594e74e3189d7290a4bd7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017359"
---
# <a name="create-and-retrieve-outlook-filters"></a>Outlook フィルターの作成と取得

このサンプルでは、Outlook のフィルターの取得方法を示します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CreartRetrieveOutlookFilters) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

上述のシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `fetchXml` のメソッドでは、オフライン フィルタを取得する asn を作成します。 Outlook クライアントでは、 **ファイル-> CRM->同期-> Outlook フィルター** 配下の [システムフィルター] タブに表示されます。
2. `InstantiateFiltersRequest` メソッドは、現在のユーザーの選択したオフライン テンプレートを有効化します。
3. `ResetUserFilterRequest` メソッドでは、現在のユーザーのオフライン テンプレートをリセットして既定の状態に戻します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

