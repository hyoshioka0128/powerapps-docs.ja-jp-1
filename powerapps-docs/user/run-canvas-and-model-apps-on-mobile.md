---
title: モバイル デバイスでキャンバス アプリやモデル駆動型アプリを実行する | Microsoft Docs
description: モバイル デバイスでキャンバス アプリまたはカスタムのモデル駆動型アプリを実行する方法について説明します。
author: mduelae
ms.service: powerapps
ms.component: pa-user
ms.topic: quickstart
ms.date: 04/30/2020
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: d7690cdab07c32b740e058f905ab9d96df7c1bba
ms.sourcegitcommit: 597849e2942c88a5c54953eeb8f14c8c81ac0ae2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/01/2020
ms.locfileid: "3326111"
---
# <a name="run-canvas-apps-and-model-driven-apps-on-a-mobile-device"></a>モバイル デバイスでキャンバス アプリやモデル駆動型アプリを実行する

アプリを作成するか、他のユーザーがアプリを共有する場合&mdash;キャンバス アプリかモデル駆動型アプリのいずれかで&dash; Power Apps モバイル アプリを使用することで、iOS デバイスや Android デバイスでそのアプリを実行できます。 Windows デバイスを使用している場合は、キャンバス アプリのみを実行できます。モデル駆動型アプリは、Windows デバイス用の Power Apps モバイル アプリではサポートされていません。 このトピックでは、モバイル デバイスでキャンバス アプリやモデル駆動型アプリを開始して実行する方法について説明します。 

Power Apps モバイル アプリで動作するモデル駆動型アプリを使用する方法については、[Power Apps モバイル アプリで動作するモデル駆動型アプリのユーザー ガイド](use-custom-model-driven-app-on-mobile.md) を参照してください。

> [!IMPORTANT]
> Dynamics 365 Sales、Dynamics 365 Customer Service、Dynamics 365 Field Service、Dynamics 365 Marketing、Dynamics 365 Project Service Automation のモデル駆動型アプリ<!--Via Dynamics Style Guide. If this sentence doesn't apply to all these products, maybe only mention Sales, Customer Service, and Field Service as you do in use-custom-model-driven-app-on-mobile.md? "Dynamics verticals" is out of brand.--> Power Apps モバイル アプリでは動作しません。 代わりに、スマートフォンやタブレットのアプリに Dynamics 365 を使用します。 詳細: [電話およびタブレット PC 用 Dynamics 365 ユーザー ガイド](https://docs.microsoft.com/dynamics365/mobile-app/dynamics-365-phones-tablets-users-guide)

![Power Apps モバイル](media/powerappsmobile.png "Power Apps モバイル ユーザー インターフェイス")

凡例:

1. **モデル駆動型アプリ**
2. **キャンバス アプリ**

**Power Apps モバイルのインストール**

この手順に従うには、まだ Power Apps にサインアップしていない場合は、[無料サインアップ](https://make.powerapps.com/signup?redirect=marketing&email=) を済ませ、[サポート対象のオペレーティング システム](../maker/canvas-apps/limits-and-config.md) を実行している iPhone、iPad、または Android デバイスで、[App Store](https://itunes.apple.com/app/powerapps/id1047318566?mt=8) または [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.msapps) から Power Apps をダウンロードしてください。 自分で作成したキャンバス アプリ、または他のユーザーが作成して共有されたキャンバス アプリにアクセスできることも確認してください。


## <a name="open-power-apps-and-sign-in"></a>Power Apps を開いてサインインする

モバイル デバイスで Power Apps を開き、Azure Active Directory の資格情報を使用してサインインします。

![Power Apps にサインインする](media/powerapps_mobile_app_signin_screen.png "Power Apps にサインインする")

モバイル デバイスに Microsoft Authenticator アプリがインストールされている場合は、メッセージが表示されたらユーザー名を入力し、デバイスに送信される通知を承認するだけです。


## <a name="find-the-app"></a>アプリを見つける

アプリにサインインすると、**[マイ アプリ]** フィルターが既定で設定されています。 探しているアプリが見つからない場合は、**Power Apps** メニューを開いて、別のフィルターを選択します。 


![アプリのフィルター](media/filter-menu.png "アプリのフィルター")

次のフィルターを使用できます。

* **すべてのアプリ** : 自分が作成したアプリ、他のユーザーが共有したアプリなど、アクセスできるすべてのキャンバス アプリとモデル駆動型アプリを表示します。

* **マイ アプリ** : キャンバス アプリの場合は、自分が開いたキャンバス アプリ、自分が所有者になっているアプリ、および編集可能なアプリが表示されます。 モデル駆動型アプリの場合は、アクセスできるすべてのモデル駆動型アプリが表示されます。 

* **サンプル アプリ** (キャンバス アプリのみ): 設計の可能性を模索できるように、架空のデータを使用して実際のアプリケーション シナリオを紹介する Microsoft のサンプル キャンバス アプリを表示します。

* **お気に入り** (キャンバス アプリのみ): アプリ タイルで省略記号 (...) を選択し、**お気に入り** を選択して、マークしたキャンバス アプリを表示します。 この一覧からアプリを削除するには、アプリ タイルの省略記号 [...] を選択して、**[お気に入りから外す]** を選択します。

    ![お気に入りとしてマークする](media/add_favorite_app.png "お気に入りとしてマークする")

* **おすすめアプリ** (キャンバス アプリのみ): 管理者がおすすめアプリとしてマークしたキャンバス アプリを表示します。

### <a name="sort-apps"></a>アプリの並べ替え

アプリをフィルター処理した後は、フィルター処理された一覧を、アプリが最後に開かれたり変更されたりした日付順、または名前のアルファベット順に並べ替えることができます。 アプリを閉じて再度開いたときも、これらの設定は保持されます。 キャンバス アプリとモデル駆動型アプリの両方を並べ替えることができます。

![並べ替えメニュー](media/sort_apps.png "並べ替えメニュー")

### <a name="search-apps"></a>アプリの検索

実行するアプリの名前がわかっている場合は、上部にある検索アイコンを選択して、検索ボックスに名前の一部を入力します。 キャンバス アプリとモデル駆動型アプリの両方を検索できます。

![アプリを検索する](media/search_apps.png "アプリを検索する")

アプリをフィルター処理した場合は、フィルター処理された一覧が検索されます。

### <a name="refresh-the-list-of-apps"></a>アプリの一覧の更新

アプリの一覧を更新するには、更新アイコン ![アイコンを更新する](media/refresh_icon.png) を選択します。 これにより、キャンバス アプリとモデル駆動型アプリの両方の一覧が更新されます。 

## <a name="pin-an-app-to-the-home-screen"></a>ホーム画面へのアプリのピン留め

すばやくアクセスできるように、キャンバス アプリとモデル駆動型アプリの両方をデバイスのホーム画面にピン留めすることができます。 アプリ タイルの省略記号 [...] を選択し、**[ホームにピン留め]** を選択して、表示される指示に従います。

![アプリをピン留めする](media/pin_to_home.png "アプリをピン留めする")

## <a name="see-non-production-apps"></a>非運用アプリを参照する

既定では、運用環境のモデル駆動型アプリのみがアプリの一覧に表示されます。

非運用環境のモデル駆動型アプリを表示するには、**[設定]** メニュー ![設定アイコン](media/settings_icon.png) を選択してから **[Show non-production apps] (非運用アプリを表示する)** をオンにします。 表示される指示に従います。

![非運用アプリの切り替え](media/non_prod_toggle.png "非運用アプリの切り替え")

## <a name="run-an-app"></a>アプリを実行する

モバイル デバイスでアプリを実行するには、アプリ タイルを選択します。 他のユーザーが作成したアプリをメールで共有した場合、メール内のリンクを選択することでアプリを実行できます。

### <a name="run-a-canvas-app"></a>キャンバス アプリを実行する

Power Apps モバイル アプリを使用してキャンバス アプリを初めて実行する場合は、画面にスワイプ ジェスチャが表示されます。

#### <a name="close-a-canvas-app"></a>キャンバス アプリを閉じる

アプリの左端から右に向かって指でスワイプすると、アプリが閉じます。 Android デバイスでは、[戻る] ボタンを押してから、アプリの終了を確認することもできます。

![アプリを閉じる](media/swipe.gif "アプリを閉じる")

#### <a name="pinch-and-zoom-in-on-a-canvas-app"></a>キャンバス アプリでのピンチとズームイン

![ピンチ操作によるズーム](media/pinchtozoom.jpg "ピンチ操作によるズーム")

#### <a name="give-consent-to-a-canvas-app"></a>キャンバス アプリに同意する

アプリでデータ ソースへの接続またはデバイスの機能 (カメラや位置情報サービスなど) を使うためのアクセス許可が必要な場合は、アプリを使う前に同意する必要があります。 通常、これが求められるのはアプリを初めて実行したときのみです。

![同意する](media/give_consent_canvas.jpg "同意")

### <a name="run-a-model-driven-app"></a>モデル駆動型アプリを実行する 

次の図は、サインイン後のモデル駆動型アプリの画面例を示しています。 Power Apps モバイル アプリで動作するモデル駆動型アプリを使用する方法については、[Power Apps モバイル アプリで動作するモデル駆動型アプリのユーザー ガイド](use-custom-model-driven-app-on-mobile.md) を参照してください。 

![モデル駆動型アプリのホームページ](media/model-driven-app-opened.png "モデル駆動型アプリのホームページ")

#### <a name="give-consent-to-a-model-driven-app"></a>モデル駆動型アプリに同意する

アプリでデータ ソースへの接続またはデバイスの機能 (カメラや位置情報サービスなど) を使うためのアクセス許可が必要な場合は、アプリを使う前に同意する必要があります。 通常、これが求められるのはアプリを初めて使用したときのみです。

![同意する](media/give_consent.png "同意")

#### <a name="close-a-model-drive-app"></a>モデル駆動型アプリを閉じる

サイトマップ ![サイト マップ アイコン](media/pa_mobile_sitemap_icon.png "サイト マップ アイコン") を選択し、**[アプリ]** を選択します。

![モデル駆動型アプリを閉じる](media/pa_mobile_close_app.png "モデル駆動型アプリを閉じる")



