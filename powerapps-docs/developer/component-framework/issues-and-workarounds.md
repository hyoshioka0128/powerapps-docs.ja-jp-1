---
title: 一般的な問題と回避策 (Power Apps Component Framework) | Microsoft Docs
description: Power Apps Component Framework と CLI の使用中に発生する既知の問題と回避策に関する情報を提供します
keywords: ''
author: Nkrb
ms.author: nabuthuk
manager: kvivek
ms.date: 11/25/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.openlocfilehash: aaaa3e01902f1e2a9a96b1d2501d9931a6c8d085
ms.sourcegitcommit: efb05dbd29c4e4fb31ade1fae340260aeba2e02b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "3099908"
---
# <a name="common-issues-and-workarounds"></a>共通の問題と回避策

以下は、 Power Apps Component Framework と Power Apps CLI の使用中に遭遇する可能性のある一般的な問題です。

## <a name="msbuild-error-msb4036"></a>Msbuild エラー MSB4036

- プロジェクト ファイルのタスク名はタスク クラスの名前と同じです。
- タスク クラスはパブリックで Microsoft.Build.Framework.ITask インターフェイスを実装しています。
- タスクは、プロジェクト ファイルの *\<UsingTask>* または、 パス ディレクトリに格納されている、 *.tasks ファイルにて正しく宣言されています。

**回避策**:

- Visual Studio インストーラーを開きます。
- Visual Studio 2017 で、 **修正 を選択します**。
- **個別のコンポーネント** を選択します。
- コード ツール配下の **NuGet ターゲットと構築タスク** を確認します。

> [!NOTE]
> 開発プロセス中に遭遇するたびに、共通の問題と回避策を常に追加します。 問題が発生して回避策があり、それが役立つと思う場合は、 [ここ](https://powerusers.microsoft.com/t5/Power-Apps-Component-Framework/bd-p/pa_component_framework) で問題を提起するか、プル リクエストを提起して、リストを確認してリストに追加できるようにします。

## <a name="publisher-prefix"></a>発行元の接頭辞

0.4.3 より前の CLI バージョンを使用してコンポーネントを作成した場合、 Common Data Service にソリューション ファイルを再インポートしようとするとエラーが発生します。 

**回避策**:

- Common Data Serviceからソリューションに関連するコンポーネントを削除します。 
- コンポーネントが依存関係を回避するように既に構成されている場合、コンポーネントをフィールドまたはグリッドから削除する必要があります。
- 最新の CLI バージョンで構築されたコンポーネントに対する更新を使用して、新しいソリューションをインポートします。
- 新たに読み込まれたコンポーネントは、フォームまたはグリッド上で設定できるようになっています。  

## <a name="issues-while-updating-existing-code-components"></a>既存のコード コンポーネントの更新中の問題

- pcf-scripts の使用方法を尋ねる 1ES 通知を取得した場合、これらのスクリプトはコード コンポーネントの作成のみに使用され、結果のコンポーネントによってバンドルまたは使用されないことに注意してください。
- CLI バージョン 0.1.817.1 以前を使用してコード コンポーネントを作成、あるいは、最新のビルドおよびデバッグ モジュールが使用されていることを確認したい場合は、以下に示すように `package.json` ファイルを更新します:
   
   ```JSON
   "dependencies": { "@types/node": "^10.12.18", "@types/powerapps-component-framework": "1.1.0"}, "devDependencies": { "pcf-scripts": "~0", "pcf-start": "~0" } 
   ```

## <a name="error-failed-to-retrieve-information-about-microsoftpowerappsmsbuildpcf-from-remote-source-feed-url-when-the-build-fails-for-authorization-issues"></a>エラー: 承認の問題でビルドが失敗したとき、リモート ソース <Feed Url> から Microsoft.PowerApps.MSBuild.Pcf に関する情報を取得できませんでした。 

   **回避策**

   - **%APPDATA%\NuGet** から `NuGet.Config` ファイルを開きます。 ユーザーがエラーを得たフィードはこのファイルにある必要があります。 
   - `NuGet.Config file` からフィードを削除するか、PATトークンを生成して、 ` Nuget.Config file` に追加します。 たとえば、次のようなものです。

     ```XML
     <?xml version="1.0" encoding="utf-8"?>  
     <configuration>  
     <packageSources>  
         <add key="CRMSharedFeed" value="https://dynamicscrm.pkgs.visualstudio.com/_packaging/CRMSharedFeed/nuget/v3/index.json" />  
      </packageSources>  
      <packageSourceCredentials>  
      <CRMSharedFeed>  
      <add key="Username" value="anything" />  
      <add key="Password" value="User PAT" />  
        </CRMSharedFeed>  
        </packageSourceCredentials>  
       </configuration>
     ```

## <a name="web-resource-size-is-too-big"></a>Web リソース サイズが大きすぎます

エラー  **ソリューションのインポート エラー: Web リソースのコンテンツサイズが大きすぎます**。

**回避策**

- CLI ツールから `bundle.js` ファイルを作成する場合、ファイルを大きくする多くのコンポーネントがバンドルされます。 不要なコンポーネントをいくつか削除します。
- `node_modules/pcf-scripts/webpackconfig.js` ファイルを変更して、コンポーネントを `production` モードでビルドします。

## <a name="power-apps-component-framework-datasets-getvalue-by-property-alias-doesnt-work"></a>Power Apps component framework Datasets プロパティ エイリアスによる getValue が機能しない

Power Apps component framework データセット API の getValue 関数は、マニフェストに設定されたプロパティ エイリアスではなく、データセットの列名でのみレコードを検索します。 プロパティ エイリアスによって値を取得しようとすると、空の値が返されます。

**回避策**

データセットの列名 (コンポーネントはエイリアスを使用して列配列を検索することでデータセットの列名を取得できます) を使用します。 

   ***予想される動作*** 

   ```TypeScript
   long  = dataSet.records[currentRecordId].getValue("Longitude") //based on property set in manifest"-122.3514661"
   ```

   ***現在の回避策***

   ```TypeScript
   lat = dataSet.records[currentRecordId].getValue("Address_x0020_1_x003a__x0020_Latitude")//based on the dataset column name
   ```

## <a name="power-apps-component-framework-datasets-sharepoint-issue"></a>Power Apps component framework データセット SharePoint イシュー

Power Apps component framework データセット コンポーネントは現在、SharePoint のレコードを正しく表示していません。 ネットワーク要求は正しいデータ レコードが返されて成功しますが、逆シリアル化は失敗し、空のデータセットが返されます。

**回避策**

現在のところ、回避策はありません。 展開トレインに修正プログラムをプッシュする作業を行っています。

