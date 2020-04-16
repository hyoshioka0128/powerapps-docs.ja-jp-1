---
title: 'サンプル: 複数の要求を実行する (Common Data Service) | Microsoft Docs'
description: このサンプルは、単一の Web サービス メソッド呼び出しを使用し、複数の組織メッセージ要求を実行する方法を説明します。
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
ms.openlocfilehash: eeddc1146f32abe62a6abe7a83b053790dec8fea
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155771"
---
# <a name="sample-execute-multiple-requests"></a>サンプル: 複数の要求を実行する

このサンプルは、単一の Web サービス メソッド呼び出しを使用し、[ExecuteMultipleRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.executemultiplerequest?view=dynamics-general-ce-9) をパラメーターとして渡すことで複数の組織メッセージ要求を実行する方法を説明します。 ネットワークに送信するメッセージ要求の数を減らすことにより、メッセージ処理のパフォーマンスが向上します。

サンプルは[ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/ExecutemultipleRequests)からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`ExecuteMultipleRequest` メッセージは、1 つ以上のメッセージ要求を単一のバッチ処理として実行するために必要なデータが含まれているシナリオで使用されることを意図しており、オプションで結果の収集を返します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルの概要](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います。

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>使用方法

1. `ExecuteMultipleRequest` メソッドが `ExecuteMultipleRequest` オブジェクトを作成します。
1. `ExecutingMultipleSettings` メソッドでは、実行時の動作を定義する設定を割り当てます: エラー時に続行し、応答を返します。
1. `OrganizationRequestCollection` メソッドは、空の組織要求コレクションを作成します。
1. `CreateRequest` メソッドは、各エンティティごとに要求コレクションに追加されます。
1. `GetCollectionOdEntitiesToUpdate` クラスは、以前に作成されたエンティティを更新します。


### <a name="clean-up"></a>クリーン アップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
