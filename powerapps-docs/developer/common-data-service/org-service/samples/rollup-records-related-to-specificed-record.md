---
title: " 指定したレコードに関連付けられているロールアップ レコード (Common Data Service) | Microsoft Docs"
description: このサンプルでは、指定されたレコードに関連付けられているレコードをロールアップをする方法を紹介します。
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
ms.openlocfilehash: 7756f3b180e57277a6350eca261898ecec264032
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155595"
---
# <a name="rollup-records-related-to-a-specific-record"></a>特定のレコードに関連付けられているロールアップ レコード

このサンプルでは、営業案件を取引先企業の親会社によってロールアップする方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/RollupSpecificRecords) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RollupRequest` メッセージは、ロールアップ要求を作成するために必要なデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. サンプルの取引先企業レコードと営業案件レコードを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `QueryExpression` は、取引先企業の親会社ごとに営業案件をクエリします。
2. `RollupRequest` は、ロールアップ要求を作成します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でレコードを削除するためのオプションを表示します。 サンプルで作成されたエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
