---
title: ポータルで Web サイトを管理する | MicrosoftDocs
description: ポータルで Web サイトを管理する方法について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/14/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: ae3d928a6beb05819c7c752503993a7b789a0fd7
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2976878"
---
# <a name="manage-websites"></a>Web サイトの管理

Web サイトはポータル アプリケーションのコア エンティティです。 ポータル アプリケーションは単一の Web サイト レコードを選択し、これにより、どのポータル エンティティ ([Web ページ](web-page.md)、[Web ファイル](web-files.md)、[Web ロール](create-web-roles.md)、[コンテンツ スニペット](customize-content-snippets.md)、など) がこのアプリケーションて適用対象であるか決定されます。

アプリケーション スコープを提供する Web サイトにより、複数の異なるポータル アプリケーションを単一の組織に接続することができます。

> [!NOTE]
> 指定したポータル アプリケーションのバインド対象となる Web サイト レコードを決定するのは、通常ポータル展開の構成で指定した Web サイト名です。
ただし、URL パスの接頭語 ([Web サイト属性](#website-attributes) の下の親 Web サイトと部分 URL の説明を参照)、または Web サイト バインドを使用するにより、これをコントロールすることができます。

## <a name="manage-websites"></a>Web サイトの管理

新しいポータルを作成すると、Web サイトが作成されます。 ただし、高度な Web サイト管理は、ポータル管理アプリから実行できます。 

> [!WARNING]
> Web サイト レコードを削除すると、Web ページや Web リンクなどのポータル メタデータ エンティティの Web サイト レコードに関連するデータも削除されます。 Web サイト全体およびその関連データを単一の操作で組織から削除することができることを意味するため、通常これは望ましい動作です。

1. [ポータル管理アプリ](configure-portal.md)を開きます。

2. **ポータル** > **Web サイト**に移動します。

3. 既存の Web サイトを編集するには、Web サイト名を選択します。

4. フィールドに適切な値を入力または編集します。

5. **保存して閉じる**を選択します。

### <a name="website-attributes"></a>Web サイト属性

|名前|説明|
|-----|----------|
|名前|Web サイトの内容を示す名前。 これは必須フィールドです。|
|プライマリ ドメイン名|この Web サイト レコードが追加されるポータルのプライマリ ドメイン名です。|
|親 Web サイト|Web サイトの親 Web サイトです。 このフィールドは、単一のポータル アプリケーションが、アプリケーションのルート パスにあり特定のサブパスで利用可能な 1 つまたは複数の子 Web サイトを持つ 1 つのマスター Web サイトにバインドされる、特定の詳細ポータル構成を除き、通常は無視することができます。|
|部分 URL|この Web サイト関連付けられたポータル エンティティに対して生成されるすべての URL のルート URL パス セグメントです。<br>たとえば、ポータル アプリケーションがドメイン example.com のルートで利用できるように展開され、この属性に値がない場合、`http://example.com/` に対する要求によりアプリケーションのホーム Web ページが表示されます (ホーム Web ページの部分 URL に "/" をセットすることが要求されているため)。<br>この属性に "my-website" の値が設定される場合、ホーム Web ページは `http://example.com/my-website/` の URL を持ち、その Web ページ上のすべてのページは同じ "/my-website/" パス接頭辞があります。<br>大半のポータル構成では、このフィールドは無視して空白のままにすることができます。<br>部分 URL の値は URL パス セグメントとして使用されます。 そのため、"?"、"#"、"!"、"%" などの無効な URL パスの文字を含めることはできません。 ポータル URL は、部分 URL の値をスラッシュ (/) で区切って生成されるため、一般にスラッシュが含まれないようにする必要があります。<br>部分 URL の値を文字、数値、ハイフン、アンダースコアに制限することが推奨されます。 例えば、"press-releases"、"Users_Guide"、"product1" です。|
|||

### <a name="see-also"></a>関連項目
[Web サイト バインド](website-bindings.md)
