---
title: Power Apps のモデル駆動型アプリのメイン フォーム用簡易表示コントロールのプロパティ | MicrosoftDocs
description: メイン フォーム用簡易表示コントロールのプロパティについて
Keywords: 簡易表示コントロールのプロパティ; Dynamics 365; メイン フォーム
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 05/04/2020
ms.service: powerapps
ms.topic: article
ms.assetid: 68f68d5b-6c71-4b95-bb46-d48c59d9008e
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: a76269092be62d2e8bb99138fb35b521cebb1f9c
ms.sourcegitcommit: 52b7f59e271437e86ffff226fb6c1982bf7f08b1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "3332435"
---
# <a name="model-driven-app-quick-view-control-properties"></a>モデル駆動型アプリの簡易表示コントロールのプロパティ

モデル駆動型アプリ フォームの簡易表示コントロールには、フォーム内の検索フィールドで選択されたレコードのデータが表示されます。 コントロールに表示されるデータは、簡易表示フォームを使用して定義します。 表示されたデータは編集できませんが、主フィールドが簡易表示フォームに含まれると、関連のレコードを開くリンクになります。 詳細: [簡易表示フォームの作成および編集](create-edit-quick-view-forms.md)  

> [!div class="mx-imgBorder"] 
> ![取引先企業フォームの取引先担当者簡易表示フォーム](media/quick-view-form-contact.png "取引先企業フォームの取引先担当者簡易表示フォーム")  

1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。  

3.  **種類**が**メイン**のフォームを選択します。

4.  フォーム デザイナーで、**コンポーネントの追加**を選択します。

5.  左のナビゲーション ウィンドウで、**簡易表示**を選択します。

6.  **簡易表示フォームの選択**ダイアログ ボックスで、フォームに含まれている**検索**フィールドを選択してから、関連するエンティティの簡易表示フォームを選択します。 表示される関連エンティティは、選択する**検索**フィールドによって異なります。  

    > [!div class="mx-imgBorder"] 
    > ![簡易表示コントロールの追加](media/select-quick-view-form.png "簡易表示コントロールをメイン フォームに追加する")

7.  **完了** を選択して **簡易表示フォームの選択** ダイアログ ボックスを閉じます。 簡易表示フォームがフォームに表示され、簡易表示のプロパティがプロパティ ウィンドウに表示されます。

|プロパティ|内容|  
|--------------|-----------------|  
|**ラベル**|**必須**: 簡易入力フォームに表示されるラベル。|  
|**名前**|**必須**: スクリプト内で簡易表示フォームが参照されたとき使用される一意の名前。|  
|**ラベルの非表示**|フォームでラベルを表示します。| 
|**簡易表示フォーム**|関連エンティティに対して選択した簡易表示フォームを一覧表示します。 
|**フォームの選択**|関連エンティティに対して選択した簡易表示フォームを選択または変更します。 表示される関連エンティティは、選択する**検索**フィールドによって異なります。|  
|**コンポーネント**|コンポーネントに構成するプロパティ。 簡易表示コントロール コンポーネントには構成するプロパティがなく、既定では、ユーザーが Web ブラウザー、電話用 Dynamics 365、またはタブレット PC 用 Dynamics 365 を使用しているかどうかが表示されます。

## <a name="quick-view-control-properties-in-classic-form-designer"></a>クラシック フォーム デザイナーの簡易表示コントロール プロパティ

1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。 

3.  フォームの一覧で、種類が**メイン**のフォームを開きます。

4.  コマンド メニューで、**クラシックに切り替え**を選択します。

5.  次に**挿入**タブで、**簡易表示フォーム**を選択して簡易表示コントロールのプロパティを表示します。

    > [!div class="mx-imgBorder"] 
    > ![簡易表示コントロール](media/quick-view-control.png)
  
|プロパティ|説明|  
|--------------|-----------------|  
|**名前**|**必須**: スクリプト内で簡易表示フォームが参照されたとき使用される一意の名前。|  
|**ラベル**|**必須**: 簡易入力フォームに表示されるラベル。|  
|**フォームでラベルを表示する**|フォームでラベルを表示します。|  
|**検索フィールド**|フォームに含まれる検索フィールドの 1 つを選択します。|  
|**関連エンティティ**|この値は、選択する**ルックアップ フィールド**によって異なります。 通常、検索の1:N のエンティティ関連付けの主エンティティです。<br /><br /> エンティティが取引先企業か取引先担当者のいずれかを受け入れる**見込み顧客**検索を含む場合、**簡易表示フォーム**フィールドで、取引先企業と取引先担当者両方に対する簡易表示フォームを選択できます。これは、この値を変更してから別の簡易表示フォームを選択することでできます。|  
|**簡易表示フォーム**|**関連エンティティ**に簡易表示フォームがある場合は、ここで選択できます。 そうしない場合は、**新規**を選択して作成します。<br /><br /> **編集**を選択して、選択した簡易表示フォームを変更します。|  
|**追加のプロパティ**|チェック ボックスを選択して、既定のレンダリング スタイルを指定することができます。|

>[!NOTE] 
> 簡易表示フォームに複数行のテキスト フィールドを追加すると、フィールド コントロールの高さの設定に関係なく、フォームの高さが 1 になります。 これにより、密度を維持しながらフォームを適切にレンダリングできます。 メイン フォームなど、他のフォーム タイプの複数行テキスト フィールドは、テキストの量に基づいてフォームが自動的に拡張されるため、動作が異なります。 


## <a name="next-steps"></a>次のステップ

[メイン フォームとそのコンポーネントの使用](use-main-form-and-components.md)
 
