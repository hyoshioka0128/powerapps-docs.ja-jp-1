---
title: 'クイック スタート: Web API サンプル (C#) (Common Data Service) | Microsoft Docs'
description: このサンプルでは、Common Data Service サーバーの認証方法、その後、基本的な Web API 操作である、WhoAmI Function を呼び出す方法を示しています。
ms.custom: ''
ms.date: 02/02/2019
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
ms.reviewer: pehecke
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 84ba00bfe3d634fcf4ad64e0447b6dc5dcb7d049
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155051"
---
# <a name="quick-start-web-api-sample-c"></a>クイック スタート: Web API のサンプル (C#)

このクイック スタートでは、Web API を使用して Common Data Service 環境に接続する簡単なコンソール アプリケーションを作成します。 

認証してから <xref:System.Net.Http.HttpClient> を使用して `GET` 要求を <xref href="Microsoft.Dynamics.CRM.WhoAmI?text=WhoAmI Function" /> に送信すると、応答は <xref href="Microsoft.Dynamics.CRM.WhoAmIResponse?text=WhoAmIResponse ComplexType" /> になります。 `UserId` プロパティの値が表示されます。

> [!NOTE]
> これは、最小限のコードで接続する方法を示す、非常に単純な例です。 次の[強化されたクイック スタート](enhanced-quick-start.md)は、より優れた設計パターンを適用するために、このサンプルを使用して構築されます。

## <a name="prerequisites"></a>前提条件

 - Visual Studio (2017 推奨)
 - インターネット接続
 - Common Data Service インスタンスに有効なユーザー アカウント
    - ユーザー名
    - パスワード
 - 接続に使用したい Common Data Service 環境への URL
 - Visual C# 言語の基本的な理解

> [!NOTE]
> 認証するには、Azure Active Directory に登録されているアプリが必要です。 このクイック スタート サンプルは、Microsoft が公開している実行中のサンプル コードの目的で使用できるアプリ登録 `clientid` 値を示します。 独自のアプリケーションの場合、アプリを登録する必要があります。 詳細: [チュートリアル: Azure Active Directory でアプリを登録する](../walkthrough-register-app-azure-active-directory.md)

## <a name="create-visual-studio-project"></a> Visual Studio プロジェクトの作成

1. **.NET Framework 4.6.2** を使用して新しいコンソール アプリ (.NET Framework) を作成する

    ![コンソール アプリケーション プロジェクトを開始する](../media/quick-start-web-api-console-app-csharp-1.png)

    > [!NOTE]
    > このスクリーンショットは、`WebAPIQuickStart` という名前を示していますが、必要に応じてプロジェクトとソリューションに名前を指定することを選択できます。

    > [!IMPORTANT]
    > **Visual Studio 2015 に関する既知の問題**
    > 
    > VS 2015 のデバッグモードでプロジェクト/ソリューションを実行していると、接続できなくなることがあります。 これは、4.6.2 以降のターゲットフレームワークを使用しているかどうかにかかわらず発生します。 これは、Visual Studio ホスティングプロセスが .NET 4.5 に対してコンパイルされているために発生します。これは既定で TLS 1.2 がサポートされていないことを意味します。 回避策として、Visual Studio ホスティング プロセスを無効にできます。 
    >
    > Visual Studio でプロジェクトの名前を右クリックしてから、**プロパティ**をクリックします。 **デバッグ**タブで、**Visual Studio ホスティング プロセスの有効化**オプションをオフにできます。 
    >
    > これは、VS 2015 のデバッグ エクスペリエンスにのみ影響を与えます。 これは構築されるバイナリまたは実行可能ファイルには影響しません。 同じ問題は、Visual Studio 2017 では発生しません。

1. **Solution Explorer** で、作成したプロジェクトを右クリックして、コンテキスト メニューで **NuGet パッケージの管理...** を選択します。

    ![NuGet  パッケージの追加](../media/quick-start-web-api-console-app-csharp-2.png)

1. `Microsoft.IdentityModel.Clients.ActiveDirectory` NuGet パッケージを参照する。
1. **バージョン** 2.29.0 を選択し、をインストールします。

    ![Microsoft.IdentityModel.Clients.ActiveDirectory NuGet パッケージをインストールする。](../media/quick-start-web-api-console-app-csharp-3.png)

    > [!IMPORTANT]
    > **この NuGet パッケージの最新バー所音をインストールしないでください。**
    >
    > このサンプルは、このライブラリの 3.x バージョンでは使用できない別個の Azure ログイン ダイアログを持たないユーザーのログイン資格情報を渡す機能に応じて異なります。

    > [!NOTE]
    > **ライセンスの承認** ダイアログで **同意する** を選択する必要があります。

1.  `Newtonsoft.Json` NuGet パッケージを参照して、最新バージョンをインストールします。

    ![Microsoft.IdentityModel.Clients.ActiveDirectory NuGet パッケージをインストールする。](../media/quick-start-web-api-console-app-csharp-4.png)

## <a name="edit-programcs"></a>Program.cs を編集する

1. `Program.cs` の一番上にステートメントを使用してこれらを追加する

    ```csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;
    using System.Net.Http.Headers;
    using System.Net.Http;
    using Newtonsoft.Json.Linq;
    ```

1. `Main` メソッドを次のコードに置き換えます。

    ```csharp
    static void Main(string[] args)
    {
       // Set these values:
        // e.g. https://yourorg.crm.dynamics.com
        string url = "<your environment url>";
        // e.g. you@yourorg.onmicrosoft.com
        string userName = "<your user name>";
        // e.g. y0urp455w0rd
        string password = "<your password>";

        // Azure Active Directory registered app clientid for Microsoft samples
        string clientId = "51f81489-12ee-4a9e-aaae-a2591f45987d";

        var userCredential = new UserCredential(userName, password);
        string apiVersion = "9.0";
        string webApiUrl = $"{url}/api/data/v{apiVersion}/";

        //Authenticate using IdentityModel.Clients.ActiveDirectory
        var authParameters = AuthenticationParameters.CreateFromResourceUrlAsync(new Uri(webApiUrl)).Result;
        var authContext = new AuthenticationContext(authParameters.Authority, false);
        var authResult = authContext.AcquireToken(url, clientId, userCredential);
        var authHeader = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

        using (var client = new HttpClient())
        {
            client.BaseAddress = new Uri(webApiUrl);
            client.DefaultRequestHeaders.Authorization = authHeader;

            // Use the WhoAmI function
            var response = client.GetAsync("WhoAmI").Result;

            if (response.IsSuccessStatusCode)
            {
                //Get the response content and parse it.  
                JObject body = JObject.Parse(response.Content.ReadAsStringAsync().Result);
                Guid userId = (Guid)body["UserId"];
                Console.WriteLine("Your UserId is {0}", userId);
            }
            else
            {
                Console.WriteLine("The request failed with a status of '{0}'",
                            response.ReasonPhrase);
            }

            Console.WriteLine("Press any key to exit.");
            Console.ReadLine();
        }       
    }
    ```

1. 環境の情報を追加するには、次の値を編集します。

    ```csharp
    // e.g. https://yourorg.crm.dynamics.com
    string url = "<your environment url>";
    // e.g. you@yourorg.onmicrosoft.com
    string userName = "<your user name>";
    // e.g. y0urp455w0rd
    string password = "<your password>";
    ```
    `url` を取得する: 

    1. 適切な環境が選択されている [https://make.powerapps.com](https://make.powerapps.com) サイトで、**設定** ![設定ボタン](media/settings-icon.png) を選択し、設定ボタン [設定] ボタンを選択し、**高度なカスタマイズ**を選択します。 **開発者リソース**を選択します。
    1. **開発者リソース** ページで、**インスタンスの Web API** 値を探してコピーします。 

        `https://yourorgname.api.crm.dynamics.com/api/data/v9.1/` のようになります。 ただし、このサンプルでは、最後の部分 (`/api/data/v9.1/`) を切り取って `https://yourorgname.api.crm.dynamics.com` にする必要があります。

    `userName` 変数と `password` 変数の場合は、[https://make.powerapps.com](https://make.powerapps.com) サイトにログインするのと同じ資格情報を使用します。

## <a name="run-the-program"></a>プログラムを実行する

1. F5 キーを押してプログラムを実行します。 出力は次のように表示されます。

    ```
    Your UserId is 969effb0-98ae-478c-b547-53a2968c2e75
    Press any key to exit.
    ```

### <a name="congratulations"></a>ご報告: 

Web API に正常に接続されました。

クイック スタートのサンプルでは、 Visual Studio プロジェクトを作成する簡単な方法を示しており、例外処理やアクセス トークンを更新するメソッドは使用していません。 

これは接続を確認するには十分ですが、アプリを構築するための優れたパターンは示しません。

[強化されたクイック スタート](enhanced-quick-start.md) のトピックでは、例外処理メソッド、接続文字列を使用する基本的な認証メソッド、アクセス トークンを更新するための再利用可能なメソッドの実装方法を示し、データ操作を実行するための再利用可能なメソッドの構築方法を紹介します。

## <a name="next-steps"></a>次のステップ

より優れた設計のためのコードを構造化する方法を説明します。

> [!div class="nextstepaction"]
> [強化されたクイック スタート](enhanced-quick-start.md)<br/>
