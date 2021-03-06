---
title: ポータル用 Web ページへのアクセスの制御 | MicrosoftDocs
description: ポータルに Web ページ アクセス制御ルールを作成するための手順。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/04/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: 894c06982084e2f9b4a96d5cd0189dd3a763b97e
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2978110"
---
# <a name="control-webpage-access-for-portals"></a>ポータル用 Web ページへのアクセスの制御

Web ページ アクセス制御ルールとは、Web ロールが Web サイトのページにわたって実行するパブリッシュ アクションおよびどの Web ロールによってどのページが表示されるかを制御するユーザーのサイトに対して作成するルールです。 Web ページ アクセス エンティティには次の属性があります。


|    名前     |                                                                                                                                                                  内容                                                                                                                                                                   |
|-------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    名前     |                                                                                                                                                        ルールの内容を示す名前                                                                                                                                                        |
|   Web サイト   |                                                                                                           このルールを適用するサイトはこのルールが適用されるページの Web サイトと一致する必要があります。 [Web ページのフィルター]                                                                                                           |
|  Web ページ   |                            このルールを適用する Web ページです。 ルールはページにだけでなく、そのページにあるすべての子ページにも影響を与えるため、この属性によってルールを適用するサイト分岐が選択されます。 ルールがホーム ページに適用される場合は、ポータル全体に適用されます。                            |
|    右詰め    |                                                                                                                                    下記にある [[付与の変更](#grant-change)] または [[読み取りの制限](#restrict-read)] です。                                                                                                                                     |
|    スコープ    | <ul><li><strong>すべてのコンテンツ</strong>: すべての子孫コンテンツはセキュリティ検証に含まれています。</li><li><strong>直接の子 Web ファイルを除外する</strong>: 直接この Web ページに関連付けられているすべての子 Web ファイルはセキュリティ検証から除外されています。 これには子孫を除外しません。</li></ul>既定では、すべてのコンテンツが選択されています。 |
| 内容 |                                                                                                                                                     ルールの説明 (任意)。                                                                                                                                                      |

新しいアクセス制御ルールを作成した後、ページと関連付けます。 これにより、ルールを割り当てるページおよびすべての子ページ&mdash;、つまり Web サイトの分岐全体に適用されます。

アクセス制御ルールには 2 種類あります。権限変更と制限付き読み取りです。

## <a name="grant-change"></a>変更の許可

変更権限では、ルールに関連付けられている Web ロールのユーザーがこのページにおけるコンテンツの変更およびすべての子ページを公開することができるようになります。 変更権限は、制限付き読み取りよりも優先されます。 たとえば、サイトにニュース セクションがあるときは、ニュース エディターの Web ロールのユーザーが編集できるようにしたい場合があります。 これらのユーザーはサイト全体にアクセスできない場合があります。確かにサイト全体を編集できませんが、この分岐内におけるすべての公開コンテンツに対する権限があります。 ニュース公開をニュース エディターに付与するという Web ページ アクセス制御ルールを作成します。

次に、その権限を変更権限に設定し、Web ページをサイトのニュースの分岐全体の親ページに設定します。 新しいエディターとして割り当てるすべての取引先担当者にこの Web ロールを割り当てます。 1 名のユーザーに複数の Web ロールを設定することが可能です。

権限の変更ルールはフロント サイド編集を有効にするすべてのポータルに常に存在する必要があります。 このルールを使用すると、サイトのホーム ページに適用されるため、サイト全体の既定ルールとなります。 このルールはサイト管理者の役割であることを表す Web ロールに関連付けられます。 フロント サイド編集の権限を付与されているユーザーはこのロールに割り当てられます。

## <a name="restrict-read"></a>制限付き読み取り
制限付き読み取りの制限ルールはページ (およびその子ページ) およびそのコンテンツの表示を特定のユーザーに制限するために使用されます。 変更権限は許可的ルール (ユーザーが何かの作業を行うことができるように許可する) である一方で、制限付き読み取りは特定のユーザーにのみアクションを制限する制限ルールです。 たとえば、従業員のみの使用を想定したサイトのセクションがある場合があります。 従業員 Web ロールを持つユーザーにのみこの分岐の読み取りを制限できます。 従業員のみに制限付き読み取りという新しいルールを作成します。

権限を制限付き読み取りに設定し、ページを、従業員にのみ読み取りを限定する分岐のトップ ページに設定します。 このルールを従業員 web ロールに関連付け、ユーザーをこのロールに割り当てます。

> [!Note]
> Web サイトのルート 'ホーム' ページに**読み取り**権を適用し、**直接の子 Web ファイルを除外する**を**スコープ**として選択することによって、ホーム ページの直接の子 Web ファイルにすべてのユーザーがアクセスできるようになります。

### <a name="see-also"></a>関連項目

[ポータルの Web ロールの作成](create-web-roles.md)  
[ポータルのエンティティのアクセス許可を使用するレコード ベースのセキュリティの追加](assign-entity-permissions.md)
