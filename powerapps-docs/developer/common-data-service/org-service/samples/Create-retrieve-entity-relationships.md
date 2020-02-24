---
title: 'サンプル: エンティティの関連付けを作成、取得する (Common Data Service) | Microsoft Docs'
description: この例では、エンティティの関連付けの作成と取得の方法について説明します。
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
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
ms.openlocfilehash: 9542b7b9b76530cdfc40318fbd237657d7dc6134
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956330"
---
# <a name="create-and-retrieve-entity-relationships"></a>エンティティ関係の作成および取得

この例では、エンティティの関連付けの作成と取得の方法について説明します。 関連付けの作成や取得をするには、次のメソッドを使用します:

- [CreateOneToManyRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.createonetomanyrequest?view=dynamics-general-ce-9)
- [CreateManyToManyRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.createmanytomanyrequest?view=dynamics-general-ce-9)
- [CanBeReferencedRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.canbereferencedrequest?view=dynamics-general-ce-9)
- [CanBeReferencingRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.canbereferencingrequest?view=dynamics-general-ce-9)
- [CanManyToManyRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.canmanytomanyrequest?view=dynamics-general-ce-9)
- [RetrieveRelationshipRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrieverelationshiprequest?view=dynamics-general-ce-9)

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CreateRetrieveEntityRelationships) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`CreateOneToManyRequest`、 `CreateManyToManyRequest`、 `CanManyToManyRequest`、 `CreateOneToManyRequest`、 `CanBeReferencedRequest`、 `CanBeReferencingRequest`、 `RetrieveRelationshipRequest` のメッセージは、エンティティの関連付けを作成、取得が必要となるデータを使用する場合に表示されます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `CreateOneToManyRequest` のメソッドは、新しい 1対多（1：N）の の関連付けを作成します。 
2. `CreateManyToManyRequest` のメソッドは、新しい 多対多（N：N）の の関連付けを作成します。
3. `EligibleCreateManyToManyRelationship` のメソッドは、エンティティがN：N の の関連付けに参加できるかどうかを検証します。
4. `RetrieveRelationshipRequest` のメソッドは、前述の手順で作成された 2 つのエンティティの関連付けを取得します。


### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
