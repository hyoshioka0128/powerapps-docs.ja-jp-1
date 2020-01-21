---
title: コード コンポーネントとは? | MicrosoftDocs
description: Power Apps component framework を使用してコード コンポーネントを作成し、フォーム、ビュー、ダッシュボードでデータを表示して作業する高度なユーザー エクスペリエンスを提供します。
manager: kvivek
ms.date: 09/05/2019
ms.service: powerapps
ms.topic: article
ms.assetid: 135481cd-4583-4e49-8f58-02f32a9b054a
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: 93d60cb1e6c00951e51acd4f92d8c62dce84fc28
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2909080"
---
# <a name="what-are-code-components"></a>コード コンポーネントとは

コード コンポーネントはソリューション コンポーネントの一種です。つまり、コード コンポーネントをソリューション ファイルに含めて異なる環境にインストールできます。 詳細: [ソリューションを使用した拡張機能のパッケージ化および配布](https://docs.microsoft.com/dynamics365/customer-engagement/developer/package-distribute-extensions-use-solutions).

コード コンポーネントをソリューションに含めて追加し、そして Common Data Service にインポートします。 コンポーネントが Common Data Service に組み込まれたら、システム管理者とシステム カスタマイザーは既定のコンポーネントの代わりにそれらを使用するよう、フォーム フィールド、サブグリッド、ビュー、ダッシュボード の サブグリッドを構成できます。 キャンバス アプリでこれたのコード コンポーネントも追加できます。 

コードコンポーネントは、3つの要素で構成されています:

- [マニフェスト](#manifest)
- [コンポーネントの実装](#component-implementation)
- [リソース](#resources)

## <a name="manifest"></a>マニフェスト

マニフェストはコンポーネントを定義するメタデータ ファイルです。 それは次を記述する XML 文書です:

- コンポーネントの名前
- 構成が可能なデータの種類、あるいはフィールド、データセット。
- コンポーネントが追加されたときにアプリケーションで構成できる任意のプロパティ。
- コンポーネントが必要とするリソース ファイルの一覧。 
- 必要なコンポーネント インタフェースを適用するオブジェクトを返すコンポーネント実装ライブラリの TypeScript 関数名。

ユーザーがコード コンポーネントを設定したときに、マニフェスト ファイルのデータは利用可能なコンポーネントを除外して、コンテキストに有効なコンポーネントのみ構成に使用できるようにします。 コンポーネントのマニフェストで定義されたプロパティは、ユーザーがコンポーネントの設定時に値を指定できるよう構成フィールドとして表示されます。 これらのプロパティ値は、実行時にコンポーネントで利用可能になります。 詳細については次を参照してください: [マニフェスト スキーマの参照](manifest-schema-reference/index.md)

## <a name="component-implementation"></a>コンポーネントの実装

Power Apps component framework を使用して カスタム コンポーネントを開発するにあたり、コンポーネント ライブラリの実装は重要なステップのひとつとなります。 開発者は TypeScript を使用してコンポーネント を実装することができます。 それぞれの カスタム コンポーネント には、コード コンポーネント インタフェースに記述されたメソッドを実装したオブジェクトを返す関数の定義を含む、 `index.ts` ファイルが必要となります。 このファイルは、メイン スタブ メソッド を備えたCLIツールを介して自動生成されます。

オブジェクトは次のメソッドを実装します:

- [init](reference/control/init.md) (必須)
- [updateView](reference/control/updateview.md) (必須)
- [getOutputs](reference/control/getoutputs.md) (オプション)
- [destroy](reference/control/destroy.md) (必須)

これらのメソッドはコード コンポーネントのライフサイクルを制御します。

### <a name="page-load"></a>ページの読み込み

ページを読み込む時に、アプリケーションは作業するオブジェクトを必要とします。 マニフェスト ファイルからのデータを使用して、コードは呼び出しによってオブジェクトを取得します

```js
var obj =  new <"namespace on manifest">.<"constructor on manifest">();
```

マニフェストの名前空間とコンストラクターの値がそれぞれ `SampleNameSpace` と `LinearInputComponent` である場合、オブジェクトをインスタンス化するコードはこれになります:

```js
var controlObj = new SampleNameSpace.LinearInputComponent();
```

ページの準備ができたら、一連のパラメーターとともに [init](reference/control/init.md) メソッドを呼び出してコンポーネントを初期化します。

```js
controlObj.init(context,notifyOutputChanged,state,container);
```

|パラメーター|説明|
|---|---|
|コンテキスト| コンポーネントの構成方法に関するすべての情報と、 [Power Apps Component Framework API](reference/index.md) とともにコンポーネント内で使用できるすべてのパラメータを含みます。 たとえば、`context.parameters.<"property name from manifest">` を入力プロパティへのアクセスに使用できます。|
|notifyOutputChanged |コード コンポーネントに非同期に取得可能な新しい出力があるとフレームワークに警告します。|
|状態|コンポーネントがすでに [setControlState](reference/mode/setcontrolstate.md) メソッドを使用して、以前に明示的に保存した場合は、現在のセッションで以前読み込まれたページのコンポーネント データが含まれます。|
|コンテナ|開発者とアプリ メーカーが、コンポーネントを定義する UI の HTML 要素を追加することができるHTML div 要素。|

### <a name="user-changes-data"></a>ユーザーがデータを変更する

ページがロードされると、ユーザーがデータを変更するためにコンポーネントを操作するまで、コンポーネントはデータを表示します。 この場合は、 [init](reference/control/init.md) メソッドの *notifyOutputChanged* パラメータとして渡されたメソッドを呼び出す必要があります。 このメソッドを使用すると、プラットフォームは、 [getOutputs](reference/control/getoutputs.md) メソッドを呼び出すことで応答します。 [getOutputs](reference/control/getoutputs.md) メソッドは、ユーザーによって変更された値を返します。 フィールド コンポーネントの場合、通常これはコンポーネントの新しい値になります。

### <a name="app-changes-data"></a>アプリがデータを変更する

プラットフォームがデータを変更すると、コンポーネントの [updateView](reference/control/updateview.md) メソッドを呼び出し、新しいコンテキスト オブジェクトをパラメータとして渡します。 このメソッドを実装し、コンポーネントに表示された値を更新する必要があります。

### <a name="page-close"></a>ページを閉じる

ユーザーがページから離れると、コードコンポーネントはスコープを失い、そのページでオブジェクトに割り当てられたすべてのメモリーが消去されます。 ただし、ブラウザーの実装メカニズムに基づく一部のメソッドはそのまま残り、メモリーを消費する可能性があります。 通常、これらはイベント ハンドラーです。 ユーザーがこの情報を保存する必要がある場合は、同じセッション内で次回、情報が渡されるように [setControlState](reference/mode/setcontrolstate.md) メソッドを実装する必要があります。

開発者は、ページが閉じたときに呼び出される [destroy](reference/control/destroy.md) メソッドを実装して、イベントハンドラなどのクリーンアップコードを削除する必要があります。

## <a name="resources"></a>リソース

各コード コンポーネントは視覚化を構築するためのリソース ファイルが必要です。 マニフェストでリソース ファイルを定義できます。 マニフェスト ファイルのリソース ノードは、コンポーネントが視覚化を実装するために必要なリソースを参照します。 詳細については次を参照してください: [リソースの要素](manifest-schema-reference/resources.md)

### <a name="related-topics"></a>関連トピック

[コードコンポーネントを作成、構築する](create-custom-controls-using-pcf.md)
