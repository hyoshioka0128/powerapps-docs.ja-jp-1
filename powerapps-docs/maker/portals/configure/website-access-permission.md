---
title: Power Apps ポータルで Web サイトのアクセス許可を作成する | MicrosoftDocs
description: Web サイトのアクセス許可を作成してポータル内の要素に関連付ける方法を説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/04/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: c333039eddb7e0e8bb376a8b6850b18f9d1a46ad
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2977846"
---
# <a name="create-website-access-permissions"></a>Web サイトのアクセス許可の作成

Web サイト アクセス許可は、Web ページ以外にポータル内のさまざまなコンテンツ マネージド要素のフロント サイド編集を許可する [Web ロール](create-web-roles.md)に関連付けられているアクセス許可セットです。 アクセス許可設定によって、ポータル内で管理できるコンポーネントが決まります。

| 名前                         | 説明                                                                                      |
|------------------------------|--------------------------------------------------------------------------------------------------|
| コンテンツ スニペットの管理      | スニペットのコントロールの編集を許可します。                                                          |
| サイト マーカーの管理          | サイトマーカーを使用するハイパーリンクの編集を許可します。                                           |
| Web リンク セットの管理         | Web リンクのセットからの Web リンクの追加および削除を含む、[Web リンクのセット](manage-web-links.md)の編集を許可します。 |
| 非公開のエンティティのプレビュー | 公開の状態がドラフトであるポータルに公開済みのエンティティの表示を許可します。             |
|||

Web サイトのアクセス許可を作成して Web ロールに追加する方法:

1. [ポータル管理アプリ](configure-portal.md)を開きます。

2. **ポータル** > **Web サイトのアクセス許可**の順に移動します。

3. **新規**を選択します。

4. **全般**で、名前、Web サイトを入力し、必要なアクセス許可を選択します。

    ![Web サイトのアクセス許可の作成](../media/website-access-permission.png "Web サイトのアクセス許可の作成")

5. **Web ロール**で、**既存の Web リソースの追加**を選択して、アクセス許可を関連付ける Web ロールを選択して追加します。

6. 変更を保存します。

    
