---
title: Microsoft Teams にアプリを追加する | Microsoft Docs
description: Microsoft Teams チャネルにアプリを追加すると、アプリの共有相手であるユーザーはそのチャネルでアプリを開くことができます。
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: quickstart
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/18/2018
ms.author: mblythe
ms.openlocfilehash: 02248cc3e98f256df36bb6a57fac6e66c684a8bf
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-add-an-app-to-microsoft-teams"></a>クイック スタート: Microsoft Teams にアプリを追加する

Microsoft Teams は、Office 365 テクノロジを基に構築されているチャット ベースのコラボレーション プラットフォームです。 Teams のチャネルに PowerApps キャンバス アプリを追加して、Teams のエクスペリエンスをカスタマイズできます。 このクイック スタートでは、Product Showcase サンプル アプリを Teams のチャネルに追加し、そのチャネルからアプリを開く方法を説明します。 

![Microsoft Teams に埋め込まれたアプリ](./media/open-app-embedded-in-teams/embedded-app.png)

PowerApps にサインアップしていない場合は、[無料でサインアップ](https://web.powerapps.com/signup?redirect=marketing&email=)してください。

## <a name="prerequisites"></a>前提条件

このクイック スタートを行うには、[Office 365 サブスクリプション](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1)と [Teams のチャネル](https://www.youtube.com/watch?v=he2f1quaR7M)が必要です。

## <a name="sign-in-to-powerapps"></a>PowerApps へのサインイン

[https://web.powerapps.com]([https://web.powerapps.com) で PowerApps にサインインします。

## <a name="add-an-app"></a>アプリを追加する

1. Microsoft Teams で、チームとそのチームが所有するチャネルを選びます。 この例では、**Business Development** チームの **General** チャネルです。

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. **[+]** を選んでタブを追加します。

    ![](./media/open-app-embedded-in-teams/teams-add-tab.png)

3. **[タブの追加]** ダイアログ ボックスで、**[PowerApps]** を選びます。

    ![](./media/open-app-embedded-in-teams/add-a-tab.png)

4. **[サンプル アプリ]** > **[Product Showcase]** > **[保存]** の順に選びます。

    ![](./media/open-app-embedded-in-teams/select-an-app.png)

    アプリがチャネルで使用可能になりました。

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

> [!NOTE]
> 独自のアプリの場合は、Teams に追加する前に[共有する](../maker/canvas-apps/share-app.md)必要があります (サンプル アプリは既定で共有されます)。

## <a name="open-an-app"></a>アプリを開く

1. Microsoft Teams で、チームと、アプリを含むチャネルを選びます。

    ![](./media/open-app-embedded-in-teams/teams-select-channel.png)

2. **[Product Showcase]** タブを選びます。

    ![](./media/open-app-embedded-in-teams/open-tab.png)

    チャネルでアプリが開きます。

    ![](./media/open-app-embedded-in-teams/app-in-channel.png)

## <a name="known-issues"></a>既知の問題

Microsoft Teams のデスクトップ アプリでは:

* アプリは、セキュリティで保護された (https) 接続経由でイメージや .pdf ファイルなどのコンテンツを読み込む必要があります。
* すべてのセンサー (**Acceleration**、**Compass**、**Location** など) がサポートされているとは限りません。
* サポートされているオーディオ形式は、AAC、H264、OGG Vorbis、および WAV のみです。

## <a name="clean-up-resources"></a>リソースのクリーンアップ

チャネルからアプリを削除するには、**[Product Showcase]** タブ、**[削除]** の順に選びます。

## <a name="next-steps"></a>次の手順

このクイック スタートでは、Product Showcase サンプル アプリを Teams のチャネルに追加し、そのチャネルからアプリを開きました。 PowerApps についてさらに詳しく学習するには、PowerApps のチュートリアルを続けてください。

> [!div class="nextstepaction"]
> [PowerApps チュートリアル](../maker/canvas-apps/get-started-create-from-blank.md)