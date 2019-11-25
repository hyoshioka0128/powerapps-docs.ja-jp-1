---
title: ポータルのサーバー側キャッシュをクリアする | MicrosoftDocs
description: ポータルで強制的にキャッシュを更新させる指示。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 8351ca8d3befec80a9e97da03ca62980383b01b1
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2709896"
---
# <a name="clear-the-server-side-cache-for-a-portal"></a>ポータルのサーバー側キャッシュをクリアにします

ポータル管理者として、Common Data Service からの更新されたデータがポータルにすぐに反映されるよう、ポータル全体のサーバー側キャッシュをクリアできます。 Common Data Service からの更新は非同期モードでポータルに伝えられるので、Common Data Service で更新された時刻のデータおよびポータルで表示される更新されたデータの時刻との間に遅れがあるかもしれません。 この遅延&mdash;を排除するには、例えば、ポータルの構成&mdash;に影響を与える場合、ポータルがキャッシュを迅速に更新するよう強制することができます。

> [!NOTE]
> キャッシュ リフレッシュの SLA (Common Data Service とポータル間のデータ転送) は 15 分です。

サーバー側のキャッシュをクリアする

1.  ポータルに管理者としてサインインします。

2.  次のような URL に移動します: `<portal_path>/_services/about`

3.  **キャッシュのクリア**を選択します。 

サーバー側のキャッシュが削除され、データが Common Data Serviceから再度読み込まれます。 ポータルのサーバー側キャッシュをクリアすることにより、Common Data Service から再度読み込みをしている間、一時的にポータル パフォーマンスが低下することに注意してください。

> [!div class=mx-imgBorder]
> ![ポータルのキャッシュをクリアする](../media/clear-portal-cache.png "ポータルのキャッシュをクリアする")
