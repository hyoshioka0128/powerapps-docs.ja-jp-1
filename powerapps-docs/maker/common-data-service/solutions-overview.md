---
title: Power Apps でのソリューションに関する作業 | MicrosoftDocs
description: ソリューションの配布方法を説明します
ms.custom: ''
ms.date: 01/21/2020
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
ms.assetid: ece68f5f-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1838f1303d706ab7b9c2ec7356a4ad447a6d0d23
ms.sourcegitcommit: c6906775005aec98973b1f5c3dbe5924aff6d26e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "3341392"
---
# <a name="solutions-overview"></a>ソリューションの概要  

Power Apps では、別の環境にアプリケーションおよびコンポーネントを移動したり、既存のアプリケーションに一連のカスタマイズを適用するために、ソリューションが利用されます。 ソリューションには、1 つ以上のアプリに加えて、サイト マップ、エンティティ、プロセス、Web リソース、オプション セットなど、それ以外のコンポーネントを含めることができます。  ソリューションは [AppSource](https://appsource.microsoft.com/) または独立系ソフトウェア ベンダー (ISV) から取得することができます。
  
詳細: [ソリューションの概要](/power-platform/alm/solution-concepts-alm)
  
> [!NOTE]
>  配布するアプリを作成する ISV の場合は、ソリューションを使用する必要があります。 ソリューションの使用に関する詳細は [開発者ガイド: ソリューションの概要](/powerapps/developer/common-data-service/introduction-solutions) を参照してください。  
  

<a name="BKMK_SolutionComponents"></a>   
## <a name="components"></a>[コンポーネント]  
 コンポーネントは、カスタマイズできる可能性のあるものを示します。 ソリューションに含めることのできるものは、コンポーネントです。 ソリューションに含まれるコンポーネントを表示するには、ソリューションエクスプローラーで **設定** > **ソリューション** 移動して、必要なソリューションを開きます。 コンポーネントは、**コンポーネント** リストに一覧表示されています。 管理ソリューションに含まれるコンポーネントは編集できないことに注意してください。 

> [!div class="mx-imgBorder"] 
> ![ソリューションのコンポーネント](media/components-in-solution.png "ソリューションのコンポーネント") 

ソリューションに追加できるコンポーネントの種類のリストを表示するには、[ComponentType オプション](../../developer/common-data-service/reference/entities/solutioncomponent.md#componenttype-options) をご参照してください。 

ソリューションの詳細については、これらの記事を参照してください。 
- [ソリューションの概念](/power-platform/alm/solution-concepts-alm)
- [ソリューションの階層](/power-platform/alm/solution-layers-alm)
- [管理ソリューションのマージ方法について](/power-platform/alm/how-managed-solutions-merged)
- [カスタマイズするためのソリューションを使用する](/power-platform/alm/use-solutions-for-your-customizations)
- [マネージド プロパティ](/power-platform/alm/managed-properties-alm)
- [セグメント化されたソリューションの使用](/power-platform/alm/segmented-solutions-alm)
- [ソリューションの更新](/power-platform/alm/update-solutions-alm)


<!-- The following is a list of components that you can view in a solution:  
  
-   AI Model

-   Application Ribbon  
  
-   Article Template  
  
-   Business Rule  

-   Canvas App 
  
-   Chart  
  
-   Connection Role  
  
-   Contract Template  

-   Custom Connector
 
-   Custom Control
  
-   Dashboard  
  
-   Email Template  
  
-   Entity  
  
-   Entity Relationship  

-   Environment variable
  
-   Field  
  
-   Field Security Profile  

-   Flow
  
-   Form  
  
-   Mail Merge Template  
  
-   Message  

-   Model-driven app
  
-   Option Set  
  
-   Plug-in Assembly  
  
-   Process  

-   Report  

-   Sdk Message Processing Step  
  
-   Security Role  
  
-   Service Endpoint  
  
-   Site Map  

-   Virtual Entity Data Provider

-   Virtual Entity Data Source
  
-   Web Resource  -->
  
 コンポーネントによっては、他のコンポーネントにネストしています。 たとえば、エンティティには、フォーム、ビュー、グラフ、フィールド、エンティティ関係、メッセージや業務ルールが含まれています。 各コンポーネントには、エンティティの存在が必要です。 フィールドはエンティティの外部に存在することはできません。 フィールドは、エンティティに依存していると言えます。 実際には、上記の一覧に示したコンポーネントの 2 倍の種類のソリューション コンポーネントがありますが、そのほとんどが他のコンポーネント内にテストされておらず、アプリケーションに表示されません。  
  
 コンポーネントの目的は、マネージド プロパティおよびすべてのソリューションの依存関係を使用してカスタマイズできることの制限を追跡し、何も残さずにエクスポート、インポート、および (管理ソリューション内で) 削除することです。  

<!--  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
## Managed and unmanaged solutions  
 There are **managed** and **unmanaged** solutions. A **managed** solution cannot be modified and can be uninstalled after it is imported. All the components of that solution are deleted by uninstalling the solution.  
  
 When you import an **unmanaged** solution, you add all the components of that solution into your environment. You can’t delete the components by uninstalling the solution.  
  
 When you import an **unmanaged** solution that contains components that you have already customized, your customizations will be overwritten by the customizations in the imported unmanaged solution. You can’t undo this.  
  
> [!IMPORTANT]
>  Install an unmanaged solution only if you want to add all the components to your environment and overwrite any existing customizations.  
  
 Even if you don’t plan on distributing your apps or customizations, you may want to create and use an unmanaged solution to have a separate view that only includes those parts of the application that you have customized. Whenever you customize something, just add it to the unmanaged solution that you created.  
  
 To create a **managed** solution, you choose the **As managed** option when you export the solution. If you create a managed solution, you can’t import it back into the same environment you used to create it. You can only import it into a different environment.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### How solutions are applied  
 All solutions are evaluated as layers to determine what your app will actually do. The following diagram shows how managed and unmanaged solutions are evaluated and how changes in them will appear in your environment.  
  
 ![Solution layering](media/solution-layering.png "Solution layering")  
  
 Starting from the bottom and working up to top:  
  
 **System Solution**  
 The system solution is like a managed solution that every environment has. The system solution is the definition of all the out-of-the box components in the system.  
  
 **Managed Solutions**  
 Managed solutions can modify the system solution components and add new components. If multiple managed solutions are installed, the first one installed is below the managed solution installed later. This means that the second solution installed can customize the one installed before it. When two managed solutions have conflicting definitions, the general rule is “Last one wins”. If you uninstall a managed solution, the managed solution below it takes effect. If you uninstall all managed solution, the default behavior defined within the system solution is applied.  
  
 **Unmanaged Customizations**  
 Unmanaged customizations are any change you have made to your environment through an unmanaged solution. The system solution defines what you can or can't customize by using managed properties. Publishers of managed solutions have the same ability to limit your ability to customize solution components that they add in their solution. You can customize any of the solution components that do not have managed properties that prevent you from customizing them.  
  
 **Application Behavior**  
 This is what you actually see in your environment. The default system solution plus any managed solutions, plus any unmanaged customizations you have applied.  
  
<a name="BKMK_ManagedProperties"></a>   
## Managed properties  
 Some components can’t be customized. These components in the system solution have metadata that prevents you from customizing them. These are called **managed properties**. The publisher of a managed solution can also set the managed properties to prevent you from customizing their solution in ways they don’t want you to.  
  
<a name="BKMK_Dependencies"></a>   
## Solution dependencies  
 Because of the way that managed solutions are layered, some managed solutions can be dependent on solution components in other managed solutions. Some solution publishers will take advantage of this to build solutions that are modular. You may need to install a “base” managed solution first and then you can install a second managed solution that will further customize the components in the base managed solution. The second managed solution depends on solution components that are part of the first solution.  
  
 The system tracks these dependencies between solutions. If you try to install a solution that requires a base solution that isn’t installed, you won’t be able to install the solution. You will get a message saying that the solution requires another solution to be installed first. Similarly, because of the dependencies, you can’t uninstall the base solution while a solution that depends on it is still installed. You have to uninstall the dependent solution before you can uninstall the base solution.  
 
## Solution publisher prefix 

By default, the solution you will work with in Power Apps will be the **Common Data Services Default Solution** which is associated with the **Common Data Service Default Publisher**. The default customization prefix will be randomly assigned for this publisher, for example it could be `cr8a3`. This means that the name of every new item of metadata created for your organization will have this prepended to the names used to uniquely identify the items. 

We recommend that you change the solution publisher prefix so that it will be more meaningful. More information: [Change the solution publisher prefix](change-solution-publisher-prefix.md) -->
  
### <a name="next-steps"></a>次のステップ  
[Power Apps でのソリューションの使用](use-solution-explorer.md) <br/>

 
