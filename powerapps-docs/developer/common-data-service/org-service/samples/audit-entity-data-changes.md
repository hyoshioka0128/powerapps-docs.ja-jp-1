---
title: 'サンプル: エンティティ データの変更を監査する (Common Data Service) | Microsoft Docs'
description: このサンプルでは、エンティティ データの変更を監査する方法を紹介します
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
ms.openlocfilehash: 907ac09f9cd530c26c2e577351736d52f005a65a
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155927"
---
# <a name="sample-audit-entity-data-changes"></a>サンプル: エンティティのデータ変更を監査する

このサンプルでは、エンティティとその属性に対する監査を有効または無効にする方法、監査対象エンティティのデータ変更履歴を取得する方法、および監査レコードを削除する方法を説明します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/AuditEntityData) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RetrieveRecordChangeHistoryRequest` メッセージは、エンティティに関する監査履歴を検出する必要があるデータが含まれているシナリオで使用するためのものです。


## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. サンプルの取引先企業エンティティを作成します。

### <a name="demonstrate"></a>使用方法

1. システム ユーザー レコードからの組織の ID を取得します。
2. 組織での監査およびサンプルの取引先企業エンティティでの監査を有効化します。
3. `RetrieveRecordChangeHistoryRequest` では、取引先企業エンティティに対する監査履歴が取得され、結果が表示されます。

### <a name="clean-up"></a>クリーン アップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
