---
title: 危機通信アプリ-サンプルテンプレート |Microsoft Docs
description: Power Apps の危機通信のサンプルテンプレートについて説明します。
author: matthewbolanos
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/04/2020
ms.author: mabolan
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: a547eac25e71467fb751e0a0c6eb30eccdac48ec
ms.sourcegitcommit: efb05dbd29c4e4fb31ade1fae340260aeba2e02b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "78293467"
---
# <a name="set-up-and-learn-about-the-crisis-communication-sample-template-in-power-apps"></a>Power Apps での危機通信のサンプルテンプレートのセットアップと学習

電源アプリ用の危機通信アプリをインストールおよび構成するための詳細な手順です。

これらの手順の推定所要時間: **20-25 分**

## <a name="overview-of-the-app"></a>アプリの概要

*危機通信*アプリは、ユーザーフレンドリなエクスペリエンスを提供し、緊急時の情報をエンドユーザーに接続します。 社内の社内ニュースをすばやく更新し、よく寄せられる質問への回答を取得し、リンクや緊急連絡先などの重要な情報にアクセスします。 このアプリをお使いの環境に合わせるには、少し設定が必要です。

このチュートリアルでは、次の方法について説明します。
- データの場所を作成する
- 危機通信アプリとその管理アプリの両方をインポートします。
- アプリのコンテンツを作成する
- フローをインポートしてユーザーに通知を送信する
- 集中管理されたチームチームを作成してデータを集計し、問題に効果的に対応する

## <a name="prerequisites"></a>前提条件

- Power Apps 用の[サインアップ](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 。
- 有効な SharePoint Online ライセンスと、リストを作成するためのアクセス許可が必要です。
- アプリのデータを格納できるパブリック SharePoint サイトが必要です。
- [Aka.ms/CrisisCommunicationSolution](https://aka.ms/CrisisCommunicationSolution)から資産をダウンロードします。

## <a name="create-a-home-for-your-data"></a>データのホームを作成する

アプリのデータは SharePoint リストに存在します。 最初に、新しい SharePoint サイトを作成して作業を開始する必要があります。

### <a name="create-a-sharepoint-site"></a>SharePoint サイトの作成

1. [Office online](https://www.office.com)にサインインし、 **[SharePoint]** を選択します。
1. [サイトの作成] を選択し、[次へ] を選択します。

    ![SharePoint サイトのサンプル](media/sample-crisis-communication-app/01-Create-Site.png)

1. チームサイトの選択:

    ![チームサイト](media/sample-crisis-communication-app/02-Team-Site.png)

1. サイトに名前と説明を指定します。
1. プライバシー設定を [パブリック] に設定して、会社内のすべてのユーザーが必要な情報を取得できるようにします。

    ![サイトの設定](media/sample-crisis-communication-app/03-Privacy-Settings.png)

1. [次へ] を選択します。
1. 必要に応じて、他の所有者を追加します。
1. [完了] を選択します。

### <a name="create-the-sharepoint-lists-for-app"></a>アプリの SharePoint リストを作成する
アプリには、すべてのデータを格納する複数のリストが必要です。 SharePoint リストの作成を自動化するには、ダウンロードした[アセットパッケージ](#prerequisites)から入手できる*DeploySPLists* flow を使用します。

#### <a name="import-the-sharepoint-list-deployment-flow"></a>SharePoint リストのデプロイフローをインポートする
1. [Flow.microsoft.com](https://flow.microsoft.com)にアクセス
1. 左側のナビゲーションから **[自分のフロー]** を選択します。
1. コマンドバーの **[インポート]** をクリックします。
1. GitHub リポジトリから**DeploySPList**パッケージをアップロードします。

    ![パッケージのインポート](media/sample-crisis-communication-app/import-package.png)

1. **[インポート時に選択]** リンクを選択し、フォームに入力して、新しいフローの SharePoint 接続を追加します。

    ![［設定のインポート］](media/sample-crisis-communication-app/import-settings.png)

1. 新しい SharePoint 接続を作成する必要がある場合は、まず、セットアップのインポート ウィンドウで **新規作成** を選択します。
1. コマンドバーの **[新しい接続]** を選択します。

    ![新しい接続を作成する](media/sample-crisis-communication-app/create-connection.png)

1. *SharePoint*などの接続の名前を検索します。
1. 適切な接続を選択します。
1. **[保存]** を選択します。
1. **[インポート]** を選択します。

#### <a name="edit-the-sharepoint-list-deployment-flow"></a>SharePoint リストのデプロイフローを編集する

1. インポートが完了したら、 **[マイフロー** ] に戻り、フローの一覧を更新します。
1. 新しくインポートされたフロー **DeploySPList**を選択します。
1. コマンドバーの **[編集]** を選択します。
1. **リストの [変数–ターゲットサイト]** という名前のカードを開きます。
1. 値を SharePoint サイトの名前に変更します。
1. [**変数–アプリ名]** という名前のカードを開きます。
1. 値をアプリの名前に変更します。既定では、"危機通信" になります。

    ![フローパラメーター](media/sample-crisis-communication-app/04-Flow-Settings.png)

1. **[保存]** を選択して変更をコミットします。

#### <a name="run-the-sharepoint-list-deployment-flow"></a>SharePoint リスト配置フローの実行

1. DeploySPList flow の詳細画面に戻り**ます。**
1. コマンドバーの **[実行]** を選択します。
1. **[続行]** を選択してから**フローを実行**し、フローをトリガーします。

    ![サインインしてフローを実行する](media/sample-crisis-communication-app/sign-in-flow.png)

    ![フローを実行する](media/sample-crisis-communication-app/run-flow.png)

> [!NOTE]
> ロケーションサービスが必要であることを示すエラーが表示される場合があります。
この問題が発生した場合は、位置情報サービスの自動化を許可し、ページを更新してから再試行してください。

その後、フローによって、SharePoint サイト内に次の SharePoint リストが作成されます。

| **タイトルの表示**| **目的** | **説明** |
|-|-|-|
| CI_LogosAssets| ロゴ、またはアプリから参照されるその他のイメージを保持する。 ロゴは、直接リンクまたは目的のロゴの ID 番号を使用して、Power Apps で参照されます。 | [App Name] アプリの関連するロゴとその他のイメージアセットのライブラリ。 |
| CI_configAdminSetup | ツールの管理者による機能の構成。 **注**: この一覧は、管理者ではないすべてのメンバーに対して読み取り専用である必要があります。 | [App Name] アプリの管理者構成の一覧。
| CI_Contacts | 既定の連絡先のコンテンツタイプを使用して、連絡先に関する情報をキャプチャします。 (People 選択は含まれていません。そのため、データを最新の状態に保つためにメンテナンスが必要になる場合があります)。 **注**: これは、リストの既定のコンテンツタイプとして、グローバル連絡先リストの種類によって異なります。 | [App Name] アプリの連絡先リスト。|
| CI_CompanyNews | 会社のニュース項目のコレクション。 | [アプリ名] アプリに表示されるニュース項目の管理の一覧。 非推奨の列は、アプリからニュース項目をフィルター処理するために使用できます (レコードとして保持します)。 | 
| CI_FAQ  | よく寄せられる質問。 | [App Name] アプリに関してよく寄せられる質問。 非推奨の列を使用して、アプリから FAQ 項目をフィルター処理できます (レコードとして保持します)。 |
| CI_UsefullLinks | 役に立つハイパーリンクの一覧 | [App Name] アプリの便利なハイパーリンクの一覧。 非推奨の列は、アプリからハイパーリンク項目をフィルター処理するために使用できます (レコードとして保持します)。 |
| CI_Employee | 現在の従業員のプレゼンス状態を追跡しています。 例:*自宅からの作業* *病欠*。*個人用のまま*です。*休暇*中。  **注**:*作業*が行われ、リストオプションに含まれていないことを前提としています。 | [App Name] アプリの便利なハイパーリンクの一覧。 非推奨の列は、アプリからリンク項目をフィルター処理するために使用できます (レコードとして保持します)。 |
| CI_HelpfulTips             | ユーザーは、仲間に役立つヒントを投稿することができます。 | [App Name] アプリの共有ヒントを管理するための一覧です。 非推奨の列は、アプリビューからヒントを削除するために使用できます (SPO でレコードとして保持されます)。  |

> [!NOTE]
> - 上記の一覧のすべての列は、依存関係と見なす必要があります。
    誤ったスキーマ変更からリストを保護してください (たとえば、新しい列の追加は許可されますが、列を削除するとアプリが壊れる可能性があります)。
> - リスト項目を削除するときは注意が必要です。リスト項目を削除すると、履歴レコードが削除されます。 非推奨の値を [*いいえ* *] から [はい]* に切り替えて、連絡先、ニュース、faq、リンクからレコードを削除することができます。

## <a name="import-and-set-up-the-crisis-communication-app"></a>危機通信アプリをインポートしてセットアップする

すべての SharePoint リストが作成されたので、アプリをインポートして新しいデータソースに接続できるようになりました。

> [!NOTE]
> 管理アプリを使用しない場合は、SharePoint リストを手動で編集することで、これらの同じプロパティを編集することもできます。

### <a name="import-the-app"></a>アプリをインポートする

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションから **[アプリ]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. GitHub リポジトリから**CrisisCommunication**ファイルをアップロードします。

    ![アプリパッケージのインポート](media/sample-crisis-communication-app/31-Import-App.png)

1. **[インポート]** を選択します。

### <a name="update-the-sharepoint-connections"></a>SharePoint 接続を更新する

1. **アプリ**の一覧に戻ります。
1. [**緊急通信**アプリ] で [**その他のコマンド**(...)] を選択します。
1. コンテキストメニューの **[編集]** を選択します。

    ![アプリの編集](media/sample-crisis-communication-app/05-Edit-App.png)

1. **サインイン**するか、必要な接続を作成して、 **[許可]** を選択します。

    ![接続を許可する](media/sample-crisis-communication-app/allow-connections.png)

1. 左側のウィンドウでデータソースに移動します。

    ![データ ソース](media/sample-crisis-communication-app/data-sources.png)

1. 現在の SharePoint サイトを指していないため、アプリ内の既存の SharePoint リストを**削除**します。

    ![データソースの削除](media/sample-crisis-communication-app/remove-data-source.png)

1. 独自の SharePoint サイトからリストを追加します。 検索バーで SharePoint を検索することから始めます。

    ![SharePoint の検索](media/sample-crisis-communication-app/sharepoint.png)

1. **SharePoint**を選択し、接続を選択します。

    ![SharePoint 接続](media/sample-crisis-communication-app/sharepoint-connection.png)

1. SharePoint サイトの URL をコピーしてテキストフィールドに貼り付け、 **[接続]** を選択します。

    ![SharePoint サイトの URL](media/sample-crisis-communication-app/site-url.png)

1. すべての SharePoint リストとライブラリを選択し、 **[接続]** を選択します。

    ![SharePoint リストに接続する](media/sample-crisis-communication-app/sharepoint-lists.png)

1. アプリを**保存**して**発行**します。

### <a name="update-the-request-help-flow"></a>要求のヘルプフローを更新する

このフローでは、支援を求めている集中型チームチームにアダプティブカードを送信します。

![アプリパッケージのインポート](media/sample-crisis-communication-app/21-Request-Help.png)

次の手順を完了する前に、まず、危機管理チームのチームチームを作成します。 その後、ID を取得してフローに取り込むことができます。 チームチームの作成に関するヘルプが必要な場合は、「[集中型の緊急管理チームチームを作成](#create-a-central-crisis-management-teams-team)する」に進んでください。

1. すべてのヘルプ要求を投稿するチームチャネルに移動します。
1. チャネルの [.. **.** ] メニューを選択します。
1. **[チャネルへのリンクの取得]** を選択します。

    ![チャネルへのリンクの取得](media/sample-crisis-communication-app/17-Get-link-to-channel.png)

1. リンクをコピーし、テキストエディターに貼り付けます。

    ![リンクのコピー](media/sample-crisis-communication-app/18-Copy-link.png)

1. チーム ID を抽出します。これは `groupId=` の後、`&tenantId=`する前のものです。 <br> たとえば、次の URL では、チャネル ID は `8bc7c0c2-0d4c-4fb8-af99-32da74c9237b`になります。
   
   `https://teams.microsoft.com/l/channel/19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2/General?groupId=8bc7c0c2-0d4c-4fb8-af99-32da74c9237b&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47`、
   
1. チャネル ID を抽出します。これは `https://teams.microsoft.com/l/channel/` の後、`/General`する前のものです。 <br> たとえば、次の URL では、チャネル ID は `19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2`になります。
   
   `https://teams.microsoft.com/l/channel/19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2/General?groupId=8bc7c0c2-0d4c-4fb8-af99-32da74c9237b&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47`、
   
1. [Flow.microsoft.com](https://flow.microsoft.com)に移動します。
1. 左側のナビゲーションから **[自分のフロー]** を選択します。
1. **その他のコマンド**を選択する (...) **CrisisCommunication を RequestHelp** 、 **[編集]** を選択します。
    アプリ](media/sample-crisis-communication-app/20-Edit-Flow.png) を編集 ![には
1. **チーム Id**カードを開きます。
1. チーム ID を **[値]** フィールドに貼り付けます。
1. **チャンネル ID**カードを開きます。
1. チャンネル ID を **[値]** フィールドに貼り付けます。
    チーム Id を設定 ![](media/sample-crisis-communication-app/22-Set-Team-IDs.png)

## <a name="import-and-set-up-the-admin-app"></a>管理アプリをインポートしてセットアップする
インポートしたアプリを管理するには、管理アプリに対して同じ手順を繰り返す必要があります。

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションから **[アプリ]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. GitHub リポジトリから**CrisisCommunicationAdminApp**ファイルをアップロードします。

    ![アプリパッケージのインポート](media/sample-crisis-communication-app/import-app.png)

1. **[インポート]** を選択します。

### <a name="update-the-sharepoint-connections"></a>SharePoint 接続を更新する

1. **アプリ**の一覧に戻ります。
1. [**緊急通信の管理] アプリ**アプリの [**その他のコマンド**(...)] を選択します。
1. コンテキストメニューの **[編集]** を選択します。

    ![アプリの編集](media/sample-crisis-communication-app/08-Edit-Admin-App.png)

1. **サインイン**するか、必要な接続を作成して、 **[許可]** を選択します。

1. 左側のウィンドウでデータソースに移動します。

    ![データ ソース](media/sample-crisis-communication-app/data-sources.png)

1. 現在の SharePoint サイトを指していないため、アプリ内の既存の SharePoint リストを**削除**します。

    ![データソースの削除](media/sample-crisis-communication-app/remove-data-source.png)

1. 独自の SharePoint サイトからリストを追加します。 検索バーで SharePoint を検索することから始めます。

    ![SharePoint の検索](media/sample-crisis-communication-app/sharepoint.png)

1. **SharePoint**を選択し、接続を選択します。

    ![SharePoint 接続](media/sample-crisis-communication-app/sharepoint-connection.png)

1. SharePoint サイトの URL をコピーしてテキストフィールドに貼り付け、 **[接続]** を選択します。

    ![SharePoint サイトの URL](media/sample-crisis-communication-app/site-url.png)

1. すべての SharePoint リストとライブラリを選択し、 **[接続]** を選択します。

    ![SharePoint リストに接続する](media/sample-crisis-communication-app/sharepoint-lists.png)

1. 管理アプリを**保存**して**発行**します。

## <a name="create-initial-content-for-the-app"></a>アプリの初期コンテンツを作成する

これで、危機通信アプリとその管理アプリの両方が正常にインポートされました。

これで、初期コンテンツの作成を開始できます。 開始するには、危機通信管理アプリを開きます。

![管理アプリ](media/sample-crisis-communication-app/09-Admin-App.png)

管理アプリケーションを使用すると、危機通信アプリ内のすべての情報をカスタマイズできます。また、付随するフローのキー設定も設定できます。

> [!NOTE]
> また、管理アプリを使用しない場合は、SharePoint リストを手動で編集して、これらの同じプロパティを編集することもできます。

### <a name="setup-key-parameters-under-admin-settings"></a>[管理者の設定] でキーパラメーターを設定する

アプリを初期化するには、 **[管理者の設定]** に移動して、必要なフィールドをすべて指定する必要があります。

すべてのフィールドを入力し、 **[保存]** を選択します。

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| 管理者の電子メール | AdminContactEmail | アプリケーションを管理している他のユーザーに通知するために使用します。 |
| ロゴの URL | Logo | 左上隅に表示されるアプリのロゴ。 |
| AAD グループ ID | AADGroupID | *新しい緊急時の通信に関するニュース*フローのユーザーへの通知を通じて、社内の更新に関する通知をエンドユーザーに送信するために使用されます。 |  
| アプリの URL | AppURL | [**詳細**を表示] を選択した後、[*新しい緊急通信のユーザーに通知] ニュースフローで*ユーザーをリダイレクトできるようにするためのアプリの場所。 | 
| Government の RSS フィード | GovernmentRSSFeed | アプリ内の世界のニュース機能を設定するために使用されます。 信頼できる発行元から従業員に追加情報を提供する場合に便利です。 |
| 通知方法 | PreferredSentNotification | *新しい緊急時通信ニュース*フローのユーザーへの通知によって、通知を送信するときにどの配布チャネルを使用する必要があるかを判断するために使用されます。 |
| 機能フラグ | Feature1.feature...8 | アプリケーション内の各機能を無効または有効にするために使用します。 |

#### <a name="finding-the-aad-of-your-distribution-group"></a>配布グループの AAD の検索
1. [Aad.portal.azure.com](https://aad.portal.azure.com)に移動します。
1. 左側のナビゲーションから **[Azure Active Directory]** を選択します。
1. **[グループ]** を選択します。
1. 配布グループを検索して選択します。
1. **[オブジェクト Id]** フィールドをコピーします。

    ![Azure での AAD ID の取得](media/sample-crisis-communication-app/11-AAD-Group-ID.png)

1. ID を管理アプリケーション内の**AAD グループ id**フィールドに貼り付けます。

### <a name="setup-emergency-contacts"></a>緊急時の連絡先の設定

1. **[会社の連絡先]** に移動します。
1. **[新しい連絡先の作成]** を選択します。
1. 連絡先の詳細を入力して、フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| 氏名 | FullName | 連絡先の名前。 |
| 電子メール | 電子メール | 連絡先に対して表示される電子メール。 |
| 国 | 国 | 連絡先の国。 これは連絡先をグループ化するために使用されます。そのため、国に意味がない場合は、このフィールドを他のグループ化に使用できます。 |
| コメント | コメント | 連絡先に関する追加情報を表示します。この連絡先にいつアクセスするかを説明するのに役立ちます。 |
| 非推奨 | 非推奨 | 既存の緊急連絡先を非表示にすることができます。 |

### <a name="setup-initial-company-news"></a>会社の最初のニュースをセットアップする

1. **[会社のニュース]** に移動します。
1. **新しい投稿を作成する**
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | 更新プログラムのタイトル。 |
| 詳細 | 詳細 | 完全な更新プログラム。 このフィールドでは HTML を使用できます。 |
| 宣伝文 | 宣伝文 | 更新に関する短いメッセージ。 これは、[*新しい緊急時の通信] ニュース*フローおよび更新プログラムのギャラリーでユーザーに通知するときに使用されます。 |
| 非推奨 | 非推奨 | 既存の投稿を非表示にすることができます。 |

### <a name="setup-helpful-tips"></a>便利なヒントを設定する

1. 役に**立つヒント**に移動します。
1. **[新しいヒント]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | 役に立つヒントのタイトル。 |
| リソース URL | ResourceURL | 追加の読み取り資料へのリンク。 (オプション) |
| サブタイトル | サブタイトル | ヒントのサブタイトル。 (オプション) |
| 説明 | 説明 | 役に立つヒントの詳しい説明。 |
| 非推奨 | 非推奨 | 役に立つヒントを非表示にすることができます。 |

### <a name="setup-links"></a>セットアップリンク

1. **リンク**に移動します。
1. **[新しいリンクの作成]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | リンクのテキスト。 |
| URL | URL | リンクの URL。 |
| 説明 | 説明 | リンクに関する追加情報。 (オプション) |
| 非推奨 | 非推奨 | リンクを非表示にすることができます。 |

### <a name="setup-faqs"></a>セットアップに関する Faq

1. **FAQ**に移動します。
1. **[新しい FAQ の作成]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | FAQ の質問。 |
| ランク | ランク | FAQ の順序。 |
| 受信 | 受信 | FAQ に対する回答 |
| 非推奨 | 非推奨 | FAQ を非表示にすることができます。 |

## <a name="test-and-share-the-app"></a>アプリをテストして共有する

すべてのデータを正常に設定したので、アプリをテストして動作することを確認できます。

1. [Power Apps](https://make.powerapps.com) にサインインします。
2. 左側のナビゲーションから **[アプリ]** を選択します。
3. アプリを再生するには、 **[危機通信]** を選択します。

アプリが正常にテストされると、社内のすべてのユーザーとアプリを共有できるようになります。

## <a name="import-and-set-up-the-notification-flow"></a>通知フローのインポートと設定

アプリは、新しい会社の更新が発生するたびに、フローを使用してエンドユーザーに通知を送信します。

### <a name="import-the-news-notification-flow"></a>ニュース通知フローをインポートする

1. [Flow.microsoft.com](https://flow.microsoft.com)に移動します。
1. 左側のナビゲーションから **[自分のフロー]** を選択します。
1. コマンドバーの **[インポート]** をクリックします。
1. GitHub リポジトリから**CrisisCommunicationNewsNotification**パッケージをアップロードします。

    ![CrisisCommunicationNewsNotification のアップロード](media/sample-crisis-communication-app/upload-news-notification.png)

1. 新しいフローの接続を追加するには、各接続の **[インポート中に選択]** リンクを選択し、次のように入力します。

    ![インポート時に選択](media/sample-crisis-communication-app/select-during-import.png)

1. 新しい接続を作成する必要がある場合は、まず、セットアップのインポート ウィンドウで **新規作成** を選択します。
1. コマンドバーの **[新しい接続]** を選択します。

    ![新しい接続を作成する](media/sample-crisis-communication-app/create-connection.png)

1. 接続の名前を検索します。たとえば、 **PowerApps Notification (プレビュー)** :

    ![通知](media/sample-crisis-communication-app/notifications.png)

1. 適切な接続を選択します。
1. **PowerApps の通知 (プレビュー)** への接続を作成している場合は、次のダイアログが表示されます。

    ![通知ダイアログ](media/sample-crisis-communication-app/notifications-dialog.png)

1. ID を取得するには、**アプリ**の一覧に移動します。
1. **危機通信**アプリのその**他のコマンド**(...) を選択し、[詳細] を選択します。

    ![その他のコマンド](media/sample-crisis-communication-app/06-App-Details.png)

1. **アプリ ID**をコピーします。

    ![アプリ ID](media/sample-crisis-communication-app/07-App-ID.png)

1. [接続の作成] ダイアログに**アプリ ID**を貼り付け、 **[作成]** を選択します。

    ![アプリ ID の貼り付け](media/sample-crisis-communication-app/target-app-id.png)

1. 新しい接続を作成したら、 **[セットアップのインポート]** パネルに戻り、 **[更新リスト]** ボタンを選択します。
1. 新しい接続が表示されます。これを選択して **[保存]** を選択できます。
1. すべての接続の追加が完了したら、 **[インポート]** を選択します。

    ![インポートの接続](media/sample-crisis-communication-app/imported-connections.png)

### <a name="edit-the-news-notification-flow"></a>ニュース通知フローを編集する

1. インポートが完了したら、 **[マイフロー**] に戻ります。
1. 新しくインポートされたフローを選択して、**新しい危機的通信ニュースをユーザーに通知**します。
1. コマンドバーの **[編集]** を選択します。
1. **新しい項目が投稿されたときに**呼び出されるカードを開きます。
1. **サイトアドレス**を SharePoint サイトの名前に変更します。
1. **リスト名**を**CI_CompanyNews**に変更します。
1. 「 **Get the admin config settings**」という名前のカードを開きます。
1. **サイトアドレス**を SharePoint サイトの名前に変更します。
1. **リスト名**を**CI_configAdminSetup**に変更します。
1. [**変数の初期化-詳細**を表示] という名前のカードを開きます。
1. ネイティブ言語で**値**を "Read more" に変更します。

    ![フローの設定](media/sample-crisis-communication-app/flow-options.png)

1. **[保存]** を選択して変更をコミットします。

> [!NOTE]
> 接続のいずれかがまだ承認されていない場合、エラーが表示されることがあります。
この問題が発生した場合は、許可されていない接続と再認証を使用してカードを開いてください。

### <a name="test-the-news-notification-flow"></a>ニュース通知フローをテストする

ニュース通知フローをテストするには、管理者アプリに戻り、社内の新しい更新プログラムを作成します。
後で、配布リスト内のすべてのユーザーが、優先する通知設定によって更新プログラムを受信します。

> [!NOTE]
> エラーが発生した場合は、管理アプリ内の管理者設定に配布グループの ID が正常に入力されていることを確認してください。

## <a name="monitor-office-absences-with-power-bi"></a>Power BI でオフィスの休暇を監視する

アプリを展開した後、さまざまな理由 (病気や自宅での作業など) のために、ユーザーがオフィスの外に出ることを通知することができるようになりました。 Power BI レポートを使用して、それらのユーザーの数と場所を追跡できるようになりました。

開始するには、ダウンロードした[アセットパッケージ](#prerequisites)から使用可能なサンプルレポートの "プレゼンス状態レポート .pbix" を使用します。
必要に応じて、 [Power BI Desktop](https://powerbi.microsoft.com/downloads)をダウンロードします。 また、前に作成した**CI_Employee Status** SharePoint リストからいくつかの情報が必要になるので、先に説明します。 サイトの一覧を開き、[設定] アイコンの下の [リストの設定] を選択します。

![従業員の状態の一覧の設定](media/sample-crisis-communication-app/001-SharePointList-ListSettings-nolines.PNG)

ブラウザーのアドレスバーで、**サイト名**と**リスト id**をメモしておきます。

![従業員の状態の一覧とサイト Id](media/sample-crisis-communication-app/002-SharePointList-AddressAndId-nolines.PNG)

この時点で、Power BI レポートを開く準備が整いました。Power BI を起動して、**プレゼンス状態レポート .pbix**ファイルを開きます。 **CI_Employee 状態**データソースの右側にマウスポインターを移動し、省略記号が表示されていることを確認し、[クエリの編集] オプションを選択します。

![クエリの編集](media/sample-crisis-communication-app/003-PowerBI-EditQuery-nolines.PNG)

Power Query エディターが開いたら、 **CI_Employee の状態**データソースを右クリックし、**詳細エディター**を選択します。

![Power Query 詳細エディター](media/sample-crisis-communication-app/004-PowerQuery-AdvancedEditor-nolines.PNG)

ここでは、SharePoint リストのサイト名とリスト id を使用します。テーブル内の新しい SharePoint サイトをコピーし、GUID が強調表示されている3つの場所のリスト id を使用して、 **[完了]** を選択します。

![詳細エディター更新プログラムの Power Query](media/sample-crisis-communication-app/005-PowerQuery-AdvancedEditorUpdates-nolines.PNG)

SharePoint リストからデータをプルするようにレポートを更新するには、 **[閉じる & 適用]** を選択します。

![Power Query 閉じて適用](media/sample-crisis-communication-app/006-PowerQuery-CloseAndApply-nolines.PNG)

現在の日における office の休暇に関する地理情報と、数日にわたるそのような休暇の傾向を示す Power BI レポートが作成されました。 これで、組織内の他の担当者が表示できるようにレポートを発行できるようになりました。

![レポートのパブリッシュ Power BI](media/sample-crisis-communication-app/007-PowerBI-Publish-nolines.PNG)

## <a name="integrate-your-app-into-teams"></a>アプリをチームに統合する

すべてのユーザーと共有されている機能を持つアプリが完成したので、チームを使用してアプリをデプロイし、問題に対応するために、Microsoft チーム内で危機管理チームを作成できます。

### <a name="deploy-the-app-to-the-app-bar"></a>アプリをアプリバーにデプロイする

チーム管理者は、Teams アプリバー内のすべてのユーザーにアプリをプッシュできます。

![チーム内のアプリ](media/sample-crisis-communication-app/19-App-in-Teams.png)

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションから **[アプリ]** を選択します。
1. **危機通信**アプリの [.. **.** ] メニューを選択します。
1. **[チームに追加]** を選択します。

    ![チームに追加](media/sample-crisis-communication-app/24-Add-to-Teams.png)

1. **[アプリのダウンロード]** を選択します。

    ![アプリのダウンロード](media/sample-crisis-communication-app/25-Download-App.png)

1. **チーム**を開く
1. 左側のアプリバーから **[アプリ]** に移動します。
1. **[カスタムアプリのアップロード]** を選択します。
1. チーム管理者の場合は、テナント全体のアプリをアップロードする機能が表示されます。 **[Contoso のアップロード]** を選択します。

    ![アップロード](media/sample-crisis-communication-app/26-Upload-for-Contoso.png)

1. Power Apps からダウンロードしたファイルをアップロードします。
1. [チーム管理センター](https://admin.teams.microsoft.com/dashboard)に移動します。
1. 左側のナビゲーションで、 **[チームアプリ]** の **[セットアップポリシー]** を選択します。

    ![アプリセットアップポリシー](media/sample-crisis-communication-app/27-Setup-Policies.png)

1. **[グローバル (組織全体のセットアップ)]** を選択します。
1. **[アプリの追加]** を選択します。

    ![アプリの追加](media/sample-crisis-communication-app/28-Add-App.png)

1. アップロードした**危機情報**アプリを検索して選択します。

    ![ピン留めされたアプリの追加](media/sample-crisis-communication-app/29-Add-Pinned-App.png)

1. **[追加]** を選択します。
1. **[保存]** を選択します。

> [!NOTE]
> アプリがアプリバーに自動的にピン留めされることをユーザーが確認するまでに、最大で24時間かかることがあります。

### <a name="create-a-central-crisis-management-teams-team"></a>集中型の危機管理チームチームを作成する

危機的な応答を調整するには、危機管理チームのための集中チームチームを作成し、関連するすべての情報を設定する必要があります。

1. [チーム] に移動します。
1. 左側のアプリバーから **[チーム]** を選択します。
1. [**参加] または [チームの作成**] を選択します。
1. **[チームの作成]** を選択し、残りの手順を完了します。

    ![チームの作成](media/sample-crisis-communication-app/23-Create-Team.png)

チームが正常に作成されたら、関連する情報をタブとしてピン留めできます。 たとえば、危機管理管理者アプリまたは Power BI レポートをチームにピン留めすることができます。 管理アプリをタブとして追加するには、次のようにします。

1. [ **+** ] ボタンを選択します。
1. **[Power Apps]** を検索して選択します。
1. [**緊急情報] 管理者**を検索して選択します。

    ![アプリのピン留め](media/sample-crisis-communication-app/32-Pin-Teams-app.png)

1. **[保存]** を選択します。

Power BI レポートを追加するには:

1. [ **+** ] ボタンを選択します。
1. **Power BI**を検索して選択します。
1. Power BI レポートを検索して選択します。
1. **[保存]** を選択します。

## <a name="next-steps"></a>次のステップ:
- [数式のリファレンス](https://docs.microsoft.com/powerapps/maker/canvas-apps/formula-reference)
- [コントロールのリファレンス](https://docs.microsoft.com/powerapps/maker/canvas-apps/reference-properties)
