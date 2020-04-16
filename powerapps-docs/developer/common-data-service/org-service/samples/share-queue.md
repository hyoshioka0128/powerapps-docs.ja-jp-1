---
title: " キューを共有する (Common Data Service) | Microsoft Docs"
description: このサンプルでは、キューを共有する方法を示します。
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
ms.openlocfilehash: d2f569de501b89be1a535244864dac8ff6a7578d
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155571"
---
# <a name="share-a-queue"></a>キューの共有

このサンプルは、ユーザーまたはチームにキューへのアクセス権を与える方法を示します。 [AddPrincipalToQueueRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.addprincipaltoqueuerequest?view=dynamics-general-ce-9) では、キュー メンバーの一覧に指定したプリンシパルが追加されます。 渡されたセキュリティ プリンシパルがチームの場合、キューにチームの各メンバーが追加されます。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ShareQueue) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

このサンプルの実行方法については、[このサンプルの実行方法](https://github.com/microsoft/PowerApps-Samples/blob/master/cds/README.md)をご覧ください。

## <a name="what-this-sample-does"></a>このサンプルの概要

[AddPrincipalToQueueRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.addprincipaltoqueuerequest?view=dynamics-general-ce-9) メッセージは、キュー メンバーの一覧に指定したプリンシパルが追加するデータが含まれているシナリオで使用するためのものです。 プリンシパルがチームの場合、キューに各チーム メンバーを追加します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。 
1. このサンプルに求められる必須データを作成します。

### <a name="demonstrate"></a>実際にやってみます

`AddPrincipalToQueueRequest` メッセージはチームとキューを共有します。

### <a name="clean-up"></a>クリーンアップ

サンプルで作成されたすべてのデータを削除するためのオプションを表示します。 サンプルで作成されるデータを検証する場合、削除は任意です。 手動でデータを削除することで同じ結果を得られます。