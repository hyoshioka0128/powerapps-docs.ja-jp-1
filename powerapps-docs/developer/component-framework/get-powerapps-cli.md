---
title: Power Apps Component Framework のツールの入手 | Microsoft Docs
description: Microsoft Power Apps CLI を取得して、 Power Apps Component Framework を使用してコード コンポーネントを作成、デバッグおよび展開します。
keywords: Power Apps component framework、コード コンポーネント、コンポーネント フレームワーク
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f393f227-7a88-4f25-9036-780b3bf14070
ms.openlocfilehash: 4bc237027dab1459c3a9f83c6ff18310f35ff614
ms.sourcegitcommit: 64d816a759c5cc6343928d56a673812c3ea066c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "2895013"
---
# <a name="get-tooling-for-power-apps-component-framework"></a>Power Apps Component Framework のツールを入手します。

Power Apps Component Framework を使用して、コード コンポーネントを作成、デバッグ、および展開するには、**Microsoft Power Apps CLI** (コマンドライン インターフェイス) を使用します。 Power Apps CLI を使用すると、開発者はコードコンポーネントを簡単に作成することができます。 将来的に、追加の開発やアプリケーション ライフサイクル管理 (ALM) のエクスペリエンスのサポートを含むように拡張されます。 

## <a name="what-is-microsoft-power-apps-cli"></a>Microsoft Power Apps CLI とは 

Microsoft Power Apps CLIは、開発者やアプリ作成者がコード コンポーネントを作成できるようにするシンプルでワンストップな開発者向けコマンド ライン インターフェイスです。 Power Apps CLI ツールは、エンタープライズ開発者と ISV が拡張機能とカスタマイズを、すばやく効率的に作成、構築、デバッグ、および公開できる、包括的な ALM ストーリーの最初のステップです。  

## <a name="install-microsoft-power-apps-cli"></a>Microsoft Power Apps CLI のインストール

Microsoft Power Apps CLI を取得するには、次の手順を実行します。

1. [Npm](https://www.npmjs.com/get-npm) (Node.js に含まれる) または [Node.js](https://nodejs.org/en/) (npm に含まれる) をインストールします。 LTS (長期サポート）) バージョン10.15.3 以降をお勧めします。

1. [.NET Framework4.6.2開発者パック](https://dotnet.microsoft.com/download/dotnet-framework/net462) をインストールします 。 

1. Visual Studio 2017 以降をお持ちでない場合は、次のいずれかの方法に従ってください:
   - オプション1: [Visual Studio 2017](https://docs.microsoft.com/visualstudio/install/install-visual-studio?view=vs-2017)以降をインストールします。
   - オプション 2: [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download/dotnet-core/2.2) をインストールしてから、 [Visual Studioコード](https://code.visualstudio.com/Download) をインストールします。

1. [Microsoft Power Apps CLI](https://aka.ms/PowerAppsCLI) のインストール
1. すべての最新機能を利用するには、このコマンドを使用して Power Apps CLI ツールを最新バージョンに更新します:

    ```CLI
    pac install latest
    ```

> [!NOTE]
> - Power Apps CLI を使用してコード コンポーネントを展開するには、システム管理者またはシステム カスタマイザー特権を持つ Common Data Service 環境が必要です。
> - 現在、Power Apps CLI は Windows 10 でのみサポートされています。

## <a name="common-commands"></a>一般的なコマンド 

この表に、CLI で使用されるいくつかの一般的なコマンドを示します

|Command|説明|例|
|------|-----------|--------|
|**pcf**|Power Apps  Component Framework を使った作業に使用するコマンド これには次のパラメータが使用されています : <br/> - **init**：: コード コンポーネント プロジェクトを初期化します。 <br/> - **名前空間**: コード コンポーネントの名前空間。 <br/> - **名前**: コード コンポーネントの名前です。 <br/> - **テンプレート** : フィールドまたはデータセット <br/> - **プッシュ** : コードコンポーネントを最新のすべての変更を含む Common Data Service インスタンスにプッシュします。| `pac pcf init --namespace <specify your namespace here> --name <Name of the code component> --template <component type>` <br/> <br/> `pac pcf push --publisher-prefix <your publisher prefix>`|
|**ソリューション**|Common Data Service プロジェクトを使った業務に使用するコマンド これには次のパラメータが使用されています : <br/> - **init** : ソリューション プロジェクトを初期化します。<br/> - **公開元名** : 組織の公開元の名前。 <br/> - **公開元の名** : 組織の公開元のプレフックス。 <br/> - **参照の追加** : `path` パラメータを渡すことで、参照パスをコンポーネント プロジェクト フォルダーに設定します。<br/> - **クローン** : 次の`name`、`version`、および `include` パラメーターを渡すことにより、既存のソリューション プロジェクトに基づいてソリューション プロジェクトを作成します。|`pac solution init --publisher-name <enter your publisher name> --publisher-prefix <enter your publisher prefix>` <br/><br/> `pac solution add-reference --path <path to your Power Apps component framework project>`<br/><br/> `pac solution clone –name<name of the solution to be exported> --version <version of your solution> --include <settings that should be included>`|
|**auth**|Common Data Serviceへの認証をおこなうためのコマンド。 これには次のパラメータが使用されています : <br/> - **作成** : `url` パラメータを渡すことにより、組織の認証プロファイルを作成します。 `url` パラメータの組織の URL を提供する必要があります。 <br/> - **リスト** : 認証プロファイルのリストを提供します。 <br/> - **選択** : `index`パラメータを渡すことにより、以前に作成された認証プロファイルを切り替える方法を提供します。|`pac auth create --url <your Common Data Service org’s url>` <br/> <br/> `pac auth list` <br/><br/> `Pac auth select --index <index of the active profile>`|
|**テレメトリ**|テレメトリ設定を管理します。 次のパラメーターがあります : 有効および無効。|`pac telemetry enable` <br/><br/> `pac telemetry disable`|
|**org**|Common Data Service と作業するためのコマンド。|`pac org who`|
|**プラグイン**|プラグイン プロジェクトの作成を管理する|`pac plugin init`|

## <a name="uninstall-microsoft-power-apps-cli"></a>Microsoft Power Apps CLI をアンインストールします。

Power Apps CLI ツールをアンインストールするには、[こちら](https://aka.ms/PowerAppsCLI)から MSI を実行してください。 

プライベート プレビューの参加者の方で、CLI の古いバージョンをお持ちの場合は、次の手順を実行します:

1. Power Apps CLI がインストールされた場所を調べるには、コマンド プロンプトを開いて `where pac` と入力します。
1. PowerAppsCLI フォルダを削除します。
1. コマンド プロンプトでコマンド `rundll32 sysdm.cpl,EditEnvironmentVariables` を実行し、環境変数ツールを開きます。
1. `User variable for...` セクションの `Path` をダブルクリックします。
1. PowerAppsCLI のパスを含む行を選択して、右側の **削除** ボタンを選択します。
1. **OK** を 2 回選択します。

### <a name="see-also"></a>関連項目

[初めてコード コンポーネントを作成する](implementing-controls-using-typescript.md)<br/>
