---
title: 'サンプル: 永続的なキュー リスナー (Common Data Service) | Microsoft Docs'
description: このサンプルは、Azure Service Bus リスナー アプリケーションを永続キュー エンドポイント契約に対して記述する方法を示します。
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
ms.openlocfilehash: f277caf86819ee00ead90855a6d60e09e76ec077
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3155707"
---
# <a name="sample-persistent-queue-listener"></a>サンプル: 永続キュー リスナー

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/sample-persistent-queue-listener -->

このサンプルは、Azure Service Bus リスナー アプリケーションを永続キュー エンドポイント契約に対して記述する方法を示します。 サンプルは [ここ](https://github.com/Microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/PersistentQueueListener) からダウンロードできます。

このリスナーは、メッセージがサービス バスにポストされて、エンドポイント キューで使用可能になるまで待機します。 メッセージがキューに入ると、リスナーはメッセージを読み取り、メッセージに含まれる実行コンテキストをコンソールに出力し、キューからメッセージを削除します。
