---
title: 'サンプル: QueryExpression を使用した複数の取得 (Common Data Service) | Microsoft Docs'
description: このサンプルは、QueryExpression を使用して複数を取得する方法を示します
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: samples
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 73384e223a3b4ea23193ca2b8654b9cf3177a811
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155623"
---
# <a name="sample-retrieve-multiple-with-the-queryexpression-class"></a>サンプル: QueryExpression クラスを使用した複数取得

<!-- Re-title? This is really about retrieving  related records 
https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/sample-retrieve-multiple-queryexpression-class
-->
このサンプルでは、[IOrganizationService.RetrieveMultiple(QueryBase)](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.retrievemultiple?view=dynamics-general-ce-9#Microsoft_Xrm_Sdk_IOrganizationService_RetrieveMultiple_Microsoft_Xrm_Sdk_Query_QueryBase_) メソッドを [QueryExpression](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.query.queryexpression?view=dynamics-general-ce-9) とともに使用して、複数のエンティティを関連エンティティ列と共に取得する方法について示しています。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/RetrieveMultipleByQueryExpression) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]


## <a name="what-this-sample-does"></a>このサンプルの概要

`QueryExpression` クラスは、式の階層で表現された複雑なクエリを含むシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>使用方法

1. 取引先責任者を含む複数の取引先企業を作成します。
1. `QueryExpression` クラスは、リンク エンティティ エイリアスと返すリンク エンティティの列を指定するクエリ式を作成します。

### <a name="clean-up"></a>クリーン アップ

クリーンアップの必要はありません。
