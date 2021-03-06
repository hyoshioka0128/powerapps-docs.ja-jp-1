---
title: グリッド上のデータをフィルター処理する | MicrosoftDocs
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 03/31/2020
ms.author: mkaur
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 047263130052c412b69d4b69d219352b214b0671
ms.sourcegitcommit: 52b7f59e271437e86ffff226fb6c1982bf7f08b1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "3332707"
---
# <a name="use-grid-filters"></a>グリッド フィルターを使用する 

統一インターフェイスのグリッドが改善され、画面に表示できるデータの量が増えました。 列のさまざまなフィルター処理オプションから選択できるようになりました。列のデータの種類によって、使用できるフィルター オプションが決まります。 たとえば、**[取引先担当者]** グリッドの **[氏名]** 列と、**[活動]** グリッドの **[活動の種類]** 列では、フィルター オプションが異なります。

> [!IMPORTANT]
> 統一インターフェイスのグリッドでは、現在のビュー定義に基づいた列フィルターが事前入力されません。

   > [!div class="mx-imgBorder"]
   > ![グリッドのフィルター処理](media/filter-options.png "グリッドのフィルター処理")
   

## <a name="grid-and-filter-navigation"></a>グリッドとフィルターのナビゲーション

グリッド上のデータをフィルター処理すると、ページを離れて戻ったときに、メイン グリッド ページでフィルター、並べ替え順序、ページの状態が記憶されています。 これは、簡易検索、列フィルター、ページ番号など、データのフィルター処理方法が何であっても同じように機能します。 


   > [!div class="mx-imgBorder"]
   > ![ページに戻ると、同じ状態で表示される](media/grid-remember-state-on-back-navigate.gif "ページに戻ると、同じ状態で表示される")

ページ ジャンプ バーでは、最初に並べ替えられたフィールドが使用されます。 並べ替え順序が変更されていない場合、ジャンプ バーではプライマリ フィールドが使用されます。

   > [!div class="mx-imgBorder"]
   > ![ジャンプ バーでフィルターを選択する](media/jumpbar-filter-on-sorted-column.gif "ジャンプ バーでフィルターを選択する")
  
階層アイコンを選択すると、階層ビューに移動します。

   > [!div class="mx-imgBorder"]
   > ![階層アイコン](media/grid-row-hierarchy-icon.png "階層アイコン")

また、新しいタブまたはウィンドウで、プライマリ フィールドやルックアップ フィールドを開くこともできます。

   > [!div class="mx-imgBorder"]
   > ![新しいウィンドウで開く](media/newtab.png "新しいウィンドウで開く")
  
  
## <a name="lookup-field-column"></a>ルックアップ フィールド列

ルックアップ列でフィルター処理を行うときは、データを手動で入力するのではなく、フィルター処理するレコードの一覧から選択できます。 たとえば、**[取引先責任者]** ルックアップ列では、フィルター処理するレコードの一覧から取引先担当者名を選択できます。

   > [!div class="mx-imgBorder"]
   > ![ルックアップ フィルター処理](media/lookup-filter.png "ルックアップ フィルター処理")

## <a name="date-filter"></a>日付フィルター

堅牢な **[日付]** フィルターでは、正確な日付で検索する **[次の日付]** や、年度または四半期で検索するための **[今後 X 年の会計年度]** や **[会計期間内]** など、多くの異なる値から選択できます。

   > [!div class="mx-imgBorder"]
   > ![日付のフィルター処理](media/date-filter.png "日付のフィルター処理")

## <a name="filter-the-list-of-activities"></a>活動の一覧をフィルター処理する

活動の一覧をフィルター処理して、関心のあるものだけを表示することができます。 たとえば、活動種類フィルターを使用して、ビューに表示される活動をさらに制限することができます。 活動種類フィルターを使用すると、メール、タスク、電話などの種類に基づいて、活動をフィルター処理できます。


   > [!div class="mx-imgBorder"]
   > ![活動フィルター](media/activity_filter.png "活動フィルター")


### <a name="known-issue"></a>既知の問題 

数値、通貨、時刻、または日付の既定の表示形式を変更してから、グリッドのデータをフィルター処理すると、フィルターは選択した表示形式で表示されません。 フィルターはまだシステムの既定の形式で表示され、フィルター処理がまったく機能しない場合もあります。 

この問題を解決するには、数値、通貨、時刻、日付の表示形式を既定の設定に戻します。 

1. 右上隅にある歯車アイコン ![歯車アイコン](media/selection-rule-gear-button.png) を選択し、**[個人設定]** を選択します。

2. **[形式]** タブで、数値、通貨、時刻、日付の値を、既定の設定に戻します。

    > [!div class="mx-imgBorder"] 
    > ![形式の設定](media/default-format.png "形式の設定")
    
この問題への対処を行っていますので、修正を利用できるかどうかはもう一度ご確認ください。

  
## <a name="use-search-on-a-grid"></a>グリッドで検索を使用する

グリッド ページの **[このビューを検索]** オプションを使用すると、現在表示されているビューのデータが検索されます。 次の例では、**[取引先担当者]** グリッドで検索を行います。

1. **[取引先担当者]** グリッドに移動し、ビューの一覧から **[自分のアクティブな取引先担当者]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![[自分のアクティブな取引先担当者] ビュー](media/myactive-contacts-view.png "[自分のアクティブな取引先担当者] ビュー")

2. **[このビューを検索]** を選択検索し、表示されているビューのデータを検索します。

    > [!div class="mx-imgBorder"]
    > ![ビューを検索する](media/search-view.png "このビューを検索")

システムでは、**[自分のアクティブな取引先担当者]** ビューのデータが検索され、現在のビューで使用されているのと同じ列のセットを使用して検索結果が表示されます。

   > [!div class="mx-imgBorder"]
   > ![ビューを検索する](media/search-view2.png "[このビューを検索] コマンドの検索結果")


## <a name="use-the-quick-find-search-experience"></a>簡易ク検索の検索エクスペリエンスを使用する

エンティティの簡易検索ビュー定義を使用して検索が実行される従来のクイック検索検索エクスペリエンスに切り替えるには、管理者権限が必要です。

1. 右上隅の歯車アイコン ![歯車アイコン](media/selection-rule-gear-button.png) を選択して、**[詳細設定]** を選択します。

2. **設定** > **管理** > **システムの設定**の順に移動します。

3. **[全般]** タブの **[簡易検索の設定]** の下にある **[Use quick find view of an entity for searching on grids and sub-grids]\(グリッドとサブグリッドの検索にエンティティの簡易検索ビューを使用する\)** で、**[はい]** を選択します。





