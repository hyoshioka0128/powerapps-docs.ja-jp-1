---
title: 自社組織のURLを検出する (Common Data Service)| Microsoft Docs
description: 検出サービスを使用して、ログオンしているユーザーが属する組織（インスタンス）を検索します
ms.custom: ''
ms.date: 1/16/2020
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 2db13b4e-0e7c-4f25-b7be-70a612fb96e2
caps.latest.revision: 18
author: JimDaly
ms.author: jdaly
ms.reviewer: pehecke
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: bc68a5ae74c72f2dbc9a8240253574348d85a7cd
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155091"
---
# <a name="discover-the-url-for-your-organization"></a>組織の URL を見つける

[!INCLUDE [cc-discovery-service-description](../includes/cc-discovery-service-description.md)]

OData V4 RESTful API を使用して検出サービスにアクセスする場合、サービス リクエストに標準的な `$filter` と `$select` パラメーターを追加して、返されるインスタンス データのリストをカスタマイズすることができます。

> [!IMPORTANT]
> - 2020年3月2日より、*地域* の検出サービスは [廃止](/power-platform/important-changes-coming#regional-discovery-service-is-deprecated) されます。 アプリケーションは、このトピックに記載されているグローバル 検出サービスを使用する必要があります。  
> - Dynamics 365 US Government ユーザーの場合、 **GCC** と **GCC High** ユーザーは、*グローバル* 検出サービスのエンドポイントが利用できます。このURLは通常のグローバル検出サービスのURLとは異なります。 詳細情報: [Dynamics 365 Government の URL](https://docs.microsoft.com/dynamics365/customer-engagement/admin/government/microsoft-dynamics-365-government#dynamics-365-us-government-urls)。

  
## <a name="information-provided-by-the-discovery-service"></a>検出サービスが提供する情報 
 
組織の情報は、検出サービスの `Instance` エンティティに保存されます。  そのエンティティに含まれている情報を表示するには、まずインスタンスの 1 つのサービスに HTTP GET 要求を送信します。  
  
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(UniqueName='myorg')  
```  
  
上記の例では、 グローバル検出サービスを使用して、「myorg」 という一意の名前のインスタンスの組織情報を取得しています。 この要求に関する詳細については、このトピックの後半で詳しく説明します。  

### <a name="scope-of-the-returned-information"></a>返される情報のスコープ

グローバル検出サービスでは、 `Instances` エンティティ セットは、フィルターが適用されない場合に、すべての地域のユーザーがアクセスするインスタンスのセットを返します。   次の説明に従って、返されたデータのスコープがあります。  
  
-   主権あるクラウド インスタンスが返されないことを除き、ユーザーに対してプロビジョニングされ、有効化された商用クラウド内のすべてのインスタンスが含まれます
-   ユーザー アカウントが無効の場合、インスタンスは含まれません。
-   インスタンス セキュリティ グループに基づいて、ユーザーがフィルターによって除外された場合、インスタンスは含まれません。
-   ユーザーが代理管理者であるためアクセス権を持っている場合、インスタンスは含まれません。
-   呼び出し元ユーザーがインスタンスへのアクセス権を持っていない場合は、応答は、空のリストを返します。

## <a name="how-to-access-the-discovery-service"></a>検出サービスへのアクセス方法

一般に、検出サービスの Web API アドレスのフォーマットは、 `<service base address>/api/discovery/` です。  **設定 > カスタマイズ > 開発者リソース** に移動することで、Common Data Service Web アプリケーションで展開されている Web アドレスとバージョン番号を簡単に検索できます  
  
### <a name="common-data-service-discovery-services"></a>Common Data Service 探索サービス  

グローバル検出サービスのサービス ベース アドレスは、 `https://globaldisco.crm.dynamics.com/` です。 この結果、`https://globaldisco.crm.dynamics.com/api/discovery/` のサービス アドレスになります。  
  
## <a name="using-the-discovery-service"></a>探索サービスの使用  

`Instances` という名前のエンティティ セットを使用して、インスタンス情報を取得します。 返されたデータをフィルター処理するようにセットされたインスタンス エンティティで`$select` と `$filter` を使用できます。 または `$metadata` を使用して、サービスのメタデータ ドキュメントを取得できます。  
  
### <a name="authentication"></a>認証

検出サービスのへのアクセスには、OAuth アクセス トークンを使用した認証が必要となります。

検出サービスが、OAuth 認証用に構成されている場合、アクセス トークンを使用せずにサービス に送信される要求は、「共通」するエンドポイントの権限とサービスのリソース ID と共にベアラー チャレンジをトリガーします。

### <a name="cors-support"></a>CORS サポート

検出サービスは、クロス オリジン アクセスの CORS標準規格に対応しています。 CORS サポートの詳細については、[OAuth を使用するクロス オリジン リソース共有を使用して単一ページのアプリケーションへ接続する](../oauth-cross-origin-resource-sharing-connect-single-page-application.md) を参照してください。  
  
### <a name="examples"></a>例  
  
-   特定のインスタンスの詳細を取得します。 GUID を省くと、認証されたユーザーがアクセスできるすべてのインスタンスが返されます。  
  
    ```http      
    GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(<guid>)
    ```  
  
-   代替キーとして UniqueName 属性を使用できます。  
  
    ```http  
    GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(UniqueName='myorg')  
    ```  
  
-   運用の種類によってフィルター処理された、利用可能なインスタンスのリストを取得します。  
  
    ```http  
    GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances?$select=DisplayName,Description&$filter=Type+eq+0   
    ```  
  
## <a name="see-also"></a>関連項目

[検出サービスのサンプル (C#)](samples/global-discovery-service-csharp.md)

