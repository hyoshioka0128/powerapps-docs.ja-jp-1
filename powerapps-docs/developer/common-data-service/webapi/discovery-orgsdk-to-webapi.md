---
title: コードを変更してグローバル検出サービスを使用する (Common Data Service) | Microsoft Docs
description: アプリケーションコードを更新して、最新の RESTful API を使用して検出 サービスを呼び出します。
ms.custom: ''
ms.date: 1/16/2020
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: bpevans
ms.author: bevans
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ca4a6ad8d86999a878ce51d8fffe08039230a12f
ms.sourcegitcommit: 6b2961308c41867756ecdd55f55eccbebf70f7f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2975899"
---
# <a name="modify-your-code-to-use-global-discovery-service"></a>コードを変更してグローバル検出サービスを使用する

検出サービス API はアプリケーションで使用して、アプリケーション ユーザーがアクセス権を持つビジネス組織のインスタンスを検出できます。 アプリケーションが現在 2011 SOAPエンドポイントで Organization Service API を使用して組織インスタンスを検出している場合、このトピックの手順に従って、OData V4 RESTful API とグローバル検出サービスの URL を使用して組織の詳細にアクセスするようにアプリケーションを変換できます。 アプリケーションが地域の検出サービスの URLを使用して検出サービスにアクセスする場合は、アプリケーション コードを地域のURLを使用したものからグローバルな検出サービスの URL に変更する必要があります。

RESTful API を使用した検出サービスに関する詳細な解説は、[組織のURLを見つける](/powerapps/developer/common-data-service/webapi/discover-url-organization-web-api) ページを参照してください。

> [!IMPORTANT]
> 検出サービスへのアクセスには、 *グローバル* 検出サービス エンドポイント (https://globaldisco.crm.dynamics.com) を使用することを強く推奨します。 *地域型* 検出サービス エンドポイントは、2020年3月2日で [廃止](/power-platform/important-changes-coming#regional-discovery-service-is-deprecated) となります。 グローバル 検出 サービスは、RESTful API を使用している場合にのみ利用可能となります。

RESTful API を使用して検出サービスを呼び出すにあたって必要な変更について以下で解説します。

## <a name="authentication"></a>認証
RESTful API を使用した検出サービスのへのアクセスには、OAuth 2.0 アクセス トークンを使用した認証が必要となります。
アプリケーションコードが認証に WS-Trust SAML トークンを使用する場合は、アプリケーション コードを変更して、Azure Active Directory (AD) から OAuth 2.0 トークンを取得する必要があります。続いてそのトークンを、検出サービス API 呼び出しの認証ヘッダーに追加します。 詳細については [Common Data Service で OAuth を使用する](../authenticate-oauth.md) を参照してください: 。

## <a name="odata-api-calls"></a>OData API 呼び出し
以下に示す HTTP リクエストの例は、検出サービス RESTful API で対応することができます。 これらの例では、インスタンス API を使用して、組織 サービス API の  <xref:Microsoft.Xrm.Sdk.Discovery.RetrieveOrganizationsRequest> および <xref:Microsoft.Xrm.Sdk.Discovery.RetrieveOrganizationRequest> メッセージ要求と同じ組織データを戻します。

-    すべての地域のユーザーのすべてのインスタンスを取得します。
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances
```  
-    特定の地域のユーザーのすべてのインスタンスを取得します。
```http  
GET  https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(Region={region})
```
応答
```javascript
{
  "value":[
    {
      "Id":"<GUID>",
      "UniqueName":"myorg",
      "UrlName":"orgurlname",
      "FriendlyName":"My Org",
      "State":0,
      "Version":"<Version>",
      "Url":"https://orgurlname.crm.dynamics.com",
      "ApiUrl":"https://orgurlname.api.crm.dynamics.com"
    }
  ]
}
```

-    ID で 単一のインスタンスを取得する
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(<guid>)
```  
-    一意の名称で単一のインスタンスを取得する
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v2.0/Instances(UniqueName='myorg')  
```  

応答
```javascript
{
  "Id":"<GUID>",
  "UniqueName":"myorg",
  "UrlName":"orgurlname",
  "FriendlyName":"My Org",
  "State":0,
  "Version":"<Version>",
  "Url":"https://orgurlname.crm.dynamics.com",
  "ApiUrl":"https://orgurlname.api.crm.dynamics.com"
}
```

## <a name="mapping-of-fields"></a>フィールドのマッピング
次の表は、2つの API を使用した検出サービスから返される応答のフィールド マッピングを示しています。 これらは、前述のすべての呼び出し例に対応しています。

応答フィールド（SOAP エンドポイント） |    応答フィールド（OData V4 RESTful エンドポイント）
------------------------------------|---------------------------------
エンドポイント [WebApplication] | Url
エンドポイント [OrganizationService]  | {ApiUrl}/XRMServices/2011/Organization.svc
エンドポイント [OrganizationDataService] |{ApiUrl}//XRMServices/2011/OrganizationData.svc
FriendlyName|FriendlyName
OrganizationId|ID
OrganizationVersion|[バージョン]
都道府県 | 都道府県<br/><ul><li>0 : 有効</li><li>1 : 無効</li><ul>
UniqueName|UniqueName
UrlName|UrlName

## <a name="deprecated-api-call"></a>廃止される API 呼び出し
組織サービスの API メッセージ [GetUserIdByExternalId] は、RESTful API では対応していません。

## <a name="see-also"></a>関連項目
[検出サービス](/powerapps/developer/common-data-service/discovery-service)

[ Common Data Service Web API を使用する](/powerapps/developer/common-data-service/webapi/discover-url-organization-web-api)
