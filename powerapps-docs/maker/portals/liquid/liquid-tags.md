---
title: ポータルの Liquid タグを使用する | MicrosoftDocs
description: ポータルで使用可能な Liquid のタグについて説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: 3f85e4b86b305696f5b155c7e9e3b773f8ba2103
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2981102"
---
# <a name="available-liquid-tags"></a>使用可能な Liquid タグ

タグは、実行すべき処理をテンプレートに伝えるプログラミング ロジックを構成しています。 タグは、{% %} にパッケージ化されています。

```
{% if user.fullname == 'Dave Bowman' %} Hello, Dave. {% endif %}
```

## <a name="whitespace-control"></a>空白スペースのコントロール

Liquid は通常、現状のままのすべての空白スペースと共に、変数や各タグ ブロックを除くすべての文字を表示します。 余分な空白スペースが必要ではない場合もありますが、適切にテンプレートを作成したいなら、空白スペースが必要となります。

開始ブロック タグや終了ブロック タグにハイフン (-) を追加することによって、先頭および末尾のすべての空白スペースの削除をエンジンに通知できます。

**コード**

```
{% for i in (1..5) --%}

{{ i }}

{%-- endfor %}
```

**Output**

```
12345
```
### <a name="see-also"></a>関連項目

[Liquid の種類](liquid-types.md)  
[Liquid オブジェクト](liquid-objects.md)  
[Liquid フィルター](liquid-filters.md) 
