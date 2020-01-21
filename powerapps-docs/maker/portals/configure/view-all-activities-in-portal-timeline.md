---
title: ポータル タイムラインでアクティビティを表示する | MicrosoftDocs
description: ポータル タイムラインですべてのアクティビティを表示する手順。
author: tapanm-msft
manager: kumarvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 12/12/2019
ms.author: dileeps
ms.reviewer: tapanm
ms.openlocfilehash: 0536890f5665d6b3f6a3cd94aaf6612d06b97293
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914357"
---
# <a name="view-activities-in-a-portal-timeline"></a>ポータル タイムラインでアクティビティを表示する

ケースの処理中または顧客とのやり取り中に、予定、メール、または電話などのアクティビティを作成できます。 サポート ポータルのタイムラインに移動すると、既定ではすべての活動がポータルのタイムラインには表示されないため、この活動が見つからない場合があります。 

ポータル タイムラインでアクティビティを表示するには: 

1. **CustomerSupport/DisplayAllUserActivitiesOnTimeline** サイト設定を true に設定します。  
    
    > [!NOTE]
    > もし **DisplayAllUserActivitiesOnTimeline** サイト設定が存在しない場合、この名前で新しい設定ができます。

2. 存在しない場合は、ビュー フィルターに含めるアクティビティの種類を追加します。  
    1. [**設定**](https://docs.microsoft.com/power-platform/admin/admin-settings#app-settings) > **カスタマイズ** > **システムのカスタマイズ**に順に移動します。
    2. **アクティビティ**エンティティを選択し、 **ビュー**を展開します。
    3. **ポータル タイムライン ビュー**を編集します。
    4. **フィルター条件の編集**を更新して、**予定、メール、または電話**などの必要なアクティビティの種類を追加します。
    5. カスタマイズして**保存**し、**公開**します。 

    > [!IMPORTANT]
    > カスタマイズの準備には時間がかかることがあります。 ブラウザーのページが反応しなくなっているというメッセージが表示された場合は、閉じないで、ページが反応する状態になるまで待機します。

3. これはポータル メタデータの変更であるため、[サーバー側のキャッシュをクリア](../admin/clear-server-side-cache.md)して、更新されたデータがポータルに表示されることを確認してください。
