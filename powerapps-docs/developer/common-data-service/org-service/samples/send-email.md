---
title: 'サンプル: 電子メールを送信する (Common Data Service) | Microsoft Docs Microsoft'
description: このサンプルは、電子メールを送信する方法を説明します
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
ms.openlocfilehash: aa053f5940f7f315d3d3cbadfc6550b70ed3959e
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155582"
---
# <a name="sample-send-an-email"></a>サンプル: 電子メールの送信

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/sample-send-email -->

このサンプルでは、[SendEmailRequest](https://docs.microsoft.com/dotnet/api/microsoft.crm.sdk.messages.sendemailrequest?view=dynamics-general-ce-9) メッセージを電子メールで送信する方法を示します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/SenEmail) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`SendEmailRequest` メッセージは、電子メール メッセージを送信するために必要なデータが含まれているシナリオで使用するためのものです。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。
1. `Contact` メソッドは、`(To: field)` に電子メールを送信する連絡先を作成します。
1. `WhoAmIRequest` 方法は、電子メールを送信するために現在のユーザー情報をすばやく取得します `(From: field)`。
1. `ActivityParty` メソッドは、電子メールの `To` および `From` 活動関係者を作成します。
1. `Email` メソッドは電子メール メッセージを作成します。

### <a name="demonstrate"></a>使用方法

`SendEmailRequest` メソッドは、[セットアップ](#setup)で作成した電子メール メッセージを送信します。

### <a name="clean-up"></a>クリーン アップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
