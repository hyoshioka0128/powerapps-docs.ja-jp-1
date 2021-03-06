---
title: Power Apps のモデル駆動型アプリのメイン フォーム用セクションのプロパティ | MicrosoftDocs
description: メイン フォームのセクション プロパティについて
Keywords: メイン フォーム; セクションのプロパティ; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 03/23/2020
ms.service: powerapps
ms.topic: article
ms.assetid: 2d3af6e9-e8a4-4129-b708-383b2740c015
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 25d2edd58bf146f9537af87a0b7564b4ce421395
ms.sourcegitcommit: 9f2694bd14d70798310b89a4673672c1bfad989d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "3166579"
---
# <a name="model-driven-app-form-section-properties"></a>モデル駆動型アプリ フォームのセクション プロパティ

 フォーム内のセクションは、タブ列で使用可能なスペースを占めます。 セクションには、表示できるラベルとラベルの下に表示される線があります。  
  
 セクションには 4 個まで列を含めることができ、セクションでフィールドのラベルを表示する方法を設定するオプションが含まれます。  
  
 ヘッダーとフッターはセクションと似てますが、削除することはできません。 何も含まれていない場合、表示されません。

## <a name="section-properties-in-form-designer"></a>フォーム デザイナーのセクション プロパティ

1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。 

3.  フォームの一覧で、種類が**メイン**のフォームを開きます。 別のタブでフォームを開くには、**その他のコマンド** ![その他のコマンド ボタン](media/more-commands.gif "フォームの その他のコマンド ボタン") を選択し、**編集フォーム** > **新しいタブでフォームを編集** を選択します。

4.  セクションのプロパティを表示するにはセクションの 1 つを選択します。

    > [!div class="mx-imgBorder"]
    > ![section-properties](media/new-section-properties.png "フォーム デザイナーのセクション プロパティ")

|プロパティ|説明|  
|---------|--------------|  
|**セクション ラベル**|**必須**: ユーザーに表示されるセクションのローカライズ可能なラベル。|  
|**名前**|**必須**: スクリプト内でセクションが参照されたとき使用される一意の名前。 名前には、英数字とアンダースコアのみを使用できます。|  
|**ラベルの非表示**|セクションは、セクション内のフィールドの書式を制御するのにラベルなしでしばしば使用されます。|
|**セクションのロック**|これは通常、セクションが誤って削除されることを防止したり、ユーザーが内容を削除することを防ぎます。<br /><br /> セクションを削除すると、セクションを削除するだけでなく、その中のフィールドも削除します。<br /><br /> このセクションを削除する場合、削除する前にこの設定を変更する必要があります。|  
|**セクションの非表示**|セクションの表示は任意で、スクリプトを使用して管理します。 詳細情報: [表示オプション](visibility-options-legacy.md)|  
|**電話の非表示**|タブを電話で使用できるようにするかどうかを選択します。|  
|**形式**|セクション内に最高 4 個の列を指定します。|  

## <a name="section-properties-in-classic-form-designer"></a>クラシック フォーム デザイナーのセクション プロパティ

Power Apps サイトからソリューション エクスプローラーの **セクションのプロパティ** にアクセスすることができます。

1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。  

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。 

3.  フォームの一覧で、種類が**メイン**のフォームを開きます。 

4.  **クラシックに切り替える** を選択して、クラシック フォーム デザイナーでフォームを編集します。

5.  セクションのプロパティを表示するには、いずれかのセクションの内部をダブルクリックします。 

    > [!div class="mx-imgBorder"]
    > ![section-properties](media/section-properties.png "ソリューション エクスプローラーのセクション プロパティ")
  
|タブ|プロパティ|説明|  
|---------|--------------|-----------------|  
|**表示**|**名前**|**必須**: スクリプト内でセクションが参照されたとき使用される一意の名前。 名前には、英数字とアンダースコアのみを使用できます。|  
||**ラベル**|**必須**: ユーザーに表示されるセクションのローカライズ可能なラベル。|  
||**このセクションのラベルをフォーム上に表示**|セクションは、セクション内のフィールドの書式を制御するのにラベルなしでしばしば使用されます。|  
||**セクションの上端に線を表示する**|セクションの上端の線で、フォーム レイアウトを区分できます。|  
||**フィールド ラベルの幅**|**必須**: 50 から 250 の値を設定して、フィールド ラベルに許可するスペースを指定します。<br /><br /> ヘッダーおよびフッター要素には、このプロパティがあります。|  
||**表示**|セクションの表示は任意で、スクリプトを使用して管理します。 詳細情報: [表示オプション](visibility-options-legacy.md)|  
||**使用可否**|タブを電話で使用できるようにするかどうかを選択します。|  
||**フォームでセクションをロックする**|これは通常、セクションが誤って削除されることを防止したり、ユーザーが内容を削除することを防ぎます。<br /><br /> セクションを削除すると、セクションを削除するだけでなく、その中のフィールドも削除します。<br /><br /> このセクションを削除する場合、削除する前にこの設定を変更する必要があります。|  
|**形式**<br /><br /> ヘッダーおよびフッターコンポーネントには、このプロパティがあります。|**レイアウト**|セクション内に最高 4 個の列を指定します。|  
||**フィールド ラベルの配置**|セクション内のフィールドのラベルを、左、右または中央に配置することができます。|  
||**フィールド ラベルの位置**|セクション内のフィールドのラベルは、フィールドの横または上に置くことができます。|  


**参照パネル**と呼ばれる新しい種類のセクションを追加することもできます。 参照パネルは、1 つの列セクションです。 サブグリッド、簡易表示コントロール、またはサポート情報検索コントロールを、参照パネル セクションに挿入することができます。 参照パネルで追加した各コントロールは、実行時にパネル内で垂直タブとして表示されます。 参照パネル セクション内にあるさまざまなコントロールをドラッグ アンド ドロップすることができます。 実行時の既定のタブは、参照パネルに追加される最初のコントロールです。 その他のタブは、フォーム エディターに追加された順序で表示されます。 タブを削除するには、キーボードの Del キーを使用します。  
  
参照パネルを挿入すると、既定でタブの最後のセクションとして追加されます。フォームごとに 1 つの参照パネルのみを追加することができます。  
  
> [!IMPORTANT]
>  [サポート案件]、[取引先企業]、[取引先担当者] というこれらの標準のフォームでは、既定で参照パネル セクションがロックされています。 削除または変更するには、ロックを解除する必要があります。 

## <a name="next-steps"></a>次のステップ

[メイン フォームとそのコンポーネントの使用](use-main-form-and-components.md)
