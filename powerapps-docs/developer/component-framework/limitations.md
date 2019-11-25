---
title: PowerApps Component Framework の制限 | MicrosoftDocs
description: PowerApps Component Framework を使用する際の制限
author: nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: index-page
ms.assetid: 18e88d702-3349-4022-a7d8-a9adf52cd34f
ms.author: nabuthuk
ms.openlocfilehash: aabcf4518e71648797c795a006c2d842f3e5ff01
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749055"
---
# <a name="limitations"></a>制限 

PowerApps Component Framework のリリースにより、モデル駆動型アプリとキャンバス アプリのユーザー エクスペリエンスを向上させる、独自のコード コンポーネントを作成できるようになりました。 独自のコンポーネントを作成することができますが、コード コンポーネントには機能を実装する時に開発者を制限するいくつかの制約があります。 以下にその制限をいくつか示します:

1. コンポーネントの*フィールド*タイプのみがキャンバスのアプリの実験プレビューでサポートされており、*データセット*タイプのコンポーネントはサポートされていません。 
2. WebAPI などの Common Data Service 依存型 API と少数のその他 API はこの実験プレビューでは利用できません。 この実験プレビュー リリースの個々実験の API については、[PowerApps Component Framework の API リファレンス](reference/index.md)を参照してください。
3. コード コンポーネントは、外部ライブラリのコンテンツを含むすべてのコードを、主要なコード バンドルにバンドルする必要があります。 PowerApps コマンド ライン インターフェースが、外部ライブラリーのコンテンツをコンポーネント固有のバンドルにバンドルするのに役立つ方法を確認するには、[Angular フリップ コンポーネント](sample-controls/angular-flip-control.md)の例を参照してください。

   > [!NOTE]
   > コンポーネント マニフェストでライブラリ ノードを使用しているコンポーネント間での共有ライブラリのサポートは、まだサポートされません。 これを見直してこの機能を今後のリリースで追加する予定です。
4. 単一マニフェスト ファイル内での複数コンポーネントの定義は、まだサポートされていません。
5. コールアウト プロセスとアクションはまだサポートされていません。 [ナビゲーション](reference/navigation.md) メソッドを使用した、ダイアログ ボックスのみを呼び出すことができます。
6. 別のコード コンポーネントから一つのコンポーネントの呼び出しはまだサポートされていません。
7. 現在、フォント リソース (.tff) はまだサポートされていません。

## <a name="related-topics"></a>関連トピック

[PowerApps Component Framework API の参照](reference/index.md)<br/>
[PowerApps Component Framework の概要](overview.md)
