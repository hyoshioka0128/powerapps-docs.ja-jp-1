---
title: " エンティティの権限をファイル に ダンプする (Common Data Service) | Microsoft Docs"
description: このサンプルでは、エンティティの権限をファイルにダンプする方法を説明します。
ms.custom: ''
ms.date: 12/20/2019
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
ms.openlocfilehash: 645977524a8d90bf4c241aba672a311da044419b
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934327"
---
# <a name="dump-entity-privileges-information-to-a-file"></a>エンティティの権限情報をファイルにダンプする

このサンプルでは、 `XML` ファイルにすべての属性メタデータを書き出す方法を説明しています。 [RetrieveAllEntitiesRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrieveallentitiesrequest?view=dynamics-general-ce-9) メッセージを使用します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DumpEntityPriviliges) からダウンロードできます。

次のサンプルでは、`\DumpEntityPriviliges\bin\Debug\EntityPrivileges.xml` に新しいファイルを作成します。 このファイルを **Office Excel** で開き、表形式のレポートを確認することができます。 

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