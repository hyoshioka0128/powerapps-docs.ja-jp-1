---
title: " ユーザー に ロール が 割り当てられているかどうかを確認する (Common Data Service) | Microsoft Docs"
description: このサンプルでは、ユーザーが特定のロールに関連付けられているかどうかを確認する方法を説明します。
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
ms.openlocfilehash: 77474ebc6f46800a3b1c28bea0a0dd1e1fb89c7e
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914473"
---
# <a name="determine-whether-a-user-has-a-role"></a>ユーザー に ロール があるかどうかを確認する

このサンプルは、Common Data Serviceのユーザーが特定のロールに関連付けられているかどうかを確認する方法を示します。 これは、[IOrganizationService.RetrieveMultiple](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.retrievemultiple?view=dynamics-general-ce-9) メソッドを使用して実行されます。  サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DetermineWhetherUserHasRole) からダウンロードできます。

このサンプルでは、システムに存在しない追加のユーザーが必要です。 **Office 365** で必要なユーザーを手動で作成し、サンプルがエラーなしで実行されるようにします。 このサンプルでは、次に示す**現状有姿**でユーザー プロファイルを作成します。 

**名**: Dan<br/>
**姓**: Park<br/>
**セキュリティ ロール**: セキュリティ ロールなし<br/>
**ユーザー名**: dpark@yourorg.onmicrosoft.com<br/>

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[IOrganizationService.RetrieveMultiple](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.retrievemultiple?view=dynamics-general-ce-9) メッセージは、レコードの集合を取得する際に使用することを意図しています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドは、上記のような セキュリティ ロール が割り当てられないユーザーを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `retrieve` メソッドは Common Data Service から ユーザー を取得します。
2. `query` メッセージを使用して、役割を見つけることができます。

### <a name="clean-up"></a>クリーンアップ

このサンプルでは、レコードは作成されません。 クリーンアップの必要はありません。
