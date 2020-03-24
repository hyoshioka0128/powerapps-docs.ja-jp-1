---
title: WS-Trust セキュリティプロトコルを使用した Office365 の認証の運用（Common Data Service）| Microsoft Docs
description: WS-Trust セキュリティ プロトコルを使用する上での非推奨事項と、アプリケーションで必要となる認証コードの変更点について説明します。
ms.custom: ''
ms.date: 02/05/2020
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: phecke
ms.author: pehecke
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 734d64fe24e7fbaec56109987fc8f0bb9163f5c8
ms.sourcegitcommit: 4f2e9e8f9bd3204ca9eee9e2a46f797c957c55ec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029795"
---
# <a name="use-of-office365-authentication-with-the-ws-trust-security-protocol"></a>WS-Trust セキュリティプロトコルを使用した Office365 の認証の運用

Common Data Service への接続時に WS-Trust 認証セキュリティ プロトコルを使用することは非推奨となっており、現在廃止されています。[お知らせ](/power-platform/important-changes-coming#deprecation-of-office365-authentication-type-and-organizationserviceproxy-class-for-connecting-to-common-data-service)を参照してください。 

この変更は、「Office365」の認証を使用したカスタマイズ クライアント アプリケーションと、[Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy](/dotnet/api/microsoft.xrm.sdk.client.organizationserviceproxy) または [Microsoft.Xrm.Tooling.Connector.CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient) クラスに影響します。 アプリケーションでこのタイプの認証プロトコルと API を使用している場合は、以下の説明をお読みの上で、アプリケーションのコードに推奨される認証の変更についてご確認ください。

## <a name="how-do-i-know-if-my-code-or-application-is-using-ws-trust"></a>コードやアプリケーションが WS-Trust を使用しているかどうかを確認するにはどうすればよいですか？

最も重要なことは、この変更が Common Data Service に接続するクライアント アプリケーション **のみ** に影響を与えるという点です。 カスタム プラグイン、ワークフロー アクティビティ、オンプレミス / IFDサービスの接続には影響しません。

- ご利用のコードで Common Data Service 、またはアプリケーションとの認証にユーザー アカウントとパスワード資格情報を使用する場合は、WS-Trust セキュリティ プロトコルを使用している可能性があります。 以下にいくつかの例を示しますが、この一覧にすべてが網羅されているわけではありません。

  - [CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient)クラスを接続文字列で使用している場合。

    `connectionString="AuthType=Office365; Username=jsmith\@contoso.onmicrosoft.com;Password=passcode;Url=https://contoso.crm.dynamics.com"`

  - [OrganizationServiceProxy](/dotnet/api/microsoft.xrm.sdk.client.organizationserviceproxy)クラスのコンストラクターを使用している場合。


```csharp
using (OrganizationServiceProxy organizationServiceProxy =
    new OrganizationServiceProxy(serviceManagement, clientCredentials)
{ ... }
```

- コードで `OrganizationServiceProxy` クラスを使用している場合は、WS-Trust を使用していることになります。

- [CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient).`OrganizationServiceProxy` を使用している場合。 ご利用のコードでは、WS-Trust を使用しています。

## <a name="what-should-i-do-to-fix-my-application-code-if-affected"></a>この影響を受けた場合、アプリケーションのコードを修正するにはどうすればよいですか？

非常に簡単な手順をご用意していますので、これに従ってアプリケーションのコードを変更し、推奨される接続インターフェイスを使用して Common Data Service との認証をしてください。

- コードで [Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy](/dotnet/api/microsoft.xrm.sdk.client.organizationserviceproxy)インスタンスを使用している場合。

  `OrganizationServiceProxy` インスタンスを複数のメソッドに渡している場合、または関数からインスタンスを返す、タイプ `OrganizationServiceProxy` のすべてのオカレンスを[IOrganizationService](/dotnet/api/microsoft.xrm.sdk.iorganizationservice?view=dynamics-general-ce-9) インターフェースに置き換えている場合。 このインタフェースは、Common Data Service との通信に使用されるすべてのコア メソッドを公開します。

  コンストラクターを呼び出す際には、プロジェクトに NuGet パッケージの [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) を追加し、すべての `OrganizationServiceProxy` コンストラクターと[CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient) クラスのコンストラクターを上書きすることを推奨します。 ここではコーディングのパターンを変更する必要がありますが、単純化をする目的で `CrmServiceClient` は複雑なコンストラクターや外部認証ハンドラーを提供する機能に加えて接続文字列にも対応しています。 `CrmServiceClient` は `IOrganizationService` を実装します。したがって、新しい認証コードをアプリケーション コードの残りの部分に移植することができます。 `CrmServiceClient` の使用例については、 [PowerApps-Samples](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23) リポジトリにて確認できます。

- コードが 「Office365」の認証タイプに [CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient) を使用している場合。

    この例で使用しているのは、次のような接続文字列です。

    `connectionString = "AuthType=Office365;Username=jsmith@contoso.onmicrosoft.com;Password=passcode;Url=https://contoso.crm.dynamics.com"`

    同様に、`AuthType.Office365` の `CrmServiceClient`コンストラクターとパスを使用することもできます。

    これに対処するには 2 つの選択肢があります。<p/>

    - Oauth ベースの接続文字列の使用へと切り替えます。 このような接続文字列は次のようになります。

        `connectionString = "AuthType=OAuth;Username=jsmith@contoso.onmicrosoft.com;
    Password=passcode;Url=https://contosotest.crm.dynamics.com;AppId=51f81489-12ee-4a9e-aaae-a2591f45987d;
    RedirectUri=app://58145B91-0C36-4500-8554-080854F2AC97;LoginPrompt=Auto"`

        これが一番早くコードを更新する方法となります。 LoginPrompt を 「never」 に設定すると、Office 365 の動作をシミュレートできます。

        上記の AppId および RedirectUri は、実動アプリケーションの登録値の例です。 これらの値は、オンライン サービスが展開されているすべての場所で機能します。 ただし、ここでは例として提供しているものであるため、テナントで実行されているアプリケーションに対しては、 Azure Active Directory (AAD)で独自のアプリケーション登録を作成することを推奨します。<p/>

    - この発表がされたあとで、自動リダイレクト サポートを含む最新の [Microsoft.CrmSdk.XrmTooling.CoreAssembly](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.CoreAssembly/) NuGet パッケージに更新してください。 このライブラリは、Office365 の認証タイプを Oauth へとリダイレクトし、サンプルの AppId とリダイレクト URI を自動的に使用します。 この機能は、Microsoft.CrmSdk.XrmTooling.CoreAssembly パッケージのバージョン 9.2.x で予定されています。

- [CrmServiceClient](/dotnet/api/microsoft.xrm.tooling.connector.crmserviceclient).`OrganizationServiceProxy` にアクセスしている場合。 プロパティ：

     ご利用のコード内にて、当該プロパティの使用をすべて停止します。 `CrmServiceClient` は、 `IOrganizationService` の実装を行い、組織のサービス プロキシに設定可能なすべてを公開します。

> [!IMPORTANT]
> Oauth を使用しても、ユーザーID / パスワードを使用してログインできない場合：テナントとユーザーが Azure Active Directory で設定されていて、条件付きアクセスを使用している。かつ/または多要素認証が必要となっている場合、ユーザーID /パスワードのフローを非対話形式で使用することはできません。 これらの状況では、サービス プリンシパル ユーザーを使用して Common Data Service を認証する必要があります。<p/>
これを行うには、Azure Active Directory で最初にアプリケーションユーザー（サービスプリンシパル）を登録する必要があります。 この方法については、[こちら](https://docs.microsoft.com/azure/active-directory/develop/howto-create-service-principal-portal)を参照してください。 アプリケーションの登録中に、Common Data Service でこのユーザーを作成し、権限を付与する必要があります。 これらの権限は、Common Data Service で権限を付与されたチームにアプリケーション ユーザーを追加することで、直接または間接的に付与することができます。 Common Data Service で認証するアプリケーションユーザーを設定する方法の詳細については、[こちら](/powerapps/developer/common-data-service/use-single-tenant-server-server-authentication)を参照してください。

## <a name="need-help"></a>ヘルプ

Power Apps ALM と ProDev のコミュニティ[フォーラム](https://powerusers.microsoft.com/t5/Power-Apps-Component-Framework/bd-p/pa_component_framework)を継続して監視します。 さまざまな問題の解決方法については、こちらをご確認頂くか、質問を投稿してください。
