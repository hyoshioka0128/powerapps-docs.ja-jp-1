---
title: Power Apps でモデル駆動型アプリの簡易作成ビューを作成、編集する | MicrosoftDocs
description: 簡易表示フォームの作成または編集の方法を学習する
ms.custom: ''
ms.date: 03/13/2020
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 9b101734-cc11-4d05-bd45-eb611eae9931
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1e94b836fc7718f3aa259b677edc58419c98af06
ms.sourcegitcommit: 9f2694bd14d70798310b89a4673672c1bfad989d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "3167107"
---
# <a name="create-a-model-driven-app-quick-view-form-to-view-information-about-a-related-entity"></a>モデル駆動型アプリの簡易表示フォームを作成して関連エンティティに関する情報を表示する

このトピックでは、簡易ビュー フォームを作成する方法、および簡易ビュー コントロールをメイン フォームに追加する方法について説明します。 

簡易表示フォームを別のフォームに簡易表示コントロールとして追加できます。 簡易表示フォームは、別のエンティティ レコードのフォーム内の関連エンティティ レコードに関する情報を表示するテンプレートを提供します。 これにより、アプリ ユーザーは、仕事の遂行に必要な情報を確認するために、別のレコードに移動する必要がなくなります。  
  
 簡易表示コントロールは、フォームに含まれる検索フィールドに関連付けられています。 検索フィールド値が設定されていない場合は、簡易表示コントロールは表示されません。 簡易表示コントロールのデータは編集できません。また簡易表示フォームはフォーム スクリプトをサポートしません。  
  
 簡易表示フォームはフォームの簡易表示コントロールを使用して表示されるので、簡易表示フォームには、見出し、フッター、またはナビゲーション領域は含まれません。 セキュリティ ロールは簡易表示フォームに割り当てることはできないし、アクティブ化または非アクティブ化することはできません。  
  
<a name="BKMK_CreateQFV"></a>   
## <a name="create-a-quick-view-form"></a>簡易表示フォームの作成  
 簡易表示フォームは、他のフォームの作成と同様な方法で、フォーム エディターを使用して作成されます。 簡易表示フォームは読み取り専用です。 これを使用して、読み取り専用のフォームを作成します。  
  
1. [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2. **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。 
  
3. ツール バーで、**フォームの追加** > **簡易ビュー フォーム** を選択します。  
  
5. **フォーム** ウィンドウで、**表示名** と **説明** を入力して、この簡易表示フォームを他の簡易表示フォームと区別します。  
  
6. フォーム デザイナーで **フィールド エクスプローラー**からフィールドをフォームのセクションにドラッグします。

    > [!IMPORTANT]
    > 必須フィールドはフォームから削除できません。 必須フィールドをフォームに追加して削除したい場合は、フォームを削除してから再度作成する必要があります。 フィールドの必須プロパティを設定すると、このフィールドにデータがないとレコードを保存できません。

7. フォームを保存するには **保存** を選択します。  

8. アプリケーション内で新しいフォームを表示するために **公開** を選択します。 <!-- Which app? What does Publish do?-->
  
<a name="BKMK_EditQVF"></a>   
## <a name="edit-a-quick-view-form"></a>簡易表示フォームの編集  
 簡易表示フォームは、フォーム セクション内に表示されるように設計されているため、レイアウトが単純化されています。 利用できるタブは 1 つだけです。 別の単一の列セクション、フィールド、サブグリッド、およびスペーサーのみを追加できます。   
  
  > [!IMPORTANT]
  > 必須フィールドは削除できません。 必須フィールドをフォームに追加した場合、それを削除することはできません。 フォームでこのフィールドが必要ない場合は、フォーム全体を削除してフォームを再度作成する必要があります。
  
 簡易表示フォームを編集したとき、変更をアプリケーションで表示できるようにするには、その前に、変更を公開する必要があります。  
  
<a name="BKMK_AddQVF"></a>   
## <a name="add-a-quick-view-control-to-a-main-form"></a>メイン フォームへの簡易表示コントロールの追加  
 簡易表示フォームは、簡易表示フォームのエンティティを対象とした検索フィールドが存在するメイン フォームにのみ追加できます。  
  
1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。  

3. **種類**が**メイン**のフォームを選択します。

4. フォーム デザイナーの [コンポーネント] ウィンドウで、**クイックビュー** を選択します。  
  
5.  **クイックビュー フォームを選択** ダイアログボックスで **検索** フィールドをクリックし、検索フィールドの値を選択します。 詳細情報: [簡易表示フォーム プロパティ](quick-view-control-properties-legacy.md).  

    > [!div class="mx-imgBorder"] 
    > ![簡易表示コントロールの追加](media/add-quick-view-control.png "簡易表示コントロールをメイン フォームに追加する")

6.  **完了** を選択して **簡易表示フォームの選択** ダイアログ ボックスを閉じます。 簡易表示フォームがフォームに表示されます。

7.  フォームを保存するには **保存** を選択します。  

## <a name="next-steps"></a>次のステップ   
 [フォームの作成および設計](create-design-forms.md)   
 [簡易作成フォームの作成または編集](create-edit-quick-create-forms.md)
