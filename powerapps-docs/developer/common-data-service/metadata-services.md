---
title: コードを使用してメタデータで作業する (Common Data Service) | Microsoft Docs
description: '[Web API](webapi/overview.md) および [組織サービス](org-service/overview.md) の両方には、エンティティのスキーマの CRUD 操作を実行する機能があります。'
ms.custom: ''
ms.date: 10/31/2018
ms.reviewer: kvivek
ms.service: powerapps
ms.topic: article
author: mayadumesh
ms.author: jdaly
manager: ryjones
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 853fc53221f82a25aeab271c5fca53b19d17eabe
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749134"
---
# <a name="work-with-metadata-using-code"></a>コードを使用してメタデータを扱う

[Web API](webapi/overview.md) および [組織サービス](org-service/overview.md) の両方には、エンティティのスキーマの CRUD 操作を実行する機能があります。 コードを使用してこれらの操作を実行できる一方で、通常デザイナーを使用して、カスタマイズされたスキーマ要素を追加、更新、削除します。 ユーザーは管理者特権を持ち、スキーマ変更を適用する必要がありますが、すべてのユーザーがメタデータを読み取ることができます。

## <a name="why-work-with-metadata"></a>メタデータを扱う理由

メタデータ サービスのより一般的な使用方法は、拡張機能が実行される環境に関するメタデータを取得することです。 それぞれの環境は異なり、スキーマ メタデータには、環境がどのように構成されるかという情報がさらに含まれ、この情報を取得し、拡張機能が、その環境で有効であるその他のカスタマイズに適応される必要があります。

いくつかの例:
- オプションセット属性で入手可能であるオプション数は変更できます。 環境内の値をハードコードするのではなく、異なるオプションがあるかどうかを検討します。 システムをクエリし、既存の環境に異なるオプションがあるかどうかを決めます。
- エンティティの表示名を変更できます。 取引先企業エンティティの既定表示名は*取引先企業*です。 これを*会社*に変更できます。 ユーザに対してメッセージを表示し、エンティティ名を参照する場合、これをハードコードすることはできず、ユーザーが見慣れているものと一致する値を使用し、使用しているエンティティ メタデータから取得した表示名を使用します。

## <a name="browse-the-metadata-for-your-organization"></a>組織のメタデータの参照

システムのメタデータを十分に理解することで、 Common Data Service プラットフォームの働きを容易に把握することができます。 メタデータを編集できるデザイナーは、メタデータにあるすべての詳細を表示できません。 システムにあるメタデータ プロパティとすべての非表示エンティティを表示できるように、*Metadata Browser* というモデル駆動型のアプリをインストールできます。 *Metadata Browser* の詳細: [組織のメタデータをブラウズする](browse-your-metadata.md)

## <a name="programmatically-work-with-metadata"></a>メタデータをプログラムにより扱う

次を使用してメタデータをプログラムにより扱う際の詳細について:
- **Web API**: [ Common Data Service メタデータと Web API を使用する](webapi/use-web-api-metadata.md)
- **組織サービス**: [Common Data Service メタデータを使って組織サービスを使用する](org-service/work-with-metadata.md)