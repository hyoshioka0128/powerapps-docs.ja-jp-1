---
title: Dynamics 365 ドメイン から Power Apps ポータル ドメイン への更新 | MicrosoftDocs
description: Dynamics 365 ドメイン から Power Apps ポータル ドメインに更新する手順。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/18/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: cddb04f048c9af2a3c5873577a36a3929d6c6a34
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2978594"
---
# <a name="update-to-power-apps-portals-domain"></a>Power Apps ポータル ドメインへの更新

古いポータル アドオンを使用してポータルをプロビジョニングすると、ポータルのドメインは`microsoftcrmportals.com`のようになります。 Power Apps ポータルのプレビュー リリースでは、Dynamics 365 ドメイン `microsoftcrmportals.com` を Power Apps ポータル ドメイン `powerappsportals.com` に更新できます。

> [!NOTE]
> `microsoftcrmportals.com`1ドメインは廃止され、古いポータルアドオンを使用してプロビジョニングされたポータルのみに制限されます。 非推奨期間では、この機能は引き続き動作し、正式に削除されるまで完全にサポートされます。 この廃止通知は数年にわたり設定できます。

1. [Power Apps ポータル管理センター](admin-overview.md) を開きます。

2. **ポータル アクション** > **Power Apps ポータル ドメインへの更新** に移動します。

    > [!div class=mx-imgBorder]
    > ![Power Apps ポータル ドメインへの更新](../media/update-portal-domain-button.png "Power Apps ポータル ドメインへの更新")

3. **ポータルの URL** では、Web サイトのアドレスを入力し、 **OK** を選択します。

    > [!div class=mx-imgBorder]
    > ![Power Apps ポータル ドメインへの更新](../media/update-portal-domain.png "Power Apps ポータル ドメインへの更新")

既に Power Apps ポータル ドメインを使用しており、古いドメインに戻したい場合は、**Power Apps ポータル ドメインへの更新** アクションをして古いドメインに戻すことができます。 この場合、メッセージは、次のように表示されます:

> [!div class=mx-imgBorder]
> ![古いドメインに戻す](../media/revert-portal-domain.png "古いドメインに戻す")
