---
title: グリッド上のデータのフィルター |MicrosoftDocs
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 02/03/2019
ms.author: mkaur
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 2cfe55db19b5d8a7aeed86169a188455686cf81b
ms.sourcegitcommit: 68a31e3fa4d1635ccf4cd8bd9da5fba1bfecefa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051973"
---
# <a name="use-grid-filters"></a>グリッドフィルターを使用する 

統合インターフェイスのグリッドが改善され、画面に表示できるデータの量が増加しました。 列のさまざまなフィルター処理オプションから選択できるようになりました。列のデータの種類によって、使用できるフィルターオプションが決まります。 たとえば、 **[連絡先]** グリッドの **[フルネーム]** 列には、 **[アクティビティ]** グリッドの **[アクティビティの種類]** 列とは異なるフィルターオプションがあります。


   > [!div class="mx-imgBorder"]
   > ![グリッドフィルター処理](media/filter-options.png "グリッドフィルター処理")
   

## <a name="grid-and-filter-navigation"></a>グリッドとフィルターのナビゲーション

グリッド上のデータをフィルター処理する場合、メイングリッドページでは、移動後にページに戻ると、フィルター、並べ替え順序、およびページの状態が記憶されます。 これは、データが [クイック検索]、[列フィルター]、[ページ番号] でフィルター処理されている場合にも同じように機能します。 

   > [!div class="mx-imgBorder"]
   > ![ページに戻ると、同じ状態で表示されます。](media/grid-remember-state-on-back-navigate.gif "ページに戻ると、同じ状態で表示されます。")

ページジャンプバーでは、最初に並べ替えられたフィールドを使用します。 並べ替え順序に変更が加えられていない場合、ジャンプバーはプライマリフィールドを使用します。

   > [!div class="mx-imgBorder"]
   > ![ジャンプバーでフィルターを選択する](media/jumpbar-filter-on-sorted-column.gif "ジャンプバーでフィルターを選択する")
  
階層アイコンを選択すると、[階層] ビューに移動します。

   > [!div class="mx-imgBorder"]
   > ![階層アイコン](media/grid-row-hierarchy-icon.png "[階層] アイコン")

また、新しいタブまたはウィンドウで、プライマリフィールドとルックアップフィールドを開くこともできます。

   > [!div class="mx-imgBorder"]
   > ![新しいウィンドウで開く](media/newtab.png "[新しいウィンドウで開く]")
   
   
### <a name="known-issue"></a>既知の問題

数値、通貨、時刻、または日付の既定の表示形式を変更し、グリッドのデータをフィルター処理すると、選択した表示形式はフィルターに表示されません。 フィルターはシステムの既定の形式で表示されますが、フィルターがまったく機能しない場合もあります。 

この問題を解決するには、数値、通貨、時刻、日付の表示形式を既定の設定に戻します。 

1. 右上隅にある歯車アイコン ![歯車アイコン](media/selection-rule-gear-button.png)を選択し、 **[パーソナル設定]** を選択します。

2. **[書式]** タブで、数値、通貨、時刻、および日付の値を既定の設定に戻します。

    > [!div class="mx-imgBorder"] 
    > ![書式設定](media/default-format.png "書式設定")
    
    
  問題に取り組んでいます。もう一度ご確認ください。 



## <a name="preview-new-grid-filters-and-search-option"></a>プレビュー: 新しいグリッドフィルターと検索オプション

このセクションは、早期アクセス機能を対象としています。 環境でこれらの機能を有効にするために、早い段階で選択できます。 これにより、これらの機能をテストして、環境全体に導入することができます。 これらの機能を有効にする方法の詳細については、「 [2020 リリース wave 1 更新プログラムのオプトイン](https://docs.microsoft.com/power-platform/admin/opt-in-early-access-updates)」を参照してください。


   > [!NOTE]
   > 時刻、数値、通貨、時刻、または日付の既定の表示形式を変更しないでください。これにより、このような問題が発生します。 詳細については、「[既知の問題](https://docs.microsoft.com/powerapps/user/grid-filters#known-issue)」を参照してください。

### <a name="lookup-field-column"></a>ルックアップフィールド列

参照列でフィルター処理を行う場合は、データを手動で入力するのではなく、フィルター処理するレコードの一覧から選択できます。 たとえば、**主要連絡先**の参照列では、フィルター処理するレコードの一覧から連絡先名を選択できます。

   > [!div class="mx-imgBorder"]
   > ![参照のフィルター処理](media/lookup-filter.png "参照のフィルター処理")

### <a name="date-filter"></a>日付フィルター

堅牢な**日付**フィルターには、 **[** 次の日付で検索する]、 **[次の X 会計年度]** 、または **[会計期間]** (年または四半期) で検索する など、選択するさまざまな値が含まれます。

   > [!div class="mx-imgBorder"]
   > ![日付のフィルター処理](media/date-filter.png "日付のフィルター処理")

### <a name="filter-the-list-of-activities"></a>アクティビティの一覧をフィルター処理する

アクティビティの一覧をフィルター処理して、関心のあるものだけを表示することができます。 たとえば、[アクティビティの種類] フィルターを使用して、ビューに表示するアクティビティをさらに制限することができます。 [アクティビティの種類] フィルターを使用すると、電子メール、タスク、電話などの種類に基づいてアクティビティをフィルター処理できます。


   > [!div class="mx-imgBorder"]
   > ![アクティビティフィルター](media/activity_filter.png "アクティビティフィルター")


#### <a name="known-issue"></a>既知の問題

数値、通貨、時刻、または日付の既定の表示形式を変更し、グリッドのデータをフィルター処理すると、選択した表示形式はフィルターに表示されません。 フィルターはシステムの既定の形式で表示されますが、フィルターがまったく機能しない場合もあります。 

この問題を解決するには、数値、通貨、時刻、日付の表示形式を既定の設定に戻します。 

1. 右上隅にある歯車アイコン ![歯車アイコン](media/selection-rule-gear-button.png)を選択し、 **[パーソナル設定]** を選択します。

2. **[書式]** タブで、数値、通貨、時刻、および日付の値を既定の設定に戻します。

    > [!div class="mx-imgBorder"] 
    > ![書式設定](media/default-format.png "書式設定")
    
    
問題に取り組んでいます。もう一度ご確認ください。 
  
### <a name="use-search-on-a-grid"></a>グリッドで検索を使用する

グリッドページで [**このビューを検索**する] オプションを使用すると、現在使用しているビューのデータが検索されます。 次の例では、 **[連絡先]** グリッドで検索を実行します。

1. **[Contacts]** グリッドにアクセスし、ビューの一覧から **[My Active Contacts]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![自分のアクティブな連絡先ビュー](media/myactive-contacts-view.png "自分のアクティブな連絡先ビュー")

2. [**このビューを検索**する] を選択して、表示されているデータを検索します。

    > [!div class="mx-imgBorder"]
    > ![検索ビュー](media/search-view.png "このビューを検索します")

システムは、 **[自分のアクティブな連絡先**] ビューでデータを検索し、現在のビューで使用されているのと同じ列のセットを使用して検索結果を表示します。

   > [!div class="mx-imgBorder"]
   > ![検索ビュー](media/search-view2.png "[この表示を検索] コマンドの検索結果")


#### <a name="use-the-quick-find-search-experience"></a>クイック検索の検索エクスペリエンスを使用する

エンティティのクイック検索ビュー定義を使用して検索を実行する従来のクイック検索検索エクスペリエンスに切り替えるには、管理者権限が必要です。

1. 右上隅にある歯車アイコン ![歯車アイコン](media/selection-rule-gear-button.png)を選択し、 **[詳細設定]** を選択します。

2. **設定** > **管理** > **システム設定** にアクセスします。

3. **[全般]** タブの **[クイック検索の設定]** で、**グリッドおよびサブグリッドで検索するエンティティの [クイック検索] ビューを使用**する場合は [**はい]** を選択します。



