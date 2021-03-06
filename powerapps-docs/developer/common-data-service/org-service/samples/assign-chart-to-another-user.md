---
title: " 他のユーザーへのグラフの割り当て (Common Data Service) | MicrosoftDocs"
description: 'この例では、あるユーザーが所有の視覚化を別のユーザーに割り当てる方法を説明します '
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
ms.openlocfilehash: 7274ff6800dc86c5e566f64dbd5fe1b72182327d
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155967"
---
# <a name="assign-a-chart-to-another-user"></a>他のユーザーにグラフを割り当てる

このサンプルでは、 [AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージを使用してあるユーザーが所有する視覚化を別のユーザーに割り当てる方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssignChartToAnotherUser) からダウンロードできます。

このサンプルでは、システムに存在しない追加のユーザーが必要です。 **Office 365** で必要なユーザーを手動で作成し、サンプルがエラーなしで実行されるようにします。 このサンプルでは、次に示す**現状有姿**でユーザー プロファイルを作成します。 

**名**: Kevin<br/>
**姓**: Cook<br/>
**セキュリティ ロール**: 営業課長<br/>
**ユーザー名**: kcook@yourorg.onmicrosoft.com<br/>

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージは、レコードの OwnerId 属性を変更して、指定されたレコードを新たな所有者（ユーザーまたはチーム）に割り当てる際に必要となるデータを含むシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` のメソッドは、サンプル版の取引先企業と営業案件レコードを作成して視覚化します。
3. `newUserOwnedVisualization` メソッドは、ビジュアル化 エンティティ インスタンス を作成します。

### <a name="demonstrate"></a>実際にやってみます

`AssignRequest` メソッドは、視覚化またはグラフを新規作成されたユーザーに割り当てます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。