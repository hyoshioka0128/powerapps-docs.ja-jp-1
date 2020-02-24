---
title: ポータル Power Apps ポータル Studio の構造分析 | Microsoft Docs
description: Power Apps ポータル Studio の構造分析について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/29/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: 6b04cc8d392e5a633240c1a01467e6be3272464c
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2981498"
---
# <a name="power-apps-portals-studio-anatomy"></a>Power Apps ポータル Studio の構造分析

Web サイトの作成とカスタマイズを行う場合は Power Apps ポータル Studio を使用できます。 これには、Web ページ、コンポーネント、フォーム、リストを追加したり構成したりするための多様なオプションが含まれています。 Power Apps ポータル Studio の構造分析については以下の通りです:

![Power Apps ポータル Studio の構造分析](media/maker-anatomy.png "Power Apps ポータル Studio の構造分析")  

| **Annotation** | **名前**        | **説明**                                                                              |
|----------------|-----------------|----------------------------------------------------------------------------------------------|
| 1              | コマンド バー     | Web ページを作成し、コンポーネントを削除し、作成中の Web サイトを閲覧できます。  |
| 2              | ツールベルト        | これにより以下が可能となります。<ul><li>Web ページの表示と管理</li><li>コンポーネントを追加</li><li>テンプレートの編集</li></ul>  |
| 3              | キャンバス          | Web ページをビルドするコンポーネントが含まれています。                                                    |
| 4              | [フッター]          | ソース コード エディターを開くには、オートセーブ状態を表示します。                         |
| 5              | プロパティ ウィンドウ | Web ページのプロパティおよび選択したコンポーネントを表示し、必要に応じて編集します。 |

> [!NOTE]
> Power Apps ポータル Studio を通じてポータルを編集するには、複数のバックグラウンド プロセスにより一時的にポータルのパフォーマンスを低下させます。 たとえば、キャッシュのクリアプロセスが実行され、Common Data Service からデータがリロードされます。
