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
ms.openlocfilehash: d9a5d345204d82a1e5f6629a3f0bb7cf2159ddd7
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914468"
---
# <a name="common-issues-and-workarounds"></a>共通の問題と回避策

以下は、 Power Apps Component Framework と Power Apps CLI の使用中に遭遇する可能性のある一般的な問題です。

**Msbuild エラー MSB4036**

1. プロジェクト ファイルのタスク名はタスク クラスの名前と同じです。
2. タスク クラスはパブリックで Microsoft.Build.Framework.ITask インターフェイスを実装しています。
3. タスクは、プロジェクト ファイルの *\<UsingTask>* または、 パス ディレクトリに格納されている、 *.tasks ファイルにて正しく宣言されています。

**回避策**:

1. Visual Studio インストーラーを開きます。 
1. Visual Studio 2017 で、 **修正 を選択します**。 
1. **個別のコンポーネント** を選択します。
1. コード ツール配下の **NuGet ターゲットと構築タスク** を確認します。

> [!NOTE]
> 開発プロセス中に遭遇するたびに、共通の問題と回避策を常に追加します。 問題が発生して回避策があり、それが役立つと思う場合は、 [ここ](https://powerusers.microsoft.com/t5/Power-Apps-Component-Framework/bd-p/pa_component_framework) で問題を提起するか、プル リクエストを提起して、リストを確認してリストに追加できるようにします。

**発行元の接頭辞**

0.4.3 より前の CLI バージョンを使用してコンポーネントを作成した場合、 Common Data Service にソリューション ファイルを再インポートしようとするとエラーが発生します。 

**回避策**:

- Common Data Serviceからソリューションに関連するコンポーネントを削除します。 
- コンポーネントが依存関係を回避するように既に構成されている場合、コンポーネントをフィールドまたはグリッドから削除する必要があります。
- 最新の CLI バージョンで構築されたコンポーネントに対する更新を使用して、新しいソリューションをインポートします。
- 新たに読み込まれたコンポーネントは、フォームまたはグリッド上で設定できるようになっています。  

**既存のコード コンポーネントの更新中の問題**

1. pcf-scripts の使用方法を尋ねる 1ES 通知を取得した場合、これらのスクリプトはコード コンポーネントの作成のみに使用され、結果のコンポーネントによってバンドルまたは使用されないことに注意してください。  
2. CLI バージョン 0.1.817.1 以前を使用してコード コンポーネントを作成、あるいは、最新のビルドおよびデバッグ モジュールが使用されていることを確認したい場合は、以下に示すように `package.json` ファイルを更新します:
   
   ```JSON
   "dependencies": { "@types/node": "^10.12.18", "@types/powerapps-component-framework": "1.1.0"}, "devDependencies": { "pcf-scripts": "~0", "pcf-start": "~0" } 
   ```

3. 承認の問題でビルドが失敗したとき、エラー **リモート ソース <Feed Url> から Microsoft.PowerApps.MSBuild.Pcf に関する情報を取得できませんでした**。 

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
