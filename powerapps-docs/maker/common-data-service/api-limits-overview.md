---
title: API 制限の概要 (Common Data Service) | Microsoft Docs
description: Common Data Service の API 要求に対する制限について理解します。
ms.custom: ''
ms.date: 11/23/2019
ms.reviewer: kvivek
ms.service: powerapps
ms.topic: article
author: JimDaly
ms.author: jdaly
manager: ryjones
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 786994fa531698919d1506dc90217f435e43fb8a
ms.sourcegitcommit: abeedb952afc5e09ae4c158611e4813b63cb49b3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2019
ms.locfileid: "2854782"
---
# <a name="common-data-service-api-limits-overview"></a>Common Data Service の API 制限の概要

Common Data Service の API の制限により、サービスレベル、可用性、品質を確保できます。 Common Data Service の API の制限は、Power Platform 要求の制限と割り当ての一部です。 このトピックでは特に、Dynamics 365 のモデル駆動型アプリ (Dynamics 365 Sales や Dynamics 365 Customer Service など)、Power Apps、および Dynamics 365 の Common Data Service / モデル駆動型アプリに接続する Power Automate に適用可能な Common Data Service の制限について紹介します。 

Power Platform 内の全領域の制限についての情報は、[Power Platform の要求の制限と割り当て](/power-platform/admin/api-request-limits-allocations) を参照してください。

Common Data Service に適用される制限には、*権利*および*サービス保護*の制限の 2 つのカテゴリーがあります。

## <a name="entitlement-limits"></a>権利の制限

これらの制限は、ユーザーが毎日行う資格がある要求の数を表します。 割り当てられた制限は、各ユーザーに割り当て済みのライセンスの種類によって異なります。

ユーザーが要求の権利を超えた場合、管理者は通知を受け、Power Apps および Power Automate の要求のキャパシティをそのユーザーに割り当てることができます。 この時点で、ユーザーが不定期であまりひどく超過していないアプリの使用をブロックされることはありません。

Common Data Service の場合、API 要求には、レコードが作成、取得、更新、または削除 (CRUD) されるエンティティ レコードとやり取りするすべてのデータ操作が含まれます。 *共有*や*割り当て*などの特別な操作は、更新と見なされるため、これに含まれています。 これらの要求は、任意のクライアントまたはアプリケーションからのもので、すべてのエンドポイントを使用できます。 これらには、プラグイン、非同期ワークフロー、カスタム コントロールによって実行される操作が含まれますが、これらに限定されません。 ログイン、ログアウト、システム メタデータの操作など、除外されるシステム内部操作がいくつかあります。

> [!IMPORTANT]
> Power Platformの API 要求の割り当てには、Power Automate、AI Builder、および Connector API などの使用が含まれます。 Common Data Service 要求に繋がるコネクタを介したすべての要求は、1 つの Power Platform 要求とみなされます。

これらの権利制限の詳細については、[ライセンスに基づいた Microsoft Power Platform 要求の割り当て](/power-platform/admin/api-request-limits-allocations#microsoft-power-platform-requests-allocations-based-on-licenses) を参照してください。

容量アドオンの表示と割り当ての詳細については、[容量アドオン](/power-platform/admin/capacity-add-on) を参照してください。

個々の容量アドオンの購入に関する情報については、[Power Apps および Power Automate のライセンス ガイド](https://go.microsoft.com/fwlink/?linkid=2085130) を参照してください。 
<!-- There should be some help about purchasing these through the Portal -->


## <a name="service-protection-limits"></a>サービス保護の制限

すべてのユーザーに一貫した可用性とパフォーマンスを確実に提供するために、Common Data Service での API の使用方法にいくつかの制限を適用します。 サービス保護 API 制限は、アプリケーションを実行しているユーザーがリソースの制約に基づいて互いに干渉できないようにします。 これらの制限はプラットフォームの標準ユーザーに影響しません。 影響を受ける可能性があるのは多数の API 要求を実行するアプリケーションのみです。 この制限は、Common Data Service プラットフォームの可用性とパフォーマンス特性に対する脅威となる、ランダムに発生する予期しない要求数の急増に備えて一定レベルの保護を提供します。

ユーザー アカウントごとのコンカレント接続の数、接続ごとの API 要求の数、および各接続に使用できる実行時間を制限します。 これらは、5 分間のスライド枠内で評価されます。 これらの制限のひとつを超えると、例外がプラットフォームによってスローされます。

> [!NOTE]
> サービス保護の制限は、権利の制限に対してカウントされるエンティティに対する CRUD 操作だけでなく、すべての要求に適用されます。
> 
> プラグインとカスタム ワークフロー活動はログオンしているユーザーから独立してサーバー上で実行されるため、サービス保護 API 制限はプラグイン コードから生成された API 呼び出しに対して適用されません。

通常、サービス保護の制限は大量のデータ操作を実行するアプリケーションによってのみ発生するため、これらの例外が返された後、それらのアプリケーションを構築する開発者はパターンを適用して再試行操作を行うことをお勧めします。 これにより、アプリケーションはサービスが送信する例外に応答し、要求の総数を減らし、可能な限り最高のスループットを達成できます。

返される可能性のある特定のエラーと、開発者がパターンを適用してこれらのエラーに対応する方法については、[サービス保護 API の制限](../../developer/common-data-service/api-limits.md) を参照してください。


### <a name="see-also"></a>関連項目

[Power Platform の管理 / ライセンスとライセンス管理 / 要求の制限と割り当て](/power-platform/admin/api-request-limits-allocations)<br />
[開発者 / コードを使用したデータの操作 / サービス保護 API の制限](../../developer/common-data-service/api-limits.md)

