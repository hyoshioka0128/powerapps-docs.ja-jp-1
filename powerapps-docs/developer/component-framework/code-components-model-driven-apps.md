---
title: モデル駆動型アプリのコード コンポーネント | Microsoft Docs
description: キャンバス アプリのコード コンポーネントを作成する
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 02/24/2020
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d100dc3-bd82-4b45-964c-d90eaebc0735
ms.openlocfilehash: 7011c11ef8beb9549e864f650fad891f9c3d61bc
ms.sourcegitcommit: 13d4042c7bd73580cc8c595e137de7e7fec22875
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "3170219"
---
# <a name="code-components-for-model-driven-apps"></a>モデル駆動型アプリのコード コンポーネント

Power Apps component framework により、開発者はモデル駆動型アプリの視覚化を拡張することができます。 プロの開発者は [Power Apps CLI ](get-powerapps-cli.md) を使用して、コード コンポーネントを作成、デバッグ、インポートしモデル駆動型アプリに追加できます。 モデル駆動型アプリのフィールド、グリッド、サブグリッドにコード コンポーネントを追加できます。 

> [!IMPORTANT]
> Power Apps component framework は、モデル駆動型アプリに対して既定で有効となっています。 キャンバス アプリで Power Apps  component framework を有効化する方法については、[キャンバス アプリのコード コンポーネント](component-framework-for-canvas-apps.md)を参照してください。

## <a name="implementing-code-components"></a>コード コンポーネントの実装

コード コンポーネントの作成を開始する前に、Power Apps  component framework を使用したコンポーネントの開発に必要な前提条件がすべてインストールされていることを確認してください。 

[はじめてのコード コンポーネント作成](implementing-controls-using-typescript.md) の記事では、コード コンポーネントを作成するステップ バイ ステップの手順について説明しています。

## <a name="add-code-components-to-model-driven-apps"></a>モデル駆動型アプリにコード コンポーネントを追加する

モデル駆動型アプリのフィールド、またはエンティティにコード コンポーネントを追加する方法については、[モデル駆動型アプリにコード コンポーネントを追加する](add-custom-controls-to-a-field-or-entity.md)を参照してください。

> [!div class="mx-imgBorder"] 
> ![線形スライダー コントロールの追加](../../maker/model-driven-apps/media/add-slider.PNG "線形スライダー コントロールの追加")

> [!div class="mx-imgBorder"]
> ![データセット グリッド コンポーネント](media/add-dataset-component.png "データセット グリッド コンポーネント")

## <a name="update-existing-code-components"></a>既存のコード コンポーネントの更新

コードコンポーネントを更新し、実行時に変更を確認する場合は、マニフェスト ファイルのバージョン属性を変更する必要があります。 変更を加える際には、常にコンポーネント の バージョン を更新することを推奨します。

## <a name="see-also"></a>関連項目

[Power Apps Component Framework の概要](overview.md)<br/>
[初めてコード コンポーネントを作成する](implementing-controls-using-typescript.md)<br/>
[Power Apps component framework の学習](https://docs.microsoft.com/learn/paths/use-power-apps-component-framework)
