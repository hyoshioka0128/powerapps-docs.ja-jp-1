---
title: 'サンプル: レポートを組織で使用可能または使用不可能にする (Common Data Service) | Microsoft Docs'
description: このサンプルでは、レポートを組織で使用可能または使用不可能にする方法を示します。
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
ms.openlocfilehash: 7c248c4393bd2872b3fba32977b47ebd32b15c17
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155727"
---
# <a name="make-a-report-available-or-unavailable-to-organization"></a>レポートを組織で使用可能または使用不可能にする

このサンプルでは、レポートを組織で使用可能または使用不可能にする方法を説明します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/MakeReportAvailableToOrganization) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

上述のシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドを活用すれば、このサンプルに必要なすべてのエンティティ レコードを作成できます。

### <a name="demonstrate"></a>実際にやってみます

1. `service.Retrieve` メソッドは、既存の個人用レポートを取得します。
2. `IsPersonal` パラメーターを False に設定します。
3. `service.Update` メソッドは、組織がレポートを使用できるようにします。
4. `IsPersonal` パラメーターを true に設定します。 これにより、組織がレポートを使用できなくなります。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
