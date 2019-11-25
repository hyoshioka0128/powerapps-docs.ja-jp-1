---
title: PowerApps を使用してモデル駆動型アプリで Bing マップを構成する | MicrosoftDocs
ms.custom: ''
ms.date: 10/18/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: f9729664-561c-4758-86ce-7216d68075d9
caps.latest.revision: 63
ms.author: matp
author: Mattp123
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ff7f5c01e913da60409bb60c637b37ebd4bfa096
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2756481"
---
# <a name="configure-a-map-on-a-form"></a>フォームのマップを構成する
既定では、Bing マップ コントロールは取引先企業エンティティと取引先担当者エンティティの両方のメイン フォームで構成され、エンティティ レコードにマップを表示する機能を提供します。 規定では構成されていませんが、Bing マップ コントロールをシステム ユーザー エンティティに追加できます。 Bing マップ コントロールは、Dynamics 365 Sales や Dynamics 365 Customer Service など、Dynamics 365 のモデル駆動型アプリに含まれる一部のエンティティでも使用できます。 例えば、潜在顧客、見積もり、受注、請求書、競合企業などのエンティティです。 Bing マップ コントロールは、ユーザー定義エンティティでは使用できません。  

有効にすると、マップには、指定されたレコードのアドレス複合フィールドで指定された場所が表示されます。 

> [!div class="mx-imgBorder"] 
> ![アプリの Bing マップ コントロール](media/bing-map-example.png "アプリの Bing マップ コントロール")

> [!IMPORTANT]
> Bing マップを使用するには、システム設定「フォームに Bing マップを表示する」を有効にする必要があります。 詳細: [環境でマップを有効にする](#enable-maps-for-your-environment)

フォーム エディターのマップ領域を削除したり、クラシック フォーム エディターの**挿入**タブの **Bing マップ**ボタンを使用して追加し直すこともできます。

## <a name="enable-maps-for-your-environment"></a>環境でマップを有効にする
1. モデル駆動型アプリを開き、**設定** > **詳細設定**を選択します。 
2. **設定** > **管理** > **システムの設定**の順に選択します。 
3. **全般**タブで、**フォームに Bing マップを表示する**を選択した後、**OK** を選択します。 
 
    ![フォームのマップを有効にする](media/enable-maps.png)

## <a name="configure-a-map"></a>マップを構成する 
1. [PowerApps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。 
2. **データ** > **エンティティ**へと移動し、メイン フォームでマップを構成するエンティティを選択します。 
3. **フォーム** タブを選択した後、メイン フォームを選択し、コマンド バーで**クラシックに切り替え**を選択します。 
4. クラシック フォーム デザイナーで**マップ ビュー**をダブルクリックし、プロパティを表示および編集します。 詳細:  [マップ プロパティの表示および編集](#view-and-edit-map-properties)

    ![マップ ビュー コントロール](media/map-view-control.png)

マップ コントロールをフォームから削除するには、**マップ ビュー** コントロールを選択し、Delete キーを押します。

## <a name="view-and-edit-map-properties"></a>マップ プロパティの表示および編集

|      タブ       |                        プロパティ                         |                                                                                                  説明                                                                                                   |
|----------------|---------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  **一般**   |                        **ラベル**                        |                                                                              **必須**: Bing マップに表示されるラベル。                                                                               |
|                |              **フォームでラベルを表示する**              |                                                                                     ラベルを表示するかどうか。                                                                                     |
|                | **この Bing マップ コントロールで使用するアドレスを選択します** |                                                                        マップにデータを提供するのに使用するアドレスを選択します。                                                                        |
|                |                 **既定で表示する**                  | Bing マップの表示は任意で、業務ルールまたはスクリプトを使用して制御できます。 詳細情報: [表示オプション](visibility-options-legacy.md) |
| **形式** |  **コントロールが使用する列数を指定してください**  |                              Bing マップを含むセクションに複数の列があるとき、フィールドがセクションにある列の数まで占めるように設定できます。                              |
|                |   **コントロールが使用する行数を指定してください**    |                                                                  列数を指定することで、Bing マップの高さを制御できます。                                                                   |
|                |     **自動拡張して、使用可能なスペースを広げます**     |                                                                        Bing マップの高さを使用可能なスペースまで広げることができます。                                                                        |

### <a name="see-also"></a>関連項目
[モデル駆動型アプリ フォームを作成および設計する](create-design-forms.md) 
