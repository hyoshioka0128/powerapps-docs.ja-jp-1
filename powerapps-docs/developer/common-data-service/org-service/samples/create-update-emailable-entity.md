---
title: " 電子メールに対応したエンティティの作成と更新 (Common Data Service) | Microsoft Docs"
description: このサンプルでは、電子メールで送信可能なエンティティの作成と更新方法を示します。
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
ms.openlocfilehash: bf9d88fbd87a00ec8770a8779b668e6802945454
ms.sourcegitcommit: 5ec7c7f04fe41896dec966706a3b3d295648726f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934347"
---
# <a name="create-an-email-entity"></a>電子メール エンティティの作成

このサンプルでは [CreateEntityRequest](https://docs.microsoft.com/dotnet/api/microsoft.xrm.sdk.messages.createentityrequest?view=dynamics-general-ce-9) メッセージを使用してエンティティを作成、更新する方法を示します。

サンプルは [ここ](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/CreateUpdateEmailableEntity) からダウンロードできます。

## <a name="how-to-run-this-sample"></a>このサンプルを実行する方法

[!include[cc-how-to-run-samples](../../includes/cc-how-to-run-samples.md)]

## <a name="what-this-sample-does"></a>このサンプルの概要

`CreateEntityRequest` メッセージは、カスタムエンティティの作成に必要なデータが含まれるシナリオで使用することを目的としています。任意で、指定されたアンマネージド ソリューションに追加することもできます。

## <a name="how-this-sample-works"></a>このサンプルがどのように動作するか

[このサンプルは何をするか](#what-this-sample-does) で説明されているシナリオをシミュレートするために、サンプルは次のことを行います:

### <a name="setup"></a>セットアップ

1. 組織の現在のバージョンをチェックします。

### <a name="demonstrate"></a>実際にやってみます

1. `Entity` メソッドは、ユーザー定義の エンティティ を作成します。 エンティティを定義してメール送信を有効にします。 これには、 `IsActivityParty` を true に設定する必要があります。
2. `StringAttributeMetadata` メソッドは、ActivityParty 画面で使用する エンティティ の プライマリ属性の定義に使用されます。 説明的な属性を選択するようにしてください。
3. `PublishRequest` メソッドではすべてのカスタマイズを公開します。
4. `CreateFirstEmailAttributeRequest` メソッドは、メールの属性を作成して、エンティティから電子メールを作成します。

### <a name="clean-up"></a>クリーンアップ

[セットアップ](#setup) で作成されたレコードを削除するオプションを表示します。 サンプルで作成されるエンティティおよびデータを検証する場合、削除は任意です。 手動でレコードを削除することで同じ結果を得られます。

