---
title: " エンティティの関連付けをファイル に ダンプする (Common Data Service) | Microsoft Docs"
description: このサンプルでは、エンティティの関連付けをファイルにダンプする方法を説明します。
ms.custom: ''
ms.date: 12/20/2019
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
ms.openlocfilehash: 1dec5680fc1bd42d2443c94bd1afe740ffb2aaf0
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155791"
---
# <a name="dump-entity-relationships-information-to-a-file"></a>エンティティ関連情報のファイルへのダンプ

このサンプルでは、 `XML` ファイルにすべての属性メタデータを書き出す方法を説明しています。 [RetrieveAllEntitiesRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrieveallentitiesrequest?view=dynamics-general-ce-9) メッセージを使用します。 サンプルは [こちら](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DumpEntityRelationShips) からダウンロードすることができます。

次のサンプルでは、`\DumpEntityRelationShips\bin\Debug\RelationshipInfo.xml` に新しいファイルを作成します。 このファイルを **Office Excel** で開き、表形式のレポートを確認することができます。 

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RetrieveAllEntitiesRequest` メッセージは、すべてのエンティティに関するメタデータ情報を取得するにあたって必要となるデータを含むシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>使用方法

1. `RetrieveAllEntitiesRequest` メソッドは、メタデータを取得します。 
1. `StreamWriter` では、StreamWriter のインスタンスを作成し、テキストをファイルへ書き込みます。

### <a name="clean-up"></a>クリーン アップ

このサンプルでは、レコードは作成されません。 クリーンアップの必要はありません。
