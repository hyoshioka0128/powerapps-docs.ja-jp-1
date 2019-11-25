---
title: ColumnSet クラスの使用 (Common Data Service) | Microsoft Docs
description: <Description>
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
ms.openlocfilehash: 0fe094ecd43483d0fb6d91d5dcabd15b87472ee7
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749256"
---
# <a name="use-the-columnset-class"></a>ColumnSet クラスの使用

Common Data Serviceでは、<xref:Microsoft.Xrm.Sdk.Query.ColumnSet>クラスを使用して <xref:Microsoft.Xrm.Sdk.Query.QueryExpression>および <xref:Microsoft.Xrm.Sdk.Query.QueryByAttribute>クラスを使用して定義されたクエリから返す属性を指定できます。 さらに、<xref:Microsoft.Xrm.Sdk.IOrganizationService>.<xref:Microsoft.Xrm.Sdk.IOrganizationService.Retrieve*> のパラメーターです。 方法と、<xref:Microsoft.Xrm.Sdk.EntityCollection> のデータを返すいくつかのメッセージ要求クラスでプロパティとして使用されます。

> [!NOTE]
> <xref:Microsoft.Xrm.Sdk.Query.ColumnSet> クラスにはエンティティのすべての列が戻るように指定する <xref:Microsoft.Xrm.Sdk.Query.ColumnSet.AllColumns> プロパティがあります。 パフォーマンスのベスト プラクティスとして、運用コードにこれを使用しないでください。 詳細: [クエリ API を使用してエンティティのすべての列を取得することはできません](/dynamics365/customer-engagement/guidance/data/retrieve-specific-columns-entity-via-query-apis)

次のコード例は、`ColumnSet` クラスを使用して、クエリ式から返す属性を指定する方法を示しています。  
  
```csharp  
QueryExpression contactquery = new QueryExpression   
{  
   EntityName="contact",  
   ColumnSet = new ColumnSet("firstname", "lastname", "contactid")   
};  
```  
  
### <a name="see-also"></a>関連項目  

[QueryExpression クラスの使用](use-queryexpression-class.md)<br />
[QueryExpression でクエリを作成する](build-queries-with-queryexpression.md)<br />
[ConditionExpression クラスの使用](use-conditionexpression-class.md)<br /> 
<xref:Microsoft.Xrm.Sdk.Query.QueryExpression> クラス <br />
<xref:Microsoft.Xrm.Sdk.Query.QueryByAttribute> クラス <br />