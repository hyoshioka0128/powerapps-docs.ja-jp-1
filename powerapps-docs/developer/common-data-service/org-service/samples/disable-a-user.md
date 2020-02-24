---
title: " ユーザーを無効化または有効化する (Common Data Service) | Microsoft Docs"
description: このサンプルでは、システム ユーザーを無効化、有効化する方法を示しています。
ms.custom: ''
ms.date: 1/27/2020
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
ms.openlocfilehash: aa87ed58a38db30435f60e3066b62b27f5d98730
ms.sourcegitcommit: 5bfd0448f1d5ca3d938e3bd928d1dd3d4042afff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "2992870"
---
# <a name="sample-disable-or-enable-a-user"></a>例: ユーザーを有効化、または無効化する

このサンプルは、オンラインまたはオンプレミス/ IFD環境でシステム ユーザー アカウントを無効化、または有効化する方法を示しています。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/DisableOrEnableUser) からダウンロードできます

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

システムユーザーを有効、または無効にするには、このプログラムを実行する Customer Engagement のユーザー　アカウントに システム管理者のロールが必要です。

このサンプルを構築する前に、 Visual Studio のソリューションを開き、 続いて **表示** > **タスクリスト** を選択します。 組織内の既存のシステム ユーザーに関する必要な情報を入力するには、実行する必要がある TODO コメントが2つあります。

このサンプルの実行方法については、[サンプルの実行方法](https://github.com/microsoft/PowerApps-Samples/blob/master/cds/README.md) をご覧ください。

## <a name="what-this-sample-does"></a>このサンプルの概要

サンプルは、既存のシステ ムユーザーの識別子を取得し、そのユーザ ーアカウントを無効化または有効化します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

指定した既存のシステム ユーザーの識別子を取得します（[このサンプルの実行方法](#how-to-run-this-sample)を参照してください）。

### <a name="demonstrate"></a>実際にやってみます

`SetStateRequest` を使用して、システムユーザーを無効化、または有効化します。 また、システム ユーザーに関する情報の取得方法も示します。

Customer Engagement で指定されたシステム ユーザーの概要を表示するには、 **設定** > **セキュリティ** > **ユーザー** に移動し、リスト内の対象となるシステム ユーザーのアカウントを選択します。 必要に応じて、**無効なユーザー** のシステム ビューを使用して、すべてのユーザーのリストをフィルター処理します。 これにより、ユーザーのステータスが「無効」となります。

### <a name="clean-up"></a>クリーンアップ

`Main()` のメソッドで無効化されたユーザーアカウントを有効化するオプションを表示します。

Customer Engagement で無効なユーザーアカウントを調べる場合には、必ずしも 「はい」 と応答する必要はありません。 Active Directory や Office 365 で手動でユーザー アカウントを有効にしても同じ結果が得られます。