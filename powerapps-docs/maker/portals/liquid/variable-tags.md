---
title: ポータルで変数タグを使用する | MicrosoftDocs
description: ポータルで使用可能な変数タグについて説明します
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: cdccf267000247a7363a05f72c3ccdd93abb6fd6
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2866272"
---
# <a name="variable-tags"></a>変数タグ

変数タグは、新しい Liquid 変数の作成に使用されます。

## <a name="assign"></a>割り当て

新しい変数を作成します。 また、割り当ては[フィルター](liquid-filters.md)を使用して値を変更することができます。  

**コード**

```
{% assign is_valid = true %}

{% if is_valid %}

It is valid.

{% endif %}

{% assign name = dave bowman' | upcase %}

{{ name }}
```

**出力**

```
It is valid.

DAVE BOWMAN
```

## <a name="capture"></a>取得

ブロック内のコンテンツを取得し、変数に割り当てます。 このコンテンツは、出力タグを使用して後で表示できます。

**コード**

```
{% capture hello %}Hello, {{ user.fullname }}.{% endcapture %}

{{ hello }}

{{ hello }}
```

**Output**

```
Hello, DAVE BOWMAN.

Hello, DAVE BOWMAN.
```

### <a name="see-also"></a>関連項目

[制御フロー タグ](control-flow-tags.md)<br>
[反復タグ](iteration-tags.md)<br>
[テンプレート タグ](template-tags.md)<br>
[Power Apps common data service エンティティ タグ](portals-entity-tags.md)
