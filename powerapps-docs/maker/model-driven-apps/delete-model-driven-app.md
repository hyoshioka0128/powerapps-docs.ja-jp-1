---
title: モデル駆動型アプリを削除する | MicrosoftDocs
description: Power Apps 環境からモデル駆動型アプリを削除する方法について説明します。
keywords: ''
ms.date: 02/14/2020
ms.service: powerapps
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 56510a744cfe010a3f52724e5b98a65a65e783e2
ms.sourcegitcommit: 97a36c9df2a7067a29fb6bd254975dadc2bc16fa
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "3072781"
---
# <a name="delete-a-model-driven-app"></a>モデル駆動型アプリを削除する
環境内で使われなくなったアプリを削除します。

> [!IMPORTANT]
> - モデル駆動型アプリが管理ソリューションの一部として既定のソリューションにインストールされていた場合は、 [管理ソリューションの一部としてインストールされたモデル駆動型アプリを削除する](#delete-a-model-driven-app-that-was-installed-as-part-of-a-managed-solution) を参照してください。
> - Dynamics 365 Sales 、Dynamics 365 Customer Service 、Dynamics 365 Field Service などの、Dynamics 365 モデル駆動型アプリです。 これらのアプリをユーザーに非表示とするには、アプリに割り当てられているセキュリティ ロールを削除します。 これらのアプリは、環境の作成者、システム管理者、およびシステム カスタマイザーのロールを持つユーザー、またはモデル駆動型アプリのエンティティーの作成権限を持つすべてのユーザーに表示されます。 

1. [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。
2. 左のナビゲーションで、 **アプリ** を選択します。 
3. 削除するアプリを選択し、コマンド バーで、**削除**を選択します。
4. 表示される確認メッセージで、**削除**を選びます。

   アプリが環境から削除されます。
  
コンポーネントに関連付けなどの依存関係がある場合は、アプリケーションを削除する前にこの依存関係を削除する必要があります。 アプリの依存関係を確認するには、アプリを選択し、コマンド バーで、 **依存関係を表示** を選択します。

> [!NOTE]
> アプリケーションを削除するとき、それに関連付けられているサイト マップを削除することをお勧めします。 関連付けられているサイト マップを削除しなかった場合、同じ名前で別のアプリを作成しようとしたときにサイト マップ デザイナーにエラーが表示されます。 ただし、エラーを無視することができます。アプリを再度作成するときに、エラーは表示されません。

## <a name="delete-a-model-driven-app-that-was-installed-as-part-of-a-managed-solution"></a>管理ソリューションの一部としてインストールされたモデル駆動型アプリを削除する
管理ソリューションの一部として環境にインストールされたモデル駆動型アプリを削除するには、管理ソリューションを削除します。 

### <a name="delete-a-managed-solution"></a>管理ソリューションの削除 
管理ソリューションのすべてのコンポーネントは、ソリューションを削除によって削除されます。
1.  [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。 
2.  左のナビゲーションで、 **ソリューション** を選択します。
3.  **ソリューション** 一覧で、削除する管理ソリューションを選択し、ツール バーで **削除** を選択します。 

