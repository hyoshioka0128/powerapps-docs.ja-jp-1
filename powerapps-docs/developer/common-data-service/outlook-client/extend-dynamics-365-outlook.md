---
title: Dynamics 365 for Outlook の拡張 (Common Data Service) | Microsoft Docs
description: Dynamics 365 for Outlook を使うと、ユーザーはオフラインでサーバーに接続していない状態でも、データと対話することができます。 Common Data Service は、カスタム コードから Web サービス オフラインを呼び出すことによってソリューションをオフラインのシナリオを拡張する機能を備えています。 また、SDK アセンブリで、同期、オフラインとオンラインの切り替え、 Dynamics 365 for Outlook クライアントの状態の検証など、Outlookの基本的なアクションに対するプログラム的なサポートが提供されています。 オフラインのプログラムでは、 ASP.NET Development Server を使用します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: sriharibs
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: b73543ce9220db75269e9452b4e839fcd6d2cb1c
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155403"
---
<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/extend-customer-engagement-outlook 

This topic should be in powerapps-docs/developer/common-data-service/outlook-client/
-->

# <a name="extend-dynamics-365-for-outlook"></a>Dynamics 365 for Outlook を拡張する

> [!IMPORTANT]
> 2018 年 1 月 29 日の時点で、お客様から多数のフィードバックをいただき、お客様を継続的にサポートすることは弊社の願うところであることから、 **Dynamics 365 for Outlook を廃止しないことを決定しました** (Outlook アドイン)。 詳細については、[このブログの投稿](https://blogs.msdn.microsoft.com/crm/2018/01/29/continued-support-for-outlook-add-in-dynamics-365-for-outlook/)をお読みください。

Microsoft Dynamics 365 for Outlook を使うと、ユーザーはオフラインでサーバーに接続していない状態でも、データと対話することができます。 Common Data Service は、カスタム コードから Web サービス オフラインを呼び出すことによってソリューションをオフラインのシナリオを拡張する機能を備えています。 また、 <xref:Microsoft.Crm.Outlook.Sdk> アセンブリで、同期、オフラインとオンラインの切り替え、 Dynamics 365 for Outlook の状態の検証など、Outlookの基本的なアクションに対するプログラム的なサポートが提供されています。 オフラインのプログラムでは、 ASP.NET Development Server を使用します。  
  
 Dynamics 365 では、管理者がユーザーのフィルターをカスタマイズして管理できるようにする機能を備えています。 フィルターのテンプレートは、Dynamics 365 for Outlook のエンティティの同期の開始点を提供します。 フィルターは、オフライン対応の Dynamics 365 ソリューションのために Outlook および SQL Server 2008 Express Edition に同期するエンティティ コレクションを決定します。  
  
## <a name="in-this-section"></a>このセクションの内容

[オフラインと Outlook のフィルターおよびテンプレート](offline-outlook-filters-templates.md)<br />  
[サンプル: Outlook フィルターの取得](sample-create-retrieve-outlook-filters.md)<br />  
[サンプル: Outlook メソッドの使用](sample-outlook-methods.md)<br />
  
## <a name="related-sections"></a>関連セクション

<!-- TODO:
[Extend Dynamics 365](extend-dynamics-365-server.md)<br />
[Supported Extensions for Dynamics 365](supported-extensions.md)<br />
[The Metadata and Data Models in Dynamics 365](metadata-data-models.md)<br />
[Extend Dynamics 365 on the server](extend-dynamics-365-server.md)<br />
[Extend Dynamics 365 on the client](extend-client.md)<br />
[Customize Dynamics 365 applications](customize-dev/customize-applications.md)<br />
[Package and distribute extensions using solutions](package-distribute-extensions-use-solutions.md)<br />
[Integrate Dynamics 365 with SharePoint](integration-dev/integrate-sharepoint.md)<br />
 -->
<xref href="Microsoft.Dynamics.CRM.savedquery?text=savedquery EntityType" /><br />
[SavedQuery エンティティ](../reference/entities/savedquery.md)<br />
  

