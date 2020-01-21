---
title: " 2つのレコードをマージ (Common Data Service) | Microsoft Docs"
description: このサンプルでは、2 つのレコードをマージする方法を示します。
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
ms.openlocfilehash: 640f0fe624b6652d7d590b24eef747b89d69f850
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934568"
---
#  <a name="merge-two-record"></a>2 つのレコードの統合

このサンプルでは、2 つのレコードをマージする方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/MergeTwoRecords) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`MergeRequest` メッセージは、同じ種類の 2 つのエンティティ レコードからの情報をマージするために必要なデータが含まれるシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドを活用すれば、このサンプルに必要なすべてのエンティティ レコードを作成できます。

### <a name="demonstrate"></a>実際にやってみます

1. `MergeRequest` メソッドは要求を作成します。 
2. `Account` メッセージは、エンティティにマージする新しいデータを保持するための別のアカウントを作成します。


### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

