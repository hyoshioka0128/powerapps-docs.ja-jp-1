---
title: 'サンプル: トランザクション内で複数の要求を実行する (Common Data Service) | Microsoft Docs'
description: このサンプルでは、トランザクションで複数のリクエストを実行する方法を説明します。
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
ms.openlocfilehash: a02a88b5939a1997df01f8f2344ee6cdd85ecb04
ms.sourcegitcommit: 3bf59896a98e5f01289a2489e185f27518aeaec3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2020
ms.locfileid: "2956339"
---
# <a name="sample-execute-multiple-requests-in-transaction"></a>サンプル: トランザクション内での複数の要求の実行

このサンプルでは、単一のWebメソッド呼び出しを使用して、単一のデータベーストランザクションの一部として、コレクション内のすべてのメッセージ要求を実行する方法を説明します。 ビジネス アプリケーションでは、システム内の複数のレコードの変更を調整して、すべてのデータの変更が成功したか失敗したかのいずれかになるようにすることが一般的な要件です。 データベースの用語では、どれか一つの操作が失敗したときにすべてのデータの変更をロール バックする機能を持つ単一のトランザクションで、複数の操作を実行することとして知られています。

[ExecuteTransactionRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.executetransactionrequest?view=dynamics-general-ce-9) メッセージ要求を使用して、1つのデータベース トランザクションで2つ以上の組織のサービス リクエストを実行することができます。 

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ExecuteMultipleInTransaction) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`ExecuteTransactionRequest` メッセージは、1つのデータベース トランザクションで1つ以上のメッセージ要求を実行する際に必要となるデータを含んでおり、さらに必要に応じて結果の集合を返すシナリオで使用することを意図しています。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `ExecuteTransactionRequest` メソッドが `ExecuteTransactionRequest` オブジェクトを作成します。
2. `OrganizationRequestCollection` メソッドは、空の組織要求コレクションを作成します。
3. `CreateRequest` メソッドは、各エンティティごとに要求コレクションに追加されます。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
