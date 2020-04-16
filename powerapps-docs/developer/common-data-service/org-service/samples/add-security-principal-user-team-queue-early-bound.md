---
title: 'サンプル: セキュリティ プリンシパル (ユーザーまたはチーム) をキューに追加 (Common Data Service) | Microsoft Docs'
description: 'サンプル: キューへのセキュリティ プリンシパルの追加'
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
ms.openlocfilehash: a9d8b35cf3d856ed1f72f56f0640bb0dc0cb1779
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155975"
---
# <a name="sample-add-a-security-principal-user-or-team-to-a-queue"></a>サンプル: キューへのセキュリティ プリンシパル (ユーザーまたはチーム) の追加 

このサンプルは、ユーザーまたはチームにキューへのアクセス権を与える方法を紹介します。 [AddPrincipalToQueueRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.addprincipaltoqueuerequest?view=dynamics-general-ce-9) では、キュー メンバーの一覧に指定したプリンシパルが追加されます。 渡されたセキュリティ プリンシパルがチームの場合、キューにチームの各メンバーが追加されます。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AddSecurityPrincipalToQueue) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`AddPrincipalToQueueRequest` メッセージは、キュー メンバーの一覧に指定したプリンシパルが追加する必要があるデータが含まれているシナリオで使用するためのものです。 プリンシパルがチームの場合、キューに各チーム メンバーを追加します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `Queue` メソッドではキュー インスタンスが作成され、プロパティ値が設定されます。 返された GUID は変数で保存されます。
3. `QueryExpression` は、チームおよびロールの作成に対する既定の部署を取得します。
4. サンプルに必要な、新しいチームおよびロールの例を作成します。
5. `prvReadQueue` および `prvAppendToQueue` 特権を取得します。
6. `AddPrivilegeRoleRequest` メソッドでは、 `prvReadQueue` と `prvAppendToQueue` の権限が役割に追加されます。

### <a name="demonstrate"></a>実際にやってみます

`AddPrincipalToQueueRequest` メソッドでは、キューにチームが追加されます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
