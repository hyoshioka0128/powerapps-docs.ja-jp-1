---
title: ユーザー定義エンティティの削除 | Microsoft Docs
description: ユーザー定義エンティティを削除し PowerApps のすべてのデータを消去する方法に関する詳細な手順
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 8b4b9fb7942a7977bf6795ca21985b93c5469d26
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2754920"
---
# <a name="delete-a-custom-entity"></a>ユーザー定義エンティティの削除
ユーザー定義エンティティを削除できますが、標準のエンティティは削除できません。

1. [powerapps.com](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) で**データ**セクションを展開し、左側のナビゲーション ウィンドウで**エンティティ**をクリックまたはタップします。

    ![エンティティの詳細](./media/data-platform-cds-create-entity/entitylist.png "エンティティ リスト")

2. エンティティの一覧で、削除するエンティティをクリックまたはタップし、コマンド バーから**エンティティの削除**オプションをクリックまたはタップします。

3. 表示するダイアログ ボックスで、**削除**をクリックまたはタップしてエンティティを削除します。

>[!NOTE]
>エンティティを削除すると、エンティティ定義およびエンティティに含まれるすべてのデータの両方とも削除されます。 エンティティおよびエンティティ内のデータは削除後には復旧できません。

>[!NOTE]
>そのアプリで使用されるエンティティを削除すると、アプリやフローが破損する場合があります。

>[!NOTE]
>エンティティ A にエンティティ B への [検索フィールド](data-platform-entity-lookup.md) がある場合、エンティティ A を削除する前にエンティティ B を削除する必要があります。

