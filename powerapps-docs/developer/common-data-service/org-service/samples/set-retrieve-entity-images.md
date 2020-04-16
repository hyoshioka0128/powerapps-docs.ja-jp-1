---
title: " エンティティ イメージを設定および取得する (Common Data Service) | Microsoft Docs"
description: このサンプルでは、エンティティ イメージの設定および取得する方法を示します。
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
ms.openlocfilehash: 79a2b18db60afa9f487f4313116c9600c72a13c0
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155575"
---
# <a name="set-and-retrieve-entity-images"></a>エンティティ イメージの設定および取得

このサンプルでは、エンティティ イメージのデータを設定および取得する方法を示しています。 サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/SetRetrieveImages) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

このサンプルは、取引先企業および取引先担当者に対して使用できるつながりロールの作成方法を示します。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. CreateImageAttributeDemoEntity メソッドを使って、スキーマ名 `sample_ImageAttributeDemo` を持つユーザー定義エンティティおよびスキーマ名 `sample_Name` を持つ主属性を作成します。
2. スキーマ名 `EntityImage` を持つイメージ属性を作成します。 すべてのイメージ属性は、この名前を使用します。

3. `sample_ImageAttributeDemo` のエンティティのメイン フォームを取得および更新し、イメージがフォームに表示されるように `showImage` 属性を true に設定します。

4. `sample_ImageAttributeDemo` エンティティを公開します。

5. ここに示すように、イメージ フォルター内にある異なるサイズの 5 つのイメージを使って、`sample_ImageAttributeDemo` エンティティの 5 つの新しいレコードを作成します。各レコードを作成した後、`ShowEntityFormInBrowser` メソッドを使って Web ブラウザー アプリケーションでレコードを表示し、フォームで利用可能なスペースに合うようにソースイメージがどのようにサイズ変更されるかを見ることができます。
6. `entityimage` 属性のレコードを取得し、サイズ変更されたファイルを保存します。 サンプルを実行した後で、`\bin\Debug` フォルダーに保存されたファイルを表示できます。
7. `entityimage_url` 属性のレコードを取得し、画像にアクセスするアプリケーションに含まれる相対的な URL 値が表示されます。 転送されるデータの量が少ないため、このクエリの反応は速くなります。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) でレコードを削除するためのオプションを表示します。 サンプルで作成されたエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。
