---
title: Power Apps でモデル駆動型アプリのフォーム要素を表示または非表示にする | MicrosoftDocs
description: タブ、セクション、またはフィールドなどを、要素から表示または非表示にする方法を学習
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 7b9e8dc2-229c-455f-ae18-49e8d879ff71
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 54a2aeed489cf3e3621bcf21f5f6e0f12b15deff
ms.sourcegitcommit: 2d21c2c65875f97dff6d5843611d4221a4282f22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2020
ms.locfileid: "3027591"
---
# <a name="show-or-hide-model-driven-app-form-elements"></a>モデル駆動型アプリのフォーム要素を表示または非表示にする

 複数の種類のフォーム要素には、既定で、表示するか、非表示にするかのオプションがあります。 タブ、セクション、フィールド、iFrame、および Web リソースはすべてこのオプションを提供します。 フォーム スクリプトまたは業務ルールを使用して、それらの要素の表示を制御し、フォームの条件に適合したユーザー インターフェイスを提供する動的なフォームを作成できます。  
  
> [!NOTE]
>  フォーム要素を非表示にすることは、セキュリティ上、推奨される方法ではありません。 要素を非表示にした場合、ユーザーがフォームの要素およびデータを見ることのできる複数の方法があります。 
  
 オプションの表示を制御するためにスクリプトに依存するフォームをデザインするよりも、業務プロセス フロー、ダイアログ、または別のフォームに切換えたほうが、要件を満たすのに適しているかどうかを考慮します。 それでもスクリプトを使用する場合、非表示になる要素は既定で非表示になることを確認してください。 ロジックが要求する場合に、スクリプトを使用してその要素を表示します。 こうすると、スクリプトをサポートしていない表示方法で、表示されなくなります。
 
 > [!NOTE]
> 統一インターフェイスで、フィールドが複数の列にまたがらないセクションでは、セクション内のフィールドを非表示にすると、フォームの下のフィールドが上に移動します。 フィールドがセクション内の 3 つ以上の列にまたがる場合、コントロールのあるセクション内のフィールドを非表示にしても、その下のフィールドはフォーム上で移動しません。 セクションの非表示フィールドがある場所に追加の空白が表示されます。

## <a name="next-steps"></a>次のステップ

[フォーム エディターのインターフェイスの概要](form-editor-user-interface-legacy.md)
