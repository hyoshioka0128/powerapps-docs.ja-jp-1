---
title: コードコンポーネントの作成と構築 | Microsoft Docs
description: PowerApps component framework ツールを使用してコンポーネントを作成する
keywords: PowerApps component framework、コード コンポーネント、コンポーネント フレームワーク
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 06/20/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d2cbf58a-9112-45c2-b823-2c07a310714c
ms.openlocfilehash: 9a02b64321564b0a09e6b53223f13748358d76cf
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2748894"
---
# <a name="create-and-build-a-code-component"></a>コードコンポーネントを作成、構築する

このトピックでは、 PowerApps CLIコンポーネントを使用してコードを作成および展開する方法を説明します。 [Microsoft PowerApps CLI](https://aka.ms/PowerAppsCLI) がインストールされていることが前提となります。

## <a name="create-a-new-component"></a>新しいコンポーネントの作成

開始するには、 PowerApps CLIのインストール後に **VS 2017 の開発者向けコマンド プロンプト** 開きます。

1. VS 2017 の開発者向けコマンド プロンプトでは、コマンド `mkdir <Specify the folder name>`を使用して、ローカルのハードディスクに *C:\Users\your name\Documents\My_code_Component* のような新規フォルダを作成します。
2. コマンド `cd <specify your new folder path>` を使用して、新しく作成したフォルダに移動します。
3. このコマンドを実行して、基本パラメータを渡して新たなコンポーネントプロジェクトを作成します。

    `pac pcf init --namespace <specify your namespace here> --name <Name of the code component> --template <component type>`
 
   > [!NOTE]
   > 現在、 PowerApps CLIでは二つの種類のコンポーネントに対応しています: モデル駆動型アプリケーションの **フィールド** と **データセット**。  キャンバス アプリの場合は、**フィールド** タイプはこの試験的なプレビューに対応しています。

4. 必要なプロジェクトの依存関係をすべて取得するには、コマンド `npm install` を実行します。
5. 任意の開発者環境でプロジェクト フォルダ ( `C:\Users\<your name>\Documents\<My_code_Component>` ) を開き、コード コンポーネントの開発を始めます。 最も手軽に開始するには、 `C:\Users\<your name>\Documents\<My_code_Component>` に移動してコマンド プロンプトで `code .` を実行する方法があります。 このコマンドは、 Visual Studio コードにあるコンポーネントプロジェクトを開きます。
6. マニフェスト、コンポーネントロジック、スタイル設定などのコンポーネントに必要なアーティファクトを実装し、コンポーネントプロジェクトを構築します。 詳細: [サンプル コンポーネントの実装](implementing-controls-using-typescript.md)

## <a name="build-your-component"></a>コンポーネントを構築する

コンポーネント プロジェクト を構築するには、 Visual Studio コードで `package.json` を含むプロジェクトのフォルダを開きます。(Ctrl-Shift-B) コマンドを使用して、構築オプションを選択します。 または、VS 2017 ウィンドウの開発者向けコマンド プロンプトで  `npm run build` コマンドを使用することで、簡単にコンポーネントを構築することができます。

> [!TIP]
> 構築中、または構築完了後にコンポーネントのデバッグを行うには、 [コード コンポーネントのデバッグ](debugging-custom-controls.md) を参照してください。

TypeScript へのコンポーネントロジックの実装が完了したら、Common Data Service にソリューションをインポートできるように、すべてのコード コンポーネント要素をソリューション ファイルにバンドルする必要があります。 詳細: [コード コンポーネントをパッケージする](import-custom-controls.md)

## <a name="known-configuration-issues-and-workarounds"></a>構成に関する既知の問題と回避策

**Msbuild エラー MSB4036:**

1. プロジェクト ファイルのタスク名はタスク クラスの名前と同じです。
2. タスク クラスはパブリックで Microsoft.Build.Framework.ITask インターフェイスを実装しています。
3. タスクは、プロジェクト ファイルの *\<UsingTask>* または、 パス ディレクトリに格納されている、 *.tasks ファイルにて正しく宣言されています。

**解決方法:**

1. Visual Studio インストーラーを開きます。 
1. Visual Studio 2017 で、 **修正 を選択します**。 
1. **個別のコンポーネント** を選択します。
1. コード ツール配下の **NuGet ターゲットと構築タスク** を確認します。

**発行元の接頭辞**

コンポーネントが PowerApps CLIツールキットのバージョン 0.4.3 よりも0.4.3低くバージョンで作成されている場合は、Common Data Service にソリューションファイルをインポートする際にエラーが表示されます。 このエラーが表示されるのは、新しくインポートされたコンポーネントの名称に、その一意性と競合を回避する目的で発行元の接頭辞が付加されてるためです。

**回避策**:

- Common Data Serviceからソリューションに関連するコンポーネントを削除します。 フォーム、またはグリッドにコンポーネントが既に構成されている場合は、コンポーネントソリューションは構成に依存するため、当該コンポーネントを削除する必要があります。  
- 最新の CLI バージョンで構築されたコンポーネントに対する更新を使用して、新しいソリューションをインポートします。
- 新たに読み込まれたコンポーネントは、フォームまたはグリッド上で設定できるようになっています。  


<!--2. When the components are created with the publisher prefix in mixed or upper case using the new CLI tooling version, it throws an error while importing the solution. This happens because the updated tooling version (0.4.3 and newer) now enforces the platform standard for lower case publisher prefix.

   **Workaround**:

    Update the solution and customizations to ensure that the associated prefix is modified to lower case and import the new solution into Common Data Service.-->


### <a name="see-also"></a>関連項目

[コード コンポーネントのデバッグ](debugging-custom-controls.md)<br/>
[コード コンポーネントをパッケージ化する](import-custom-controls.md)<br/>
[コード コンポーネントをフィールドやエンティティに追加する](add-custom-controls-to-a-field-or-entity.md)<br/>
[既存のコード コンポーネントを更新する](updating-existing-controls.md)<br/>
[PowerApps Component Framework API の参照](reference/index.md)<br/>
[PowerApps Component Framework の概要](overview.md)
