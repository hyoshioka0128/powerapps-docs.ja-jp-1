---
title: チーム エンティティをアプリの検索オプションとして追加する | MicrosoftDocs
description: チーム エンティティをアプリの検索オプションとして追加する方法を説明します
ms.custom: ''
ms.date: 07/24/2019
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
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 81b20a326be239445422cce51a54b2e0b991d5c4
ms.sourcegitcommit: a7f2313a048d3b8a03516a2e4c349f3fb08f4a22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "2805698"
---
# <a name="add-an-entity-as-a-lookup-option-in-your-app"></a>エンティティをアプリの検索オプションとして追加する

統一インターフェイス アプリを使用する場合、エンティティを検索で使用できるようにするには、エンティティをアプリに追加する必要があります。 たとえば、取引先担当者レコードはユーザーまたはチームに割り当てることができます。  

> [!div class="mx-imgBorder"] 
> ![](media/entity-lookup-teams.png "Entity lookup with both users and teams available")

ただし、ユーザー エンティティがアプリケーションに含まれていて、チーム エンティティが含まれていない場合は、ユーザーレコードのみが検索で表示されます。 

> [!div class="mx-imgBorder"] 
> ![](media/entity-lookup-user-only.png "Entity lookup with users only")

## <a name="add-the-team-entity-to-an-app"></a>チームエンティティをアプリに追加する

1. アプリデザイナーでアプリを開きます。 
2. **コンポーネント** タブを選択し、 **エンティティ** 、 **チーム** と選択します。    

    > [!div class="mx-imgBorder"] 
    > ![](media/add-team-entity-app.png "Add the team entity to the app")

3. **保存** を選択し、 **公開** を選択することで、アプリのユーザーが変更内容を使用できるようになります。   

