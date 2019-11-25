---
title: テンプレートに関する作業 | Microsoft Docs
description: ポータルでテンプレートを使用する手順。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 207a1abdfc8145c38b8d6222f71281ce714e8947
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2751826"
---
# <a name="work-with-templates"></a>テンプレートに関する作業

組み込みのテンプレートは、一つはプロビジョニング用のポータルに使用できます。 コード エディターを使用して、組み込みテンプレートを編集できます。 たとえば、Common Data Service スターター ポータルをプロビジョニングする場合、次の組み込みテンプレートを使用できます。

- 既定のスタジオ テンプレート
- タイトルを含むページ
- 子リンクのあるページ


> [!NOTE]
> **デフォルトのスタジオテンプレート**、**プロファイル**、および**検索**テンプレートは編集しないことをお勧めします。

コード エディターでテンプレートを開くには

1.  [ポータルを編集](manage-existing-portals.md#edit) して、ポータルを PowerApps ポータル Studioで開きます。  

2.  画面の左側のツールベルトから**テンプレート**![テンプレート アイコン](media/templates-icon.png "テンプレート アイコン")を選択します。 使用可能なテンプレートが表示されます。  

    > [!div class=mx-imgBorder]
    > ![テンプレート ウィンドウ](media/templates-pane.png "テンプレート ウィンドウ")  

3.  目的のテンプレートを選択してコード エディターで開きます。

4.  コードを編集して変更を保存します。

> [!NOTE]
> - また、ソース コード エディターに Liquid タグを追加して、高度な構成を行うこともできます。 詳細: [Liquid テンプレートに関する作業](liquid/liquid-overview.md)
> -  [ポータル管理アプリ](configure/configure-portal.md)を使用して作成されるページ テンプレートは、**テンプレート** ウィンドウにも表示されます。
