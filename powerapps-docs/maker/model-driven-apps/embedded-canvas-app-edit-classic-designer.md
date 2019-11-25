---
title: モデル駆動型フォーム上でキャンバス アプリを編集 | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
- PowerApps maker portal impact
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: cb265233e0d72e7350603b496f91e6d62e32002d
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2758505"
---
# <a name="edit-a-canvas-app-embedded-on-a-model-driven-form"></a>モデル駆動型フォーム上でキャンバス アプリを編集
このトピックでは、モデル駆動型フォームに埋め込まれたキャンバス アプリを編集する方法を説明します。

## <a name="edit-the-canvas-app-directly"></a>キャンバス アプリを直接編集します。
そのほかのキャンバス アプリと同様に、モデル駆動型フォームに埋め込まれたキャンバス アプリを編集できます。 キャンバス アプリの編集手順については [キャンバス アプリの編集](../canvas-apps/edit-app.md) を参照ください。

## <a name="edit-the-canvas-app-via-the-host-model-driven-form"></a>ホストのモデル駆動型フォームを介してキャンバス アプリを編集します。
代替オプションは、ホストのモデル駆動型フォームを介して埋め込みキャンバス アプリを編集することです。

取引先企業エンティティの取引先企業メイン フォームという名前のファームに埋め込まれたキャンバス アプリを編集するとします。 これを行うには、次の手順を実行します。 

1.  [PowerApps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。
2.  取引先企業エンティティの取引先企業メイン フォームいう名前の [フォームを編集します](create-and-edit-forms.md) 。 
3.  コマンドバーの **クラシックに切り替える** を選択して、クラシック フォームデザイナでフォームを開きます。
4.  標準フォーム デザイナーで、埋め込みキャンバス アプリを表示するようにカスタマイズするフィールドを選択します。
5.  選択したフィールドで、**ホーム** タブの **編集**グループで、**プロパティの変更**を選択します。
6.  **フィールド プロパティ** ダイアログ ボックスで、**コントロール** タブを選択します。
7.  **フィールド プロパティ** ダイアログ ボックスの、コントロールの一覧で **キャンバス アプリ** を選択します。
8.  コントロール一覧の下のセクションでは、キャンバス アプリを編集するために、 **カスタマイズ** を選択します。 これにより、新しいタブで PowerApps Studio で編集するためのキャンバス アプリを開きます。
       > [!NOTE]
       > PowerApps Studio を開くことが Web ブラウザーのポップアップ ブロッカーによりブロックされた場合は、make.powerapps.com  サイトを有効にするか、一時的にポップアップ ブロッカーを無効にしてから、再び **カスタマイズ** を選択する必要があります。
9. 変更が完了したら、 **ファイル** タブを選択し、 **保存**を選択します。
10. 変更した内容をエンドユーザーが利用できるようにするには、 **公開** を選択し、 **このバージョンを公開する**を選択します。

## <a name="see-also"></a>関連項目
[モデル駆動型フォーム上にキャンバス アプリを埋め込む](embed-canvas-app-in-form.md) <br />
[埋め込み型キャンバス アプリケーションをモデル駆動フォームに追加する](embedded-canvas-app-add-classic-designer.md) <br />
[モデル駆動フォームに埋め込まれたキャンバス アプリケーションの画面サイズと表示方向をカスタマイズする](embedded-canvas-app-customize-screen.md) <br />
[組み込みキャンバス アプリ内からホスト フォームで事前定義済みの操作を実行する](embedded-canvas-app-actions.md) <br />
[ModelDrivenFormIntegrationコントロールのプロパティとアクション](embedded-canvas-app-properties-actions.md) <br />
[埋め込みキャンバス アプリの共有](share-embedded-canvas-app.md)。 <br />
[埋め込みキャンバス アプリの作業のガイドライン](embedded-canvas-app-guidelines.md) <br />
[パブリック プレビュー リリースを使用して作成された、モデル駆動型フォームの埋込み型キャンバスアプリケーションを最新版へと移行する](embedded-canvas-app-migrate-from-preview.md) <br />
