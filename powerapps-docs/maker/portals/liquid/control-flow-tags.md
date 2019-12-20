---
title: ポータルの制御フロー タグを使用する | MicrosoftDocs
description: ポータルで利用可能な制御フロー タグについて説明します。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 8f5b3701aedc0e0e98d203d5048577647c276120
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2864769"
---
# <a name="control-flow-tags"></a>制御フロー タグ

フロー タグの管理は、特定の条件に基づいて実行する必要があるコード ブロックおよび表示する必要があるコンテンツを決定します。 条件は、利用可能な[Liquid の演算子](liquid-operators.md)を使用してビルド、または単に[指定された値の真偽](liquid-conditional-operators.md)に基づきビルドされます。  

## <a name="if"></a>if

特定の条件を満たす場合コード ブロックを実行します。

```
{% if user.fullname == 'Dave Bowman' %}

Hello, Dave.

{% endif %}
```

## <a name="unless"></a>unless

if と似ていますが、特定の条件が満た**ない**場合にのみコード ブロックを実行します。

```
{% unless page.title == 'Home' %}

This is not the Home page.

{% endunless %}
```

## <a name="elsifelse"></a>elsif/else

if または unless ブロックにさらなる条件を追加します。

```
{% if user.fullname == 'Dave Bowman' %}

Hello, Dave.

{% elsif user.fullname == 'John Smith' %}

Hello, Mr. Smith.

{% else %}

Hello, stranger.

{% endif %}
```

## <a name="casewhen"></a>case/when

変数を複数の値と比較するためにスイッチ文を作成し、値ごとに別のコード ブロックを実行します。

```
{% case user.fullname %}

{% when 'Dave Bowman' %}

Hello, Dave.

{% when 'John Smith' %}

Hello, Mr. Smith.

{% else %}

Hello, stranger.

{% endcase %}
```

### <a name="see-also"></a>関連項目

[反復タグ](iteration-tags.md)<br>
[変数タグ](variable-tags.md)<br>
[テンプレート タグ](template-tags.md)<br>
[Power Apps common data service エンティティ タグ](portals-entity-tags.md)
