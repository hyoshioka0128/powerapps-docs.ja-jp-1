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
ms.openlocfilehash: 4380d99439b9103ea40800ea8a5a20e1e13768d8
ms.sourcegitcommit: 27cb5ad024d43f208ef6acfbea456a05df3edf8e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2020
ms.locfileid: "3082824"
---
# <a name="code-components-for-model-driven-apps"></a>モデル駆動型アプリのコード コンポーネント

Power Apps component framework により、開発者はモデル駆動型アプリの視覚化を拡張することができます。 プロの開発者は、[Power Apps CLI](get-powerapps-cli.md) を使用して、コード コンポーネントを作成、デバッグ、インポートし、モデル駆動型アプリケーションに追加できます。 モデル駆動型アプリのフィールド、グリッド、サブグリッドにコード コンポーネントを追加できます。 

> [!IMPORTANT]
> Power Apps component framework は、モデル駆動型アプリに対して既定で有効となっています。 キャンバス アプリで Power Apps  component framework を有効化する方法については、[キャンバス アプリのコード コンポーネント](component-framework-for-canvas-apps.md)を参照してください。

## <a name="implementing-code-components"></a>コード コンポーネントの実装

コード コンポーネントの作成を開始する前に、Power Apps  component framework を使用したコンポーネントの開発に必要な前提条件がすべてインストールされていることを確認してください。 

[はじめてのコード コンポーネント作成](implementing-controls-using-typescript.md) のトピックでは、コード コンポーネントを作成する手順について説明しています。

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
[初めてコード コンポーネントを作成する](implementing-controls-using-typescript.md)
