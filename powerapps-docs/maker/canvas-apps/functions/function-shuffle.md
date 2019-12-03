---
title: Shuffle 関数 | Microsoft Docs
description: 構文と例を含む Power Apps のシャッフル関数の参照情報
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
ms.openlocfilehash: c67e8095a7c0ed3246bce0401bbe787becd7cea0
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74730158"
---
# <a name="shuffle-function-in-power-apps"></a>Power Apps のシャッフル関数
[テーブル](../working-with-tables.md)の[レコード](../working-with-tables.md#records)をランダムに並べ替えます。

## <a name="description"></a>Description
**Shuffle** 関数は、テーブルのレコードを並べ替えます。

**Shuffle** は、引数と同じ[列](../working-with-tables.md#columns)と行数を持つテーブルを返します。

## <a name="syntax"></a>構文
**Shuffle**( *Table* )

* *Table* - 必須。  シャッフルするテーブル。

## <a name="example"></a>例
**Deck** という名前の[コレクション](../working-with-data-sources.md#collections)にトランプの詳細情報を格納していた場合、この数式は、ランダムにシャッフルされたそのコレクションのコピーを返します。

**Shuffle(Deck)**

