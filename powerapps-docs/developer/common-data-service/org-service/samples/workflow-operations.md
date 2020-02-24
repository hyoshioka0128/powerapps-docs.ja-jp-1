---
title: 'サンプル: ワークフロー操作 (Common Data Service) | MicrosoftDocs'
description: このサンプルでは、作成、削除、アクティブ化、状態の設定など、多数のワークフロー操作を実行する方法を示します。
ms.custom: ''
ms.date: 1/14/2020
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: samples
author: JimDaly
ms.author: jdaly
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 051e08f11afaf9a291f28d8229311cf667e1db56
ms.sourcegitcommit: 1c4ab1859febccf79a835bd2f168e7e12a953a18
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2020
ms.locfileid: "2957658"
---
# <a name="sample-workflow-operations"></a>サンプル: ワークフロー操作

このサンプルでは、作成、削除、アクティブ化、状態の設定など、多数のワークフロー操作を実行する方法を示します。

サンプルのダウンロード: [ワークフロー](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/Workflow)

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

このサンプルの実行方法に関する一般情報については、[サンプルの実行方法](https://github.com/microsoft/PowerApps-Samples/blob/master/cds/README.md)をご覧ください。

5 つの個別のサンプルがあり、それぞれがソリューションの[プロジェクト](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/Workflow/Workflow)の C# ファイルにあることに注意してください。 各サンプルを実行するには、サンプルを実行する前に、プロジェクトのプロパティでスタートアップ オブジェクトとして設定します。

## <a name="what-this-sample-does"></a>このサンプルの概要

これらのサンプルが示す操作は次のとおりです。

- 同期 (リアルタイム) または非同期ワークフローを作成する
- ワークフローを削除する
- ワークフローを実行する
- ワークフローのアクティブ化または非アクティブ化
- ワークフローのステータスと状態を設定または取得する
- テンプレートからのワークフローの作成

作成されたワークフローは、Web ブラウザーを使用して組織を表示するときに **設定 > プロセス** (処理センターの下) で表示できます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

各サンプルは、デモンストレーション コードで必要なエンティティ インスタンスを作成します。 これは、`CreateRequiredRecords()` メソッドで実行されます。

### <a name="demonstrate"></a>実際にやってみます

各サンプルの主なデモ コードは、各クラス ファイルの `Main()` メソッドの `Demonstrate` リージョンにあります。

### <a name="clean-up"></a>クリーンアップ

`DeleteRequiredRecords()` メソッドは、サンプルによって作成されたレコードを削除するオプションをコンソール ウィンドウに表示します。

サンプルで作成されるエンティティ インスタンス (レコード) を検証する場合、削除は任意です。 通常、ブラウザーで新しい組織レコードを表示するまで、コンソール ウィンドウの削除プロンプトに応答することはありません。 プログラムが終了した後はいつでも、作成されたレコードを手動で削除して、同じ結果を得ることができます。
