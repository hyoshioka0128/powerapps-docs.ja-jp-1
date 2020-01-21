---
title: " ライセンス情報の取得 (Common Data Service) | Microsoft Docs"
description: 'このサンプルでは、ライセンス情報を取得する方法を示します '
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
ms.openlocfilehash: 1ed007c4536a359b0e3a6a4c072f02cebd7c3311
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934207"
---
# <a name="retrieve-license-information"></a>ライセンス情報の取得

このサンプルでは、 [IDeploymentService.RetrieveDeploymentLicenseTypeRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrievedeploymentlicensetyperequest?view=dynamics-general-ce-9) メッセージおよび [IOrganizationService.RetrieveLicenseInfoRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrievelicenseinforequest?view=dynamics-general-ce-9) メッセージを使用して、ライセンスに関する情報を取得する方法を示します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/RetrieveLicenseInformation) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

[IDeploymentService.RetrieveDeploymentLicenseTypeRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrievedeploymentlicensetyperequest?view=dynamics-general-ce-9) メッセージは、 Common Data Service 展開のライセンスのタイプを取得するために必要なデータが含まれているシナリオで使用することを目的としています。

[IOrganizationService.RetrieveLicenseInfoRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.retrievelicenseinforequest?view=dynamics-general-ce-9) メッセージは、 Common Data Service の展開で使用済みおよび使用可能なライセンスの数を取得するために必要なデータが含まれているシナリオで使用することを目的としています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `deploymentTypeRequest` メソッドでは、展開ライセンス タイプを取得する要求を作成します。
2. `licenseInfoRequest` メッセージでは、ライセンス情報要求を取得する要求を作成します。

### <a name="clean-up"></a>クリーンアップ

このサンプルでは、レコードは作成されません。 クリーンアップの必要はありません。