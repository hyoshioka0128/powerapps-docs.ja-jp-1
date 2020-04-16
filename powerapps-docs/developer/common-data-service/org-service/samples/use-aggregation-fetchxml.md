---
title: 'サンプル: FetchXML での集計の使用 (Common Data Service)| Microsoft Docs'
description: このサンプルは FetchXML を使用して集計レコード データを取得する方法を説明します。
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
ms.openlocfilehash: 7042b99fede796c6eea75d6f700ca36293d91897
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155539"
---
# <a name="sample-use-aggregation-in-fetchxml"></a>サンプル: FetchXML での集計の使用

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/sample-use-aggregation-fetchxml -->

このサンプルは FetchXML を使用して集計レコード データを取得する方法を説明します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/UseAggregationInFetchXML) からダウンロードできます。

## <a name="what-this-sample-does"></a>このサンプルの概要

`FetchXML` クエリは、データを取得するクエリを作成するシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `CreateRequiredRecords` クラスは、3 つの営業案件レコードと取引先企業レコードを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `estimatedvalue_avg` はすべての営業案件における見込み値の平均をフェッチします。 `EntityCollection` メソッドは `RetrieveMultiple` 要求の結果を返します。
1. `opportunity_count` は営業案件の総数をフェッチします。
1. `estimatedvalue_max` はすべての営業案件における最大の見込み値をフェッチします。
1. `estimatedvalue_min` はすべての営業案件における最小の見込み値をフェッチします。
1. `estimatedvalue_sum` はすべての営業案件における見込み値の合計をフェッチします。
1. `estimatedvalue_avg2` は 1 つのクエリで複数の集計値をフェッチします。
1. `groupby1` は groupby を用いてユーザーが持つ営業案件の総数とともに、ユーザーのリストをフェッチします。
1. `byyear` は獲得したすべての営業案件の集計情報を年別にフェッチします。
1. `byquarter` は獲得した営業案件の集計情報を四半期別にフェッチします。
1. `bymonth` は獲得した営業案件の集計情報を月別にフェッチします。
1. `byweek` は獲得した営業案件の集計情報を週別にフェッチします。
1. `byday` は獲得した営業案件の集計情報を日別にフェッチします。
1. `byyrqtr` は獲得した営業案件の集計情報を年別および四半期別にフェッチします。
1. `byyrqtr2` 結果の順序を指定します。 


### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。
