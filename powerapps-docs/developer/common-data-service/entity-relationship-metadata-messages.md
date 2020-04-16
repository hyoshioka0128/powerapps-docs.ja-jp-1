---
title: エンティティ関連付けメタデータ メッセージ (Common Data Service) | Microsoft Docs
description: この記事では、Web API と組織サービスを使用してエンティティの関連付けの作成、取得、更新、および削除に使用することができるメッセージについて説明します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: mayadumesh
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 88ced3454045917012c3736dcc6faad5dfcdf091
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3156211"
---
# <a name="entity-relationship-metadata-messages"></a>エンティティの関連付けのメタデータ メッセージ

エンティティの関連付けは、エンティティの相互関係を定義します。 これには、アプリケーションでどのように関係が表示されるかに関する情報が表示されます。 また、操作がレコードに対して実行された場合、その関連付けは、関連するレコードで実行する操作について示します。  
  
次の表は、エンティティの関連付けの作成、取得、更新、および削除に使用できるメッセージです。  
  
|Web API|組織のサービス|説明|  
|-------------|-------------|-----------------|  
|`RelationshipDefinitions` エンティティに対する `POST` 要求。 <br/>詳細については、[多対多の関連付けを作成する](webapi/create-update-entity-relationships-using-web-api.md#create-a-many-to-many-relationship) を参照してください。 |<xref:Microsoft.Xrm.Sdk.Messages.CreateManyToManyRequest>|2 つのエンティティ間に多対多の関連付けを作成します。|  
|`RelationshipDefinitions` エンティティに対する `POST` 要求。 <br/>詳細については、[一対多の関連付けを作成する](webapi/create-update-entity-relationships-using-web-api.md#create-a-one-to-many-relationship) を参照してください。|<xref:Microsoft.Xrm.Sdk.Messages.CreateOneToManyRequest>|2 つのエンティティ間に 1 対多の関連付けを作成します。|  
|`RelationshipDefinitions` エンティティに対する `DELETE` 要求。<br/>詳細については: [関連付けの削除](webapi/create-update-entity-relationships-using-web-api.md#delete-relationships) を参照してください。|<xref:Microsoft.Xrm.Sdk.Messages.DeleteRelationshipRequest>|エンティティの関連付けを削除します。|  
|`RelationshipDefinitions` エンティティに対する `GET` 要求。|<xref:Microsoft.Xrm.Sdk.Messages.RetrieveRelationshipRequest>|エンティティの関連付けを取得します。|  
|`RelationshipDefinitions` エンティティに対する `PUT` 要求。<br/>詳細については: [関連付けの更新](webapi/create-update-entity-relationships-using-web-api.md#update-relationships) を参照してください。|<xref:Microsoft.Xrm.Sdk.Messages.UpdateRelationshipRequest>|エンティティの関連付けを更新します。|  
  
### <a name="see-also"></a>関連項目  

 [エンティティの関連付けの有効性](entity-relationship-eligibility.md)   
 [エンティティ関係のカスケード動作の構成](configure-entity-relationship-cascading-behavior.md)