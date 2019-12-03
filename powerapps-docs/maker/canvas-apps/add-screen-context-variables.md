---
title: キャンバス アプリに画面を追加し、画面間を移動する | Microsoft Docs
description: キャンバスアプリに画面を追加し、[次へ] と [戻る] 矢印を使用して、電源アプリの画面間を切り替える
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 02/03/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cbe6173c94f001874b126a5b8ecb1bdf9ad21b70
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74724451"
---
# <a name="add-a-screen-to-a-canvas-app-and-navigate-between-screens"></a>キャンバス アプリに画面を追加し、画面間を移動する

複数の画面があるキャンバス アプリを作成し、ユーザーが画面間を移動するための方法を追加します。

## <a name="add-and-rename-a-screen"></a>画面を追加し、名前を変更する

1. **[ホーム]** タブで **[新しい画面]** を選択し、追加する画面の種類を選択します。

    ![[ホーム] タブの画面追加オプション](./media/add-screen-context-variables/add-screen.png)

2. 右側のウィンドウで、画面の名前 ( **[プロパティ]** タブのすぐ上) を選択し、「 **Source**」と入力します。

    ![既定の画面の名前を変更する](./media/add-screen-context-variables/name-source-screen.png)

3. 別の画面を追加し、**Target** という名前を付けます。

    ![左側のナビゲーション バーの 2 つの画面](./media/add-screen-context-variables/two-screens-in-nav.png)

## <a name="reorder-screens"></a>画面の順序を変更する

左のナビゲーションバーで、上または下に移動する画面にマウスポインターを合わせ、表示される省略記号ボタンを選択し、 **[上へ移動]** または **[下へ移動]** を選択します。

![画面の順序変更](./media/add-screen-context-variables/reorder-screen.png)

> [!NOTE]
> アプリを開くと、通常、コントロールの階層リストの上部にある画面が最初に表示されます。 ただし、 **[OnStart](controls/control-screen.md)** プロパティを **[Navigate](functions/function-navigate.md)** 関数を含む数式に設定して、別の画面を指定することもできます。

## <a name="add-navigation"></a>ナビゲーションを追加する

1. **ソース**画面を選択した状態で、 **[挿入]** タブを開いて **[アイコン]** を選択し、[**次へ] 矢印**を選択します。  

    ![[挿入] タブの図形オプション](./media/add-screen-context-variables/add-next-arrow.png)

2. (省略可能) 画面の右下隅に表示されるように矢印を移動します。

3. 矢印を選択したまま、 **[操作]** タブを選択し、 **[移動]** を選択します。

    矢印の **[OnSelect](controls/properties-core.md)** プロパティが **Navigate** 関数に自動的に設定されます。

    ![Navigate 関数に設定された OnSelect プロパティ](./media/add-screen-context-variables/onselect-default.png)

    ユーザーが矢印を選択すると、**ターゲット**画面がフェードインします。

4. **Target** 画面で、 **[戻る矢印]** を追加し、その **[OnSelect](controls/properties-core.md)** プロパティをこの式に設定します。

    `Navigate(Source, ScreenTransition.Fade)`

5. Alt キーを押したまま、各画面の矢印を選択して画面を切り替えます。

## <a name="more-information"></a>詳細

[画面制御リファレンス](controls/control-screen.md)