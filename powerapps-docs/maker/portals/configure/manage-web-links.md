---
title: Web リンクの管理 | MicrosoftDocs
description: Web リンクを管理するための手順
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/04/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: a466c47b9349e7fb2692ff509ecb61f54779e1be
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2979978"
---
# <a name="manage-web-links"></a>Web のリンクを管理する

Web リンクは、任意の URL または同じ Web サイト内の Web ページにリンクできます。 Web リンクが Web ページへのリンクである場合、Web ページのセキュリティと公開状態は Web リンクにも適用されます。 Web リンクは、常に Web リンクのセットの一部です。 Web リンクのセットは、主ナビゲーションやフッター リンクのグループなどの、リンクのグループです。 Web リンクのセットでは、サイト マップ内の位置にかかわらず、内部および外部リンクをまとめてグループ化し、並べ替えをすることができます。

## <a name="manage-web-links-in-power-apps-portals"></a>Power Apps  ポータルでの Web リンクの管理

カスタマイズ ポータルが Common Data Service 環境にインポートされたら、Web リンク セットで Web リンクを管理できます。

1. [ポータル管理アプリ](configure-portal.md)を開きます。

2. **ポータル** > **Web リンク セット**の順に移動します。

3. 新しい Web リンク セットを作成するには、**新規**を選択します。

4. 既存の Web リンク セットを編集するには、Web リンク セットの名前を選択します。

5. フィールドに適切な値を入力します。

6. 新しい Web リンク セットを作成する場合は、Web リンクを追加することができるように、**保存**を選択してレコードを保存します。

7. **リンク** タブに移動します。

8. 新しい Web リンクを作成するには、**新規 Web リンク**を選択します。

    ![Web リンクの追加](../media/add-web-link.png "Web リンクの追加")

9. 既存の Web リンクを編集するには、Web リンクの名前を選択します。

9. フィールドに適切な値を入力します。

6. 変更を保存します。

## <a name="web-link-set-attributes-and-relationships"></a>Web リンクのセットの属性および関連付け

次の表で、ポータルで使用される標準の Web リンクのセットのプロパティの多くを説明します。 多くのコンテンツ用や表示用のプロパティの表示方法が、使用しているページ テンプレートによって管理されていることに特に注意する必要があります。

| 名前    | 内容                                                                                                                                                                                  |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 名前    | Web リンクのセットのわかりやすい名前。 この値は通常、プライマリ ナビゲーションなどのページ テンプレートにあるセットの配置を示します。 これは必須フィールドです。                   |
| Web サイト | エンティティが属する Web サイトです。 これは必須フィールドです。                                                                                                                             |
| 敬称   | オプションで Web リンクのセットに付けるタイトル。 この値は、ページ テンプレートの一部である場合にポータルで使用できます。 自分のパートナーなどとして、サイド バーに表示されます。    |
| Copy    | オプションで Web リンクのセットに付ける説明。 この値は、ページ テンプレートの一部である場合にポータルで使用できます。 サイド バーで自分のパートナーなどとすることもできます。 |
||

## <a name="web-link-attributes-and-relationships"></a>Web リンクの属性および関連付け

下表は、ポータルで使用される多くの標準 Web リンクのプロパティを説明します。 多くのコンテンツ用や表示用のプロパティの表示方法が、使用しているページ テンプレートによって管理されていることに特に注意する必要があります。


|           名前           |                                                                                                               内容                                                                                                               |
|--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           名前           |                                                          Web リンクのタイトル。 この値は、ほとんどのテンプレートで、Web リンクのタイトルとして使用されます。 これは必須フィールドです。                                                           |
|       Web リンクのセット       |                                                                                  エンティティが属する Web リンクのセット。 これは必須フィールドです。                                                                                  |
|     親 Web リンク      |                                      複数レベルの Web リンクのセットで、エンティティの親の Web リンク。 親の Web リンクを指定しない場合は、エンティティは Web リンクのセットの中でトップ/ルート レベルです。                                      |
|           ページ           |                                                                                          同じ Web サイトからリンクする、オプションの Web ページ。                                                                                          |
|        外部 URL      |                                                                                リンク先のオプションの URL。 この値には、正しい書式の任意の URL を指定できます。                                                                                |
|       内容        |                                                              オプションで Web リンクに付ける概要。 この値は、ページ テンプレートの一部である場合にポータルで使用できます。                                                              |
|     公開の状態     | Web リンクの現在の公開ワークフロー状態は、サイトに Web リンクが表示されるかどうかを示すこともあります。 この機能の一般的な用途は、コンテンツの公開済/下書きの制御です。 これは必須フィールドです。 |
|    ロボットのフォロー リンク    |                                                           サーチ インデクサーがリンクを辿ってリンク先の内容をインデックスするかどうかを示します。 これは必須フィールドです。                                                            |
|      表示順序       |                                                  Web リンクの順序を示す整数値。同一の Web リンクのセット内での他の Web リソースに対する相対位置。                                                  |
| ページの子リンクを表示 |  複数レベルの Web リンクのセットをサポートするテンプレートで、ポータル サイト マップ プロバイダーを使用して、このエンティティに対する子のリンクを生成します。 このオプションは、外部 URL ではなく、内部ページを参照する Web リンクにのみ有効なことに注意してください。  |
|    新しいウィンドウで開く    |                                                                            リンクを選択したときに、新しいブラウザー ウィンドウでリンクを読み込むかどうかを示します。                                                                             |
| ページの検証の無効化  |                                                                       リンクされた Web ページのセキュリティを Web リンクにも適用するかどうかを示します。                                                                       |
|        画像の URL         |                                                   オプションの、画像への URL。 ページ テンプレートの一部である場合、アイコンなどとして、リンクされた画像をポータルで使用できます。                                                   |
|       画像の高さ       |                                                                                      オプションの、[画像の URL] プロパティの画像の高さ。                                                                                      |
|       画像の幅        |                                                                                      オプションの、[画像の URL] プロパティの画像の幅。                                                                                       |
|      画像の Alt テキスト      |                                                                                   オプションの、[画像の URL] プロパティの画像の説明。                                                                                    |
|    画像のみ表示    |                                                   この Web リンクについて、画像とリンク名を一緒に表示するのではなく、画像リンクのみをテンプレートが表示する必要があることを示します。                                                    |
|                          |                                                                                                                                                                                                                                         |

> [!Note]
> - Web リンクが Web ページへのリンクである場合、Web ページのセキュリティと公開状態は Web リンクにも適用されます。 この検証は、ページの検証を無効にするオプションで無効にできます。 
>   - コンテンツ管理のアクセス許可を持つユーザーは、非公開のコンテンツをユーザーが表示 (プレビュー) できるプレビュー モードを使用することができます。

### <a name="see-also"></a>関連項目

[コンテンツ スニペットの使用によるコンテンツのカスタマイズ](customize-content-snippets.md)
