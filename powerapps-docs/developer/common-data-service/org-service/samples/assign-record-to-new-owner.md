---
title: " 新たな所有者にレコードを割り当てる (Common Data Service) | MicrosoftDocs"
description: このサンプルでは、レコードを新しい所有者に割り当てる方法を紹介します。
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
ms.openlocfilehash: e33db08a3a6aa5118a5ac9d8d0871457e2cfc4d5
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155959"
---
# <a name="assign-a-record-to-a-new-owner"></a>新たな所有者へのレコードの割り当て

このサンプルでは、[IOrganizationService.Update](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.update?view=dynamics-general-ce-9) メッセージを使用して取引先企業を別のユーザーに割り当てる方法を示しています。

[AssignRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.assignrequest?view=dynamics-general-ce-9) では、特殊なメッセージを削除する必要があるため、この例では `IOrganization.Update` メソッドを使用しています。 詳細については: [更新プログラムを使用して特殊な操作を実行する](https://docs.microsoft.com/powerapps/developer/common-data-service/special-update-operation-behavior) を参照してください

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AssignRecordToNewOwner) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[IOrganizationService.Update](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.iorganizationservice.update?view=dynamics-general-ce-9) メッセージは、既存のレコードの更新を行う必要があるデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。 
1. このサンプルに求められる必須データを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `Retrieve` メソッドでは、setup(#setup) で作成された取引先企業のレコードを取得します。
1. `Update` メッセージは、レコードを所有するユーザーの `ownerid` 属性を更新します。 

### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。