---
title: Power BI レポートに新しいキャンバス アプリを埋め込む | Microsoft Docs
description: 同じデータ ソースを使用し、他のレポート項目のようにフィルター処理できる新しいキャンバス アプリを埋め込みます
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/15/2018
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 60577eb3b6c272093222f1c14685d5ffe1d433f9
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74731526"
---
# <a name="embed-a-new-canvas-app-in-a-power-bi-report"></a>Power BI レポートに新しいキャンバス アプリを埋め込む

Power BI を使用すると、*カスタム ビジュアル*をレポートに追加して機能を拡張できます。 このチュートリアルでは、Power Apps カスタムビジュアルを使用して、サンプルレポートに埋め込まれているキャンバスアプリを作成します。 このアプリは、そのレポート内の他の項目と対話します。

Power Apps サブスクリプションをお持ちでない場合は、開始する前に[無料アカウントを作成](../signup-for-powerapps.md)してください。

このチュートリアルで学習する内容は次のとおりです。
> [!div class="checklist"]
> * Power Apps カスタムビジュアルを Power BI レポートにインポートする
> * レポートのデータを使用する新しいアプリを作成する
> * レポートでアプリを確認する

## <a name="prerequisites"></a>前提条件

* [Google Chrome](https://www.google.com/chrome/browser/) または [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) ブラウザー
* [営業案件の分析のサンプル](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample)がインストールされた [Power BI サブスクリプション](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi)
* [アプリを Power apps で作成](data-platform-create-app-scratch.md)する方法と[Power BI レポートを編集](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour)する方法について理解する

## <a name="import-the-power-apps-custom-visual"></a>Power Apps カスタムビジュアルをインポートする

最初の手順として、Power Apps カスタムビジュアルをインポートして、サンプルレポートで使用できるようにします。

1. 営業案件の分析のサンプル レポートで、 **[Upcoming Opportunities]\(今後の案件\)** タブをクリックまたはタップします。

2. レポートの上部にある **[レポートの編集]** をクリックまたはタップします。

3. **[視覚化]** ウィンドウで、省略記号ボタン ( **[...]** )、 **[Marketplace からインポートする]** の順にクリックまたはタップします。 

    ![Marketplace からインポートする](media/embed-powerapps-powerbi/import-visual.png)

4. **[Power BI ビジュアル]** 画面で「PowerApps」を検索し、 **[追加]** をクリックまたはタップします。 Power BI の **[視覚化]** ウィンドウの下部にカスタム ビジュアル アイコンが追加されます。

    ![Power Apps のビジュアルアイコン](media/embed-powerapps-powerbi/powerapps-icon.png)

5. レポートを保存します。

## <a name="create-a-new-app"></a>新しいアプリの作成
これでカスタム ビジュアルがレポートに追加され、レポートのデータに基づいて新しいアプリが作成されます。 アプリを作成すると、電源アプリと Power BI の間のライブデータ接続を使用して、Power Apps Studio が起動します。

1. アプリのスペースを確保するためにレポート タイルの一部を移動してサイズを変更します。

    ![レポート タイルの移動とサイズ変更](media/embed-powerapps-powerbi/move-resize.png)

2. [Power Apps] カスタムビジュアルアイコンをクリックまたはタップし、作成した領域に合わせてタイルのサイズを変更します。

3. **[フィールド]** ウィンドウで、 **[名前]** 、 **[製品コード]** 、 **[営業段階]** を選択します。 

    ![フィールドの選択](media/embed-powerapps-powerbi/select-fields.png)

4. カスタムビジュアル タイルで、アプリを作成する Power Apps 環境を選択し、**新規作成** をクリックまたはタップします。

    ![新しいアプリの作成](media/embed-powerapps-powerbi/create-new-app.png)

    Power Apps Studio では、基本的なアプリが作成され、Power BI で選択したフィールドの1つが*ギャラリー*に表示されます。

5.  画面の半分のみを占めるようにギャラリーのサイズを変更します。 

6. 左側のウィンドウで、 **[Screen1]** をクリックまたはタップし、画面の **[塗りつぶし]** プロパティを (レポートで目立つように) [ライトブルー] に設定します。

    ![ギャラリーのサイズを変更したアプリ](media/embed-powerapps-powerbi/app-gallery.png)

6. **[テキスト]** プロパティを `"Opportunity Count: " & CountRows(Gallery1.AllItems)` に設定して、ギャラリーの下に [ラベル] コントロールを追加します。 これで、データ セット内の営業案件の総数が表示されます。

    ![営業案件数](media/embed-powerapps-powerbi/opportunity-count.png)

7. 「営業案件」という名前でアプリを保存します。 


## <a name="view-the-app-in-the-report"></a>レポートでアプリを確認する
レポートでアプリを使用できるようになりました。アプリは他のビジュアルと対話できます。これは、同じデータ ソースを共有しているためです。

Power BI レポートのスライサーで **[1 月]** を選択します。これで、アプリ内のデータを含むレポート全体がフィルター処理されます。

![フィルター処理されたレポート](media/embed-powerapps-powerbi/filtered-report.png)

アプリの営業案件数が、レポートの左上の数と一致することに注目してください。 レポートの他の項目を選択すると、アプリのデータが更新されます。


## <a name="clean-up-resources"></a>リソースのクリーンアップ
営業案件の分析のサンプルをもう使用しない場合は、ダッシュボード、レポート、およびデータセットを削除できます。


## <a name="next-steps"></a>次の手順
このチュートリアルでは、次の内容を学習しました。
> [!div class="checklist"]
> * Power Apps カスタムビジュアルを Power BI レポートにインポートする
> * レポートのデータを使用する新しいアプリを作成する
> * レポートでアプリを確認する

さらに学習するには、次の記事に進んでください
> [!div class="nextstepaction"]
> [Power BI 用の Power Apps カスタムビジュアル](powerapps-custom-visual.md)

