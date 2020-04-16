---
title: " セキュリティ ロール を チーム に関連付ける（Common Data Service）| Microsoft Docs"
description: 'このサンプルではチームにセキュリティ ロールを割り当てる方法を示します '
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
ms.openlocfilehash: 6ea2984f5fd8ad276581307edf3ff76ca1abeef8
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155951"
---
# <a name="sample-associate-security-role-to-a-team"></a>サンプル: チーム に セキュリティ ロール を関連付ける 

このサンプルでは、 [AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージを使用してチームに セキュリティ ロールを割り当てる方法を示します。 この例では、チームまたはユーザーに割り当てることができるのはその部署のロールのみであることを考慮していません。 割り当てを行う ロール は、 RetrieveMultiple メソッド によって返された コレクション の最初の ロールです。 そのレコードが要求チームの部署以外のものである場合、割り当ては失敗します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssociateSecurityRoleToTeam) からダウンロードできます

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) メッセージは、レコードの OwnerId 属性を変更して、指定されたレコードを新たな所有者（ユーザーまたはチーム）に割り当てる際に必要となるデータを含むシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドは、サンプルに必要なレコードを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `query`メソッドは Common Data Service からロールを取得します。
2. `Associate` メッセージはチームに役割を割り当てします。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
