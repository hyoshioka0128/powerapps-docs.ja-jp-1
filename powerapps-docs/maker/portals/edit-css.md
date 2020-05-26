---
title: ポータルで CSS の編集 | Microsoft Docs
description: ポータルで CSS 編集の手順。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 04/07/2020
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: 9c6689932e6098bf036d1cfb8cfd158d0a0cfd10
ms.sourcegitcommit: 6aa28b13d942c4a907642962348f0c0443623fd1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "3285259"
---
# <a name="edit-css-for-themes-in-power-apps-portal"></a>Power Apps ポータルで、テーマの CSS を編集する

カスケード スタイル シート (CSS) を使用して、Webサイトの書式を管理することができます。 既定では、bootstrap.min.css と theme.css ファイルを使用できます。 既存の CSS ファイルを編集して、新しい CSS ファイルをアップロードできます。 新しい CSS ファイルをアップロードすると、ポータル管理アプリで Web ファイルとして使用できます。

> [!NOTE]
> Power Apps ポータルは、[イベント ポータル](https://docs.microsoft.com/dynamics365/marketing/developer/event-management-web-application) 以外の Bootstrap 3.3.x に基づいています。 ポータル開発者は、Bootstrap 3 をその他の CSS ライブラリと置き換えるべきではありません、なぜなら Power Apps ポータルの一部のシナリオは Bootstrap 3.3.x に依存しているからです。

コード エディターで CSS を開くには

1.  [ポータルを編集](manage-existing-portals.md#edit) して、ポータルを Power Apps ポータル Studioで開きます。  

2.  画面左側のツールベルトから **テーマ** ![テーマ アイコン](media/theme-icon.png "テーマ アイコン") を選択してください。 次に使用可能なテーマ が表示されます。  

    ![テーマ](./media/edit-css/themes.png)

3.  必要な CSS を選択してコード エディターで開きます。

4.  コードを編集して変更を保存します。

新しい CSS ファイルをアップロードするには:

1.  [ポータルを編集](manage-existing-portals.md#edit) して、ポータルを Power Apps ポータル Studioで開きます。  

2.  画面左側のツールベルトから **テーマ** ![テーマ アイコン](media/theme-icon.png "テーマ アイコン") を選択してください。 次に使用可能なテーマ が表示されます。  

3. **カスタム CSS** のアップロード を選択します。

    ![カスタム CSS のアップロード](./media/edit-css/upload-custom-css.png) 

4. アップロードする CSS ファイルを参照して選択します。


