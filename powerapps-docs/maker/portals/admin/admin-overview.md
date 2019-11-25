---
title: PowerApps ポータル管理センターの概要 | MicrosoftDocs
description: PowerApps ポータル管理センターに関する情報。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/07/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 6f8434a6a395931fc4edfe02913f47536b4a709d
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2756173"
---
# <a name="powerapps-portals-admin-center"></a>PowerApps ポータル管理センター

PowerApps ポータル管理センターでポータルの高度な管理操作を実行できます。 管理センターはポータルが正常にプロビジョニングされると利用可能になります。

## <a name="open-powerapps-portals-admin-center"></a>PowerApps ポータル管理センターを開く

1. PowerApps ホーム ページの **最近のアプリ** セクションに移動してポータルを見つけます。

    > [!div class=mx-imgBorder]
    > ![最近のアプリ](../media/recent-apps.png "最近のアプリ")  

2. **その他のコマンド (...)** > **設定** を順に選択します。

    > [!div class=mx-imgBorder]
    > ![ポータル設定オプション](../media/portal-settings-option.png "ポータル設定オプション")

3. **ポータル設定** ウィンドウで **管理** を選択します。

    > [!div class=mx-imgBorder]
    > ![ポータル設定ウィンドウ](../media/portal-settings-admin.png "ポータル設定ウィンドウ")

## <a name="add-yourself-as-an-owner-of-the-azure-ad-application"></a>自分を Azure AD アプリケーションの所有者として追加する

グローバル管理者でなく、すでにプロビジョニングされたポータルを管理しようとした場合、またはプロビジョニングに失敗した場合にプロビジョニングを再実行する場合は、ポータルに接続された Azure Active Directory (Azure AD) アプリケーションの所有者である必要があります。

1. PowerApps ポータル管理センターに移動し、**ポータルの詳細**タブを開きます。

2. **アプリケーション ID** フィールドから値をコピーします。

    > [!div class=mx-imgBorder]
    > ![ポータルの詳細タブ](../media/portal-details-admin.png "ポータルの詳細タブ")

3. テナントに関連付けられる Azure AD に移動します。 [!include[](../../../includes/proc-more-information.md)] [アンマネージド ディレクトリを Azure Active Directory の管理者として引き継ぐ](https://docs.microsoft.com/azure/active-directory/active-directory-manage-o365-subscription)

4. Azure AD では、コピーしたアプリケーション ID を使用してアプリ登録を検索します。 **マイ アプリ**から**すべてのアプリ**への切り替えが必要になることがあります。

5. このアプリ登録の所有者としてユーザーまたはグループを追加します。 [!include[](../../../includes/proc-more-information.md)] [アプリケーションへのアクセスの管理](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)

    > [!Note]
    > このタスクは、組織のグローバル管理者またはこのアプリケーションの既存の所有者のいずれかによって実行できます。

6. 所有者として自分を追加すると、PowerApps ポータル管理センターのページが再オープンされます。