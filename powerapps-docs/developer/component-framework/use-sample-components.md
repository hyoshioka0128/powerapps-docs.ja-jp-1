---
title: サンプルコンポーネントの使用方法 (Power Apps Component Framework) | Microsoft Docs
description: モデル駆動型アプリとキャンバス アプリで Power Apps Component Framework を使用して作成されたサンプル コンポーネントの使用方法について説明します。
keywords: ''
author: Nkrb
ms.author: nabuthuk
manager: kvivek
ms.date: 11/25/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.openlocfilehash: a674b37fd4616a21fe8d61336f255debafd552dd
ms.sourcegitcommit: 3b68c4e29be4e8f68c0bfb88abdd1bbdf0187c57
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "3080841"
---
# <a name="how-to-use-the-sample-components"></a>サンプルコンポーネントの使用方法

このセクションに記載されているすべてのサンプル コンポーネントは、[ここ](https://go.microsoft.com/fwlink/?linkid=2088525)からダウンロードできるため、モデル駆動型アプリまたはキャンバス アプリで試すことができます。

このセクションの個々のサンプル コンポーネントのトピックでは、サンプル コンポーネントの概要、外観、およびサンプル コンポーネントのマニフェスト、コード、およびリソースについて説明します。

## <a name="before-you-can-try-the-sample-components"></a>サンプル コンポーネントを試す前に
サンプル コンポーネントを試すには、まず次の手順を実行する必要があります。
- [ダウンロード](https://go.microsoft.com/fwlink/?linkid=2088525)サンプル コンポーネントを使用して、ローカル コピーを作成できるようにします。
- [Power Apps CLI](https://aka.ms/PowerAppsCLI) のインストール

## <a name="try-the-sample-components"></a>サンプル コンポーネントを試す
モデル駆動型アプリまたはキャンバス アプリでサンプル コンポーネントをインポートして試すには、次の手順に従います。

1. サンプル コンポーネントをダウンロードしたコンピューター上のフォルダーに移動し、.zip ファイルを展開します。  
1. Visual Studio 2017 の開発者コマンド プロンプトを開き、ランタイムで表示する展開フォルダー内のサンプル コンポーネント フォルダーに移動します。 たとえば、\<extract_folder>/TS_IncrementComponent フォルダに移動します。
1. 次のコマンドを実行して、必要なすべての依存関係を取得します。
    ```CLI
    npm install
    ```
1. サンプル コンポーネント フォルダ内のコマンド`mkdir <folder name>`を使用して新しいフォルダを作成し、 コマンド `cd <folder name>` を使用してフォルダ内に移動します。 
1. 次のコマンドを使用して、フォルダー内に新しいソリューション プロジェクトを作成します。
    ```CLI
    pac solution init --publisher-name <Name of the publisher> --publisher-prefix <Publisher prefix>
    ```
1. 新しいソリューション プロジェクトを作成したら、サンプル コンポーネントが配置されている場所を参照します。 次のコマンドを使用して参照を追加できます。
    ```CLI
    pac solution add-reference --path <Path to the root of the sample component>
    ```
1. ソリューション プロジェクトから zip ファイルを生成するには、ソリューション プロジェクト ディレクトリに `cd` して、以下のコマンドを使ってプロジェクトをビルドする必要があります:
    
     ```CLI
     msbuild /t:restore
    ```
1. 再度、コマンド`msbuild`を実行します。
1. 生成されたソリューション zip ファイルは`Solution\bin\debug`フォルダーで使用できます。 zip ファイルの準備ができたら、Web ポータルを使用して、Common Data Service環境に手動で[ソリューションをインポート](/powerapps/maker/common-data-service/import-update-export-solutions)します。 または、Power Apps CLI コマンドを使用してソリューションをインポートするには、[環境への接続](https://docs.microsoft.com/powerapps/developer/component-framework/import-custom-controls#connecting-to-your-environment)および[デプロイメント](https://docs.microsoft.com/powerapps/developer/component-framework/import-custom-controls#deploying-code-components)セクションを参照してください。
1. 最後に、モデル駆動型アプリとキャンバス アプリにコード コンポーネントを追加するには、[モデル駆動型アプリにコンポーネントを追加する](https://docs.microsoft.com/powerapps/developer/component-framework/add-custom-controls-to-a-field-or-entity) and [キャンバスアプリにコンポーネントを追加する](https://docs.microsoft.com/powerapps/developer/component-framework/component-framework-for-canvas-apps#add-components-to-a-canvas-app)を参照してください。
