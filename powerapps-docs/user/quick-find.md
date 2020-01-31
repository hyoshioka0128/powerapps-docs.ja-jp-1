---
title: クイック検索 |MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 1/28/2020
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 23152da4aa8d50247f4132399c25861dbc7a66ac
ms.sourcegitcommit: 4d858e628c89d245317d6192801d136f3591ea52
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "76832356"
---
# <a name="using-quick-find-to-search-for-records"></a>クイック検索を使用してレコードを検索する

## <a name="single-entity-quick-find"></a>単一エンティティのクイック検索

単一エンティティのクイック検索は、1つの種類のレコードのみを検索するために使用されます。 この検索オプションは、ビュー内から使用できます。 

   > [!div class="mx-imgBorder"]
   > ![単一エンティティのクイック検索](media/single-quick-find-search-box.png "単一エンティティのクイック検索の検索ボックス") 

## <a name="multi-entity-quick-find-categorized-search"></a>複数エンティティのクイック検索 (分類された検索)

複数エンティティのクイック検索は、分類された検索とも呼ばれます。 

1.  分類された検索を開始するには、上部のナビゲーションバーで **[検索]** ボタンを選択します。  

     > [!div class="mx-imgBorder"]
     > ![グローバル検索ボタン](media/global-search-button.png "グローバル検索ボタン")   
  
2.  検索ボックスに検索語句を入力し、 **[検索]** ボタンを選択します。 分類された検索は、勘定科目や連絡先などのエンティティの種類別にグループ化された結果を返します。

     > [!div class="mx-imgBorder"]
     > ![分類された検索結果](media/categorized-search-results.png "分類された検索結果ページ") 

分類された検索では、特定の単語で始まるレコードを検索したり、ワイルドカードを使用したりできます。
  
- 次**で始まる**: 結果には、特定の単語で始まるレコードが含まれます。 たとえば、"Alpine Ski House" を検索する場合は、検索ボックスに「 **alp** 」と入力します。「 **ski**」と入力した場合、レコードは表示されません。  
  
- **ワイルドカード**: たとえば、* ski または * ski\*です。 

  > [!NOTE]
  >  クイック検索 (単一または複数のエンティティ) の検索クエリの先頭でワイルドカードを使用すると、パフォーマンスが低下する可能性があります。
  
## <a name="filter-categorized-search-results"></a>分類された検索結果のフィルター処理 
  
-   レコードの種類によって結果をフィルター処理するには、 **[フィルター]** ボックスの一覧からレコードの種類を選択します。 

    > [!div class="mx-imgBorder"]
    > ![カテゴリ化された検索結果のフィルター処理](media/filter-categorized-search-results.png "カテゴリ化された検索結果のフィルター処理")  

  
-   すべてのレコードの種類を検索するには、 **[フィルター]** ボックスの一覧から **[なし]** を選択します。  


