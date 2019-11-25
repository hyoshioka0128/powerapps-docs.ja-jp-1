---
title: コンポーネントのインポート | Microsoft Docs
description: このトピックでは、コード コンポーネントをインポートする方法について説明します
keywords: ''
ms.author: nabuthuk
manager: kvivek
ms.date: 06/20/2019
ms.service: powerapps
ms.suite: ''
ms.topic: article
author: Nkrb
ms.openlocfilehash: 4bb581e06102ac351b3202d30fa8d418951fa291
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749056"
---
# <a name="package-a-code-component"></a>コード コンポーネントをパッケージ化する

このトピックでは、コード コンポーネントを Common Data Service にインポートする方法について説明します。 PowerApps CLIを使用してコード コンポーネントを実装した後、次の手順としては、すべてのコード コンポーネント要素をソリューション ファイルにバンドルし、ソリューション ファイルを  Common Data Service にインポートします。これによりランタイムでコード コンポーネントを表示できるようになります。

ソリューション ファイルを作成およびインポートするには:

1. サンプル コンポーネントのフォルダー内に新規フォルダーを作成するには、コマンド `mkdir Solutions` を使用して **ソリューション** (または任意の名前) と名前を付けます。 コマンド `cd Solutions` を使用して、ディレクトリに移動します。

2. コマンド `pac solution init --publisher-name <enter your publisher name> --publisher-prefix <enter your publisher prefix>` を使用して新しいソリューション プロジェクトを作成します。 ソリューション プロジェクトは、Common Data Service へインポートするために使用されるソリューション zip ファイルにコード コンポーネントをビルドするために使用されます。

   > [!NOTE]
   > `publisher-name` と `publisher-prefix` の値は環境に固有である必要があります。
 
3. 新しいソリューション プロジェクトを作成したら、**ソリューション** フォルダーを作成したサンプル コンポーネントがある場所に参照します。 以下に示すコマンドを使用して参照を追加することができます。 この参照は、コード コンポーネントがビルド中に追加すべきソリューションのプロジェクトを通知します。 参照を 1 つのソリューションのプロジェクトの複数コンポーネントへ追加できます。

   ```CLI   
    pac solution add-reference --path <path to your PowerApps component framework project>
   ```

3. ソリューションプロジェクトから zip ファイルを生成するには、ソリューション プロジェクトのディレクトリに移動して、コマンド `msbuild /t:build /restore` を使用してプロジェクトをビルドします。 このコマンドは *MSBuild* を使用して、復元の一部として *NuGet* の依存関係をプルダウンすることで、ソリューション プロジェクトを構築します。 初めてソリューションプロジェクトを構築する際には `/restore` のみを使用します。 その後の各ビルドに対しては、コマンド `msbuild` を実行できます。


    > [!NOTE]
    > - msbuild 15.9.*がパスに存在しない場合は、VS2017の開発者コマンドプロンプトを開いて `msbuild` コマンドを実行します。
    > - *デバッグ* 構成でソリューションをビルドして、アンマネージド ソリューション パッケージを生成します。 管理ソリューション パッケージは、*リリース* 構成でソリューションを構築することにより生成されます。 これらの設定は、`cdsproj` ファイルの `SolutionPackageType` プロパティを指定することでオーバーライドできます。
    > - 運用ビルドを発行するために`Release` にmsbuild構成を設定できます。 例: `msbuild /p:configuration=Release`
    > - ソリューションで `msbuild` コマンドを実行する際に *Ambiguous project name* と言うエラーが発生した場合は、ソリューション名とプロジェクト名が同じでないことを確認してください。

4. 生成されたソリューション ファイルは、ビルド正常に行なわれたら `\bin\debug\` フォルダー内に配置されます。
5. 手動で Web ポータルを使って[ソリューションを Common Data Service にインポートする](https://docs.microsoft.com/powerapps/maker/common-data-service/import-update-export-solutions) か、[あなたの組織に対する認証](#authenticating-to-your-organization) および [展開](#deploying-code-components) セクションを PowerApps CLI コマンドを使用してインポートします。

## <a name="authenticating-to-your-organization"></a>組織への認証

Common Data Service 組織への認証をして、その後更新したコンプ―ネントをプッシュすることで、 PowerApps CLI から直接コード コンポーネントを展開することができます。 認証プロファイルを作成して、Common Data Service に接続し、更新コンポーネントをプッシュするには次の手順を使用します。 
 
1. 次のコマンドを使用して認証プロファイルを作成します: 
 
    ```CLI
    pac auth create --url <your Common Data Service org’s url> 
    ```
 
2. 以前認証プロファイルを作成した場合は、次のコマンドを使用してすべての既存プロファイルを表示できます: 

   ```CLI
    pac auth list 
   ```
 
3. 前に作成した認証プロファイル間を切り替えるには、次のコマンドを使用します: 
   
   ```CLI
    Pac auth select --index <index of the active profile>
    ``` 

4. 組織に関する基本的な情報を取得するには、次のコマンドを使用します。 接続は既定の認証のプロファイルを使用しておこないます。 

    ```CLI
    pac org who 
    ```
 
5. 特定の認証プロファイルを削除するには、`pac auth delete --index < index of the profile >` コマンドを使用します。 
6. ローカル コンピューターからすべての認証プロファイルをオフにする場合は、`pac auth clear` コマンドを使用します。 この操作は、ローカル コンピュータから完全に `authprofile.json` ファイルやトークン キャッシュ ファイルを削除するため不可逆です。 

## <a name="deploying-code-components"></a>コード コンポーネントのデプロイ 

正常に認証プロファイルを作成したら、すべて最新の変更で Common Data Service インスタンスにコード コンポーネントをプッシュし始めることができます。 `push` 機能は、コード コンポーネントのバージョン管理要件をバイパスして、コード コンポーネントをインポートするためにソリューション (cdsproj) を作成する必要がないため、社内開発者サイクルの開発を高速化します。 `push` 機能を使用するには、以下のことを行います:

1. 有効な認証のプロファイルを作成したことを確認します。
2. コード コンポーネントのプロジェクトが作成されたルート ディレクトリに移動します。
3. `pac pcf push --publisher-prefix <your publisher prefix>` コマンドを実行します。

   > [!NOTE]
   > `push` コマンドで使用する公開元は、コンポーネントを含むソリューションの公開元の接頭辞と一致させる必要があります。

## <a name="how-to-remove-components-from-a-solution"></a>ソリューションからコンポーネントを削除する方法

ソリューション ファイルからコード コンポーネントを削除したい場合:

1.  ソリューション プロジェクト ディレクトリの `cdsproj` ファイルを編集し、コンポーネントへの参照を削除します。 以下は、コンポーネント 参照の例です:

   ```XML
   <ItemGroup>
       <Projectreference Include="..\pcf_component\pcf_component.pcfproj">
         <Project>0481bd83-ffb0-4b70-b526-e0b3dd63e7ef</Project>
         <Name>pcf_component </Name>
         <Targets>Build</Targets>
         <referenceOutputAssembly>false</referenceOutputAssembly>
         <OutputItemType>Content</OutputItemType>
         <CopyToOutputDirectory>Always</CopyToOutputDirectory>
       </Projectreference>
   </ItemGroup>
   ```

2. 以下のコマンドを使用して再構築 (またはクリーンアップ) を実行します:
   
    ```CLI
    msbuild /t:rebuild
    ```

### <a name="see-also"></a>関連項目

[モデル駆動型アプリでフィールドやエンティティにコード コンポーネントを追加する](add-custom-controls-to-a-field-or-entity.md)<br/>
[キャンバス アプリにコンポーネントを追加する](component-framework-for-canvas-apps.md#add-components-to-a-canvas-app)<br/>
[PowerApps Component Framework API の参照](reference/index.md)<br/>
[PowerApps Component Framework の概要](overview.md)
