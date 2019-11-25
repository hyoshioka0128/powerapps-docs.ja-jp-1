---
title: PowerApps ポータルのライフサイクルについて | MicrosoftDocs
description: PowerApps ポータルのライフサイクルおよびそれを試用版から運用に変換することに関する情報。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 5476bb0306b5d9e0767f451fba36a567a70c4c54
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2756789"
---
# <a name="about-portal-lifecycle"></a>ポータルのライフサイクルについて

ポータルは、試用版として常に作成されます。 30 日後に有効期限が切れる試用版は、無料でポータルの機能を試すために役立ちます。 有効期限が切れた後、ポータルは中断されシャットダウンされます。 中断から 7 日後に、試用版ポータルは削除されます。 中断に接近する、中断された、削除済み、試用版から運用への変換などのポータルのライフサイクル ステージの変化ごとに、電子メールでトーストとしての通知が送信されます。

管理者の場合は、中断したポータルを運用ポータルへと変換できます。 試用版用ポータルから運用に変換すると、環境も運用環境であることを確認します。 試用版を試用版の運用環境で運用に変換することはできません。 試用ポータルを作成した環境を削除すると、ポータルも削除されます。

最初のポータルは、テナントの環境で作成するのは無料です。 1 つ以上のポータルを作成する必要がある場合、テナントに 1 GBの未使用の保存領域が必要です。

## <a name="stages-in-portal-lifecycle"></a>ポータル ライフサイクルのステージ

### <a name="trial-portal"></a>試用版ポータル

ポータルは、試用版ポータルとして常に作成されます。 必要なライセンスを持っている場合は、PowerApps ポータルの管理センターから運用版に変換できます。 試用版ポータルを運用に変換することに関する詳細については、[試用版ポータルを運用に変換する](#convert-a-trial-portal-to-production)を参照してください。

試用版ポータルを運用に変換するには、環境には、外部ユーザーでは追加項目または内部ユーザーではライセンスが必要です。 ライセンスの詳細については、[PowerApps および Microsoft Flow のライセンスに関するよくあるご質問](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) および [PowerApps ポータルのライセンス](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#can-you-share-more-details-regarding-the-new-powerapps-portals-licensing) をご覧ください。

### <a name="suspended-portal"></a>中断状態のポータル

試用版ポータルの有効期限については、PowerApps ポータル管理センターで継続して通知が表示されます。 試用版ポータルは 30 日で有効期限が切れます。 試用期間内にポータルを運用に変換しないと、ポータルはシャットダウンされ、中断状態になります。 有効期限が切れた後は、ポータルにアクセスできません。

ただし、中断されたポータルは、中断開始から 7 日以内であれば運用に変換できます。 

### <a name="deleted-portal"></a>削除されたポータル

ポータルを 7 日の中断期間内に運用に変換しない場合は、ポータルは削除されます。 ポータルのデータは環境から削除されませんが、環境でポータルが使用した領域はリリースされ、新しいポータルを作成できます。

## <a name="convert-a-trial-portal-to-production"></a>試用版ポータルを運用に変換する

試用版ポータルは、PowerApps ポータル管理センターに表示されている通知から運用へと変換できます。

> [!NOTE]
> 試用版ポータルを運用に変換するには、次ロールの一つを割り当てる必要があります:
> - グローバル管理者
> - システム管理者

[PowerApps ポータル管理センター](admin-overview.md) を開き、[ポータルの詳細](portal-details.md) タブへと移動すると、**種類** フィールドの下に試用版の有効期限について通知が表示されます。

> [!div class=mx-imgBorder]
> ![ポータル詳細タブの試用版に関する通知](../media/admin-center-convert-notif.png "ポータル詳細タブの試用版に関する通知")

管理センターのその他のページには、ページの上部に通知が表示されます。

> [!div class=mx-imgBorder]
> ![その他のタブ上の通知](../media/admin-center-convert-notif-all.png "その他のタブ上の通知")

試用版ポータルを運用に変換するには:

1.  通知で、**変換**を選択します。

2.  **確認**を選択します。

    > [!div class=mx-imgBorder]
    > ![試用版から運用への確認](../media/trial-to-prod-confirm.png "試用版から運用への確認")
