---
title: Power Apps のソリューションのベスト プラクティス | MicrosoftDocs
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
ms.openlocfilehash: 810fd536da5236f5ac7490505e82e78179ab61da
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2865296"
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
