---
title: ポータルでテンプレート タグを使用する | MicrosoftDocs
description: ポータルで使用可能なテンプレート タグについて説明します
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 951b4055aa47a6fba31df5473bd517ed67c8f17d
ms.sourcegitcommit: 861ba8e719fa16899d14e4a628f9087b47206993
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "2873226"
---
# <a name="template-tags"></a>テンプレート タグ

テンプレート タグは、さまざまな方法でテンプレートの出力を制御し、複数のテンプレートを 1 つの出力にまとめることができます。

## <a name="include"></a>include

名前により、1 つのテンプレートの内容を別のテンプレートに含めます。 Power Apps ポータルでは、これ以外のテンプレートのソースは、通常 [Web テンプレート](store-content-web-templates.md)です。 これにより、複数の場所で共通のテンプレートのフラグメントを再利用できます。  

テンプレートが別のテンプレートに含まれている場合、含まれたテンプレートは親のテンプレートで定義された変数にアクセスできます。

`{% include 'My Template' %}`

include タグに、名前の付けられた任意の数のパラメーターを渡すこともできます。 これらは、含まれたテンプレートで変数として定義されます。

`{% include 'My Template' a:x, b:y %}`

## <a name="block"></a>block

テンプレートを継承するために、拡張と組み合わせて使用されます。 使用方法については、拡張を参照してください。

## <a name="extends"></a>extends

テンプレートを継承するために、ブロック タグと組み合わせて使用されます。 これにより、親のレイアウトのオーバーライド指定領域でも、複数のテンプレートで共有レイアウトを使用できす。

Power Apps ポータルでは、タグに提供された親のテンプレート名は、通常 [Web テンプレート](store-content-web-templates.md)の名前を参照します。  

拡張を使用する場合は、テンプレートの最初の内容である必要があり、1 つ以上のブロック タグのみ続けることができます。

親のテンプレートで定義された block がオーバーライドされなかった場合、親のテンプレートの内容 (ある場合) が表示されます。

## <a name="comment"></a>comment

流動テンプレート内の非表示コードをそのままの状態にすることができます。 ブロック内のコンテンツが表示されない場合、内部の流動コードは実行されません。

**コード**

`Hello{% comment %}, {{ user.fullname }}{% endcomment %}. My name is Charles.`

**出力**

`Hello. My name is Charles.`

## <a name="raw"></a>raw

解析および実行せずに、ページの流動コードを出力できます。

**Output**

`Hello, {{ user.fullname }}. My name is Charles.`

## <a name="substitution"></a>代替

ユーザーがヘッダーとフッターのキャッシュを有効にし、特定のセクション出力のキャッシュを避けたい場合、このタグを使用できます。 このタグは、ラップされたコンテンツ ブロックの出力がキャッシュされないヘッダーまたはフッターにコンテンツブロックを提供します。 これは、リクエスト、ページ、言語、日付など、頻繁に更新される可能性のあるオブジェクトをユーザーが使用しているシナリオで役立ちます。 たとえば、[ヘッダーとフッターのキャッシュが有効になっている](../configure/enable-header-footer-output-caching.md)場合にヘッダーとフッターの Web テンプレート ソース コード更新シナリオを参照してください。

### <a name="see-also"></a>関連項目

[制御フロー タグ](control-flow-tags.md)<br>
[反復タグ](iteration-tags.md)<br>
[変数タグ](variable-tags.md)<br>
[Power Apps common data service エンティティ タグ](portals-entity-tags.md)
