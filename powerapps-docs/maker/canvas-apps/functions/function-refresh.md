---
title: Refresh 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の Refresh 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/21/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8376d21117c286a540ca8b873c7e91b07d53d607
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74730378"
---
# <a name="refresh-function-in-power-apps"></a>Power Apps の関数の更新
[データ ソース](../working-with-data-sources.md)の[レコード](../working-with-tables.md#records)を更新します。

## <a name="description"></a>Description
**Refresh** 関数は、データ ソースの新しいコピーを取得します。  他のユーザーが加えた変更が表示されます。

**Refresh** には戻り値が存在せず、[動作の数式](../working-with-formulas-in-depth.md)内でのみ使用できます。

## <a name="syntax"></a>構文
**Refresh**( *DataSource* )

* *DataSource* – 必須。 更新するデータ ソース。

## <a name="example"></a>例
この例では、**IceCream** という名前のデータ ソースを更新します。このデータ ソースは次のデータから始まります。

![](media/function-refresh/icecream.png)

別のデバイスのユーザーが、**Strawberry** レコードの **Quantity** を **400** に変更します。  この数式が実行されるまで、この変更は表示されません。

**Refresh( IceCream )**

その数式が実行された後、**IceCream** データ ソースにバインドされたギャラリーに、**Strawberry** の更新後の値が表示されます。

![](media/function-refresh/icecream-after.png)

