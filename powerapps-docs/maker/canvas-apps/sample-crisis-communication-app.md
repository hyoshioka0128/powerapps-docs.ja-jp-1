---
title: 危機通信アプリ-サンプルテンプレート |Microsoft Docs
description: Power Apps の危機通信のサンプルテンプレートについて説明します。
author: matthewbolanos
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/31/2020
ms.author: mabolan
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fedcec7c8f3f093bf59b3ef607cbe4fbeea6ac54
ms.sourcegitcommit: f5d15c973b2a129a0cc29a74cf8eaf6b24fbf36d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2020
ms.locfileid: "80516693"
---
# <a name="set-up-and-learn-about-the-crisis-communication-sample-template-in-power-apps"></a>Power Apps での危機通信のサンプルテンプレートのセットアップと学習

危機通信アプリは、ユーザーにとって、危機に関する情報をユーザーに接続するための使いやすいエクスペリエンスを提供します。 社内の社内ニュースをすばやく更新し、よく寄せられる質問への回答を取得し、リンクや緊急連絡先などの重要な情報にアクセスします。 このアプリをお使いの環境に合わせるには、少し設定が必要です。

このチュートリアルでは、次の方法について説明します。

- データの場所を作成します。
- 危機通信アプリとその管理アプリの両方をインポートします。
- アプリのコンテンツを作成します。
- フローをインポートして、ユーザーに通知を送信します。
- 集中管理されたチームチームを作成して、データを集計し、問題に効果的に対応します。

これらの手順の推定所要時間: **20&ndash;25 分**。

> [!NOTE]
> 危機通信のサンプルテンプレートは、Power Apps の米国政府および省電力の米国政府計画でも利用できます。 Power Apps のサービス Url と米国政府のバージョンの自動化は、商用バージョンとは異なります。 詳細情報: [Power Apps の米国政府サービスの url](https://docs.microsoft.com/power-platform/admin/powerapps-us-government#power-apps-us-government-service-urls)と、[米国政府サービスの url の自動化](https://docs.microsoft.com/power-automate/us-govt#power-automate-us-government-service-urls)

## <a name="demo-crisis-communication-app"></a>デモ: 危機通信アプリ

危機通信ソリューションの使用方法をご覧ください。

> [!VIDEO https://www.youtube.com/embed/23SypLXiOTw]

## <a name="prerequisites"></a>前提条件

- Power Apps 用の[サインアップ](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) 。
- 有効な SharePoint Online ライセンスと、リストを作成するためのアクセス許可が必要です。
- アプリのデータを格納できるパブリック SharePoint サイトが必要です。
- [Aka.ms/CrisisCommunicationSolution](https://aka.ms/CrisisCommunicationSolution)から資産をダウンロードします。

> [!IMPORTANT]
> 危機通信アプリに関連するフィードバックまたは問題については、次のリンクを参照してください。
> - **[皆様](https://aka.ms/crisis-communication-feedback)**
> - **[問題](https://aka.ms/crisis-communication-issues)**

## <a name="demo-build-and-deploy-the-crisis-communication-app"></a>デモ: 危機通信アプリを構築してデプロイする

「危機的通信アプリを構築してデプロイする方法」をご覧ください。

> [!VIDEO https://www.youtube.com/embed/Wykrwf9dZ-Y]

## <a name="create-a-home-for-your-data"></a>データのホームを作成する

アプリのデータは SharePoint リストに格納されるため、最初の手順は新しい SharePoint サイトを作成することです。

### <a name="create-a-sharepoint-site"></a>SharePoint サイトの作成

1. [Office online](https://www.office.com)にサインインし、 **[SharePoint]** を選択します。
1. **[サイトの作成]** を選択します。

    ![SharePoint サイトのサンプル](media/sample-crisis-communication-app/01-Create-Site.png)

1. **[チームサイト]** を選択します。

    ![チームサイト](media/sample-crisis-communication-app/02-Team-Site.png)

1. サイトの名前と説明を入力します。
1. 会社のすべてのユーザーが必要な情報を取得できるように、**プライバシー設定**を**パブリック**に設定します。

    ![サイトの設定](media/sample-crisis-communication-app/03-Privacy-Settings.png)

1. **[次へ]** を選択します。
1. サイトの所有者を追加します (省略可能)。
1. **[完了]** を選択します。

### <a name="create-sharepoint-lists-for-the-app"></a>アプリの SharePoint リストを作成する

アプリでは、複数のリストを使用してデータを格納します。 ダウンロードした[アセットパッケージ](#prerequisites)から入手できる DeploySPLists flow を使用すると、これらのリストを自動的に作成できます。

#### <a name="import-the-sharepoint-list-deployment-flow"></a>SharePoint リストのデプロイフローをインポートする

1. [Flow.microsoft.com](https://flow.microsoft.com)にアクセスします。
1. 左側のナビゲーションウィンドウで **[マイフロー]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. DeploySPLists をアップロードし**ます。**<!--edit to the file name okay, here and in the following instances?--> GitHub リポジトリからのパッケージ。

    ![パッケージのインポート](media/sample-crisis-communication-app/import-package.png)

1. **[インポート時に選択]** リンクを選択し、フォームに入力して、新しいフローの SharePoint 接続を追加します。

    ![［設定のインポート］](media/sample-crisis-communication-app/import-settings.png)

1. 新しい SharePoint 接続を作成する必要がある場合は、セットアップの **[インポート]** ウィンドウで **[新規作成]** を選択します。
1. コマンドバーの **[新しい接続]** を選択します。

    ![新しい接続を作成する](media/sample-crisis-communication-app/create-connection.png)

1. *SharePoint*などの接続の名前を検索します。
1. 作成した接続を選択します。<!--edit okay?-->
1. **[保存]** を選択します。
1. **[インポート]** を選択します。

#### <a name="edit-the-sharepoint-list-deployment-flow"></a>SharePoint リストのデプロイフローを編集する

1. インポートが完了したら、 **[マイフロー** ] に移動し、フローの一覧を更新します。
1. 新しくインポートされたフロー **DeploySPLists**を選択します。
1. コマンドバーの **[編集]** を選択します。
1. [**変数–リストカードのターゲットサイト] を**開きます。
1. **[値]** には、SharePoint サイトの名前を入力します。
1. [**変数-アプリ名カード]** を開きます。
1. **[値]** に、アプリの名前を入力します。既定では、名前は "**危機通信**" になります。

    ![フローパラメーター](media/sample-crisis-communication-app/04-Flow-Settings.png)

1. **[保存]** を選択します。

#### <a name="run-the-sharepoint-list-deployment-flow"></a>SharePoint リスト配置フローの実行

1. **DeploySPLists** flow の詳細画面に戻ります。
1. コマンドバーの **[実行]** を選択します。
1. **[続行]** を選択し、 **[フローの実行]** を選択します。

    ![サインインしてフローを実行する](media/sample-crisis-communication-app/sign-in-flow.png)

    ![フローを実行する](media/sample-crisis-communication-app/run-flow.png)

> [!NOTE]
> ロケーションサービスが必要であることを示すエラーが表示される場合があります。
この問題が発生した場合は、ロケーションサービスへのアクセスを許可します。<!--edit okay? I wasn't sure what this meant.--> 電源をオンにしてページを更新してから、再試行してください。

このフローでは、SharePoint サイトに次の SharePoint リストが作成されます。<!--general note; You don't need to introduce tables or graphics with colons, only lists.-->

| **タイトルの表示**| **目的** | **説明** |
|-|-|-|
| CI_LogosAssets| ロゴやその他の画像をアプリから参照する場合。 ロゴは、直接リンクまたは使用するロゴの ID 番号を使用して、Power Apps で参照されます。 | *[App Name]* アプリの関連するロゴとその他のイメージアセット用のライブラリ。 |
| CI_configAdminSetup | アプリの管理者による機能の構成に使用されます。<br>**注**: この一覧は、管理者ではないすべてのメンバーに対して読み取り専用である必要があります。 | *[App Name]* アプリの管理者構成の一覧。
| CI_Contacts | 既定の連絡先のコンテンツタイプを使用して、連絡先に関する情報をキャプチャします。 (People 選択は含まれていないため、この一覧は手動で管理する必要がある場合があります。<!--edit okay?--> データが最新の状態であることを確認してください。)<br>**注**: これは、リスト内の既定のコンテンツタイプであるグローバル連絡先リストの種類によって異なります。 | *[App Name]* アプリの連絡先リスト。|
| CI_CompanyNews | 会社の**ニュース**項目のコレクション。 | *[アプリ名]* アプリに表示されるニュース項目を管理するための一覧。 **非推奨**の列を使用して、アプリビューからニュース項目を削除できます。<!--edit okay, here and below? You use this pattern ("remove ___ from the app views") in the "Helpful tips" description, and it seems a bit more descriptive than "filter ___ out of the app".-->。レコードとして保持します。 | 
| CI_FAQ  | よく寄せられる質問。 | *[App Name]* アプリに関してよく寄せられる質問の一覧です。 **[非推奨]** 列を使用して、アプリビューから FAQ 項目を削除し、レコードとして保持することができます。 |
| CI_UsefulLinks<!--edit okay? The sharepoint-lists.png screenshot later in this article shows it as "Usefulinks," which probably isn't correct either.--> | 役に立つハイパーリンクの一覧。 | *[App Name]* アプリの便利なハイパーリンクの一覧。 **非推奨**の列を使用すると、アプリビューからハイパーリンク項目を削除し、レコードとして保持することができます。 |
| CI_Employee | 現在の従業員のプレゼンス状態を追跡しています。 例:**自宅**、**病欠**、**欠勤**、**休暇**中の仕事。  **注**:**作業**中の状態は想定されており、リストオプションには含まれていません。 | <!--Please check the following edit carefully. This cell was duplicated by mistake from the previous row. Does the note about the "Deprecated" column apply here?-->*[App Name]* アプリの従業員プレゼンスの状態を示すメッセージの一覧。 **非推奨**の列を使用して、アプリビューからステータスメッセージを削除し、レコードとして保持することができます。 |
| CI_HelpfulTips             | ユーザーが自分の同僚に貢献している便利なヒント。 | *[App Name]* アプリの共有ヒントを管理するための一覧です。 **非推奨**の列を使用して、アプリビューからヒントを削除しながら、レコードとして保持することができます。  |

> [!NOTE]
> - これらのすべてのリスト列は、依存関係と見なす必要があります。
    誤ったスキーマ変更からリストを保護します (たとえば、新しい列の追加は許可されますが、列を削除するとアプリが壊れる可能性があります)。
> - リスト項目を削除するときは注意が必要です。リスト項目を削除すると、履歴レコードが削除されます。 非推奨値の切り替えを有効にすることができます。 <!--Style Guide-->連絡先、ニュース、Faq、リンクからレコードを削除する**場合**は、 **[いいえ] から [はい]** にします。<!--Should this include status messages too?-->

## <a name="import-and-set-up-the-crisis-communication-app"></a>危機通信アプリをインポートしてセットアップする

すべての SharePoint リストが作成されたら、アプリをインポートして新しいデータソースに接続できます。

> [!NOTE]
> 管理アプリを使用しない場合は、SharePoint リストを手動で編集することで、これらの同じプロパティを編集できます。

### <a name="import-the-app"></a>アプリをインポートする

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションウィンドウで **[アプリ]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. GitHub リポジトリから**CrisisCommunication**ファイルをアップロードします。

    > [!NOTE]
    > テナントが GCC 環境にある場合は、 **CrisisCommunicationGCC**をアップロードします。

    ![アプリパッケージをインポートする](media/sample-crisis-communication-app/31-Import-App.png)

1. **[インポート時に選択]** ハイパーリンクを使用して適切な接続を選択することで、 **Microsoft Teams 接続**と**Office 365 ユーザー接続**のセットアップのインポートを完了します。 まだ存在しない場合は、[新しい接続](add-data-connection.md)を作成する必要があります。
1. **[インポート]** を選択します。

### <a name="update-the-sharepoint-connections"></a>SharePoint 接続を更新する

1. **アプリ**の一覧に戻ります。
1. **危機通信**アプリの [**その他のコマンド**(...)] を選択します。
1. コンテキストメニューの **[編集]** を選択します。

    ![アプリを編集する](media/sample-crisis-communication-app/05-Edit-App.png)

1. サインインするか、必要な接続を作成して、 **[許可]** を選択します。

1. 左側のウィンドウでデータソースに移動します。

    ![[データ ソース]](media/sample-crisis-communication-app/data-sources.png)

1. アプリ内の既存の SharePoint リストを削除する<!--Alternatively, this could be "Right-click the name of each existing SharePoint list, and then select **Remove**" if that's how the context menu works here. I think the graphic will be clear enough for the reader, though.-->は、現在の SharePoint サイトを指していないためです。

    ![データソースの削除](media/sample-crisis-communication-app/remove-data-source.png)

1. 独自の SharePoint サイトからリストを追加します。 検索バーで**SharePoint**を検索して開始します。

    ![SharePoint の検索](media/sample-crisis-communication-app/sharepoint.png)

1. **[SharePoint]** を選択し、接続を選択します。

    ![SharePoint 接続](media/sample-crisis-communication-app/sharepoint-connection.png)

1. SharePoint サイトの URL をコピーし、テキスト フィールドに貼り付けて、**接続** を選択します。

    ![SharePoint サイトの URL](media/sample-crisis-communication-app/site-url.png)

1. SharePoint のリストとライブラリをすべて選択し、 **[接続]** を選択します。

    ![SharePoint リストに接続する](media/sample-crisis-communication-app/sharepoint-lists.png)

1. **[保存]** を選択し、 **[発行]** を選択します。

### <a name="optional-enable-location-updates"></a>省略可能: 場所の更新を有効にする

このアプリを使用すると、ユーザーが状態を設定するたびにユーザーの場所を記録し、SharePoint サイトに保存することができます。 危機管理チームは、このデータを Power BI レポートで表示できます。

> [!NOTE]
> 位置情報の更新を有効にすることは任意です。 ユーザーの場所を追跡しない場合は、このセクションをスキップできます。

**位置情報の更新を有効にするには**

1. **BtnDateRange**コントロールを検索します。
1. 数式バーで、 **btnDateRange**コントロールの**onselect**プロパティを開きます。
1. 次のスニペットをコピーして、 **Onselect**プロパティの数式バーに貼り付けます。

    > [!NOTE]
    > 次のスニペットは、2020.03.16 よりも前のバージョンのソリューションを使用することを目的としています。


    ```
        UpdateContext({locSaveDates: true});
    // Store the output properties of the calendar in static variables and collections.
    ClearCollect(submittedDates,Sort(Filter(selectedDates,ComponentId=CalendarComponent.Id),Date,Ascending));
    Set(varStartDate,First(submittedDates).Date);
    Set(varEndDate,First(Sort(submittedDates,Date,Descending)).Date);
    // Create a new record for work status for each date selected in the date range.
    ForAll(
        Filter(
            RenameColumns(submittedDates,"Date","DisplayDate"),
            ComponentId=CalendarComponent.Id,
            !(DisplayDate in colDates.Date)
        ),
        Patch('CI_Employee Status',Defaults('CI_Employee Status'),
            {
                Title: varUser.userPrincipalName,
                Date: DisplayDate,
                Notes: "",
                PresenceStatus: LookUp(colWorkStatus,Value=WorkStatusComponent.Selected.Value)
                
                // To implement location, add a comma to the line above and uncomment the lines below for latitude and longitude.
                // Latitude: Text(Location.Latitude),
                // Longitude: Text(Location.Longitude)
            }
        )
    );
        // Update existing dates with the new status.
        ForAll(
            AddColumns(
                Filter(
                    RenameColumns(submittedDates,"Date","DisplayDate"),
                    ComponentId=CalendarComponent.Id,
                    DisplayDate in colDates.Date
                ),
                
                // Get the current record for each existing date.
                "LookUpId",LookUp(RenameColumns(colDates,"ID","DateId"),And(Title=varUser.userPrincipalName,Date=DisplayDate)).DateId
            ),
            Patch('CI_Employee Status',LookUp('CI_Employee Status',ID=LookUpId),
                {
                    PresenceStatus: LookUp(colWorkStatus,Value=WorkStatusComponent.Selected.Value)
                }
            )
        );
        If(
            IsEmpty(Errors('CI_Employee Status')),
            
            // Update the list of work status for the logged-in user.
            ClearCollect(colDates,Filter('CI_Employee Status',Title=varUser.userPrincipalName));
            // Send an email receipt to the logged-in user.
            UpdateContext(
                {
                    locReceiptSuccess: 
                    Office365Outlook.SendEmailV2(
                        // To: send an email to oneself
                        varUser.mail,
                        // Subject
                        Proper(WorkStatusComponent.Selected.Value) & ": " & varStartDate & If(varStartDate<>varEndDate," - " & varEndDate),
                        // Body
                        WorkStatusComponent.Selected.DateRangeReceipt & ": " &
                        // Create a bulleted list of dates
                        "<ul>" & 
                            Concat(submittedDates,"<li>" & Date & Char(10)) &
                        "</ul>"
                    )
                }
            );
            If(
                locReceiptSuccess,
                Notify("You successfully submitted your work status. An email has been sent to you with a summary.",NotificationType.Success,3000),
                Notify("There was an error sending an email summary, but you successfully submitted your work status.",NotificationType.Success,3000);
            );
            
            Navigate('Share to Team Screen',LookUp(colStyles,Key="navigation_transition").Value),
            
            // Case: Error submitting work status
            Notify(varString.WorkStatusError,NotificationType.Warning)
        );
        UpdateContext({locSaveDates: false})
    ```

### <a name="optional-add-additional-work-status-messages"></a>省略可能: 作業ステータスメッセージを追加する

作業状態をさらに追加する場合<!--Interesting fact: there is no plural of "status."--> 次の手順を実行すると、自宅や外出先から**のメッセージ**を**処理**できます。 まず、SharePoint サイトを更新する必要があります。

1. SharePoint サイトに戻り、 **[サイトコンテンツ]** を選択します。
1. **[CI_Employee の状態]** を選択します。
1. **[Presencestatus]** 列が表示されていない場合は、 **[列の追加]** を選択します。
1. **[列の表示/非表示]** を選択します。

    ![列の表示/非表示](media/sample-crisis-communication-app/36-hide-show-columns.png)

1. [選択]<!--edit okay? I didn't know what "Check" meant here.--> **Presencestatus**。
1. **[適用]** を選択します。
1. **[Presencestatus]** 列を選択します。

    ![[PresenceStatus] 列を選択します。](media/sample-crisis-communication-app/37-show-presence.png)

1. **[列の設定]** を選択し、 **[編集]** を選択します。

    ![PresenceStatus 列の編集](media/sample-crisis-communication-app/38-edit-column.png)

1. 追加の作業ステータスメッセージを **[選択肢]** フィールドに追加します。

> [!NOTE]
> 新しい選択肢の名前を記録します。これらは、後続の手順で使用します。

次に、新しい作業ステータスメッセージを表示するために、アプリ自体にいくつかの調整を行う必要があります。

1. Power Apps Studio でアプリを開く<!--edit okay?-->。
1. **[作業状態]** 画面を選択します。
1. 数式バーを**Onvisible**関数に設定します。

    ![プレゼンスの表示](media/sample-crisis-communication-app/39-onvisible-for-screen.png)

1. 次のテンプレートを編集し、値を独自の値に置き換えます。
<!--I took the liberty of editing these strings to use contractions, which is Microsoft style now.-->
    ```
        ,"<Name of option in SharePoint list; case sensitive>",
        Table(
            {
                Icon: <Image file>,
                DateRangeQuestion: "Select the dates you'll be <Name of status>.",
                DateRangeReceipt: "You're currently <Name of status>.",
                ShareToTeamEmail: "I'll be <Name of status> on these dates",
                AutoReplyMessage: "I'll be <Name of status> on these dates"
            }
        )
    ```

1. `/* TEMPLATE FOR ADDITIONAL WORK STATUS OPTIONS */` 文字列をテンプレートに置き換えます。
1. **[保存]** を選択し、 **[発行]** を選択します。

### <a name="update-the-request-for-help-flow"></a>ヘルプフローの要求を更新する

このフローは、補助カードを集中チームチームに送信し、支援を要請します。

![ヘルプの要求](media/sample-crisis-communication-app/21-Request-Help.png)

次の手順を完了する前に、チームで危機管理チームを作成してください。 チームを作成したら、その ID を取得してフローに取り込むことができます。 チームチームの作成に関する詳細情報:[一元的な危機管理チームチームの作成](#create-a-central-crisis-management-teams-team)

1. すべてのヘルプ要求を投稿するチームチャネルにアクセスします。
1. チャネルの [**その他のオプション**(...)] を選択します。
1. **[チャネルへのリンクの取得]** を選択します。

    ![チャネルへのリンクを取得する](media/sample-crisis-communication-app/17-Get-link-to-channel.png)

1. リンクをコピーし、テキストエディターに貼り付けます。

    ![チームリンクをコピーする](media/sample-crisis-communication-app/18-Copy-link.png)

1. **チーム ID**を抽出します。これは `groupId=` の後、`&tenantId=`する前のものです。 <br> たとえば、次の URL では、チャネル ID はです。<!--suggest using a line break here and in the next step so you don't have to include any closing punctuation.--> <br>`8bc7c0c2-0d4c-4fb8-af99-32da74c9237b`
   
   `https://teams.microsoft.com/l/channel/19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2/General?groupId=8bc7c0c2-0d4c-4fb8-af99-32da74c9237b&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47`
   
1. **チャネル ID**を抽出します。これは `https://teams.microsoft.com/l/channel/` の後、`/General`する前のものです。 <br> たとえば、次の URL では、チャネル ID はです。<br> `19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2`
   
   `https://teams.microsoft.com/l/channel/19%3ab2fa9fc20f3042a9b63fc5890e1813f8%40thread.tacv2/General?groupId=8bc7c0c2-0d4c-4fb8-af99-32da74c9237b&tenantId=72f988bf-86f1-41af-91ab-2d7cd011db47`、

1. [Flow.microsoft.com](https://flow.microsoft.com)にアクセスします。

1. 左側のナビゲーションウィンドウで **[マイフロー]** を選択します。

1. **その他のコマンド**を選択する (...) **CrisisCommunication**の場合は、 **[編集]** を選択します。

    ![ヘルプフローの要求の編集](media/sample-crisis-communication-app/20-Edit-Flow.png)

1. **チーム Id**カードを開きます。

1. チーム ID を **[値]** フィールドに貼り付けます。

1. **チャンネル ID**カードを開きます。

1. チャンネル ID を **[値]** フィールドに貼り付けます。

    ![チーム Id とチャネル Id を設定する](media/sample-crisis-communication-app/22-Set-Team-IDs.png)

1. **[Get time]** アクションまで下にスクロールし、選択したソースとターゲットの時刻を使用して、 **[タイムゾーンの変換]** アクションを更新します。

    ![タイムゾーン設定の変換](media/sample-crisis-communication-app/convert-time-zone.png)

## <a name="optional-configure-a-shared-inbox"></a>省略可能: 共有受信トレイの構成<a name="optional-configure-shared-inbox"></a>

CrisisCommunication フローは、要求をチームに送信する前に、受信トレイから要求をプルします。 要求メールを共有の受信トレイに送信する場合は、次の手順に従います。

> [!NOTE]
> 要求メールを共有の受信トレイに送信しない場合は、このセクションをスキップできます。

1. 編集モードで**CrisisCommunication**フローを開きます。
1. [**その他のコマンド**(...)] を選択**すると、電子メールが V3 に到着**します。
1. **[削除]** を選択します。

     ![コネクタを削除します。](media/sample-crisis-communication-app/33-delete-connector.png)

1. **共有メールボックス (V2) に新しい電子メールが届いたとき**に検索して選択します。
1. **[メールボックスアドレス]** に共有受信トレイのアドレスを入力します。
1. **コメント**カードを開きます。
1. [**値**に**動的な値を追加する**] を選択します。
1. **[本文]** を検索して選択します。

     ![本文の選択](media/sample-crisis-communication-app/35-body.png)

1. **Get user profile card (V2)** カードを開きます。
1. **[動的な値の追加]** を選択します。
1. を検索し、 **[開始]** を選択します。

     ![Select From](media/sample-crisis-communication-app/34-from.png)

## <a name="import-and-set-up-the-admin-app"></a>管理アプリをインポートしてセットアップする

インポートしたアプリを管理するには、管理アプリについても同じ手順を繰り返します。

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションウィンドウで **[アプリ]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. GitHub リポジトリから**CrisisCommunicationAdmin**ファイルをアップロードします。

    ![管理アプリケーションパッケージをインポートする](media/sample-crisis-communication-app/import-app.png)

1. **[インポート]** を選択します。

### <a name="update-sharepoint-connections-for-the-admin-app"></a>管理アプリの SharePoint 接続を更新する

1. **アプリ**の一覧に戻ります。
1. [**緊急通信の管理] アプリ**の [**その他のコマンド**(...)] を選択します。
1. コンテキストメニューの **[編集]** を選択します。

    ![管理アプリの編集](media/sample-crisis-communication-app/08-Edit-Admin-App.png)

1. サインインするか、必要な接続を作成して、 **[許可]** を選択します。

1. 左側のウィンドウでデータソースに移動します。

    ![[データ ソース]](media/sample-crisis-communication-app/data-sources.png)

1. 現在の SharePoint サイトを指していないため、アプリ内の既存の SharePoint リストを削除します。<!--Please see previous editor's note.-->

    ![データソースの削除](media/sample-crisis-communication-app/remove-data-source.png)

1. 独自の SharePoint サイトからリストを追加します。 検索バーで**SharePoint**を検索して開始します。

    ![SharePoint の検索](media/sample-crisis-communication-app/sharepoint.png)

1. **[SharePoint]** を選択し、接続を選択します。

    ![SharePoint 接続](media/sample-crisis-communication-app/sharepoint-connection.png)

1. SharePoint サイトの URL をコピーし、テキスト フィールドに貼り付けて、**接続** を選択します。

    ![SharePoint サイトの URL](media/sample-crisis-communication-app/site-url.png)

1. すべての SharePoint リストとライブラリ を選択し、**接続** を選択します。

    ![SharePoint リストに接続する](media/sample-crisis-communication-app/sharepoint-lists.png)

1. **[保存]** を選択し、 **[発行]** を選択します。

## <a name="create-initial-content-for-the-app"></a>アプリの初期コンテンツを作成する

この時点で、危機通信アプリとその管理アプリの両方が正常にインポートされました。 これで、初期コンテンツの作成を開始できます。 開始するには、危機通信管理アプリを開きます。

GCC 環境を使用している場合は、GCC モードを有効にする必要があります。 詳細については、「 [GCC 環境用にモバイルクライアントを構成する方法」を](https://docs.microsoft.com/power-platform/admin/powerapps-us-government#configure-mobile-clients)参照してください。

![危機通信管理アプリ](media/sample-crisis-communication-app/09-Admin-App.png)

管理アプリを使用して、危機通信アプリ内のすべての情報をカスタマイズしたり、付随するフローのキー設定を構成したりすることができます。

> [!NOTE]
> &mdash;管理者アプリを使用しない場合は、SharePoint リストを手動で編集して、これらのプロパティを編集することができます。

### <a name="set-up-key-parameters-under-admin-settings"></a>[管理者の設定] でキーパラメーターを設定する

アプリを初期化するには、 **[管理者の設定]** に移動して、必要なフィールドをすべて指定する必要があります。

次の表に示すようにすべてのフィールドを入力し、 **[保存]** を選択します。

| **フィールド名** | **SharePoint での論理名** | **目的** | **例** |
|-|-|-|-|
| 管理者の電子メール | AdminContactEmail | ここで、電子メール要求が送信されます。 ユーザーの電子メールアドレスに設定する必要があります。 別の受信トレイに通知を送信する場合は、この記事の「[オプションの共有受信トレイの構成](#optional-configure-shared-inbox)」を参照してください。 | admin@contoso.com |
| ロゴの URL | Logo | 左上隅に表示されるアプリのロゴ。 | https://contoso.com/logo.png |
| AAD グループ ID | AADGroupID | **新しい緊急時の通信ニュースをユーザーに通知**することで、社内の更新に関する通知をユーザーに送信するために使用されます。<!--Can you rename this flow to "Notify users of new crisis communication news"? Or maybe even "Notify users of breaking news about the crisis"?--> フロー. 次の手順に従って、グループの Azure Active Directory (Azure AD) ID を取得します。 | c0ddf873-b4fe-4602-b3a9-502dd944c8d5 |
| アプリの URL | AppURL | ユーザーアプリの場所。 [**新しい危機通信のユーザーへの通知] ニュース**フローでは、 **[読み取り]** を選択した後にユーザーをリダイレクトできます。 | https://apps.preview.powerapps.com/play/<app URL>? tenantId =<tenant ID>
| Government の RSS フィード | GovernmentRSSFeed | アプリの世界のニュース機能を設定するために使用されます。 信頼できる発行元から従業員に追加情報を提供する場合に便利です。 | https://www.who.int/rss-feeds/news-english.xml |
| 通知方法 | PreferredSentNotification | **新しい緊急時通信ニュース**フローのユーザーへの通知によって、通知を送信するときにどの配布チャネルを使用する必要があるかを判断するために使用されます。 このフィールドは必須です。 | 電子メール、チームの通知、プッシュ通知 |
| 機能フラグ | Feature1.feature...8 | アプリケーションの各機能を無効または有効にするために使用します。 |  |

> [!NOTE]
> 現在 GCC では、チームの通知とプッシュ通知はサポートされていません。


#### <a name="finding-the-azure-ad-id-for-your-distribution-group"></a>配布グループの Azure AD ID を検索しています
<!--note from editor: The Cloud Style Guide says don't use "AAD" for "Azure AD."-->
1. [Aad.portal.azure.com](https://aad.portal.azure.com)にアクセスします。
1. 左側のナビゲーションウィンドウで **[Azure Active Directory]** を選択します。
1. **[グループ]** を選択します。
1. 配布グループを検索して選択します。
1. **[オブジェクト Id]** フィールドをコピーします。

    ![Azure AD ID を取得しています](media/sample-crisis-communication-app/11-AAD-Group-ID.png)

1. ID を管理アプリの**AAD グループ id**フィールドに貼り付けます。<!--Can you have this changed to "Azure AD group ID"? -->

### <a name="set-up-emergency-contacts"></a>緊急連絡先の設定

1. **[会社の連絡先]** にアクセスします。
1. **[新しい連絡先の作成]** を選択します。
1. 連絡先の詳細を使用してフォームを完成させます。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| 氏名 | FullName | 連絡先の名前。 |
| 電子メール | 電子メール | 連絡先に表示される電子メールアドレス。 |
| 国 | 国 | 連絡先の国。 このフィールドは、連絡先をグループ化するために使用されます。他の値を使用して、国に意味がない場合に、連絡先をグループ化することができます。 |
| コメント | コメント | 連絡先に関する追加情報を表示します。この連絡先にいつアクセスするかを説明するのに役立ちます。 |
| 非推奨 | 非推奨 | 既存の緊急連絡先を非表示にするには、を使用します。 |

### <a name="set-up-initial-company-news"></a>会社の最初のニュースを設定する

1. **[会社のニュース]** にアクセスします。
1. **[新しい投稿の作成]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | 更新プログラムのタイトル。 |
| 詳細 | 詳細 | 完全な更新プログラム。 このフィールドでは HTML を使用できます。 |
| 宣伝文 | 宣伝文 | 更新に関する短いメッセージ。 これは、[**新しい緊急時の通信] ニュース**フローおよび更新プログラムのギャラリーでユーザーに通知するために使用されます。 |
| 非推奨 | 非推奨 | 既存の投稿を非表示にするには、を使用します。 |

### <a name="set-up-helpful-tips"></a>役に立つヒントを設定する

1. 役に**立つヒント**を参照してください。
1. **[新しいヒント]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | 役に立つヒントのタイトル。 |
| リソース URL | ResourceURL | 追加の読み取り資料へのリンク。 (省略可能) |
| サブタイトル | サブタイトル | チップのサブタイトル。 (省略可能) |
| 説明 | 説明 | 役に立つヒントの詳しい説明。 |
| 非推奨 | 非推奨 | 役に立つヒントを非表示にするには、を使用します。 |

### <a name="set-up-links"></a>リンクの設定

1. **リンク**にアクセスします。
1. **[新しいリンクの作成]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | リンクのテキスト。 |
| URL | URL | リンクの URL。 |
| 説明 | 説明 | リンクに関する追加情報。 (省略可能) |
| 非推奨 | 非推奨 | リンクを非表示にするには、を使用します。 |

### <a name="set-up-faqs"></a>Faq の設定

1. **FAQ**にアクセスします。
1. **[新しい FAQ の作成]** を選択します。
1. フォームに入力します。

*リストスキーマ:*

| **フィールド名** | **SharePoint での論理名** | **目的** |
|-|-|-|
| タイトル | タイトル | FAQ の質問です。 |
| ランク | ランク | FAQ の質問の順序。 |
| 受信 | 受信 | FAQ の質問に対する回答です。 |
| 非推奨 | 非推奨 | FAQ の質問を非表示にするには、を使用します。 |

## <a name="test-and-share-the-app"></a>アプリをテストして共有する

すべてのデータが正常に設定されたので、アプリをテストして動作することを確認できます。

1. [Power Apps](https://make.powerapps.com) にサインインします。
2. 左側のナビゲーションウィンドウで **[アプリ]** を選択します。
3. アプリを再生するには、 **[危機通信]** を選択します。

アプリのテストが正常に完了したら、社内のすべてのユーザーと共有できます。

## <a name="import-and-set-up-the-notification-flow"></a>通知フローのインポートと設定

アプリは、新しい会社の更新が発生するたびに、フローを使用してエンドユーザーに通知を送信します。

### <a name="import-the-news-notification-flow"></a>ニュース通知フローをインポートする

1. [Flow.microsoft.com](https://flow.microsoft.com)にアクセスします。
1. 左側のナビゲーションウィンドウで **[マイフロー]** を選択します。
1. コマンドバーの **[インポート]** を選択します。
1. GitHub リポジトリから**CrisisCommunicationNewsNotification**パッケージをアップロードします。

    > [!NOTE]
    > テナントが GCC 環境にある場合は、 **CrisisCommunicationNewsNotificationGCC**をアップロードします。

    ![CrisisCommunicationNewsNotification のアップロード](media/sample-crisis-communication-app/upload-news-notification.png)

1. 新しいフローの接続を追加するには、各接続の **[インポート中に選択]** リンクを選択し、フォームを完了します。

    ![インポート時に選択](media/sample-crisis-communication-app/select-during-import.png)

1. 新しい接続を作成する必要がある場合は、セットアップの **[インポート]** ウィンドウで **[新規作成]** を選択します。
1. コマンドバーの **[新しい接続]** を選択します。

    ![新しい接続を作成する](media/sample-crisis-communication-app/create-connection.png)

1. 接続の名前を検索します。たとえば、 **PowerApps Notification (プレビュー)** です。

    ![接続名の例](media/sample-crisis-communication-app/notifications.png)

1. 目的の接続を選択します。
1. **PowerApps の通知 (プレビュー)** への接続を作成している場合は、次の図のようなダイアログボックスが表示されます。

    ![[通知] ダイアログボックス](media/sample-crisis-communication-app/notifications-dialog.png)

1. ID を取得するには、**アプリ**の一覧に移動します。
1. **危機通信**アプリの **[その他のコマンド]** (...) を選択し、 **[詳細]** を選択します。

    ![接続の詳細](media/sample-crisis-communication-app/06-App-Details.png)

1. **アプリ ID** をコピーします。

    ![アプリ ID](media/sample-crisis-communication-app/07-App-ID.png)

1. 接続の作成 ダイアログボックスにアプリ ID を貼り付け、**作成** を選択します。

    ![接続を作成する](media/sample-crisis-communication-app/target-app-id.png)

1. 新しい接続を作成したら、 **[セットアップのインポート]** ウィンドウに戻り、 **[更新リスト]** を選択します。
1. 新しい接続が表示されます。 それを選択し、 **[保存]** を選択します。
1. すべての接続の追加が完了したら、 **[インポート]** を選択します。

    ![インポートの接続](media/sample-crisis-communication-app/imported-connections.png)

### <a name="edit-the-news-notification-flow"></a>ニュース通知フローを編集する

1. インポートが完了したら、 **[マイフロー**] に移動します。
1. 新しくインポートしたフローを選択し、**新しい緊急通信のニュースをユーザーに通知**します。

    > [!NOTE]
    > GCC パッケージをアップロードした場合、フロー名は、**新しい危機通信ニュース (gcc) を使用してユーザーに通知**します。

1. コマンドバーの **[編集]** を選択します。
1. **[新しい項目が投稿されたとき]** カードを開きます。
1. **[サイトアドレス]** に、SharePoint サイトの名前を入力します。
1. **[リスト名]** に「 **CI_CompanyNews**」と入力します。
1. **[管理構成設定の取得]** カードを開きます。
1. **[サイトアドレス]** に、SharePoint サイトの名前を入力します。
1. **[リスト名]** に「 **CI_configAdminSetup**」と入力します。
1. [**変数の初期化–追加のテキストカードを読み取る]** を開きます。
1. **[値]** に **「(ネイティブ言語)」と**入力します。

    ![フローの設定](media/sample-crisis-communication-app/flow-options.png)

1. **[保存]** を選択します。

> [!NOTE]
> 接続のいずれかがまだ承認されていない場合、エラーが表示されることがあります。
この問題が発生した場合は、許可されていない接続と再認証を使用してカードを開いてください。


### <a name="optional-sending-notifications-to-more-than-5000-users"></a>省略可能: 5000 人を超えるユーザーに通知を送信する

現在の [**グループメンバーの取得]** アクションは、Power の自動化の Office ライセンスに対して5000人のユーザーをプルすることに限定されています。 Premium ライセンスの場合でも、通知を多数のユーザーに送信しようとすると、Teams コネクタでスロットル制限に達している可能性があります。 より多くのユーザーに配布するには、代わりに、配信リストに電子メールを送信するようにフローを変更します。

1. 次のカードを削除します:**グループメンバーを取得**し、**優先する送信通知設定で切り替え**ます。

    ![アクションの削除](media/sample-crisis-communication-app/36-delete-actions.png)

1. 新しいアクションを追加します。

1. を検索し、 **[電子メールの送信 (V2)]** を選択します。

    ![追加の電子メール送信](media/sample-crisis-communication-app/37-add-send-an-email.png)

1. **[宛先]** フィールドに、配布グループの名前を入力します。

1. **[件名]** フィールドで、 **[動的な値の追加]** ボタンを選択し、 **[ニュース項目が投稿されたとき]** カードの **[タイトル]** フィールドを追加します。

    ![タイトルを追加します](media/sample-crisis-communication-app/38-add-title.png)

1. **[本文]** フィールドで、 **[動的な値の追加]** ボタンを選択し、 **[ニュース項目が投稿されたとき]** カードの **[詳細]** フィールドを追加します。

1. **[保存]** を選択します。

### <a name="optional-deep-link-teams-notification-into-teams-app"></a>省略可能: チームアプリへのディープリンクチームの通知

チーム内のキャンバスアプリにチームの通知を直接開く場合は、次の手順を実行します。

1. アプリの URL を更新して、管理アプリのチームディープリンクをポイントします。 <br>
管理アプリで、アプリの URL を次のように変更します。 `App ID` はアプリの ID です。

    ```
    https://teams.microsoft.com/l/entity/<APP ID>/<APP ID>
    ```

    ![管理アプリ](media/sample-crisis-communication-app/42-admin-app.png)

1. 通知フローの内部で生成されたアプリリンクを更新します。 <br> [アプリリンク変数の設定] カードを開き、[値] の式を次のように変更します。

    ```
    concat(items('Apply_to_each')?['AppUrl'], if(greater(indexOf(items('Apply_to_each')?['AppUrl'], '?'),0),'&','?'), 'context=%7B%22subEntityId%22%3A%22',triggerBody()?['ID'],'%22%7D')
    ```
    ![フロー設定の変更](media/sample-crisis-communication-app/43-flow-settings.png)

1. Canvas アプリを更新し、teams コンテキスト変数を使用して、正しいニュース記事へのディープリンクを行います。 <br> アプリの**OnStart**プロパティについて、パラメーターを `newsid` から `subEntityId`に変更します。

    ![変更 OnStart](media/sample-crisis-communication-app/44-onstart.png)

### <a name="test-the-news-notification-flow"></a>ニュース通知フローをテストする

ニュース通知フローをテストするには、管理者アプリにアクセスして、社内の新しい更新プログラムを作成します。 後で、配布リスト内のすべてのユーザーが、優先する通知方法によって更新プログラムを受信します。

> [!NOTE]
> エラーが発生した場合は、管理アプリの設定で配布リストのグループ ID を正しく入力していることを確認してください。

## <a name="monitor-office-absences-with-power-bi"></a>Power BI でオフィスの休暇を監視する

アプリを展開した後、さまざまな理由 (病気や自宅での作業など) に応じて、office からの通知の送信を開始すると、Power BI レポートを使用して、通知を送信したユーザーの数とその場所を追跡できます。  
マップコントロールを機能させるには、[場所の追跡を有効](#optional-enable-location-updates)にする必要があることに注意してください。 

> [!IMPORTANT]
> Power BI レポートを機能させるには、 **[CI_Employee の状態]** ボックスの一覧に少なくとも1つのエントリが必要です。

先ほど作成した**CI_Employee Status** SharePoint リストからいくつかの情報が必要なので、先に説明します。 サイトの一覧を開き、 **[設定]** アイコンの下の **[リストの設定]** を選択します。

![従業員の状態の一覧の設定](media/sample-crisis-communication-app/001-SharePointList-ListSettings-nolines.PNG)

次の図に示すように、ブラウザーのアドレスバーでサイト名とリスト ID をメモしておきます。

![従業員の状態の一覧とサイト Id](media/sample-crisis-communication-app/002-SharePointList-AddressAndId-nolines.PNG)

この時点で、Power BI レポートを開く準備が整いました。 Power BI を開き、**プレゼンス状態レポート .pbix**ファイルを開きます。 **CI_Employee 状態**データソースの右側にマウスポインターを合わせると、省略記号が表示されます。 それを選択し、 **[クエリの編集]** を選択します。

![クエリの編集](media/sample-crisis-communication-app/003-PowerBI-EditQuery-nolines.PNG)

Power Query エディターが開いたら、 **[CI_Employee ステータス]** データソースを右クリックし、 **[詳細エディター]** を選択します。

![Power Query 詳細エディター](media/sample-crisis-communication-app/004-PowerQuery-AdvancedEditor-nolines.PNG)

ここでは、SharePoint リストのサイト名とリスト ID を使用します。

次の図に示すように、新しい SharePoint サイトを SharePoint. Tables 文字列にコピーします。<!--Edit okay? This is a case where the image shows information that the text doesn't, so I'm not sure how to make this descriptive enough for people who aren't looking at the graphics, or people with low vision.--> GUID が強調表示されている3か所のリスト ID を入力し、 **[完了]** を選択します。

![詳細エディター更新プログラムの Power Query](media/sample-crisis-communication-app/005-PowerQuery-AdvancedEditorUpdates-nolines.PNG)

接続情報の更新後に接続エラーが発生した場合は、SharePoint リストへの接続に使用する資格情報の更新が必要になることがあります。 

**接続を更新するには**

1. **[ファイル]** メニューの **[オプションと設定]** をクリックし、 **[データソースの設定]** を選択します。

    ![データ ソースの設定](media/sample-crisis-communication-app/PBI-1-DataSourceSettings.PNG)

1. **[アクセス許可の編集]** を選択します。

    ![アクセス許可の編集](media/sample-crisis-communication-app/PBI-2-DataSourceSettings-EditPermissions.PNG)

1. **[資格情報]** の種類 が **[組織アカウント]** に設定されていることを確認し、資格情報を使用して SharePoint リストにアクセスします。

    ![アクセス許可の編集](media/sample-crisis-communication-app/PBI-3-OrganizationalAccount.PNG)

SharePoint リストからデータをプルするようにレポートを更新するには、 **[閉じる & 適用]** を選択します。

![Power Query 閉じて適用](media/sample-crisis-communication-app/006-PowerQuery-CloseAndApply-nolines.PNG)

現在の日の office 休暇の地理情報と、数日にわたるそのような休暇の傾向を示す Power BI レポートが作成されました。 レポートは、組織内の他の担当者が表示できるように公開できます。

![レポートのパブリッシュ Power BI](media/sample-crisis-communication-app/007-PowerBI-Publish-nolines.PNG)

これで、レポートが発行されました。 組織内の他のユーザーと共有することができます。 また[、レポートの更新頻度をスケジュール](https://docs.microsoft.com/power-bi/refresh-scheduled-refresh)することもできます。

## <a name="integrate-your-app-into-teams"></a>アプリをチームに統合する

すべてのユーザーと共有されている機能を持つアプリが完成したので、問題に対応するために、チーム内に危機管理チームを作成してアプリをデプロイできます。

### <a name="deploy-the-app-to-the-app-bar"></a>アプリをアプリバーにデプロイする

Teams 管理者の場合は、Teams アプリバーのすべてのユーザーにアプリをプッシュできます。

![チーム内のアプリバー](media/sample-crisis-communication-app/19-App-in-Teams.png)

1. [Power Apps](https://make.powerapps.com) にサインインします。
1. 左側のナビゲーションウィンドウで **[アプリ]** を選択します。
1. **危機通信**アプリの [**その他のコマンド**(...)] を選択します。
1. **[チームに追加]** を選択します。

    ![チームに追加](media/sample-crisis-communication-app/24-Add-to-Teams.png)

1. **[アプリのダウンロード]** を選択します。

    ![アプリのダウンロード](media/sample-crisis-communication-app/25-Download-App.png)

1. チームを開きます。
1. アプリバーの **[アプリ]** にアクセスします。
1. **[カスタムアプリのアップロード]** を選択します。
1. チームの管理者は、テナント全体のアプリをアップロードすることができます。 **[Contoso のアップロード]** を選択します ( *contoso*はテナントの名前を表します)。<!--Edit okay? The screenshot said "Contoto," which I fixed.-->。

    ![アプリをアップロードする](media/sample-crisis-communication-app/26-Upload-for-Contoso.png)

1. Power Apps からダウンロードしたファイルをアップロードします。
1. [Teams 管理センター](https://admin.teams.microsoft.com/dashboard)にアクセスします。
1. 左側のナビゲーションウィンドウの **[Teams apps]** で、 **[セットアップポリシー]** を選択します。

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

### <a name="create-a-central-crisis-management-team-in-teams"></a>チームで中心的な危機管理チームを作成する<a name="create-a-central-crisis-management-teams-team"></a>

危機的な応答を調整するには、チームで中心的な危機管理チームを作成し、関連するすべての情報を設定する必要があります。 このチームは、中央の応答チームとのみ共有する必要があります。

1. [チーム] にアクセスします。
1. 左側のアプリバーから **[チーム]** を選択します。
1. [**参加] または [チームの作成**] を選択します。
1. **[チームの作成]** を選択し、残りの手順を完了します。

    ![チームを作成する](media/sample-crisis-communication-app/23-Create-Team.png)

チームが正常に作成されたら、関連する情報をタブとしてピン留めできます。 たとえば、危機管理管理者アプリまたは Power BI レポートをチームにピン留めすることができます。

**管理アプリをタブとして追加するには**

1. [ **+** ] ボタンを選択します。
1. **[Power Apps]** を検索して選択します。
1. [**緊急情報] 管理者**を検索して選択します。

    ![アプリのピン留め](media/sample-crisis-communication-app/32-Pin-Teams-app.png)

1. **[保存]** を選択します。

**Power BI レポートをタブとして追加するには**

1. [ **+** ] ボタンを選択します。
1. **Power BI**を検索して選択します。
1. Power BI レポートを検索して選択します。
1. **[保存]** を選択します。

## <a name="faq"></a>よく寄せられる質問

* **このソリューションを実行するにはどのようなライセンスが必要ですか?**

    - このアプリのソリューションでは Office コネクタを使用しているため、Office からのシードされた電源アプリライセンスは、ユーザーと管理者のアプリを実行して再生するのに十分です。 詳細情報:[電源プラットフォームライセンスの概要](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)
    - Power BI レポート (ソリューションの一部としてパッケージ) を使用する場合は、Power BI ライセンスが必要です。 詳細情報: [Power BI の価格](https://powerbi.microsoft.com/pricing/)

* **ソリューションに関するフィードバックがある場合は、どこに移動すればよいですか?**

    このソリューションのデプロイとカスタマイズについて、皆様のご意見をお待ちしております。 経験を共有するには、 [aka.ms/crisis-communication-feedback](https://aka.ms/crisis-communication-feedback)にアクセスしてください。

* **アプリでバグが見つかったようです。どこに移動すればよいですか。**

   ソリューションでバグを報告するには、 [aka.ms/crisis-communication-issues](https://aka.ms/crisis-communication-issues)にアクセスしてください。

* **GCC で現在サポートされていない機能は何ですか。**

    現在、Power オートメーション bot connector for Teams およびプッシュ通知コネクタは、GCC では使用できません。 [電子メール] オプションを使用して、内部のニュースの更新に関する警告をユーザーに通知します。

* **アプリケーションを更新するにはどうすればよいですか。**

    アプリケーションを更新する場合は、 [aka.ms/CrisisCommunicationSolution](https://aka.ms/CrisisCommunicationSolution)に記載されている手順に従ってください。

## <a name="issues-and-feedback"></a>問題とフィードバック

- 危機通信サンプルテンプレートに関するフィードバックについては、 [aka.ms/crisis-communication-feedback](https://aka.ms/crisis-communication-feedback)を参照してください。
- 危機通信アプリの問題を報告するには、 [aka.ms/crisis-communication-issues](https://aka.ms/crisis-communication-issues)にアクセスしてください。

***免責事項:*** *このアプリはサンプルであり、Microsoft Power Apps および Teams と共に使用して、参照情報のみを伝達することができます。このアプリは、医療デバイス、臨床サポート、診断ツール、その他のテクノロジとして使用することを目的としたものではありません。また、病気やその他の条件の診断、治療、軽減、取り扱い、または防止に使用することを意図したものではありません。 このアプリは、専門的な医療のアドバイス、診断、取り扱い、または略しの代わりとして設計されていないため、使用しないでください。 お客様は、このアプリの使用に関して唯一のリスクと責任を負うものとします。 Microsoft では、接続関連に用意されているアプリまたはマテリアルが、医療目的、または任意のユーザーの健康や医療の要件を満たすために十分であることを保証していません。* 

### <a name="see-also"></a>参照
<!--note from editor: "Next steps" would work if you gave the reader some action items, but reference topics are random access by nature, so the heading is rightly "See also." -->
- [数式のリファレンス](formula-reference.md)
- [コントロールのリファレンス](reference-properties.md)
