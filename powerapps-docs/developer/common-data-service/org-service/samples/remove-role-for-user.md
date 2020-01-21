---
title: " ユーザーのロールの削除 (Common Data Service) | Microsoft Docs"
description: 'このサンプルは、ユーザーのロールを削除する方法を示します '
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
ms.openlocfilehash: afc53ef3cf6a06d44cf9c5c3e52157ee85f96aae
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914461"
---
# <a name="remove-a-role-for-a-user"></a>ユーザーのロールを削除する

このサンプルは、 [IOrganizationService.Disassociate](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.disassociate?view=dynamics-general-ce-9) メソッドを使用して、ユーザーとロールの関連付けを解除する方法を示しています。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/RemoveRoleFromUser) からダウンロードできます。

このサンプルでは、システムに存在しない追加のユーザーが必要です。 **Office 365** で必要なユーザーを手動で作成し、サンプルがエラーなしで実行されるようにします。 このサンプルでは、次に示す**現状有姿**でユーザー プロファイルを作成します。 

**名**: Dan<br/>
**姓**: Park<br/>
**セキュリティ ロール**: セキュリティ ロールなし<br/>
**ユーザー名**: dpark@yourorg.onmicrosoft.com<br/>

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[IOrganizationService.Disassociate](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.disassociate?view=dynamics-general-ce-9) メッセージは、レコード間のリンクを削除するシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドは、サンプルに必要なレコードを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `query`メソッドは Common Data Service からロールを取得します。
2. `Disassociate` メッセージでは、チームにロールを割り当てます。

### <a name="clean-up"></a>クリーンアップ

このサンプルでは、レコードは作成されません。 クリーンアップの必要はありません。
