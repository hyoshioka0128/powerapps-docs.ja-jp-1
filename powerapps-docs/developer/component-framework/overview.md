---
title: PowerApps component framework の概要 | MicrosoftDocs
description: PowerApps component framework を使用してコード コンポーネントを作成し、フォーム、ビュー、ダッシュボードでデータを表示して作業する高度なユーザー エクスペリエンスを提供します。
keywords: component framework、コード コンポーネント、PowerApps 制御
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
ms.openlocfilehash: 03534f925750b7c99e6d53822aab766421854968
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2753623"
---
# <a name="powerapps-component-framework-overview"></a>PowerApps component frameworkの概要

PowerApps component framework は、ユーザーがフォーム、ビュー、およびダッシュボードを使ってデータを表示して使用できる強化されたユーザー エクスペリエンスを提供する、モデル駆動型アプリとキャンバス アプリのためのコード コンポーネントを作成する能力をプロの開発者やアプリ作成者に提供します。 たとえば、次のようなものです。

- 数値テキスト値を表示するフィールドを `dial` や `slider` コード コンポーネントで置き換えます。
- リストを `Calendar` や `Map` のようにデータセットに結び付けられた全く異なる視覚的エクスペリエンスに変換します。

> [!IMPORTANT]
> - PowerApps component framework は、キャンバス アプリ向けの実験用プレビュー内と、モデル駆動型アプリ向けの GA 内にあります。 これは、モデル駆動型アプリでサポートされているすべての API が、キャンバス アプリではサポートされていない場合があることを意味します。
> - 既定で PowerApps Component Framework はモデル駆動型アプリに対して有効です。 キャンバス アプリでこの機能を有効にするには、[キャンバス アプリの可用性](component-framework-for-canvas-apps.md)を参照してください。
> - [!INCLUDE[cc_preview_features_definition](../../includes/cc-preview-features-definition.md)]
> - キャンバス アプリでは、コード コンポーネントの *フィールド*の種類のみがサポートされ、*データセット* の種類はサポートされていません。


PowerApps component framework を使用して、PowerApps 機能全域に渡り使用できるコード コンポーネントを作成します。 HTML Web リソースとは異なり、コード コンポーネントは同じコンテキストの一部として表示されると同時に、他のコンポーネントとして読み込むことができ、シームレスなエクスペリエンスを提供しています。 開発者は、すべての HTML、CSS、TypeScript または JavaScript ファイルを、単一のソリューション パッケージファイルでバンドルできます。 コード コンポーネントは、異なるエンティティとフォームにわたって何回でも再利用できます。

コード コンポーネントは、コンポーネントのライフサイクル 管理、コンテキスト データおよびメタデータ アクセス、Web API を介したシームレスなサーバー アクセス、ユーティリティとデータの書式設定方法、カメラ、位置、マイクなどのデバイス機能と、ダイアログ、検索、全ページのレンダリングなどの UX 要素のなどの機能を呈する豊富なフレームワーク API のセットへのアクセスができます。  

開発者とアプリ作成者は、最新の Web プラクティスを利用でき、また外部ライブラリの力を活用して高度なユーザー対話を作成できます。 フレームワークはコンポーネントのライフサイクルを自動的に処理し、アプリケーションのビジネス ロジックを保持し、パフォーマンスを最適化します (もう非同期 IFrames は不要です)。 コンポーネント定義、依存関係、構成は、[ソリューション](https://docs.microsoft.com/dynamics365/customer-engagement/customize/solutions-overview) にパッケージ化され、すべての環境に渡り移動することができ、[AppSource](https://appsource.microsoft.com/marketplace/apps?page=1&product=dynamics-365)を介して出荷することができます。  

## <a name="related-topics"></a>関連トピック

[コード コンポーネントとは](custom-controls-overview.md)<br/>
[キャンバス アプリの可用性](component-framework-for-canvas-apps.md)<br/>
[コードコンポーネントを作成、構築する](create-custom-controls-using-pcf.md)<br/>
[開発者向け PowerApps](https://docs.microsoft.com/powerapps/#pivot=home&panel=developer)

