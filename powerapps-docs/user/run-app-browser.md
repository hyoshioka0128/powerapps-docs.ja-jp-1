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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74956786"
---
# <a name="run-an-app-in-a-web-browser"></a>アプリを Web ブラウザーで実行する
アプリを作成する場合、または他のユーザーがアプリを共有する場合は、Dynamics 365 モバイルアプリまたはタブレットの web ブラウザーでそのアプリを実行できます。 このトピックでは、 [Dynamics 365 ホームページ](https://home.dynamics.com)からタブレットの web ブラウザーで、キャンバスまたはモデル駆動型アプリを実行する方法について説明します。

すべての機能と最適化されたエクスペリエンスを実現するには、携帯電話およびタブレットモバイルアプリ用の Dynamics 365 を使用することを強くお勧めします。 携帯電話用の Dynamics 365 およびタブレットアプリがインストールされていない場合でも、デバイスの画面解像度が十分に高い限り、タブレットで web ブラウザーを使用できます。 詳細については、「[サポートされているもの](https://docs.microsoft.com/dynamics365/mobile-app/support-phones-tablets#supported-devices-for-the-mobile-app)」を参照してください。

> [!NOTE]
> 電話で web ブラウザーを使用してモデル駆動型アプリを実行することはサポートされていません。携帯電話用の Dynamics 365 アプリを使用する必要があります。

このクイック スタートを実行するには、以下が必要です。
- Power Apps ライセンス。 これは、power apps プラン[2 の試用版](https://docs.microsoft.com/powerapps/maker/signup-for-powerapps)、power apps を含む[Microsoft Office 365](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1)または[Dynamics 365](https://dynamics.microsoft.com/pricing/)プランなどの power apps プランで利用できます。 
- 自分で作成したアプリ、または他のユーザーが作成して共有されたアプリへのアクセス。
- サポートされている Web ブラウザーとオペレーティング システムへのアクセス。
   - キャンバス アプリについては、「[システム要件、制限、構成値](../maker/canvas-apps/limits-and-config.md)」を参照してください
   - モデル駆動型アプリについては、「[サポートされる Web ブラウザーとモバイル デバイス](https://docs.microsoft.com/dynamics365/customer-engagement/admin/supported-web-browsers-and-mobile-devices)」を参照してください


## <a name="sign-in-to-dynamics-365"></a>Dynamics 365 にサインインする
[https://home.dynamics.com](https://home.dynamics.com) で Dynamics 365 にサインインします。

## <a name="find-an-app-on-the-home-page"></a>ホーム ページでアプリを探す
ホーム ページには、複数の種類のビジネス アプリが表示される場合がありますが、検索ボックスにアプリ名の一部を入力すると特定のアプリを見つけることができます。 また、一覧をフィルター処理して、Power Apps など、特定のソースによって作成されたアプリのみを表示することもできます。 これを行うには、 **[フィルター]** を選択し、ソースを選択します。

最近インストールしたアプリは、アプリの一覧にすぐに表示されない場合があります。 すべてのアプリを表示するには、 **[同期]** を選択します。 この処理には最大で 1 分ほどかかることがあります

![](./media/run-app-browser/dynamics-365-home.png)


## <a name="run-an-app-from-a-url"></a>URL からアプリを実行する
アプリの URL をタブレットのブラウザーにブックマークとして保存し、ブックマークを選択して実行するか、または電子メールでリンクとして URL を送信することができます。 他のユーザーがアプリを作成し、それを電子メールで共有している場合は、電子メールのリンクを選択してアプリを実行できます。 URL を使ってアプリを実行するときは、Azure Active Directory の資格情報をってサインインするように求められることがあります。

![](./media/run-app-browser/web-login.png)

## <a name="connect-to-data"></a>データに接続する
アプリでデータ ソースへの接続またはデバイスの機能 (カメラや位置情報サービスなど) を使うためのアクセス許可が必要な場合は、アプリを使う前に同意する必要があります。 通常、このことが求められるのは初回のみです。

![Connection](./media/run-app-browser/app-connection.png)

## <a name="close-an-app"></a>アプリを閉じる
アプリを閉じるには、Dynamics 365 ホーム ページからサインアウトするか、別のアプリを開きます。

## <a name="next-steps"></a>次の手順
このトピックでは、Web ブラウザーでキャンバス アプリまたはモデル駆動型アプリを実行する方法について説明しました。 次の方法を学習します。
- モバイルデバイスでキャンバスアプリを実行する方法については、「[モバイルデバイスでキャンバスアプリを実行](run-app-client.md)する」を参照してください。
- モバイルデバイスでモデル駆動型アプリを実行する方法については、「[モバイルデバイスでモデル駆動型アプリを実行](run-app-client-model-driven.md)する」を参照してください。
- モデル駆動型アプリの使用については、「[モデル駆動型アプリの使用](use-model-driven-apps.md)」を参照してください。

