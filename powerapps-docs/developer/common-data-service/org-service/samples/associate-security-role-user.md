---
title: " ユーザーにセキュリティ ロールを関連付ける（Common Data Service）| Microsoft Docs"
description: 'この例では、ユーザーにセキュリティ ロールを関連付ける方法を説明します '
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
ms.openlocfilehash: e01d2fd39caa6405a7340634c48f25f1c533843b
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155941"
---
# <a name="sample-associate-security-role-to-a-user"></a>サンプル: ユーザーにセキュリティ ロールを関連付ける

このサンプルでは、[IOrganizationService.Associate](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice?view=dynamics-general-ce-9) メッセージを使用してユーザーにセキュリティ ロールを関連付ける方法を説明します。 

このサンプルでは、システムに存在しない追加のユーザーが必要です。 **Office 365** で必要なユーザーを手動で作成し、サンプルがエラーなしで実行されるようにします。 このサンプルでは、次に示す**現状有姿**でユーザー プロファイルを作成します。 

**名**: Dan<br/>
**姓**: Park<br/>
**セキュリティ ロール**：ロールが割り当てられていないユーザー<br/>
**ユーザー名**: dpark@yourorg.onmicrosoft.com<br/>

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssociateSecurityRoleToUser) からダウンロードできます

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[IOrganizationService.Associate](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice?view=dynamics-general-ce-9) メッセージは、組織のメタデータとデータに対してプログラムがアクセスをするような用途で使用することを想定しています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドは、サンプルに必要なレコードを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `QueryExpression`メソッドは Common Data Service からロールを取得します。
2. `Associate` メッセージはロールをユーザーに割り当てます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
