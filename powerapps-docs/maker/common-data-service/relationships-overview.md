---
title: Power Apps のエンティティ概要 | MicrosoftDocs
description: Power Apps ポータルを使用してエンティティを作成および編集する方法について
ms.custom: ''
ms.date: 07/25/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ''
caps.latest.revision: 0
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 199c7705bd283cbc316b6a2b8056eba7f7507ea1
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2865428"
---
# <a name="entity-relationships-overview"></a>エンティティの関連付けの概要

エンティティ関係によって、エンティティ レコードを他のエンティティや同じエンティティからのレコードと関連付けることのできる方法が定義されます。 2 種類のエンティティ関係が用意されています。
- **一対多関連付け**。 一対多エンティティ関係では、多くの参照元 (関連) エンティティ レコードを単一の参照先 (主) エンティティ レコードと関連付けることができます。 参照先エンティティ レコードは "親" と呼ばれ、参照元エンティティのレコードは "子" と呼ばれることがあります。  多対 1 の関連付けは、1 対多の関連付けの下位観点です。
- **多対多関連付け**。 多対多エンティティ関係では、多数のエンティティ レコードを他の多数のエンティティ レコードと関連付けることができます。 多対多の関連付けを使用して関連付けられたレコードは同等であると考えられ、この関係は相互的なものです。 

## <a name="see-also"></a>関連項目
[エンティティ間の関連付けを作成](data-platform-entity-lookup.md) <br/>
[ Power Apps ポータルを使用して Common Data Service で多対多の関係を作成する](create-edit-nn-relationships-portal.md)
