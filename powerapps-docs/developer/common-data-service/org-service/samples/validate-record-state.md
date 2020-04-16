---
title: " レコードの状態を検証して設定する (Common Data Service) | Microsoft Docs"
description: このサンプルでは、エンティティの状態を変更して検証する方法や、状態を設定する方法を示します。
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
ms.openlocfilehash: 7dc4321cba939a0882e753cdd7741d923b7b2ae4
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155503"
---
# <a name="validate-record-state-and-set-the-state-of-record"></a>レコードの状態を検証してレコードの状態を設定する

このサンプルは、エンティティの状態の変更を検証したり、エンティティの状態を設定したりする方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ValidateandExecuteSavedQuery) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

この `IsValidStateTransitionRequest` メッセージは、状態の切り替えについて検証する必要があるデータが含まれているシナリオで使用するように意図されています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
2. `CreateRequiredRecords` メソッドを活用すれば、このサンプルに必要なすべてのエンティティ レコードを作成できます。

### <a name="demonstrate"></a>実際にやってみます

1. `EntityReference`メソッドを活用すると、未解決のケースを表す EntityReference を作成できます。 
2. この `IsValidStateTransitionRequest`メソッドでは、切り替えリクエストを未解決のケースに設定します。
3. `checkState.NewState`プロパティでは、解決済みの新しい状態と解決された問題の新しい状態が有効かどうかをチェックします。
4. この要求は、`IsValidStateTransitionResponse` メソッドで実行されます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたサンプル データを削除するためのオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

