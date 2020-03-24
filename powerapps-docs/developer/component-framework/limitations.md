---
title: Power Apps Component Framework の制限 | MicrosoftDocs
description: Power Apps Component Framework を使用する際の制限
author: nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: index-page
ms.assetid: 18e88d702-3349-4022-a7d8-a9adf52cd34f
ms.author: nabuthuk
ms.openlocfilehash: 61567ce7d1dff080c1e953751796973105f66885
ms.sourcegitcommit: 59f0b3adc56279b5673cbf04b4a55bd7678e1ea7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091238"
---
# <a name="limitations"></a>制限 

Power Apps Component Framework のリリースにより、モデル駆動型アプリとキャンバス アプリのユーザー エクスペリエンスを向上させる、独自のコード コンポーネントを作成できるようになりました。 独自のコンポーネントを作成することができますが、コード コンポーネントには機能を実装する時に開発者を制限するいくつかの制約があります。 以下にその制限をいくつか示します:

1. WebAPI などの Common Data Service 依存型 API と少数のその他 API はこの実験プレビューでは利用できません。 この実験プレビュー リリースの個々実験の API については、[Power Apps Component Framework の API リファレンス](reference/index.md)を参照してください。
2. コード コンポーネントは、外部ライブラリのコンテンツを含むすべてのコードを、主要なコード バンドルにバンドルする必要があります。 Power Apps コマンド ライン インターフェースが、外部ライブラリーのコンテンツをコンポーネント固有のバンドルにバンドルするのに役立つ方法を確認するには、[Angular フリップ コンポーネント](sample-controls/angular-flip-control.md)の例を参照してください。

   > [!NOTE]
   > コンポーネント マニフェストでライブラリ ノードを使用しているコンポーネント間での共有ライブラリのサポートは、まだサポートされません。 これを見直してこの機能を今後のリリースで追加する予定です。

## <a name="related-topics"></a>関連トピック

[Power Apps Component Framework API の参照](reference/index.md)<br/>
[Power Apps Component Framework の概要](overview.md)
