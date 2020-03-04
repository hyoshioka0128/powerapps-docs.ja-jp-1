---
title: オフライン対応キャンバス アプリを開発する | Microsoft Docs
description: オンラインまたはオフラインにかかわらず、ユーザーが生産性を高めることができるオフライン対応キャンバス アプリを開発します。
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 02/29/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6ec1a55713b3cce0a98c02058124b5b3d159b376
ms.sourcegitcommit: 129d004e3d33249b21e8f53e0217030b5c28b53f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78265563"
---
# <a name="develop-offline-capable-canvas-apps"></a>オフライン対応キャンバス アプリを開発する

モバイルユーザーは、接続が制限されている場合でも、接続がない場合でも、生産性を維持する必要があります。 キャンバスアプリをビルドするときに、次のタスクを実行できます。

- Power Apps Mobile を開き、オフラインのときにアプリを実行します。
- [Connection](functions/signals.md#connection) シグナル オブジェクトを使用して、アプリの接続状態 (オフライン、オンライン、または従量制課金接続) を判別します。
- [コレクション](create-update-collection.md)を使用し、オフライン時に基本的なデータストレージに対して[ **LoadData**関数と**SaveData** ](functions/function-savedata-loaddata.md)関数を活用します。

この記事には、Twitter データの使用例が含まれています。  [ **LoadData**および**SaveData**関数参照](functions/function-savedata-loaddata.md)には、接続を必要としない、より単純な例が含まれています。

## <a name="limitations"></a>制限事項

**LoadData**と**SaveData**を組み合わせると、小さなデータをローカルデバイスに格納するための単純なメカニズムが形成されます。 これらの関数を使用すると、単純なオフライン機能をアプリに追加できます。

これらの関数は、メモリ内コレクションで動作するため、使用可能なアプリメモリの量によって制限されます。 使用可能なメモリは、デバイス、オペレーティングシステム、Power Apps モバイルで使用されるメモリ、画面とコントロールの観点からアプリの複雑さによって異なります。 数 mb を超えるデータを格納する場合は、実行する予定のデバイスで、想定されるシナリオでアプリをテストします。 一般に、使用可能なメモリは 30-70 mb です。

また、デバイスがオンラインになったときに、マージの競合を自動的に解決する機能もありません。 保存されるデータと再接続の処理方法の構成は、式の作成時に作成者に対して行います。

オフライン機能の更新プログラムについては、このトピックに戻って、 [Power Apps ブログ](https://powerapps.microsoft.com/blog/)を購読してください。

## <a name="overview"></a>概要

オフラインシナリオを設計する場合は、まず、アプリがデータを操作する方法を検討する必要があります。 Power Apps のアプリは、主に、プラットフォームが提供する一連の[コネクタ](../canvas-apps/connections-list.md)(SharePoint、Office 365、Common Data Service など) を介してデータにアクセスします。 RESTful エンドポイントを提供するサービスへのアプリのアクセスを可能にするカスタム コネクタを構築することもできます。 Web API や Azure Functions などのサービスが考えられます。 これらのコネクタは、すべてがインターネット経由で HTTPS を使用します。つまり、ユーザーは、データやサービスが提供するその他の機能にアクセスするには、オンラインである必要があります。

![コネクタを使用した Power Apps アプリ](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>オフライン データの処理

Power Apps では、データソースに関係なく、一貫した方法でデータのフィルター処理、検索、並べ替え、集計、操作を行うことができます。 アプリ内のメモリ内コレクションから SharePoint リストへのソースの範囲は、SQL データベースと Common Data Service になります。 この一貫性により、別のデータソースを使用するようにアプリを簡単に再ターゲットできます。 さらに重要なのは、オフラインのシナリオでは、アプリケーションのロジックをほとんど変更せずに、データ管理にローカルコレクションを使用できることです。 実際、ローカル コレクションは、オフライン データを処理するための主要メカニズムです。

## <a name="build-an-offline-app"></a>オフラインアプリを構築する

このトピックでは、アプリ開発のオフラインの側面に注目するために、Twitter を中心とした簡単なシナリオについて説明します。 Twitter の投稿を読んだり、オフライン中にツイートを送信したりできるアプリを構築します。 アプリは、オンラインになったときに、ツイートを投稿し、ローカル データを再度読み込みます。

大まかに言えば、アプリは次のタスクを実行します。

- ユーザーがアプリを開くと、次のようになります。

  - デバイスがオンラインの場合、アプリは Twitter コネクタを使用してデータをフェッチし、コレクションにそのデータを設定します。
  - デバイスがオフラインの場合、アプリは[**LoadData**](../canvas-apps/functions/function-savedata-loaddata.md)関数を使用してローカルキャッシュファイルからデータを読み込みます。
  - ユーザーは、ツイートを送信できます。 アプリがオンラインの場合は、ツイートを Twitter に直接投稿し、ローカルキャッシュを更新します。

- アプリがオンラインになるまで5分ごと:

  - アプリは、ツイートをローカルキャッシュに投稿します。
  - アプリはローカルキャッシュを更新し、 [**SaveData**](../canvas-apps/functions/function-savedata-loaddata.md)関数を使用して保存します。

### <a name="step-1-add-twitter-to-a-blank-phone-app"></a>手順 1: 空の電話アプリに Twitter を追加する

1. Power Apps Studio で、[**ファイル** > **新規作成**] を選択します。
1. **[空のアプリ]** タイルで、 **[携帯電話レイアウト]** を選択します。
1. **[ビュー]** タブで **[データソース]** を選択します。
1. **データ**ペインで、 **[データソースの追加]** を選択します。
1. [**新しい接続** > **Twitter** > **作成**] を選択します。
1. 資格情報を入力し、接続を作成して、 **[データ]** ウィンドウを閉じます。

### <a name="step-2-collect-existing-tweets"></a>手順 2: 既存のツイートを収集する

1. **[ツリービュー]** ペインで **[アプリ]** を選択し、 **OnStart**プロパティを次の数式に設定します。

    ```powerapps-dot
    If( Connection.Connected,
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 10} ) );
            Set( statusText, "Online data" ),
        LoadData( LocalTweets, "LocalTweets", true );
            Set( statusText, "Local data" )
    );
    SaveData( LocalTweets, "LocalTweets" );
    ```

    > [!div class="mx-imgBorder"]
    > ツイート](./media/offline-apps/load-tweets.png) を読み込む数式 ![

1. **ツリービュー**ペインで、**アプリ**オブジェクトの省略記号メニューを選択し、 **[実行]** を選択してその数式を実行します。

    > [!div class="mx-imgBorder"]
    > ツイート](./media/offline-apps/load-tweets-run.png) を読み込むために数式を実行 ![

    > [!NOTE]
    > **LoadData**関数と**SaveData**関数は、ブラウザーがサポートしていないため、Power Apps Studio でエラーが表示されることがあります。 ただし、デバイスにこのアプリを展開した後、通常どおりに実行されます。

この数式は、デバイスがオンラインであるかどうかを確認します。

- デバイスがオンラインの場合、数式は検索語句 "PowerApps" を含む10個のツイートを**LocalTweets**コレクションに読み込みます。
- デバイスがオフラインの場合は、"LocalTweets" という名前のファイルからローカルキャッシュが読み込まれます (使用可能な場合)。

### <a name="step-3-show-tweets-in-a-gallery"></a>手順 3: ギャラリーでツイートを表示する

1. **挿入** タブで、**ギャラリー** > 空の**柔軟な高さ** を選択します。

1. [**ギャラリー**](controls/control-gallery.md)コントロールの**Items**プロパティを `LocalTweets`に設定します。

1. ギャラリーテンプレートで、3つの[**ラベル**](controls/control-text-box.md)コントロールを追加し、各ラベルの**Text**プロパティを次のいずれかの値に設定します。

    - `ThisItem.UserDetails.FullName & " (@" & ThisItem.UserDetails.UserName & ")"`
    - `Text(DateTimeValue(ThisItem.CreatedAtIso), DateTimeFormat.ShortDateTime)`
    - `ThisItem.TweetText`

1. ギャラリーがこの例に似ているように、最後のラベルのテキストを太字にします。

    > [!div class="mx-imgBorder"]
    > サンプルツイート](./media/offline-apps/tweet-gallery.png) を示す ![ギャラリー

### <a name="step-4-show-connection-status"></a>手順 4: 接続の状態を表示する

1. ギャラリーの下にラベルを挿入し、その**Color**プロパティを**赤**に設定します。

1. 最新のラベルの**Text**プロパティを次の数式に設定します。

    `If( Connection.Connected, "Connected", "Offline" )`

この数式は、デバイスがオンラインであるかどうかを判断します。 接続されている場合は、ラベルに "Connected" と表示**さ**れます。それ以外の場合は、 **[オフライン]** と表示されます。

### <a name="step-5-add-a-box-to-compose-tweets"></a>手順 5: ツイートを作成するためのボックスを追加する

1. [接続状態] ラベルの下に、[**テキスト入力**](controls/control-text-input.md)コントロールを挿入し、名前を**NewTweetTextInput**に変更します。

1. テキスト入力ボックスの**Default**プロパティを `""`に設定します。

    > [!div class="mx-imgBorder"]
    > ステータス情報とテキスト入力ボックスを ![ギャラリー](./media/offline-apps/status-input.png)

### <a name="step-6-add-a-button-to-post-the-tweet"></a>手順 6: ツイートを投稿するためのボタンを追加する

1. [テキスト入力] ボックスの下に**ボタン**コントロールを追加し、 **text**プロパティを次の値に設定します。

    `"Tweet"`

1. ボタンの**Onselect**プロパティを次の数式に設定します。

    ```powerapps-dot
    If( Connection.Connected,
        Twitter.Tweet( "", {tweetText: NewTweetTextInput.Text} ),
        Collect( LocalTweetsToPost, {tweetText: NewTweetTextInput.Text} );
            SaveData( LocalTweetsToPost, "LocalTweetsToPost" )
    );
    Reset( NewTweetTextInput );
    ```  

1. **アプリ**の**OnStart**プロパティで、数式の最後に行を追加します。

    ```powerapps-dot
    If( Connection.Connected,
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 100} ) );
            Set( statusText, "Online data" ),
        LoadData( LocalTweets, "LocalTweets", true );
            Set( statusText, "Local data" )
    );
    SaveData( LocalTweets, "LocalTweets" );
    LoadData( LocalTweetsToPost, "LocalTweetsToPost", true );  // added line
    ```

    > [!div class="mx-imgBorder"]
    > コメント解除される行を使用してツイートを読み込むには、式を実行 ![](./media/offline-apps/load-tweets-save.png)

この数式は、デバイスがオンラインであるかどうかを判断します。

- デバイスがオンラインの場合は、すぐにツイートが投稿されます。
- デバイスがオフラインの場合、ツイートが**LocalTweetsToPost**コレクションにキャプチャされ、デバイスに保存されます。

次に、式によってテキスト入力ボックス内のテキストがリセットされます。

### <a name="step-7-check-for-new-tweets"></a>手順 7: 新しいツイートを確認する

1. ボタンの右側に**Timer**コントロールを追加します。

    > [!div class="mx-imgBorder"]
    > 最終的なアプリの ![](./media/offline-apps/final-app.png)

1. タイマーの**Duration**プロパティを**30万**に設定します。

1. タイマーの **[自動開始]** を設定し **、プロパティを** **[true]** に設定します。

1. タイマーの**Ontimerend**を次の数式に設定します。

    ```powerapps-dot
    If( Connection.Connected,
        ForAll( LocalTweetsToPost, Twitter.Tweet( "", {tweetText: tweetText} ) );
        Clear( LocalTweetsToPost );
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 10} ) );
        SaveData( LocalTweets, "LocalTweets" );
   )
    ```

この数式は、デバイスがオンラインであるかどうかを判断します。 ツイートの場合、アプリは**LocalTweetsToPost**コレクション内のすべての項目を削除してから、コレクションをクリアします。

## <a name="test-the-app"></a>アプリケーションをテストする

1. インターネットに接続されているモバイルデバイスでアプリを開きます。

    ギャラリーに既存のツイートが表示され、状態が **[接続済み]** と表示されます。

1. デバイスの機内モードを有効にし、wi-fi を無効にして、インターネットからデバイスを切断します。

    状態ラベルは、アプリが**オフライン**であることを示しています。

1. デバイスがオフラインの間、 **PowerApps**を含むツイートを作成し、 **[ツイート]** ボタンを選択します。

    ツイートは、ローカルの**LocalTweetsToPost**コレクションに格納されます。

1. デバイスの機内モードを無効にし、wi-fi を有効にして、デバイスをインターネットに再接続します。

    5分以内に、アプリはギャラリーに表示されるツイートを投稿します。

この記事では、オフラインアプリを構築するために、Power Apps に用意されている機能について説明します。 常に、[フォーラム](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1)にフィードバックを提供し、 [Power apps コミュニティブログ](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog)でオフラインアプリの例を共有してください。