---
title: モデル駆動型アプリのビューでフィルターを作成、編集する | MicrosoftDocs
description: アプリのフィルターまたはビューを作成、編集する方法を説明します
keywords: 式ビルダー
ms.date: 2/04/2020
ms.service: powerapps
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: ''
author: iangpgh
ms.author: v-iapr
manager: matp
ms.reviewer: srihas
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 3a36cf57710da4e6306c7de48e19d4af6c722f10
ms.sourcegitcommit: abdc8c609a7a221ce4ca6b051a84b7083bdbe1ab
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "3225589"
---
# <a name="create-or-edit-filters-in-model-driven-app-views"></a>モデル駆動型アプリのビューでフィルターを作成、編集する

<a name="BKMK_CreateOrEditViewFilters"></a>   

Power Apps ビューのフィルターは、ビューが提供される値にとって重要となります。 適用するフィルタによって、既定でリストに表示されるレコードが決定されます。 列を選択して **フィルター** を選択すると、ビューに含める列のフィルタを追加または編集できます。 ビュー デザイナーで式ビルダーを使用することもできます。 式ビルダを使用すると、現在のビューのエンティティの任意のフィールド、または関連するエンティティの任意のフィールドのフィルターを追加または編集できます。 

このトピックでは、次のタスクを実行して、フィルターを作成または編集します。

-   [条件の追加、編集、削除](create-edit-view-filters.md#edit-or-remove-a-filter-condition)

-   [式ビルダーを起動する](create-edit-view-filters.md#open-the-expression-builder)

-   [フィルターに条件を追加する](create-edit-view-filters.md#add-conditions-to-a-filter)

-   [グループ条件をフィルターに追加する](create-edit-view-filters.md#add-a-group-condition-to-a-filter)

-   [関連するエンティティを条件に追加する](create-edit-view-filters.md#add-a-related-entity-to-a-condition)

-   [フィルターのグループ条件](create-edit-view-filters.md#group-conditions-of-a-filter)

## <a name="edit-or-remove-a-filter-condition"></a>条件の追加、編集、削除

1. [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2. **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**ビュー** タブを選択します。

3. ビューを選択して開きます。 ビューのプロパティ パネルには、既存のフィルターが一覧表示されます。

    > [!div class="mx-imgBorder"] 
    > ![ビュー パネル フィルター](media/views-panel-filters.png "ビュー パネル フィルター")

4. ビューのプロパティ パネルで、フィルター条件を選択します。

    > [!div class="mx-imgBorder"] 
    > ![フィルターの編集](media/edit-filter-viewpanel.png "フィルターの編集")

5. 使用する条件の演算子を選択します。

6. 条件の比較値を入力または選択します。

7. **適用**を選択します。

8. 条件を削除するには、**閉じる** を選択します。 確認が表示されることなく、条件が削除されます。

### <a name="open-the-expression-builder"></a>式ビルダーを起動する

- ビューのプロパティ パネルで、**フィルターの編集** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![式ビルダー](media/edit-create-filters.png "式ビルダー")

### <a name="add-conditions-to-a-filter"></a>フィルターに条件を追加する

1. 式ビルダーで、**追加** > **行の追加**を選択します。

2. 条件のフィールドを選択します。

3. 条件の演算子を選択します。

4. 比較値を選択します。  

    フィルター条件の中には、条件の比較値を必要としないものがあります。 たとえば、演算子**データを含む** には、比較値は必要ありません。 他のフィルター条件では、オプション セットから比較値を選択します。 たとえば、 **状態** フィールドには、 **アクティブ** と **非アクティブ** 値を含むオプション セットがあります。

    > [!div class="mx-imgBorder"] 
    > ![フィルターの条件](media/add-condition-filter.png "フィルターの条件")

5. **OK** を選びます。

### <a name="add-a-group-condition-to-a-filter"></a>グループ条件をフィルターに追加する

1. 式ビルダーで、**追加** > **グループの追加**を選択します。

2. グループに、関係演算子 **または**を選択します。 **かつ** は、既定の関係演算子です。

3. グループ化された条件の最初の句を指定します。 フィールド、条件演算子、比較値を選択します。

4. **追加** > **グループの追加** を選択します

5. グループ化された条件の２番目の句を指定します。

    > [!div class="mx-imgBorder"] 
    > ![グループ条件フィルター](media/add-group-filter.png "グループ条件フィルター")

    **折りたたむ**を選択して、グループを条件式として表示します。

### <a name="add-a-related-entity-to-a-condition"></a>関連するエンティティを条件に追加する

1. 式ビルダーで、**追加** > **関連するエンティティの追加** を選択します。

2. 別のエンティティに関連付けられている現在のエンティティからフィールドを選択します。 フィールドに関連するエンティティはカッコ内に表示されます。 関連エンティティと多対1、1対多、または多対多の関係を持つフィールドを選択できます。

3. 条件に関連するエンティティのフィールドを選択します。

4. 条件の演算子を選択します。

5. 比較値を選択または入力します。

    > [!div class="mx-imgBorder"] 
    > ![関連エンティティのフィルター](media/add-relatedentity-filter.png "関連エンティティのフィルター")

### <a name="group-conditions-of-a-filter"></a>フィルターのグループ条件

1. 式ビルダーで、グループ化する条件のチェックボックスをオンにします。

2. いずれかの条件に対して **その他のコマンド**（...）を選択し、**グループを作る** を選択します。

3. グループ化を解除するには、当該グループで **その他のコマンド** (...) を選択し、続いて **グループ解除** を選択します

    > [!div class="mx-imgBorder"] 
    > ![グループ化された条件のフィルター](media/group-conditions-filter.png "グループ化された条件のフィルター")

### <a name="see-also"></a>関連項目
[高度なグリッド フィルターを使用して個人用ビューを編集または作成する](../../user/grid-filters-advanced.md)
[列を選択して構成する](choose-and-configure-columns.md)  
[フィルター条件の編集](edit-filter-criteria.md)  
[1:N (一対多) または N:1 (多対一) の関連付けを作成する](../common-data-service/create-edit-1n-relationships.md)
