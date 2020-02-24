---
title: グローバル探索サービス サンプル (C#) (Common Data Service) | Microsoft Docs
description: このサンプルは、OData v4 RESTful API を使用してグローバル探索サービスにアクセスする方法を示しています
ms.custom: ''
ms.date: 1/16/2020
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
ms.reviewer: susikka
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 11c2d71263ac9c60e9dc88b00f78da81755d40f0
ms.sourcegitcommit: 6b2961308c41867756ecdd55f55eccbebf70f7f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975714"
---
# <a name="global-discovery-service-sample-c"></a>グローバル検索サービスのサンプル (C#)

このサンプルは、OData v4 RESTful API を使用してグローバル探索にアクセスする方法を示しています。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

このサンプルは、Github 上に用意されています [https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/webapi/C%23/GlobalDiscovery](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/webapi/C%23/GlobalDiscovery)。

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルは、指定されたユーザー資格情報に対して、利用可能な Common Data Service インスタンスを返します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

このサンプルは、App.config ファイル内の資格情報を使用し、接続文字列内で構成された URL は使用しません。
代わりに、ユーザー資格情報および ClientId だけを使用します。

### <a name="demonstrates"></a>説明

このサンプルは、HttpClient を使用して ADAL (v2.29) を使用した認証を行い、グローバル検索を呼び出して、ユーザーが接続できる利用可能なインスタンスに関する情報を返します。

サンプルは、次のように `GetInstances` メソッドおよび `Instance` クラスに依存しています。

```csharp
    /// <summary>
    /// Uses the Discovery Service to return organization instances.
    /// </summary>
    /// <param name="clientId">The Azure AD client (app) registration</param>
    /// <param name="username">The user name</param>
    /// <param name="password">The password</param>
    /// <returns>A List of Instances</returns>
    static List<Instance> GetInstances(string clientId, string username, string password)
    {

      string GlobalDiscoUrl = "https://globaldisco.crm.dynamics.com/";
      AuthenticationContext authContext = new AuthenticationContext("https://login.microsoftonline.com", false);

      UserCredential cred = new UserCredential(username, password);
      AuthenticationResult authResult = authContext.AcquireToken(GlobalDiscoUrl, clientId, cred);

      HttpClient client = new HttpClient();
      client.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);
      client.Timeout = new TimeSpan(0, 2, 0);
      client.BaseAddress = new Uri(GlobalDiscoUrl);

      HttpResponseMessage response = client.GetAsync("api/discovery/v2.0/Instances", HttpCompletionOption.ResponseHeadersRead).Result;


      if (response.IsSuccessStatusCode)
      {
        //Get the response content and parse it.
        string result = response.Content.ReadAsStringAsync().Result;
        JObject body = JObject.Parse(result);
        JArray values = (JArray)body.GetValue("value");

        if (!values.HasValues)
        {
          return new List<Instance>();
        }

        return JsonConvert.DeserializeObject<List<Instance>>(values.ToString());
      }
      else
      {
        throw new Exception(response.ReasonPhrase);
      }
    }
```


```csharp
/// <summary>
  /// Object returned from the Discovery Service.
  /// </summary>
  class Instance
  {
    public string Id { get; set; }
    public string UniqueName { get; set; }
    public string UrlName { get; set; }
    public string FriendlyName { get; set; }
    public int State { get; set; }
    public string Version { get; set; }
    public string Url { get; set; }
    public string ApiUrl { get; set; }
    public DateTime LastUpdated { get; set; }
  }
```

