---
title: オンプレミスデータゲートウェイ |Microsoft Docs
description: この記事では、Power Apps 用のオンプレミスデータゲートウェイの概要について説明します。
author: arthiriyer
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/16/2019
ms.author: arthii
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4dc5afc49ba1ee38889d0eb6d86bf1cde6687135
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74732206"
---
# <a name="what-is-an-on-premises-data-gateway"></a>オンプレミスデータゲートウェイとは

オンプレミスデータゲートウェイは、オンプレミスのデータ (クラウドにないデータ) と複数の Microsoft クラウドサービスの間で迅速かつ安全なデータ転送を提供するブリッジとして機能します。 これらのクラウドサービスには、Power BI、電源アプリ、電源自動化、Azure Analysis Services、Azure Logic Apps が含まれます。 ゲートウェイを使用することにより、組織はオンプレミスネットワーク上のデータベースやその他のデータソースを維持しながら、クラウドサービスでオンプレミスのデータを安全に使用することができます。

## <a name="how-the-gateway-works"></a>ゲートウェイのしくみ

![ゲートウェイの概要](media/gateway-reference/on-premises-data-gateway.png)

ゲートウェイのしくみの詳細については、「[オンプレミスデータゲートウェイのアーキテクチャ](/data-integration/gateway/service-gateway-onprem-indepth)」を参照してください。

## <a name="types-of-gateways"></a>ゲートウェイの種類

ゲートウェイには、次の2種類があります。それぞれのシナリオで異なります。

- **オンプレミスデータゲートウェイ**を使用すると、複数のユーザーが複数のオンプレミスデータソースに接続できます。 1つのゲートウェイインストールで、サポートされているすべてのサービスでオンプレミスデータゲートウェイを使用できます。 このゲートウェイは、複数のメンバーが複数のデータソースにアクセスする複雑なシナリオに適しています。

- **オンプレミスデータゲートウェイ (個人用モード)** では、1人のユーザーがソースに接続でき、他のユーザーと共有することはできません。 オンプレミスデータゲートウェイ (個人用モード) は、Power BI でのみ使用できます。 このゲートウェイは、レポートを作成する唯一のユーザーであり、他のユーザーとデータソースを共有する必要がない場合に適しています。

## <a name="use-a-gateway"></a>ゲートウェイを使用する

ゲートウェイを使用する主な手順は4つあります。

1. [ゲートウェイをダウンロードし](/data-integration/gateway/service-gateway-install)、ローカルコンピューターにインストールします。
2. ファイアウォールやその他のネットワーク要件に基づいてゲートウェイを[構成](/data-integration/gateway/service-gateway-app)します。
3. 他のネットワーク要件も管理および管理できる[ゲートウェイ管理](/data-integration/gateway/service-gateway-manage)者を追加します。
4. エラーが発生した場合にゲートウェイの[トラブルシューティング](/data-integration/gateway/service-gateway-tshoot)を行います。

## <a name="next-steps"></a>次の手順

- [オンプレミスデータゲートウェイをインストールする](/data-integration/gateway/service-gateway-install)