---
title: " エンティティのインスタンスのシリアル化と逆シリアル化 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、エンティティ インスタンスのシリアル化と逆シリアル化の方法を示します。
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
ms.openlocfilehash: b1189d6a17433d9656ba760c5bf2dd079bde34b8
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155581"
---
# <a name="serialize-and-deserialize-an-entity-instance"></a>エンティティ インスタンスのシリアル化および逆シリアル化 

このサンプルは XML 形式に事前バインド型および遅延バインド型エンティティ インスタンスをシリアル化する方法、および XML 形式から事前バインド型エンティティ インスタンスに非シリアル化する方法を説明します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/SerializeDeserializeEntity) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`DataContractSerializer` メッセージは、与えられたデータ契約を使用して、あるタイプのインスタンスを XML ストリームまたはドキュメントにシリアライズ化および逆シリアライズ化するシナリオで使用することを目的としています。 このクラスは継承できません。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `CreateRequiredRecords` メソッドは、サンプルに必要なサンプル データを作成します。

### <a name="demonstrate"></a>実際にやってみます

1. `DataContractSerializer` メソッドは、取引先担当者レコードを XML にシリアル化し、ハードドライブに書き込みます。 
1. `earlyBoundSerializer` メソッドは、エンティティ インスタンスを逆シリアル化します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
