---
title: Common Data Service | に接続します。Microsoft Docs
description: Common Data Service に接続し、それを使用してアプリを作成する方法について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/04/2020
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 227482b383acd3117cc78eddf97698ffa9146698
ms.sourcegitcommit: 56c8c7cc64695ccb00e0d021c9f98cf70b69b4a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78845194"
---
# <a name="connect-to-common-data-service"></a>Common Data Service への接続

## <a name="overview"></a>概要

ユーザーがデータを管理できるように、Common Data Service にビジネスデータを安全に格納し、強力なアプリを Power Apps に構築することができます。 また、そのデータを、Dynamics 365 の電源自動化、Power BI、データなどのソリューションに統合することもできます。

既定では、Common Data Service コネクタは、アプリの現在の環境のデータに接続します。 アプリが別の環境に移動した場合、コネクタは新しい環境のデータに接続します。 この動作は、1つの環境を使用するアプリ、または開発からテスト環境への移行のために ALM プロセスに従うアプリに適しています。

Common Data Service コネクタを使用してデータソースを追加する場合は、環境を変更してから1つまたは複数のエンティティを選択することができます。 既定では、アプリは現在の環境のデータに接続します。

![既定の環境](media/connection-common-data-service/common-data-service-connection-change-environment.png)

**[変更]** を選択した場合は、現在の環境に加えて、または現在の環境の代わりに、別の環境を使用してデータをプルするように指定できます。

![その他の環境](media/connection-common-data-service/common-data-service-connection-select-environment.png)

[エンティティ] ボックスの一覧に、選択した環境の名前が表示されます。

![新しい環境](media/connection-common-data-service/common-data-service-connection-after-change-environment.png)

Common Data Service コネクタは、Dynamics 365 コネクタより堅牢で、機能のパリティに近づいています。

### <a name="common-data-service-and-the-improved-data-source-experience"></a>Common Data Service と強化されたデータソースエクスペリエンス

2019年11月より前に Common Data Service コネクタを使用してキャンバスアプリを作成した場合、最新バージョンの Common Data Service の利点が得られない可能性があります。 詳細については、 [Common Data Service 接続の機能強化](../use-native-cds-connector.md)に関する説明と、接続のアップグレードに関する情報を参照してください。