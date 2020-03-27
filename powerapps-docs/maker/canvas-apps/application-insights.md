---
title: Application Insights を使用してアプリのテレメトリを分析する |Microsoft Docs
description: Application Insights を使用してアプリのテレメトリを分析する方法
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/25/2020
ms.author: aheaney
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cf7e65d395e8ad28e434cc957502a5bce52a3e6e
ms.sourcegitcommit: 77e00640a59a7db9d67d3ac52f74d264cbe3a494
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80328918"
---
# <a name="analyze-app-telemetry-using-application-insights"></a>Application Insights を使用したアプリテレメトリの分析

アプリを[Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)の機能である[Application Insights](https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview)に接続できます。 Application Insights には、問題を診断し、ユーザーがアプリで実際に実行する操作を理解するのに役立つ強力な分析ツールが用意されています。 

アプリを Application Insights に接続すると、ビジネス上の意思決定を改善し、アプリの品質を向上させるために役立つ情報を収集できます。

このクイックスタートでは、Kudos というキャンバスアプリをインストルメント化します。 これにより、テレメトリの概念を調査して発見し、独自のキャンバスアプリに適用することができます。 サンプル Kudos アプリは、 [Employee Experience Starter Kit](https://powerapps.microsoft.com/blog/powerapps-employee-experience-starter-kit)からダウンロードできる一連の employee engagement アプリに含まれています。

## <a name="prerequisites"></a>前提条件

- [Azure portal](https://portal.azure.com)にアクセスできる必要があります。
- [Azure リソースを作成](https://docs.microsoft.com/azure/role-based-access-control/quickstart-assign-role-user-portal)するためのアクセス許可が必要です。

### <a name="optional"></a>［オプション］

- [Employee Experience Starter Kit](https://powerapps.microsoft.com/blog/powerapps-employee-experience-starter-kit)から Kudos アプリをダウンロードしてインストールします。 代わりに、既存のアプリを使用することもできます。

## <a name="create-an-application-insights-resource"></a>Application Insights リソースの作成

アプリのテレメトリを送信するには、その前に、イベントを格納するための Azure アプリケーション Insights リソースを作成する必要があります。

1.  [Azure portal](https://portal.azure.com/)にサインインします。

1. Application Insights を検索します。

    ![Azure Application Insights](./media/application-insights/azureappinsights.png)

1. Application Insights リソースを作成します。

    ![Azure アプリケーション Insights リソースの追加](./media/application-insights/azureappinsights-add.png)

1. 適切な値を入力し、[**レビュー + 作成**] を選択します。 詳細については、「 [Application Insights リソースの作成](https://docs.microsoft.com/azure/azure-monitor/app/create-new-resource)」を参照してください。 

    ![リソースの作成](./media/application-insights/createresource.png)

1. Application Insights インスタンスが作成されると、インスタンスの概要が表示されます。 **インストルメンテーションキー**をコピーします。 アプリを構成するには、このキーが必要になります。

    ![インストルメンテーションキーのコピー](./media/application-insights/instrumentation-key.png)

## <a name="connect-your-app-to-application-insights"></a>アプリを Application Insights に接続する

1. [Power Apps](https://make.powerapps.com) にサインインします。

1. 左側のナビゲーションから [**アプリ**] を選択します。 アプリの一覧から**Kudos**アプリを選択し、[**編集**] を選択します。

    ![Kudos アプリの編集](./media/application-insights/edit-kudos-app.png)

    > [!NOTE]
    > 代わりに、新しいアプリを[作成](open-and-run-a-sample-app.md)したり、既存のアプリを[編集](edit-app.md)したりすることもできます。

1. 左側のナビゲーションツリービューで [**アプリ**] オブジェクトを選択し、**インストルメンテーションキー**を貼り付けます。

    ![インストルメンテーションキーの追加](./media/application-insights/add-instrumentation-key.png)

1. アプリを**保存** & **発行**します。

1. 発行されたアプリを**再生**し、さまざまな画面を参照します。 

さまざまな画面を参照すると、イベントは次のような使用状況の詳細を含む Application Insights に自動的に記録されます。

- アプリがどこからアクセスされるか。
- 使用するデバイスです。
- 使用されるブラウザーの種類。

> [!IMPORTANT]
> Application Insights にイベントを送信するには、発行されたアプリを再生する必要があります。 Power Apps Studio でアプリをプレビューするときに、イベントが Application Insights に送信されることはありません。

## <a name="view-events-in-application-insights"></a>Application Insights でのイベントの表示

1.  [Azure portal](https://portal.azure.com/)にサインインし、[前](#create-an-application-insights-resource)の手順で作成した Application Insights リソースを開きます。

1. 左側のナビゲーションウィンドウで下へスクロールし、[**使用状況**] セクションで [**ユーザー** ] を選択します。 

    > [!NOTE]
    > **ユーザー**ビューには、アプリの使用状況の詳細が表示されます。次に例を示します。
    > - アプリを表示したユーザーの数。
    > - アプリのユーザーによるセッションの数。
    > - アプリに対してログに記録されたイベントの数。
    > - ユーザーのオペレーティングシステムとブラウザーバージョンの詳細。
    > - ユーザーのリージョンと場所。
    > 
    > 詳細については、「 [Application Insights でのユーザー、セッション、およびイベントの分析](https://docs.microsoft.com/azure/azure-monitor/app/usage-segmentation)」を参照してください。

1. ユーザーセッションの1つを選択して、特定の詳細にドリルダウンします。 セッションの長さや、表示された画面などの情報を確認できます。

    ![ユーザーの使用状況の詳細](./media/application-insights/appinsights-users.gif)

1. 左側のナビゲーションウィンドウで [**使用量**] セクションの [**イベント**] ビューを選択します。 すべてのアプリセッションで表示されるすべての画面の概要を確認できます。

    ![アプリのイベントの詳細](./media/application-insights/appInsights-events.gif)

> [!TIP]
> 使用できる追加の Application Insights 機能の一部を次に示します。  
> - [**じょうご**](https://docs.microsoft.com/azure/azure-monitor/app/usage-funnels)
> - [**コーホート**](https://docs.microsoft.com/azure/azure-monitor/app/usage-cohorts)
> - [**影響分析**](https://docs.microsoft.com/azure/azure-monitor/app/usage-impact)
> - [**保持分析**](https://docs.microsoft.com/azure/azure-monitor/app/usage-retention)
> - [**使用フロー**](https://docs.microsoft.com/azure/azure-monitor/app/usage-flows)

## <a name="create-custom-trace-events"></a>カスタムトレースイベントの作成

カスタムトレースを Application Insights に直接記述して、シナリオに固有の情報の分析を開始することができます。 [Trace](https://docs.microsoft.com/powerapps/maker/canvas-apps/functions/function-trace)関数を使用すると、次のものを収集できます。

- 画面上のコントロールの詳細な使用方法に関する情報。
- アプリにアクセスしている特定のユーザー。
- どのようなエラーが発生しますか。

トレースは、ユーザーがアプリを参照してさまざまな操作を実行するときに情報の記録を送信できるため、問題の診断にも役立ちます。

アプリから Application Insights にカスタムトレース情報を送信する場合、トレースメッセージには3つの重大度があります。

- **参照**
- **要する**
- **エラー**

シナリオによっては、適切な重大度でトレースメッセージを送信するように選択できます。 データに対してクエリを実行し、メッセージの重要度に基づいて特定のアクションを実行することができます。

> [!NOTE]
> スタッフデータをログに記録する場合は、GDPR などのデータコンプライアンスの義務を考慮する必要があります。これは、実装する必要がある場合もあります。

次に、アプリを更新し、新しいコンポーネントを作成して、アプリの各画面に関するフィードバックを収集します。 Application Insights するイベントを記述します。

1. [Power Apps](https://make.powerapps.com) にサインインします。

1. 左側のナビゲーションから [**アプリ**] を選択します。 アプリの一覧から**Kudos**アプリを選択し、[**編集**] を選択します。

    > [!NOTE]
    > 代わりに、新しいアプリを[作成](open-and-run-a-sample-app.md)したり、既存のアプリを[編集](edit-app.md)したりすることもできます。

1. **ツリービュー**で、[**コンポーネント**] オプションを選択します。

    ![Components](./media/application-insights/new-component.png)

1. [**新しいコンポーネント**] を選択し、幅を200、[高さ] を75に変更します。

    ![高さと幅](./media/application-insights/resize-component.png)

1. メニューの [**挿入**] を選択し、[**アイコン**] を選択して、*改善点*と*絵文字*のアイコンを追加します。

    ![アイコンの追加](./media/application-insights/add-icons.png)

1. カスタムプロパティを作成するには、[**新しいカスタムプロパティ**] を選択します。

    ![カスタムプロパティの作成](./media/application-insights/create-custom-property.png)

1. プロパティの*名前*と*表示名*( *FeedbackSceen*など) を入力します。

1. プロパティの*説明*を入力します。

1. [**プロパティの種類**] として [**入力**] を選択し、[**データ型** **] を画面**に選択します

    ![カスタムプロパティ](./media/application-insights/custom-input-property.png)

    > [!NOTE]
    > Input プロパティを使用すると、この情報を Application Insights に記録できるように、画面名とそのコンポーネントをキャプチャできます。

1. **ツリービュー**でコンポーネントを選択し、[**その他のアクション**(**...**)] を選択し、[**名前の変更**] を選択して、"*フィードバックコンポーネント*" などのわかりやすい名前に変更します。

    ![コンポーネントと欠点の名前を変更する](./media/application-insights/rename-component-icons.png)

1. [アイコン] を選択し、[**その他のアクション**(**...**)] を選択し、[**名前の変更**] を選択して、 *FrownIcon*や*SmileIcon*などのわかりやすい名前でアイコンの名前を変更します。

1. *FrownIcon*を選択し、 **onselect**プロパティを選択して、数式バーに次の式を入力します。

    ```
    Trace(
       "App Feedback",
       TraceSeverity.Information,
           {
             UserName: User().FullName,
             UserEmail: User().Email,
             Screen: FeedbackComponent.FeedbackScreen.Name,
             FeedbackValue: "-1"
           }
         );
    Notify("Thanks for you feedback!");
    ```

    ![改善点アイコンの数式](./media/application-insights/frownicon-formula.png)

    > [!NOTE]
    > 数式式は、 *UserName*、 *useremail*、 *Screen* 、および*フィードバック*(値 *-1*) を Application Insights に送信します。

1. *SmileIcon*を選択し、 **onselect**プロパティを選択して、数式バーに次の式を入力します。
    
    ```
    Trace(
       "App Feedback",
       TraceSeverity.Information,
           {
             UserName: User().FullName,
             UserEmail: User().Email,
             Screen: FeedbackComponent.FeedbackScreen.Name,
             FeebackValue: "1"
           }
         );
    Notify("Thanks for you feedback!");
    ```

1. アプリのいずれかの画面にコンポーネントを追加します。

    ![フィードバックコンポーネントの追加](./media/application-insights/add-feedback-component.png)

1. [**保存**] を選択し、[**発行**] を選択してアプリを発行 & に保存します。

1. 発行されたアプリを再生し、画面から気に入った機能と改善点フィードバックを送信します。

    > [!IMPORTANT]
    > Application Insights にイベントを送信するには、発行されたアプリを再生する必要があります。 Power Apps Studio でアプリをプレビューするときに、イベントが Application Insights に送信されることはありません。

    ![発行されたアプリの再生](./media/application-insights/play-published-app.png)

## <a name="analyze-data-in-application-insights"></a>Application Insights でのデータの分析

これで、App Insights でアプリケーションから[トレース](#create-custom-trace-events)関数を使用して送信したデータの分析を開始できるようになりました。

1.  [Azure portal](https://portal.azure.com/)にサインインし、[前](#create-an-application-insights-resource)の手順で作成した Application Insights リソースを開きます。

    ![Application insights の選択](./media/application-insights/select-app-insights.png)

1. 左側のナビゲーションウィンドウで [**監視**] の下にある [**ログ**] を選択します。

    ![ログの選択](./media/application-insights/select-logs.png)

1. 次のクエリを入力し、[**実行**] を選択します。 アプリから受け取ったフィードバックが返されます。

    ```powerappsfl
    traces
    | where message == "App Feedback"
    | order by timestamp
    ```

    ![アプリのフィードバックを表示する](./media/application-insights/view-app-feedback.png)

1. 結果内の行を選択し、[*カスタムディメンション*] フィールドを展開します。 

    コンポーネントの [気に入った機能] または [改善点] アイコンの**Onselect**イベントの [画面]、[**ユーザー名**]、[ **Useremail**]、[**フィードバック値** **]** の値が記録されています。 <br>
    Application Insights に送信されるイベントごとに、いくつかの追加の値も記録されます。( **appId**、 **AppName** 、 **appsessionid**など)。

    ![カスタムディメンションを展開する](./media/application-insights/expand-custom-dimensions.png)

1. 次のクエリ例では、JSON カスタムディメンションのプロパティを拡張し、結果ビューで列を射影できます。

    ```powerappsfl
    traces
        | extend customdims = parse_json(customDimensions)
        | where message == "App Feedback"
        | project timestamp
            , message
            , AppName = customdims.['ms-appName']
            , AppId = customdims.['ms-appId']
            , FeedbackFrom = customdims.UserEmail
            , Screen = customdims.Screen
            , FeedbackValue = customdims.FeedbackValue
        | order by timestamp desc
    ```

    ![CustomDimensions クエリの拡張](./media/application-insights/custom-dimensions-extend-query.png)

    > [!TIP]
    > *ログクエリ*は非常に強力です。 複数のテーブルを結合し、大量のデータを集計し、複雑な操作を実行するために使用できます。 詳細については、「[ログクエリ](https://docs.microsoft.com/azure/azure-monitor/log-query/log-query-overview)」を参照してください。

## <a name="export-data-to-power-bi"></a>Power BI にデータをエクスポートする

分析とデータ表示のために、Application Insights データとクエリ結果を Power BI にエクスポートできます。

1.  [Azure portal](https://portal.azure.com/)にサインインし、[前](#create-an-application-insights-resource)の手順で作成した Application Insights リソースを開きます。

1. 左側のナビゲーションウィンドウで [**監視**] の下にある [**ログ**] を選択します。

1. Log analytics クエリウィンドウで、[**エクスポート**] ドロップダウンメニューを選択します。

1. [ **Power BI (M クエリ) にエクスポート**] オプションを選択します。 これにより、Power BI のクエリファイルがコンピューターにダウンロードされます。

    ![Power BI クエリのエクスポート](./media/application-insights/export-powerbi-query.png)

1. ダウンロードしたファイルをテキストエディターで開き、クエリをクリップボードにコピーします。

1. Power BI を開きます。

1. [**ホーム**] リボンで [**データの取得**] ドロップダウンメニューを選択し、[**空のクエリ**] を選択します。

    ![空のクエリを Power BI](./media/application-insights/powerbi-blank-query.png)

1. クエリウィンドウで、[**詳細エディター**] を選択します。 手順 5. のクエリをウィンドウに貼り付けて、[**完了**] を選択し、[**閉じる & 適用**] を選択します。

    ![Power BI の詳細クエリ](./media/application-insights/powerbi-advance-query.png)

1. Power BI でグラフや視覚エフェクトを作成して、アプリで受信したフィードバックを表すこともできます。 データベースの決定とアクションを行います。

    ![グラフと視覚エフェクト](./media/application-insights/powerbi-feedback.png)

## <a name="default-trace-event-context-and-dimensions"></a>既定のトレースイベントコンテキストとディメンション

既定のディメンションのセットも、各トレースイベントの*Customdimensions*プロパティに追加されます。 これらのディメンションは、イベントが発生したアプリケーションとアプリケーションセッションを識別するために使用できます。 トレース関数を使用して追加のカスタムデータをログに記録すると、カスタムディメンションにも表示されます。

| ディメンション名  | 表す内容                                            |
|-----------------|-------------------------------------------------------|
| ms-appId        | イベントを送信したアプリのアプリケーション ID     |
| ms-appName      | イベントを送信したアプリのアプリケーション名   |
| ms appSessionId | アプリケーションセッション ID。                           |

