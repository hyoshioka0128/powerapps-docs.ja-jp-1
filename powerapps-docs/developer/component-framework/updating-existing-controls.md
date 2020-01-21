---
title: Power Apps component framework ツールを使用して既存のコード コンポーネントを更新する | Microsoft Docs
description: Power Apps component framework ツールを使用してコンポーネントを更新する
keywords: Power Apps component framework、コード コンポーネント、コンポーネント フレームワーク
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2cbf58a-9112-45c2-b823-2c07a310714c
ms.openlocfilehash: 0f779dbddedbf76b3c2e7f55d314a9f0fda30332
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2909088"
---
# <a name="update-existing-code-components"></a>既存のコード コンポーネントの更新 

モデル駆動型アプリの Power Apps component framework のプライベート プレビュー参加者で、既にコード コンポーネントを作成している場合は、新しい ALM 中心のプロジェクト構造と互換性を保つために、いくつかマイナー アップデートを行う必要があります。 

既存の Power Apps component framework コード コンポーネントと共に新しい Power Apps CLI ツールを使用するには、いくつかの変更が必要です。

> [!NOTE]
> Power Apps CLIツールはモデル駆動型アプリのプライベート プレビューの時点では利用できないため、このトピックはモデル駆動型アプリのコード コンポーネントの更新にのみ適用されます。  

## <a name="creating-an-empty-project"></a>空のプロジェクトを作成する

コード コンポーネントに新しい空のプロジェクトを作成するには、Power Apps CLI を使用します。 詳細: [ツールを使用してコンポーネントを作成する](create-custom-controls-using-pcf.md).

プロジェクトが作成されたら、カスタム コンポーネントのソースを新しいプロジェクトに移行します:

1. コンポーネント ソース ファイルを古いソース ファイルから **index.ts** にコピーするか置き換えます。
2.  **ControlManifest.xml** の内容を **ControlManifest.Input.xml** ファイルにコピーまたは置き換えます。
3. CSS、RESX、IMG など他のすべての周辺コンポーネント リソースを、古いプロジェクトから新しいプロジェクトの対応するサブフォルダーにコピーします。

## <a name="updating-manifest-file"></a>マニフェスト ファイルの更新

コード コンポーネントのプロパティを定義する `ControlManifest.xml` ファイルは `ControlManifest.Input.xml` ファイルに置き換えられました。 それ以外の場合、ふたつのファイル間のスキーマにほとんど変更はありません。

重要なセマンティックの変更点がいくつかあります。

1. `code` リソース エントリはカスタム コンポーネントの事前コンパイルされたソース ファイルを指すようになりました。 ファイル名は既定で **index.ts** になります。

   たとえばコンポーネント ソースが `MyControl.ts` と呼ばれるファイルに実装された場合、`ControlManifest.Input.xml` の `code` エントリはそのファイルを指す必要があります。 `code` ファイルも有効な Typescript ファイルである必要があります。 これは `code` エントリでコンパイルされた JS 出力ファイルを指定した、従来のマニフェスト ファイルとは対照的です。
2. `code` や `css` のようなリソース要素の `path` 属性は、現在ディスクのファイルへのローカル パスを参照します。 たとえば、次のようなものです。

    ```XML
   <resources>
    <css path="css/YourControlName" order="1"/>
    </resources>
    ```

上記の `path` 属性は、`YourControlName.css` ファイルが `ControlManifest.Input.xml` がディスク上に存在する現在のディレクトリを基準にした `css` サブフォルダにあることを示します。

次のように ControlManifest.Input.xml ファイルを更新します:

1. `ControlManifest.Input.xml` の `code` エントリを、カスタム コンポーネントの事前コンパイルのソース ファイルに編集します (通常これは index.ts です)。
2. ディスク上のファイルへの相対パスを正しく参照するように、リソースのすべてのパスを編集します。

## <a name="updating-the-project-files"></a>プロジェクト ファイルの更新

古いバージョンのツールを使用してコンポーネントを作成し、最新機能を利用するには、次のように、プロジェクト ファイルを更新してください。

1. 既存のプロジェクトを更新して、最新のモジュールを使用します。
 
   - Power Apps component framework プロジェクト フォルダにある `pcfproj` の バージョン タグを更新します:

      ```XML
      <Packagereference Include="Microsoft.PowerApps.MSBuild.Pcf" Version="1.*"/>
      ```
   - ソリューション プロジェクト フォルダにある `cdsproj` の バージョン タグを次のように更新します:

      ```XML
      <Packagereference Include="Microsoft.PowerApps.MSBuild.Solution" Version="1.*"/>
      ```

      > [!NOTE] 
      > 上記の変更を行った後、正しいバージョン `msbuild /t:restore` でプロジェクトを作成するコマンドを実行します。


   - Power Apps component framework プロジェクト フォルダにある `package.json` ファイル の バージョン タグを更新します。

      ```JSON
      "devDependencies":{
       "pcf-scripts": "^1",
       "pcf-start": "^1"
          }
      ```
     > [!NOTE]
     > 上記の変更を行った後、正しいバージョン `npm update` コマンドでプロジェクトを作成するコマンドを実行します。

2. 以前に認証プロファイルを作成した場合は、再作成する必要があります。 これは、非公開のクラウドをサポートするために新しいプロパティがプロファイルに追加されたためです。 これを行うには、次のようにします。
 
    - コマンド `pac auth clear` の実行
    - コマンド `pac auth create --url <your org url>` の実行

## <a name="updating-your-project-with-the-latest-node-modules"></a>最新のノード モジュールを使用したプロジェクトの更新

従来のプロジェクトでは、最新の CLI 機能を利用するために最新の npm モジュールを取得する必要があります。 前にダウンロードしたノード モジュールを更新するには、開発者のコマンド プロンプトでのプロジェクト ディレクトリに移動し、コマンド `npm update` を実行します。 

## <a name="using-es6-module-syntax"></a>ES6 モジュール構文を使用する

ビルド ツールはコンポーネント ソースが標準の ES6 モジュール形式を使用してエクスポートされることを意図します。 レガシー コンポーネントは通常、内部モジュールにする名前空間としてエクスポートされます。 新しいビルド ツールに合わせて、コンポーネント ソース ファイルを次のように修正する必要があります。

1. コード コンポーネントを実装するソース ファイル (たとえば index.ts) を開きます。
2. モジュール宣言を削除して標準の ES6 エクスポート構文を使用します。

     削除前:
     ```TypeScript
     module SampleNamespace
     {
    export class TSLinearInputControl implements ComponentFramework.StandardControl<InputsOutputs.IInputBag, InputsOutputs.IOutputBag> {
          <your class implementation>
           }
            }
     
      ```
    以下の後で:
    ```TypeScript
     export class YourControlName implements ComponentFramework.StandardControl<IInputs, IOutputs> { 
          <your class implementation>
          }
   ```

## <a name="using-generated-manifest-typing-file"></a>生成されたマニフェスト タイピング ファイルの使用

従来のプロジェクトでは、通常は `private_typing` サブフォルダにある `inputsOutputs.d.ts` タイピング ファイルを手動で作成および編集する必要があります。 Power Apps CLI ツールはビルド時に自動的にこのファイルを生成します。 

Code-gen は、コンポーネントのソースコードで使われる `type` の定義が、コンポーネント マニフェスト ファイルで定義された `types` と同期していることを保証します。

タイピング ファイルは `ManifestTypes.d.ts` という名前に変更され、現在は `generated` という名前のサブフォルダに生成されます。 さらに、`InputsOutputs.IInputBag` と `InputsOutputs.IOutputBag` 型は `IInputs` と `IOutputs` にそれぞれ名前が変更されます。

新しいタイピング ファイルを使用するには:

1. コンポーネントのソース ファイルの先頭に次の行を追加して、新しい `ManifestTypes.d.ts` ファイルをインポートします:

    `./generated/ManifestTypes` から {IInputs、IOutputs}をインポートします。
2. **InputsOutputs.IInputBag** の参照をすべて **IInputs** に名前を変更します。
3. **InputsOutputs.IOutputBag** の参照をすべて **IOutputs** に名前を変更します。
4. コマンド `npm run build` を使って、プロジェクトをビルドして新しい **ManifestTypes.d.ts** ファイルを生成します。


### <a name="see-also"></a>関連項目

[Power Apps Component Framework の制限](limitations.md)<br/>
[Power Apps Component Framework API の参照](reference/index.md)<br/>
[Power Apps Component Framework の概要](overview.md)
