---
title: セキュリティ モデル (Common Data Service) | Microsoft Docs
description: Common Data service には、データの整合性とプライバシーを保護し、効率的なデータ アクセスと共同作業をサポートするセキュリティ モデルが用意されています。
ms.custom: ''
ms.date: 10/19/2019
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: paulliew
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: f8c23b96fdc79920ddb79fdc495aaebec00a0bc6
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155295"
---
# <a name="security-model"></a>セキュリティ モデル

Common Data Service には、データの整合性とプライバシーを保護し、効率的なデータ アクセスと共同作業をサポートするセキュリティ モデルが用意されています。 このモデルの目的は次のとおりです。
- ユーザーが各自の業務の実行に必要となる相応のレベルの情報にのみアクセスできるようにします。
- ユーザーをロールによって分類し、ロールに基づいてアクセスを制限します。
- ユーザーおよびチームが所有していないレコードに指定された共同作業の目的としてアクセスできるように、データの共有をサポートします。
- ユーザーが所有または共有していないレコードへのアクセスを禁止します。

**ロールベースのセキュリティ**では、ユーザーの職務 (または実行可能な仕事) を指定する一連の特権のグループ化に重点を置いています。 Common Data Service には定義済みの一連のセキュリティ ロールが含まれています。 各セキュリティ ロールでは、ユーザーのセキュリティ管理が容易になるようにユーザー権限のセットを集約します。 また、さまざまなユーザーのニーズに合わせて、アプリケーションの展開ごとに独自のロールを定義することもできます。 セキュリティ ロールは[部署](businessunit-entity.md)と関連付けられます。

**レコードベースのセキュリティ**では、特定のレコードに対するアクセス権に重点を置いています。

**フィールドレベルのセキュリティ**では、エンティティ内のビジネスに大きな影響を与える特定のフィールドへのアクセスを、指定されたユーザーまたはチームのみに制限します。
ロールベースのセキュリティ、レコードベースのセキュリティ、およびフィールドレベルのセキュリティを組み合わせて、カスタム Power Apps アプリのユーザーの全体的なセキュリティ権限を定義します。

開発者は、ユーザーのコンテキストでクエリが実行され、ユーザーが読み取る権限のあるレコードのみ返されることを知っておく必要があります。
さらに、コードでは、セキュリティ ロールまたはチーム メンバーシップを通じてユーザー アカウントに割り当てられている特権に基づいてのみ操作を実行できます。

詳細情報については、 [Common Data Service セキュリティ](/power-platform/admin/wp-security) を参照してください。

