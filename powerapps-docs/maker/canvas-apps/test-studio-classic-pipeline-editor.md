---
title: クラシックエディターを使用して Azure パイプラインでテストを自動化する |Microsoft Docs
description: Azure パイプラインのクラシックエディターを使用してテストスイートとケースを自動化する方法について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/16/2020
ms.author: aheaney
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ecfeeb1f62032008d7ada618afb56e6da8589f40
ms.sourcegitcommit: 223c3d19ec4fbe43fcc7a16b76423c00f8602ecd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81490892"
---
# <a name="automate-tests-with-azure-pipeline-using-classic-editor"></a>クラシックエディターを使用して Azure パイプラインでテストを自動化する

この記事では、 [Azure DevOps Services](https://docs.microsoft.com/azure/devops/user-guide/what-is-azure-devops?view=azure-devops)の[Azure Pipelines クラシックエディター](https://docs.microsoft.com/azure/devops/pipelines/get-started/pipelines-get-started?view=azure-devops#define-pipelines-using-the-classic-interface)を使用して、テスト Studio でビルドされたキャンバスアプリテストを設定して実行する方法について説明します。

GitHub のパブリックプロジェクト ( [Microsoft/PowerAppsTestAutomation](https://github.com/microsoft/PowerAppsTestAutomation) ) を使用して、次のことを行うことができます。

- アプリケーションへのログイン操作を自動化します。
- ビルドエージェントでブラウザーを開き、一連のテストケースとスイートを実行します。
- Azure DevOps パイプラインでテストの実行の状態を表示します。

## <a name="prerequisites"></a>前提条件

開始する前に、次の手順を完了しておく必要があります。

- GitHub で[Microsoft/PowerAppsTestAutomation](https://github.com/microsoft/PowerAppsTestAutomation)プロジェクトを[フォーク](#step-1---fork-the-powerappstestautomation-project)します。

    > [!NOTE]
    > パブリックフォークをプライベートにすることはできません。 プライベートリポジトリを作成する場合は、リポジトリを[複製](https://help.github.com/github/creating-cloning-and-archiving-repositories/duplicating-a-repository)してください。

- パイプラインから実行するアプリテスト Url を使用して、リポジトリに新しい[*テスト url. json ファイル*](#step-2---create-test-url-json-file)を作成します。

### <a name="step-1---fork-the-powerappstestautomation-project"></a>手順 1-PowerAppsTestAutomation プロジェクトをフォークする

[フォーク](https://help.github.com/github/getting-started-with-github/fork-a-repo)は、リポジトリのコピーです。 リポジトリをフォークすることによって、元のプロジェクトに影響を与えることなく変更を加えることができます。

1. [GitHub](https://github.com/)にサインインします。

1. [Microsoft/PowerAppsTestAutomation](https://github.com/microsoft/PowerAppsTestAutomation)リポジトリにアクセスします。 代わりに**microsoft/PowerAppsTestAutomation**を検索し、リポジトリを選択することもできます。

    ![GitHub の検索](media/test-studio-classic-pipeline-editor/search-github.png)

1. **フォーク**の選択:

    ![フォーク](media/test-studio-classic-pipeline-editor/fork.png)

1. フォークが必要な場所を選択します。

    ![フォークアカウント](media/test-studio-classic-pipeline-editor/fork-account.png)

フォークされたリポジトリが使用できるようになります。

### <a name="step-2---create-test-url-json-file"></a>手順 2-テスト URL の作成 json ファイル

テスト URL. json ファイルには、アプリを検証するためのテストスイートとテストケースの Url が含まれます。 アプリのテストスイートとテストケースの Url は、テスト studio で [[コピー再生] リンク](working-with-test-studio.md#playing-tests-in-a-browser)を選択すると取得できます。

先ほど作成したリポジトリにサンプルファイル ```Samples/TestAutomationURLs.json``` があります。

1. リポジトリに新しい ```TestURLs.json``` ファイルを作成するか、他のファイル名を使用します。 <br> ファイル名と場所は、ドキュメントの後半でパイプライン変数にマップされます。

1. ```Samples/TestAutomationURLs.json``` ファイルから形式をコピーします。

1. アプリケーションで検証するテストを使用して、[テスト Url] セクションを更新します。

1. 変更をリポジトリにコミットします。

    ![JSON の更新](media/test-studio-classic-pipeline-editor/json-update.png)

## <a name="create-a-pipeline"></a>パイプラインを作成する

1. Azure DevOps インスタンスにサインインします。

1. 既存のプロジェクトを選択するか、新しいプロジェクトを作成します。

1. 左側のメニューの **[パイプライン]** を選択します。

1. **[パイプラインの作成]** を選択します。

    ![パイプラインの作成](media/test-studio-classic-pipeline-editor/create-pipeline.png)

1. **[クラシックエディターを使用する]** を選択します。

    ![クラシックエディター](media/test-studio-classic-pipeline-editor/use-classic-editor.png)

1. ソースとして [GitHub] を選択します。

1. 必要に応じて、OAuth または個人用アクセストークンを使用して GitHub 接続を承認します。

    ![パイプライン-GitHub](media/test-studio-classic-pipeline-editor/pipeline-github.png)

1. 必要に応じて、接続名を編集します。

1. **リポジトリ**入力の右側にある [. **.** ] (省略記号) を選択します。

1. GitHub にプロジェクトの名前を入力し、**選択**します。

    ![リポジトリの選択](media/test-studio-classic-pipeline-editor/select-repo.png)

1. **[続行]** を選択します。

1. テンプレートの選択 画面で、**空のジョブ** を選択します。

    ![空のジョブ](media/test-studio-classic-pipeline-editor/empty-job.png)

1. パイプラインを**保存**します。

## <a name="add-tasks-to-the-pipeline"></a>パイプラインへのタスクの追加

ここでは、新しいジョブタスクを追加し、次の順序でパイプラインからテストを実行するようにタスクを構成します。

1. [PowerShell を使用して画面の解像度を構成します。](#step-1---configure-screen-resolution-using-powershell)

1. [PowerAppsTestAutomation ソリューションの NuGet パッケージを復元します。](#step-2---restore-nuget-packages)

1. [PowerAppsTestAutomation ソリューションをビルドします。](#step-3---build-the-powerappstestautomation-solution)

1. [Google Chrome の Visual Studio テストを追加します。](#step-4---add-visual-studio-tests-for-google-chrome)

1. [Mozilla Firefox の Visual Studio テストを追加します。](#step-5---add-visual-studio-tests-for-mozilla-firefox)

### <a name="step-1---configure-screen-resolution-using-powershell"></a>手順 1-PowerShell を使用して画面の解像度を構成する

1. *エージェントジョブ 1*の横にある [ **+** ] を選択します。

1. **PowerShell**を検索します。

1. **[追加]** を選択して、PowerShell タスクをジョブに追加します。

    ![PowerShell](media/test-studio-classic-pipeline-editor/powershell.png)

1. タスクを選択します。 <br>
    また、表示名を更新して、*エージェントの画面の解像度を 1920 x 1080*または同様に設定することもできます。

1. スクリプトの種類として **[インライン]** を選択し、スクリプトウィンドウに次のように入力します。

    ```powershell
    # Set agent screen resolution to 1920x1080 to avoid sizing issues with Portal  
    Set-DisplayResolution -Width 1920 -Height 1080 -Force
    # Wait 10 seconds  
    Start-Sleep -s 10
    # Verify Screen Resolution is set to 1920x1080  
    Get-DisplayResolution
    ```

    ![スクリプト](media/test-studio-classic-pipeline-editor/script.png)

### <a name="step-2---restore-nuget-packages"></a>手順 2-NuGet パッケージを復元する

1. エージェントジョブ1の横にある [ **+** ] を選択します。

1. **NuGet**を検索します。

1. [追加] を選択して、NuGet タスクをジョブに追加します。

1. タスクを選択します。
    <br> また、表示名を更新して**NuGet パッケージ**または同様の復元を行うこともできます。

1. 選択. **.** (省略記号) を参照してください。 [**ソリューションへのパス]、[パッケージ**の構成]、または [プロジェクトの json 構成] フィールドです。

1. PowerAppsTestAutomation ソリューションファイルを選択します。

1. [ **OK]** を選択します。

    ![NuGet パッケージ](media/test-studio-classic-pipeline-editor/nuget.png)

### <a name="step-3---build-the-powerappstestautomation-solution"></a>手順 3-PowerAppsTestAutomation ソリューションをビルドする

1. エージェントジョブ1の横にある [ **+** ] を選択します。

1. **Visual Studio のビルド**を検索します。

1. **[追加]** を選択して、Visual Studio のビルドタスクをジョブに追加します。

1. タスクを選択します。
    <br> また、表示名を更新して、**パワーアプリのテスト自動化ソリューション**または類似したビルドを作成することもできます。

1. 選択. **.** (省略記号) を**ソリューション**構成フィールドに入力します。

1. PowerAppsTestAutomation ソリューションファイルを選択します。

1. **[OK]** を選択します。

### <a name="step-4---add-visual-studio-tests-for-google-chrome"></a>手順 4-Google Chrome の Visual Studio テストを追加する

1. エージェントジョブ1の横にある [ **+** ] を選択します。

1. **Visual Studio テスト**を検索します。

1. [追加] を選択して、Visual Studio テストタスクをジョブに追加します。

1. タスクを選択します。
    <br> また、表示名を更新して、 *Power Apps テスト自動化テストを \$(Browsertypのローマ)* または同様の方法で実行することもできます。

1. [テストファイル] テキストフィールドの既定のエントリを削除し、次の項目を追加します。

    ```**\Microsoft.PowerApps.TestAutomation.Tests\bin\\Debug\Microsoft.PowerApps.TestAutomation.Tests.dll```

1. [**テストフィルター条件] フィールド**に ```TestCategory=PowerAppsTestAutomation``` を入力します。

1. **[テストミックスに UI テストを含める]** を選択します。

    ![Chrome](media/test-studio-classic-pipeline-editor/chrome.png)

1. 選択. **.** (省略記号) を**設定ファイル**フィールドに入力します。

1. [ **Microsoft.** .] を展開し、 **patestautomation. runsettings**ファイルを選択して、[ **OK]** を選択します。

    ![実行設定](media/test-studio-classic-pipeline-editor/runsettings.png)

1. **[テストの実行パラメーターのオーバーライド]** フィールドで、次の項目をコピーします。

    ```
    -OnlineUsername $(OnlineUsername) -OnlinePassword $(OnlinePassword) -BrowserType $(BrowserTypeChrome) -OnlineUrl $(OnlineUrl) -UsePrivateMode $(UsePrivateMode) -TestAutomationURLFilePath $(TestAutomationURLFilePath) -DriversPath $(ChromeWebDriver)
    ```

    > [!NOTE]
    > ここでは、パイプラインの変数を \$(VariableName) の形式で構成します。

1. テストの実行 タイトル フィールドで、 **\$(ブラウザー**の型の入力) またはそれに似た方法で実行してください。

    ![テスト実行](media/test-studio-classic-pipeline-editor/test-run.png)

### <a name="step-5---add-visual-studio-tests-for-mozilla-firefox"></a>手順 5-Mozilla Firefox の Visual Studio テストを追加する

1. **[Chrome 用 Visual Studio テストの追加]** タスクを右クリックし、 **[タスクの複製]** を選択します。

1. タスクを選択し、次の領域を更新します。

    1. **タイトル**: \$(BrowserTypeFirefox) のコピーを使用して Power Apps テスト自動化テストを実行する

    1.  **テストの実行パラメーターのオーバーライド**

        ```
        -OnlineUsername $(OnlineUsername) -OnlinePassword $(OnlinePassword) -BrowserType $(BrowserTypeFirefox) -OnlineUrl $(OnlineUrl) -UsePrivateMode $(UsePrivateMode) -TestAutomationURLFilePath $(TestAutomationURLFilePath) -DriversPath $(GeckoWebDriver)
        ```

    1.  **テストの実行のタイトル**: Power Apps を実行する \$を使用したテスト自動化テスト (browsertypefirefox)

## <a name="configure-pipeline-variables"></a>パイプライン変数の構成

ここでは、[前](#add-tasks-to-the-pipeline)に追加したタスクで定義されているパイプライン変数を構成します。

1. **[変数]** タブを選択します。

2. **[追加]** を選択し、この手順を繰り返して、次の変数を構成します。

| 変数名             | 変数値                                                                                                                 |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| ブラウザーの Typtypローマ         | Chrome                                                                                                                         |
| BrowserTypeFirefox        | Firefox                                                                                                                        |
| オンライン Url                 | <https://make.powerapps.com>                                                                                                   |
| TestAutomationURLFilePath | ```$(Build.SourcesDirectory)\<test URL file>.json``` <br>**注:** これは、前に作成した[*テスト url の json ファイル*](#step-2---create-test-url-json-file)ファイルです。                      |
| UsePrivateMode            | true                                                                                                                           |
| オンラインユーザー名            | アプリケーションにサインインするユーザーコンテキストの Azure Active Directory 電子メールアドレスを入力します。 テストは、このユーザーアカウントのコンテキストで実行されます。\> |

1. [追加] を選択し、変数名に「**オンラインパスワード**」と入力します。

1. ロックイメージを確認して、この変数をシークレットにします。

    ![変数](media/test-studio-classic-pipeline-editor/variables.png)

1. パイプラインの構成を**保存**します。

## <a name="run-and-analyze-tests"></a>テストの実行と分析

テストが正常に実行されていることを確認するには、 **[キュー]** を選択し、 **[実行]** を選択します。 ジョブの実行が開始されます。

![ジョブの実行](media/test-studio-classic-pipeline-editor/run-job.png)

ジョブの実行中、ジョブを選択すると、実行中の各タスクの詳細な状態が表示されます。

![ジョブの詳細](media/test-studio-classic-pipeline-editor/job-details.png)

ジョブが完了すると、高レベルのジョブの概要と、エラーまたは警告が表示されます。 [テスト] タブを選択すると、実行したテストケースに関する特定の詳細を表示できます。

次の例は、Chrome ブラウザーを使用してテストを実行しているときに、テストケースの少なくとも1つが失敗したことを示しています。

![Chrome-失敗](media/test-studio-classic-pipeline-editor/chrome-failed.png)

[ **Runtestautomation**テスト] を選択して、失敗したテストケースの詳細にドリルダウンします。 [*添付ファイル] タブ*では、テストの実行の概要と、テストスイートで失敗または成功したテストケースを確認できます。

![[添付ファイル] タブ](media/test-studio-classic-pipeline-editor/attachments-tab.png)

> [!NOTE]
> テストスイートを実行すると、成功したテストケースと失敗したテストケースの概要が表示されます。 テストケースを実行すると、トレース情報があれば、そのエラーに関する具体的な詳細情報が表示されます。

## <a name="known-limitations"></a>既知の制限事項

- Multi-factor authentication はサポートされていません。

- Internet Explorer 11 と Microsoft Edge はサポートされていないブラウザーです。

- テストの概要では、ブラウザーごとに1つのテスト結果が報告されます。 テスト結果には、1つ以上のテストケースまたはテストスイートの結果が含まれます。   

- Azure Active Directory サインインフロー以外の認証プロセスでは、 **PowerAppsTestAutomation**ソリューションのサインインプロセスをカスタマイズする必要があります。

### <a name="see-also"></a>参照

- [テスト スタジオの概要](test-studio.md)
- [テスト スタジオの操作](working-with-test-studio.md)