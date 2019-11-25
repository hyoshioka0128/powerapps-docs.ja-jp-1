---
title: SDK アセンブリで検出サービスを使用 (Common Data Service) | Microsoft Docs
description: .NET SDK アセンブリで探出サービスの使用方法について説明します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: e4790ae64c38cbf89a9af90822ff5b5910f64634
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2748977"
---
# <a name="use-the-discovery-service-with-the-sdk-assemblies"></a>SDK アセンブリで検出サービスを使用

[!INCLUDE [cc-discovery-service-description](../includes/cc-discovery-service-description.md)]


SDK アセンブリで検出サービスを使用するには、 `Microsoft.Xrm.Sdk.dll` アセンブリへの詳細を Visual Studio プロジェクトに追加し、 `using` に関する声明を追加して <xref:Microsoft.Xrm.Sdk.Discovery> の名前空間にアクセスします。 

<xref:Microsoft.Xrm.Sdk.WebServiceClient.DiscoveryWebProxyClient> は、<xref:Microsoft.Xrm.Sdk.Discovery.IDiscoveryService> インターフェイスを実装します。

<xref:Microsoft.Xrm.Sdk.Discovery.IDiscoveryService> インターフェイスには、編集の <xref:Microsoft.Xrm.Sdk.Discovery.DiscoveryRequest> クラスのインスタンスを渡すために使用する <xref:Microsoft.Xrm.Sdk.Discovery.IDiscoveryService.Execute(Microsoft.Xrm.Sdk.Discovery.DiscoveryRequest)> メソッドが用意されています。

## <a name="regional-discovery-services"></a>地域の探出サービス

<xref:Microsoft.Xrm.Sdk.WebServiceClient.DiscoveryWebProxyClient> をインスタンス化する場合は、次のいずれかの値を使用して地域のデータ センターの URL を記載する必要があります。

[!INCLUDE [regional-discovery-services](../../../includes/regional-discovery-services.md)]

> [!NOTE]
> ユーザーの地域が不明な場合は、結果を得るまで利用可能な地域からループする必要があります。 Web API には、単一のグローバル 検出サービスがあります。 詳細: [Web API を使用して組織の URL を検出する](../webapi/discover-url-organization-web-api.md)

## <a name="discovery-service-messages"></a>探出サービスのメッセージ

編集 <xref:Microsoft.Xrm.Sdk.Discovery.DiscoveryRequest> クラスのすべての検証を使える 3 つのメッセージがあります。

 <xref:Microsoft.Xrm.Sdk.Discovery.IDiscoveryService.Execute(Microsoft.Xrm.Sdk.Discovery.DiscoveryRequest)> メソッドでサポートされているメッセージの一覧を次の表に示します。  
  
|メッセージ|説明|  
|-------------|-----------------|  
|<xref:Microsoft.Xrm.Sdk.Discovery.RetrieveUserIdByExternalIdRequest>|Common Data Service にログオンしたユーザーの ID を取得する|  
|<xref:Microsoft.Xrm.Sdk.Discovery.RetrieveOrganizationRequest>|単一組織に関する情報を取得します。|  
|<xref:Microsoft.Xrm.Sdk.Discovery.RetrieveOrganizationsRequest>|ユーザーが属するすべての組織に関する情報を取得します。|  

## <a name="example"></a>例

コンソール アプリケーションの以下のコードは、<xref:Microsoft.Xrm.Sdk.Discovery.RetrieveOrganizationsRequest> メッセージを使用して、ユーザーのためにすべての組織を取得します。

```csharp
using System;
using System.Linq;
using Microsoft.Xrm.Sdk.Discovery;
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using Microsoft.Xrm.Sdk.WebServiceClient;

namespace DiscoveryServiceSample
{
    class Program
    {
        //These sample application registration values are available for all online instances.
        // this sample requires ADAL.net 5.2 + 
        public static string clientId = "51f81489-12ee-4a9e-aaae-a2591f45987d";

        static OrganizationDetailCollection GetOrganizationDetails(DiscoveryWebProxyClient svc)
        {

            var request = new RetrieveOrganizationsRequest()
            {
                AccessType = EndpointAccessType.Default,
                Release = OrganizationRelease.Current
            };
            try
            {
                var response = (RetrieveOrganizationsResponse)svc.Execute(request);
                return response.Details;
            }
            catch (Exception)
            {
                throw;
            }
        }
        static void Main(string[] args)
        {
            string authority = @"https://login.microsoftonline.com/common";
            string northAmericaResourceUrl = "https://disco.crm.dynamics.com";
            string discoveryUrl = $"{northAmericaResourceUrl}/XRMServices/2011/Discovery.svc/web";
            Uri discoveryUri = new Uri(discoveryUrl);

            AuthenticationContext authContext = new AuthenticationContext(authority, false);
            string username = "you@yourorg.onmicrosoft.com";
            string password = "yourPassword"; 

            AuthenticationResult authResult = null;
            if (username != string.Empty && password != string.Empty)
            {
                UserPasswordCredential cred = new UserPasswordCredential(username, password);
                authResult = authContext.AcquireTokenAsync(northAmericaResourceUrl, clientId, cred).Result;
            }

           
            using (var svc = new DiscoveryWebProxyClient(discoveryUri))
            {
                svc.HeaderToken = authResult.AccessToken;

                OrganizationDetailCollection details = GetOrganizationDetails(svc);

                details.ToList().ForEach(x =>
                {
                    Console.WriteLine("Organization Name: {0}", x.FriendlyName);
                    Console.WriteLine("Unique Name: {0}", x.UniqueName);
                    Console.WriteLine("Endpoints:");
                    foreach (var endpoint in x.Endpoints)
                    {
                        Console.WriteLine("  Name: {0}", endpoint.Key);
                        Console.WriteLine("  URL: {0}", endpoint.Value);
                    }
                    Console.WriteLine();
                });
            };
            Console.ReadLine();
        }
    }
}

```

2 つのインスタンスにアクセスできるユーザーの場合、結果は次のようになります。

```
Organization Name: Organization A
Unique Name: orga
Endpoints:
  Name: WebApplication
  URL: https://orgaservice.crm.dynamics.com/
  Name: OrganizationService
  URL: https://orgaservice.api.crm.dynamics.com/XRMServices/2011/Organization.svc
  Name: OrganizationDataService
  URL: https://orgaservice.api.crm.dynamics.com/XRMServices/2011/OrganizationData.svc

Organization Name: Organization B
Unique Name: orgb
Endpoints:
  Name: WebApplication
  URL: https://orgbservice.crm.dynamics.com/
  Name: OrganizationService
  URL: https://orgbservice.api.crm.dynamics.com/XRMServices/2011/Organization.svc
  Name: OrganizationDataService
  URL: https://orgbservice.api.crm.dynamics.com/XRMServices/2011/OrganizationData.svc
```

> [!NOTE]
> `OrganizationDataService` は、廃止された Organization Data Service で、Web API ではありません。 このサービスの場合、Web API の URL は設定されていません。


### <a name="see-also"></a>関連項目

[検出サービス](../discovery-service.md)<br />
[Web API を使用して組織の URL を検出します](../webapi/discover-url-organization-web-api.md)
