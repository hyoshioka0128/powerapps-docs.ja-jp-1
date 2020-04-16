---
title: 組織サービスを使用したメタデータに関する作業 (Common Data Service) | Microsoft Docs
description: 組織サービスを使用し、プログラムでメタデータ モデルにアクセスしたり、メタデータ モデルを変更したりする方法について説明します
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
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
ms.openlocfilehash: c63626828296ecd9e3a618390ede0f126e8d24fc
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155415"
---
# <a name="work-with-metadata-using-the-organization-service"></a>組織サービスを使用したメタデータに関する作業

メタデータとは、Common Data Service 内のデータの管理に使用するエンティティの構造のことです。 <xref:Microsoft.Xrm.Sdk.Metadata.MetadataBase> はメタデータ情報を含むクラスの基本クラスです。 このセクションでは、組織サービスを使用し、プログラムでメタデータ モデルにアクセスしたり、メタデータ モデルを変更したりする方法について説明します。

> [!IMPORTANT]
> エンティティ、代替キー、属性、または関連付けを追加、削除、または変更すると、正常なシステム操作に影響を与える可能性があります。 運用システムに変更を加える場合は、ユーザーへの影響が最小限に留まるように変更の操作をスケジューリングすることを推奨します。

## <a name="see-also"></a>関連項目

[Web API をメタデータで使用する](../webapi/use-web-api-metadata.md)

[コードを使用してメタデータを扱う](../metadata-services.md)