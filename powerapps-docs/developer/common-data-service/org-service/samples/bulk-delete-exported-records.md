---
title: 'サンプル: エクスポートしたレコードを一括で削除する (Common Data Service) | Microsoft Docs'
description: このサンプルは、レコードの一括削除を実行する方法を示します
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: ''
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 8b690bb3a7a27c278c9354073f5e4140dfe33b4d
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934411"
---
# <a name="sample-bulk-delete-exported-records"></a>サンプル: エクスポート済みレコードの一括削除

このサンプルは、**Excel にエクスポート** オプションを使用して Common Data Service から以前エクスポートしたレコードを一括で削除する方法を示します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/BulkDeleteExported) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`BulkDeleteRequest` メッセージは、一括削除要求を作成する必要があるデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. 一括削除要求の操作が完了した後に、電子メールを送信するシステム ユーザーのクエリ。
3. `BulkDeleteRequest` では一括削除プロセスを作成し、要求プロパティを設定します。
4. `CheckSuccess` メソッドでは、それが完了したか、または指定された時間がなくなるまで `BulkDeleteOperation` に対してクエリします。 次に操作が完了したかどうかを確認します。

### <a name="demonstrate"></a>使用方法

`PerformBulkDeleteBackup` メソッドでは、非アクティブな営業案件や活動でメインの一括削除操作が実行され、システムから削除されます。

### <a name="clean-up"></a>クリーン アップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
