---
title: Defaults 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の既定の機能の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/01/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ad3d8198d73a698abb771aef7230c12b48ff0f56
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74731119"
---
# <a name="defaults-function-in-power-apps"></a>Power Apps の既定の機能
[データ ソース](../working-with-data-sources.md)の既定値を返します。  

## <a name="description"></a>Description
**Defaults** 関数を使用して、データ入力フォームに事前に値を設定し、入力の手間を軽減します。

この関数は、データ ソースの既定値が含まれている[レコード](../working-with-tables.md#records)を返します。  データ ソース内の[列](../working-with-tables.md#columns)に既定値がない場合、そのプロパティは存在しません。

データ ソースが提供する既定の情報の量は、データ ソースによって異なります。まったく情報を提供しないデータ ソースもあります。  既定値をサポートしていない[コレクション](../working-with-data-sources.md#collections)やその他のデータ ソースが操作対象となった場合、**Defaults** 関数は[空](function-isblank-isempty.md)のレコードを返します。

[レコードを作成する](../working-with-data-sources.md)ために、**Defaults** 関数と **[Patch](function-patch.md)** 関数を組み合わせることができます。

## <a name="syntax"></a>構文
**Defaults**( *DataSource* )

* *DataSource* – 必須。 既定値の提供元となるデータ ソース。

## <a name="examples"></a>例

| 数式 | Description | 結果 |
| --- | --- | --- |
| **Defaults(&nbsp;Scores&nbsp;)** |**Scores** データ ソースの既定値を返します。 |**{ Score: 0 }** |

