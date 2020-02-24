---
title: " つながりロールの更新 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、つながりロールの更新方法を説明します
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
ms.openlocfilehash: 7c35643dddf9c5b8760fdedc5f1d5e574f62b64a
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956328"
---
# <a name="update-a-connection-role-early-bound"></a>つながりロールの更新 (事前バインド)

このサンプルは、つながりロールのプロパティ (ロールの名前、説明、カテゴリなど) を変更する方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/UpdateConnectionRole) からダウンロードできます。

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

`Update` メッセージはつながりロールを更新します。

### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。