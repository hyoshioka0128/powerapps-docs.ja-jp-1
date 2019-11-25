---
title: PowerApps のソリューションのベスト プラクティス | MicrosoftDocs
description: ソリューションを使用するときのベスト プラクティスについて説明します。
ms.custom: ''
ms.date: 10/08/2019
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
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: e10b9951ca70e497349620ae96308d6db49403fe
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2702152"
---
# <a name="best-practices-when-working-with-solutions"></a>ソリューションを使用する場合のベスト プラクティス 
このトピックでは、ソリューションを使用するときのベスト プラクティスについて説明します。 


## <a name="use-a-single-managed-solution-to-manage-a-model-driven-app"></a>モデル駆動型のアプリを管理する、単一のアンマネージド ソリューションを使用します。 
マネージド ソリューションに含まれるアプリを更新するには、更新または修正プログラム内のソリューションを使用します。 同じモデル駆動型のアプリケーションがインストールされている環境にさまざまなマネージド ソリューションをインストールしないでください。 詳細: [ソリューションの更新](import-update-export-solutions.md#update-solutions) および [セグメント化されたソリューションおよびパッチを使用して選択したエンティティ資産をエクスポート](use-segmented-solutions-patches-simplify-updates.md) 


## <a name="use-security-roles-to-manage-app-access"></a>セキュリティ ロールを使用してアプリのアクセスを管理する
モデル駆動型のアプリケーションには、ユーザーのアクセスを制御するために割り当てられているセキュリティ ロールが存在するべきです。 詳細: [アプリのセキュリティ ロールの追加](../model-driven-apps/share-model-driven-app.md#add-security-roles-to-the-app) 

## <a name="delete-the-managed-solution-to-delete-a-model-driven-app"></a>管理ソリューションを削除してモデル駆動型アプリを削除します。 
管理ソリューションの一部として既定のソリューションにインストールされたモデル駆動型アプリを削除するには、管理ソリューションを削除します。 

マネージド ソリューションの一部としてインストールされた既定の環境からアプリまたはアプリのサイトマップを直接削除しないでください。 これを行うと、アプリのインストールに使用したソリューションのアップグレードまたは更新の失敗につながる可能性があります。 直接モデル駆動型のアプリケーションを削除する例としては、ソリューション エクスプローラーで既定のソリューションを開き、**モデル駆動型アプリ**にアクセスし、アプリを選択してから**削除**を選択します。

### <a name="see-also"></a>関連項目
[ソリューションの概要](solutions-overview.md)
