---
title: コードを使用して Common Data Service (PowerApps) で作業する | Microsoft Docs
description: 'Common Data Service データと対話するために使用できる 2 つのWebサービス: Web API と組織サービスを提供します。'
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
ms.openlocfilehash: 3da5976eba337c6b816f7414403876f3470b77ea
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154911"
---
# <a name="work-with-data-using-code-in-common-data-service"></a>Common Data Service でコードを使用して作業する

Common Data Service には、 ビジネスデータのモデル化と管理に使用される[エンティティ](entities.md)があります。 標準のエンティティを使用することも、データを格納するために、独自のユーザー定義エンティティを作成することもできます。 

## <a name="use-web-services-to-work-with-data"></a>Web サービスを使用したデータとの連携

Common Data Service は、データと対話するために使用できる 2 つのWebサービス: **Web API**と**組織サービス**を提供します。 要件とスキルが最高に一致したものを選択します。 

![Webサービスを選択するための流れ図](media/whentousewebapi.png)

### <a name="web-api"></a>Web API

Web API は OData v4 RESTful エンドポイントです。 これは、OAuth 2.0 を使用してHTTP要求および認証をサポートする任意のプログラミング言語用に使用します。

詳細: [Common Data Service Web API アクションの使用](webapi/overview.md) を参照してください。 

### <a name="organization-service"></a>組織のサービス

プラグインまたはワークフローの拡張機能の記述を含むプロジェクト用に .NET Framework SDK アセンブリを使用します。 

詳細: [ Common Data Service 組織サービスを使用する](org-service/overview.md)を参照してください。

> [!NOTE]
> Windows クライアント アプリケーションを作成している場合は、Xrm.Tooling アセンブリを使用します。 詳細情報: [XRM ツールを使用して Windows のクライアント アプリケーションを作成する](xrm-tooling/build-windows-client-applications-xrm-tools.md)
