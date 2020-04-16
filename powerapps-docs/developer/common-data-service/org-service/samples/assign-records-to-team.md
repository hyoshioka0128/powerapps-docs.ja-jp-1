---
title: " チームにレコードを割り当てる (Common Data Service) | Microsoft Docs"
description: このサンプルではチームにレコードを割り当てる方法を示します。
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
ms.openlocfilehash: 1dbf2a9c068c9085e1d3dc2e88db23f33ef58f38
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155955"
---
# <a name="assign-a-record-to-a-team"></a>チームへのレコードの割り当て

このサンプルは、 [AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージを使用してチームにレコードを割り当てる方法を示します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssignRecordToTeam) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージは、レコードの OwnerId 属性を変更して、指定されたレコードを新たな所有者（ユーザーまたはチーム）に割り当てる際に必要となるデータを含むシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 自社組織の現在のバージョンを確認してください。 
1. このサンプルに求められる必須データを作成します。

### <a name="demonstrate"></a>実際にやってみます

`AssignRequest` メッセージは、サンプル用に作成された取引先企業のレコードをチームに割り当てます。 

### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。