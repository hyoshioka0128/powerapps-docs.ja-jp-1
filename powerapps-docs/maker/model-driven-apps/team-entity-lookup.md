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
ms.openlocfilehash: 3db46288b0f1fc384cae8c683648d1dd0a945d44
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2710864"
---
# <a name="add-the-team-entity-as-a-lookup-option-in-your-app"></a>チーム エンティティをアプリの検索オプションとして追加します

統合インターフェイス アプリを使用する場合、チーム エンティティを検索で使用できるようにするには、チーム エンティティをアプリに追加する必要があります。 たとえば、取引先担当者レコードはユーザーまたはチームに割り当てることができます。  

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

