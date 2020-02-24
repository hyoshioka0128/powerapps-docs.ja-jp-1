---
title: 'サンプル: 属性に関する作業 (Common Data Service) | Microsoft Docs'
description: このサンプルは、属性に関する作業方法を説明します
ms.custom: ''
ms.date: 10/31/2018
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
ms.openlocfilehash: 245e7091a0e7ccc9eee9b463be5d81f2a5df31d9
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956333"
---
# <a name="work-with-attribute-metadata"></a>属性メタデータに関する作業

このサンプルは属性に関するさまざまなアクションの実行方法を示します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/WorkWithAttributes) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルでは、Common Data Service でさまざまなタイプの属性を作成する方法を示します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `BooleanAttributeMetadata` メソッドは、ブール型の属性を作成します。
2. `DateTimeAttributeMetadata` メッセージは、日時型の属性を作成します。
3. `DecimalAttributeMetadata` メッセージは、小数型の属性を作成します。
4. `IntegerAttributeMetadata` メッセージは、整数型の属性を作成します。
5. `MemoAttributeMetadata` メッセージは、メモ型の属性を作成します。
6. `MoneyAttributeMetadata` メッセージは、金額型の属性を作成します。
7. `PicklistAttributeMetadata` メッセージは、選択型の属性を作成します。

### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。