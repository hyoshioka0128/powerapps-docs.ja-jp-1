---
title: " 他のユーザーへのダッシュボードの割り当て (Common Data Service) | MicrosoftDocs"
description: 'この例では、あるユーザーが所有するダッシュボードを別のユーザーに割り当てる方法を説明します '
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
ms.openlocfilehash: bbfd3f468bc59c4cbd455bda93ed8e0deae07729
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934431"
---
# <a name="assign-a-user-owned-dashboard-to-another-user"></a>ユーザー所有のダッシュボードを別のユーザーへ割り当てる

このサンプルでは、 [AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージを使用してあるユーザーが所有する視覚化を別のユーザーに割り当てる方法を示します。 別のユーザーに割り当てられているユーザー所有のダッシュボードは削除できないため、このサンプルでは偽装を使用しユーザー所有のダッシュボードを削除する方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssignUserOwnedDashboardToAnother) からダウンロードできます。

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
2. `CreateRequiredRecords` メソッドは、このサンプルで必要となるエンティティ レコードを作成します。
3. `mySavedQuery` メソッドは、営業案件の既定のパブリックビューを取得します。
4. `visualizationQuery` メソッドは、システムからビジュアル化を取得します。 このサンプルでは、 **上位の営業案件** の例を示しています。 
5. `_otherUSerId` メソッドは、ダッシュボードが割り当てられるユーザーを作成します。

### <a name="demonstrate"></a>実際にやってみます

`AssignRequest` メソッドは、視覚化またはグラフを新規作成されたユーザーに割り当てます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。