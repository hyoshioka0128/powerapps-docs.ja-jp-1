---
title: Len 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の Len 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 07b706d9cc0a61e204669646734cdcaf7fc50946
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74730649"
---
# <a name="len-function-in-power-apps"></a>Power Apps の Len 関数
テキストの文字列の長さを返します。

## <a name="description"></a>Description
1 つの文字列を引数として指定した場合、戻り値はその長さを示す数になります。  文字列が含まれている単一列[テーブル](../working-with-tables.md)を指定した場合、戻り値は、各文字列の長さが格納された単一列テーブルになります。 複数列テーブルがある場合は、[テーブルの使用](../working-with-tables.md)に関するページの説明に従って、そのテーブルを単一列テーブルにすることができます。

[空](function-isblank-isempty.md)の文字列を指定した場合、 **Len**は0を返します。

## <a name="syntax"></a>構文
**Len**( *String* )

* *String* - 必須。 測定の対象となる文字列。

**Len**( *SingleColumnTable* )

* *SingleColumnTable* - 必須。 測定対象となる文字列が含まれている単一列テーブル。

## <a name="examples"></a>例
### <a name="single-string"></a>単一の文字列
このセクションの例では、[データ ソース](../working-with-data-sources.md)は **Author** という名前のテキスト入力コントロールです。ここには、文字列 "E. E. Cummings" が含まれています。

| 数式 | Description | 結果 |
| --- | --- | --- |
| **Len( Author.Text )** |**Author** コントロール内の文字列の長さを測定します。 |14 |
| **Len( "" )** |空の文字列の長さを測定します。 |0 |

### <a name="single-column-table"></a>単一列テーブル
このセクションの最初の例では、**People** という名前のデータ ソースに次のデータが含まれています。

![](media/function-len/people-table.png)

| 数式 | Description | 結果 |
| --- | --- | --- |
| **Len( ShowColumns(&nbsp;People,&nbsp;"Address"&nbsp;) )** |**People** テーブルの **Address** [列](../working-with-tables.md#columns)を対象に以下が実行されます。<br><ul><li>各文字列の長さを測定します。</li><li>各文字列の長さが格納された単一列テーブルを返します。</li> |<style> img { max-width: none } </style> ![](media/function-len/people-table-len.png) |
| **Len( [ "Hello", "to the", "World", "" ] )** |インライン テーブルの **[Value](function-value.md)** 列を対象に以下が実行されます。<br><ul><li>各文字列の長さを測定します。</li><li>各文字列の長さが格納された単一列テーブルを返します。</li> |![](media/function-len/people-table-len-inline.png) |

