---
title: EncodeUrl および PlainText 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の EncodeUrl 関数と PlainText 関数の参照情報
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
ms.openlocfilehash: 259ab99ca38a472fda5c8cd8cdf99533a5f5dfc2
ms.sourcegitcommit: 80120b59d440bb7a3ddca93cd51154607f749f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2020
ms.locfileid: "77089744"
---
# <a name="encodeurl-and-plaintext-functions-in-power-apps"></a>Power Apps の EncodeUrl および PlainText 関数
文字列をエンコードおよびデコードします。

## <a name="description"></a>説明
**EncodeUrl**関数は、URL 文字列をエンコードして、特定の英数字以外の文字を% および16進数に置き換えます。  

**PlainText**関数は、HTML および XML タグを削除して、次のような特定のタグを適切な記号に変換します。

* **&amp;nbsp;**
* **&amp;quot;**

これらの関数からの戻り値は、エンコードまたはデコードされた文字列です。 この関数では、すべての HTML タグと XML タグが削除されるわけではありません。 

## <a name="syntax"></a>構文
**EncodeUrl**( *String* )

* *String* - 必須。  エンコードする URL。

**PlainText**( *String* )

* *String* - 必須。 HTML および XML タグが削除される文字列。

## <a name="examples"></a>使用例
テキスト ギャラリーに RSS フィードを表示し、そのギャラリーのラベルの **[Text](../controls/properties-core.md)** プロパティを **ThisItem.description** に設定した場合、ラベルには次の例のように未加工の HTML または XML コードが表示される可能性があります。

```html
    <p>We have done an unusually&nbsp;&quot;deep&quot; globalization and localization.</p>
```

ラベルの **[Text](../controls/properties-core.md)** プロパティを **PlainText(ThisItem.description)** に設定すると、次の例のようなテキストが表示されます。

```
    We have done an unusually "deep" globalization and localization.
```