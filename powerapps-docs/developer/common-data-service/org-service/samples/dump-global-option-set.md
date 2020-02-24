---
title: " グローバル オプション セット情報をファイルにダンプする (Common Data Service) | Microsoft Docs"
description: この例では、グローバル オプション セット情報をファイルにダンプする方法を解説します。
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
ms.openlocfilehash: 17940374791955a43cc27a030bc14c9d9abc2e73
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956340"
---
# <a name="dump-global-option-information-to-a-file"></a>グローバル オプション セット情報をファイルにダンプする

このサンプルは、すべてのグローバル オプションセット メタデータを `XML` ファイルへと書き出す方法を説明します。 これには、 [RetrieveAllOptionSetsRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.retrievealloptionsetsrequest?view=dynamics-general-ce-9) メッセージを使用します。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DumpGlobalOptionSetInfo) からダウンロードできます。

次のサンプルでは、`\DumpGlobalOptionSetInfo\bin\Debug\AllOptionSetValues.xml` に新しいファイルを作成します。 このファイルを **Office Excel** で開き、表形式のレポートを確認することができます。 

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`RetrieveAllOptionSetsRequest` メッセージは、すべてのグローバル オプションセット メタデータに関するメタデータ情報を検出する必要があるデータを含む場合に使用することを想定しています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>使用方法

1. `RetrieveAllOptionSetsRequest` メソッドは、メタデータを取得します。 
1. `StreamWriter` では、StreamWriter のインスタンスを作成し、テキストをファイルへ書き込みます。

### <a name="clean-up"></a>クリーン アップ

このサンプルでは、レコードは作成されません。 クリーンアップの必要はありません。