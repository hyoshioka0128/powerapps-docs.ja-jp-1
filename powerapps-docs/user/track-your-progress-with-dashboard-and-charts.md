---
title: モデル駆動型アプリでダッシュボードとグラフを使用して進行状況を追跡する |MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/4/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: 70c6f97c2617c9d6084c3aa8a0861793a0c059d5
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74726170"
---
# <a name="track-your-progress-with-dashboards-and-charts"></a>ダッシュボードとグラフを使って進行状況を追跡する

ダッシュボードは、アプリデータのコレクションを取得し、主要業績評価指標 (KPI) やその他の重要なデータを読みやすい対話型のグラフやグラフに表示するための洞察を提供します。 ダッシュボードは、すべてのレコードの種類で使用できます。

> [!div class="mx-imgBorder"]
> ![ダッシュボード](media/Dashboard.png "ダッシュボード") 

-  別のダッシュボードレイアウトを表示するには、ダッシュボードの名前の横にある下矢印を選択し、目的のレイアウトを選択します。
-  既定のダッシュボードを選択するには、目的のダッシュボードを表示し、画面の上部にある **[既定値として設定]** を選択します。

   > [!div class="mx-imgBorder"]
   > ![ダッシュボードを追加または変更する](media/add_dashboard.png "ダッシュボードを追加または変更する") 

## <a name="create-a-new-dashboard"></a>新しいダッシュボードを作成する

1. 新しいダッシュボードを作成するには、 **[Dynamics 365 ダッシュボードの作成]** を選択します。 

   > [!div class="mx-imgBorder"]
   > ![新しいダッシュボードの追加](media/new_dashboard.png "新しいダッシュボードの追加")
   
2. ダッシュボードのレイアウトを選択し、 **[作成]** を選択します。  

   > [!div class="mx-imgBorder"]
   > ![ダッシュボードを作成する](media/create_dashboard.png "ダッシュボードを作成する")
 
3. ダッシュボードの名前を入力します。 
4. ダッシュボードの各領域に必要なものを追加します。 たとえば、グラフを追加してみましょう。 

   > [!div class="mx-imgBorder"]
   > ![グラフを追加する](media/add_chart.png "表を追加")
 
 5. グラフの**レコードの種類**を選択します。
 6. グラフ内のデータが表示される**ビュー**を選択します。
 7. グラフを選択し、 **[追加]** を選択します。
 8. ダッシュボードへのコンポーネントの追加を続行し、完了したら **[保存]** を選択します。 
 
作成したダッシュボードは、使用可能なダッシュボードのドロップダウンメニューに表示されます。

## <a name="use-charts"></a>グラフを使用する 

グラフを使用すると、目標を追跡する方法を簡単に確認できます。 また、対話型であるため、グラフの領域をクリックまたはタップして詳細情報を表示できます。

-   グラフの上にマウスポインターを置くと、グラフのその領域についての簡単な情報を示すツールヒントが表示されます。
-   グラフの領域をクリックすると、グラフ内のデータに関する詳細を含むグリッドビューが表示されます。
-   グラフを展開するには、[**グラフ**の展開] をクリックしてグラフ![ビュー](media/expandviewbutton.png "グラフビューの展開")を展開します。
-   グラフのレコードを表示したり、グラフを更新したりするには、[![その他のコマンド](media/MoreButton.png "その他のコマンド")] を選択し、レコードの **[更新]** または **[レコードの表示]** を選択します。
     
     > [!div class="mx-imgBorder"]
     > ![Power Apps のグラフの表示](media/ViewOfCharts.png "Power Apps のグラフの表示")  
       

**グラフビューを変更する**
 
グラフビューを変更すると、特定の期間内に開かれた営業案件など、データのさまざまな内訳が表示されます。 グラフビューを変更するには、グリッドページでビューセレクターを選択します。

たとえば、[すべての営業案件] を選択し、別のビューを選択すると、グラフとグリッドの両方が更新されます。

> [!div class="mx-imgBorder"]
> ![Power Apps でグラフビューを変更する](media/ChangeChartView.png "Power Apps でグラフビューを変更する")

## <a name="known-issues"></a>既知の問題  
グラフデザイナーでは、特定の計算フィールドに order by を追加することはサポートされていないため、エラーが発生します。  この原因となった計算フィールドは、別の計算フィールド、関連エンティティフィールド、またはエンティティのローカルフィールドを使用します。



