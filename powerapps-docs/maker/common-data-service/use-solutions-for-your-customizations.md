---
title: 既定のソリューションを使用して Power Apps でカスタマイズ | MicrosoftDocs
description: 既定のソリューションをカスタマイズする方法を学習
ms.custom: ''
ms.date: 02/20/2020
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
ms.assetid: f993c4ed-1fc3-4e47-bef1-d38695ddb11a
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1525cdb41cb7e809a54b6389472e5be842a87697
ms.sourcegitcommit: d98dd90a7dda11f434a13a7f8976459856d6142b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/29/2020
ms.locfileid: "3093624"
---
# <a name="use-a-solution-to-customize"></a>カスタマイズするためのソリューションを使用する
カスタマイズを管理するソリューションを作成することをお勧めします。 カスタム ソリューションを使用すると、カスタマイズしたソリューション コンポーネントだけを簡単に見つけて、ソリューション発行者プレフィックスを一貫して適用し、他の環境に配布するためにソリューションをエクスポートできます。  

カスタム ソリューションを使用しない場合は、アンマネージド レイヤーの既定のソリューションで作業します。 すべての Common Data Service 環境に 2 つの規定のソリューションがあります :  
- Common Data Service 既定のソリューション。 これは、作成者がある環境で自分たちのカスタマイズするための既定によって使用できる基本ソリューションです。 Common Data Service 規定のソリューションは、Power Apps を評価したい場合に役立ちます。  
- 既定のソリューション。 これは、システムですべてのコンポーネントを含む特別なソリューションです。 規定のソリューションは、システム内のすべてのコンポーネントと構成を検出するのに役立ちます。  

## <a name="why-you-shouldnt-use-the-default-solutions-to-manage-customizations"></a>既定のソリューションを使用してカスタマイズを管理すべきではない理由
規定のソリューションのいずれかでアプリを作成してカスタマイズを行うべきではない理由はいくつかあります。  
- 既定のソリューションには、環境内のすべてのソリューションからのすべてのコンポーネントとカスタマイズを含みます。 
- 規定では、環境内のすべての有効なユーザーは、アプリケーションを作成し、Common Data Services 規定のソリューションでコンポーネントをカスタマイズできます。 
- 規定のソリューションのいずれかを使用して、環境内で行ったカスタマイズを見つけたり特定したりすることは困難です。 
- 規定のソリューションのいずれかを使用すると、コンポーネントを作成するときに、それに割り当てられた規定の公開元も使用します。 これにより、一部のコンポーネントに誤った発行元プレフィックスが適用される場合があります。 
- 既定のソリューションはエクスポートできません。 したがって、規定のソリューションを別の環境に配布することはできません。 

<!-- Notice that if you have installed or imported other applications or solutions, additional solutions may be available in the solutions list. 

By default,  when you build or customize a model-driven app, you work with the solution called Common Data Services Default Solution. You can open the Common Data Services Default Solution to view and edit the components that are contained in it. To do this, follow these steps.
 
1.  On the left navigation pane select **Solutions**.

2.  In the list of solutions, select **Common Data Services Default Solution**.
  
> [!TIP]
>  If you plan to distribute the applications your make, consider changing the publisher customization prefix. More information: [Solution publisher prefix](change-solution-publisher-prefix.md).  -->
  
<a name="BKMK_PrivacyNotice"></a>   

## <a name="privacy-notices"></a>プライバシーに関する声明  
 [!INCLUDE[cc_privacy_crm_gcc_solution_import](../../includes/cc-privacy-crm-gcc-solution-import.md)]  
  
 [!INCLUDE[cc_privacy_crm_customizations](../../includes/cc-privacy-crm-customizations.md)]  
  
### <a name="see-also"></a>関連項目  
[ソリューションの作成](create-solution.md) <br />
[モデル駆動型アプリのコンポーネントについて](../model-driven-apps/model-driven-app-components.md)


