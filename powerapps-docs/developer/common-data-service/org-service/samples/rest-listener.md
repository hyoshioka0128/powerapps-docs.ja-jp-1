---
title: 'サンプル: REST リスナー (Common Data Service) | Microsoft Docs'
description: このサンプルでは、Azure Service Bus リスナーを REST エンドポイント契約に対して記述する方法を示します。
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
ms.openlocfilehash: 336350bc0a4c61b1342b36c6e4cce519e9501578
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155667"
---
# <a name="sample-rest-listener"></a>サンプル: REST リスナー

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/sample-rest-listener -->

このサンプルでは、`Azure Service Bus` リスナーを `REST` エンドポイント契約に対して記述する方法を示します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/RESTListener) からダウンロードできます。

このサンプルでは、メッセージがサービス バスの `REST` エンドポイントにポストされると常に実行される、リモート サービス プラグインを登録します。 このプラグインは実行されるときにメッセージに含まれる実行コンテキストの内容をコンソールへ出力します。
