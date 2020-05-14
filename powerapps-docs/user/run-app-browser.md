---
title: Web ブラウザーでアプリを実行する | Microsoft Docs
description: このトピックでは、Web ブラウザーでアプリを実行する方法を説明します
author: mduelae
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 12/05/2019
ms.author: mkaur
manager: kvivek
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 8ce6cfe213817cd603857bb5ea2735b188f8cb6c
ms.sourcegitcommit: 15c6b26ff085928459ad9b3f52fb607fae4a997d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "3302980"
---
# <a name="run-an-app-in-a-web-browser"></a>アプリを Web ブラウザーで実行する
自分でアプリを作成したり、他のユーザーのアプリを共有したりしたら、そのアプリを Dynamics 365 モバイル アプリやタブレット上の Web ブラウザーで実行できます。 このトピックでは、キャンバス アプリまたはモデル駆動型アプリを、[Dynamics 365 ホーム ページ](https://home.dynamics.com)からタブレット上の Web ブラウザーで実行する方法を説明します。

スマートフォンやタブレット向けの Dynamics 365 モバイル アプリを使用することをお勧めしています。すべての機能を最大限ご利用いただけます。 スマートフォンやタブレット向けの Dynamics 365 アプリをインストールしていない場合でも、デバイスの画面解像度が十分に高ければ、タブレット上で Web ブラウザーを利用できます。 詳細情報: [サポートされている機能](https://docs.microsoft.com/dynamics365/mobile-app/support-phones-tablets#supported-devices-for-the-mobile-app)。

> [!NOTE]
> スマートフォン上の Web ブラウザーを利用してモバイル駆動型アプリを実行することはできません。スマートフォン向け Dynamics 365 アプリを使用する必要があります。

このクイック スタートを実行するには、以下が必要です。
- Power Apps ライセンス。 これは [Power Apps プラン 2 の試用版](https://docs.microsoft.com/powerapps/maker/signup-for-powerapps) などの Power Apps プラン、または Power Apps を含む [Microsoft Office 365](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) または [Dynamics 365](https://dynamics.microsoft.com/pricing/) プランのいずれかで利用できます。 
- 自分で作成したアプリ、または他のユーザーが作成して共有されたアプリへのアクセス。
- サポートされている Web ブラウザーとオペレーティング システムへのアクセス。
   - キャンバス アプリについては、「[システム要件、制限、構成値](../maker/canvas-apps/limits-and-config.md)」を参照してください
   - モデル駆動型アプリについては、「[サポートされる Web ブラウザーとモバイル デバイス](https://docs.microsoft.com/dynamics365/customer-engagement/admin/supported-web-browsers-and-mobile-devices)」を参照してください


## <a name="sign-in-to-dynamics-365"></a>Dynamics 365 へのサインイン
[https://home.dynamics.com](https://home.dynamics.com) で Dynamics 365 にサインインします。

## <a name="find-an-app-on-the-home-page"></a>ホーム ページでアプリを探す
ホーム ページには、複数の種類のビジネス アプリが表示される場合がありますが、検索ボックスにアプリ名の一部を入力すると特定のアプリを見つけることができます。 また、一覧をフィルター処理して、特定のソース (Power Apps など) によって作成されたアプリのみを表示することもできます。 そのためには、**[フィルター]** を選択し、ソースを選択します。

最近インストールしたアプリは、アプリの一覧にすぐに表示されない場合があります。 すべてのアプリを表示するには、**[同期]** を選択します。 この処理には最大で 1 分ほどかかることがあります

![](./media/run-app-browser/dynamics-365-home.png)


## <a name="run-an-app-from-a-url"></a>URL からアプリを実行する
タブレットのブラウザーのブックマークとしてアプリの URL を保存し、ブックマークを選択してアプリを実行したり、メールでリンクとして URL を送信したりできます。 他のユーザーが作成したアプリをメールで共有した場合、メール内のリンクを選択することでアプリを実行できます。 URL を使ってアプリを実行するときは、Azure Active Directory の資格情報をってサインインするように求められることがあります。

![](./media/run-app-browser/web-login.png)

## <a name="connect-to-data"></a>データへの接続
アプリでデータ ソースへの接続またはデバイスの機能 (カメラや位置情報サービスなど) を使うためのアクセス許可が必要な場合は、アプリを使う前に同意する必要があります。 通常、これが求められるのは初回のみです。

![つながり](./media/run-app-browser/app-connection.png)

## <a name="close-an-app"></a>アプリを閉じる
アプリを閉じるには、Dynamics 365 ホーム ページからサインアウトするか、別のアプリを開きます。

## <a name="next-steps"></a>次のステップ
このトピックでは、Web ブラウザーでキャンバス アプリまたはモデル駆動型アプリを実行する方法について説明しました。 参照:
- モバイル デバイスでキャンバス アプリを実行する方法については、「[キャンバス アプリをモバイル デバイスで実行する](run-app-client.md)」を参照してください
- モバイル デバイスでモデル駆動型アプリを実行する方法については、「[モバイル デバイスでモデル駆動型アプリを実行する](run-app-client-model-driven.md)」を参照してください
- モデル駆動型アプリを使用する方法については、「[モデル駆動型アプリを使う](use-model-driven-apps.md)」を参照してください

