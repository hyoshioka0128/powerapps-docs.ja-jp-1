---
title: Power Apps component framework の概要 | MicrosoftDocs
description: Power Apps component framework を使用してコード コンポーネントを作成し、フォーム、ビュー、ダッシュボードでデータを表示して作業する高度なユーザー エクスペリエンスを提供します。
keywords: component framework、コード コンポーネント、Power Apps 制御
author: nkrb
manager: kvivek
ms.date: 09/05/2019
ms.service: powerapps
ms.custom:
- dyn365-a11y
- dyn365-developer
ms.topic: article
ms.assetid: 7923e36d-3640-49f7-9f2f-c97358a632db
ms.author: nabuthuk
ms.openlocfilehash: c86182fe14617f971b8ca2183bdb4627b8e8c5b9
ms.sourcegitcommit: 64d816a759c5cc6343928d56a673812c3ea066c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "2895077"
---
# <a name="power-apps-component-framework-overview"></a>Power Apps component frameworkの概要

Power Apps component framework は、ユーザーがフォーム、ビュー、およびダッシュボードを使ってデータを表示して使用できる強化されたユーザー エクスペリエンスを提供する、モデル駆動型アプリとキャンバス アプリのためのコード コンポーネントを作成する能力をプロの開発者やアプリ作成者に提供します。 たとえば、次のようなものです。

- 数値テキスト値を表示するフィールドを `dial` や `slider` コード コンポーネントで置き換えます。
- リストを `Calendar` や `Map` のようにデータセットに結び付けられた全く異なる視覚的エクスペリエンスに変換します。

> [!IMPORTANT]
> - Power Apps component framework は、キャンバス アプリ向けの実験用プレビュー内と、モデル駆動型アプリ向けの GA 内にあります。 これは、モデル駆動型アプリでサポートされているすべての API が、キャンバス アプリではサポートされていない場合があることを意味します。
> - 既定で Power Apps Component Framework はモデル駆動型アプリに対して有効です。 キャンバス アプリでこの機能を有効にするには、[キャンバス アプリのコード コンポーネント](component-framework-for-canvas-apps.md) を参照してください。
> - [!INCLUDE[cc_preview_features_definition](../../includes/cc-preview-features-definition.md)]
> - キャンバス アプリでは、コード コンポーネントの *フィールド*の種類のみがサポートされ、*データセット* の種類はサポートされていません。

## <a name="how-its-different-from-webresources"></a>ウェブリソースとの違い

 HTML Web リソースとは異なり、コード コンポーネントは同じコンテキストの一部として表示されると同時に、他のコンポーネントとして読み込むことができ、シームレスなエクスペリエンスを提供しています。 開発者はすべての HTML、CSS、TypeScript または JavaScript ファイルを 1 つの[ソリューション](https://docs.microsoft.com/dynamics365/customer-engagement/customize/solutions-overview) パッケージ ファイルにバンドルでき、環境間で移動し、[AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=dynamics-365) 経由で出荷できます。 コード コンポーネントは、異なるエンティティとフォームにわたって何回でも再利用できます。 Power Apps component framework を使用して、Power Apps 機能全域に渡り使用できるコード コンポーネントを作成します。

## <a name="advantages"></a>利点 

- コンポーネント ライフサイクル管理、コンテキスト データ、メタデータなどの機能を公開するフレームワーク API の豊富なセットへのアクセス。 
- Web API、ユーティリティおよびデータのフォーマット方法、カメラ、ロケーション、マイクなどのデバイス機能、ならびにダイアログ、ルックアップ、フルページ レンダリングなどの起動しやすい UX 要素などを介したシームレスなサーバー アクセス。  
- 最新の Web プラクティスのサポート。
- パフォーマンスの最適化。
- 再利用性
- すべてのファイルを単一のソリューション ファイルにバンドルします。

## <a name="related-topics"></a>関連トピック

[コード コンポーネントとは](custom-controls-overview.md)<br/>
[キャンバス アプリのコード コンポーネント](component-framework-for-canvas-apps.md)<br/>
[コードコンポーネントを作成、構築する](create-custom-controls-using-pcf.md)<br/>
[開発者向け Power Apps](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer)

