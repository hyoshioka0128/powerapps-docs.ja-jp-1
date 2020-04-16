---
title: リボン タブ表示ルールを定義する (モデル駆動型アプリ) | MicrosoftDocs
description: リボン タブ表示ルールの定義について学習します。
keywords: ''
ms.date: 10/31/2018
ms.service: powerapps
ms.custom:
- ''
ms.topic: article
ms.assetid: 916f4e82-01a3-2476-c2a4-ff71caa4195c
author: Nkrb
ms.author: nabuthuk
manager: shilpas
ms.reviewer: ''
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4e4b7f1cbfc167d999881e396d53436387c2f184
ms.sourcegitcommit: 5701e7a755fade6c3bac5c4a5774fcc74627e168
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/10/2020
ms.locfileid: "3115635"
---
# <a name="define-ribbon-tab-display-rules"></a>リボン タブ表示ルールを定義する

<!-- https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/define-ribbon-tab-display-rules -->

タブ表示ルールは、特定のタブをリボンに表示するかどうかを制御します。  
  
 グループや特定のコントロールなどの他のリボン要素とは異なり、リボン上に表示するタブにはタブ表示ルールを明示的に用意する必要があります。 既定で、表示ルールで非表示に指定しない限り、他のすべてのリボン要素は常に表示されます。  
  
 `<TabDisplayRule>` 要素では、`TabCommand` 属性を常に `<Tab>` `Command` 属性値に設定する必要があります。  
  
 `RibbonDiffXml` では、特定のエンティティに対してのみタブを定義したり、グローバルにタブを定義したりすることができます。 タブを特定のエンティティに対して定義する場合、使用できるルールの種類は `<EntityRule>` だけです。 タブを特定のエンティティの範囲内に定義するとタブの表示はそのエンティティにのみに制限されるので、使用できる属性は、`AppliesTo` (`PrimaryEntity` または `SelectedEntity`) および `Context` (`Form`、`HomePageGrid`、`SubGridStandard`、または `SubGridAssociated`) だけです。  
  
 アプリケーション リボンの `RibbonDiffXml` にタブ表示ルールをグローバルに定義する場合は、`EntityRule` 要素と `<PageRule>` 要素を両方とも適用できます。  
  
### <a name="see-also"></a>関連項目  
 [コマンド、およびリボンをカスタマイズする](customize-commands-ribbon.md)   
 [リボン要素のスケーリングの定義](define-scaling-ribbon-elements.md)   
 [リボンの使用による URL へのパラメーターの受け渡し](pass-parameters-url-by-using-ribbon.md)