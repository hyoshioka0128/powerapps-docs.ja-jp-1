---
title: Power Apps でセグメント化されたソリューションを使用する | MicrosoftDocs
description: ソリューションのセグメント化を使用してソリューションを更新する方法の学習
ms.custom: ''
ms.date: 02/04/2020
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
ms.assetid: 5c05f683-e1bd-4885-be23-b6973128773f
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 16730151eb6d7ec45fad7a6803eed3e76f68f8d4
ms.sourcegitcommit: a1b54333338abbb0bc3ca0d7443a5a06b8945228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "3125490"
---
# <a name="use-segmented-solutions"></a>セグメント化されたソリューションの使用 

ソリューションのアップデートを配布するときに更新されるエンティティ コンポーネントのみを含めるように、ソリューションのセグメンテーションを使用します。 ソリューションのセグメント化では、すべての資産を含むエンティティ全体ではなく、選択したエンティティ資産 (エンティティ フィールド、フォーム、ビューなど) をソリューション アップデートと共にエクスポートできます。 <!-- Depending on the complexity of your app, segmentation of the solution can be as simple as everything in a single solution to segmenting by component type, such as entities in one solution, canvas apps in another, and plugins in a third. --> セグメント化されたソリューションを作成するには、 Power Apps で **ソリューション** 領域を使用します。  

次のオプションから選択して既存のエンティティをソリューションに追加すると、ソリューションをセグメント化できます。 
- コンポーネントは含ませません。 コンポーネントまたはメタデータを選択しない場合、最小限のエンティティ情報がソリューションに追加されます。 したがって、フレンドリ名を除き、エンティティ属性 (メタデータ) またはコンポーネントは含まれません。   
- **コンポーネントを選択する**。 フィールド、リレーションシップ、ビジネス ルール、ビュー、フォーム、グラフなど、エンティティに関連付けられている各コンポーネントを個別に選択することで、ソリューションをセグメント化することができます。 このオプションを使用して、新しいカスタムフィールドやフォームの追加など、エンティティで追加または変更されたコンポーネントのみを選択します。  
- **エンティティ メタデータを含める**。 このオプションには、関連エンティティなどのコンポーネントは含まれませんが、エンティティに関連付けられた *すべて* のメタデータを含みます。 メタデータには、監査、重複データ検出、変更追跡などのエンティティ属性が含まれます。 
- **すべてのコンポーネントを含める**。 このオプションにはすべてのコンポーネント*かつ*エンティティに関連付けられたメタデータが含まれます。 ビジネス プロセス フロー、レポート、接続、キューなどの他のエンティティまたはエンティティ コンポーネントを含めることができます。 このオプションは、ターゲット環境に存在しないアンマネージド エンティティを配布する場合にのみ使用してください。 

    > [!WARNING]
    > 意図しないコンポーネントをソリューションに追加しないでください。 更新をターゲット環境にインポートすると、意図しないコンポーネントを含むソリューションが、ソリューションの更新で導入したレイヤーの下にある既存のコンポーネントに予期しない動作を引き起こす可能性があります。 たとえば、更新されていないエンティティにビューを追加し、既存のレイヤーのビューにカスタマイズがある場合、既存のカスタマイズが非アクティブになる場合があります。 詳細については、[ソリューション レイヤ―](solution-layers.md) を参照してください。

<!-- The below was from Per but I don't think it fits in this topic that is only about solution segmentation with entities. 
Similar to the planning that goes into how you model the data that goes into your app, planning for segmentation should be considered before you distribute your solution. Segmenting solutions from a single solution into multiple solutions a month or two years after the initial app has been built can be complex and is prone to cause issues.  -->

## <a name="create-a-segmented-solution-with-entity-assets"></a>エンティティ資産を使用してセグメント化したソリューションを作成 
 セグメント化したソリューションを作成するには、アンマネージド ソリューションの作成と既に更新したコンポーネントのみの追加から開始します。 ウィザード風のセットアップにより、エンティティ資産の追加のプロセスを段階的に進みます。 

たとえば、他のどの環境にも存在しない *カスタムエンティティ* とう名前の新しいカスタムエンティティを作成し、アカウント エンティティに *トップテン* という名前の新しいフィールドを追加したとします。 セグメント化されたソリューションを作成するには、次の手順に従います。 
  
1. Power Apps ポータルに移動し、**ソリューション** を選択します。  
  
2.  **新規ソリューション** を選択してソリューションを作成します。 必須フィールドに情報を入力します。 **作成**を選びます。  
  
3.  作成したソリューションを開きます。 コマンド バーで、**既存を追加** を選択し、次に **エンティティ** を選択します。  
  
4.  **既存のエンティティの追加** ウィンドウで、ソリューションに追加する 1 つ以上のエンティティを選択します。 たとえば、**アカウント** そして **カスタム エンティティ** を選択します。 **次へ**を選択します。  

5.  **エンティティを選択** ウィンドウでは、次を含めるアセットから選択できます。 
    - **すべてのコンポーネントを含める**。 このオプションにはすべてのコンポーネント*かつ*エンティティに関連付けられたメタデータが含まれます。 ビジネス プロセス フロー、レポート、接続、キューなどの他のエンティティまたはエンティティ コンポーネントを含めることができます。 
    - **エンティティ メタデータを含める**。 このオプションにはエンティティに関連付けられたメタデータ*のみ*含まれます。 メタデータには、監査、重複データ検出、変更追跡などのエンティティ属性が含まれます。 
    - **コンポーネントを選択する**。 このオプションを使用すると、フィールド、リレーションシップ、ビジネス ルール、ビュー、フォーム、グラフなど、エンティティに関連付けられている各コンポーネントを個別に選択できます。 
    - コンポーネントは含めないでください。 

      この例では、*カスタム エンティティ* はターゲット環境にインポートされたことはないことから、**カスタム エンティティ** の横で、**すべてのコンポーネントを含める** を選択します。 **アカウント** の下で、**コンポーネントを選択** を選択します。  
      > [!div class="mx-imgBorder"] 
      > ![既存のエンティティの追加](media/add-existing-entities1.png)
  
6.  *トップテン* カスタムフィールドのみがこのアカウント エンティティにとって新しいので、**トップ テン** を選択して、**追加** を選択します。  
     > [!div class="mx-imgBorder"] 
     > ![エンティティ コンポーネントの選択](media/add-existing-entities2.png)

7. **追加** を選択して、コンポーネントをソリューションに追加します。 

### <a name="create-a-segmented-solution-using-solution-explorer"></a>ソリューション エクスプローラーを使用してセグメント化されたソリューションを作成する  
次の図に、エンティティ資産を`Account`エンティティ、`Case`エンティティ、および`Contact`エンティティから選択してセグメント化したソリューションを作成した例を示します。  

> [!NOTE]
> ケース エンティティは、Dynamics 365 Customer Service などの一部の Dynamics 365 アプリケーションに含まれています。 
  
作成したアンマネージド ソリューションを開くことから始めます。 **エンティティ** コンポーネントを選択します。  

 > [!div class="mx-imgBorder"] 
 > ![既存のリソースを追加。](media/solution-segmentation-add-existing-resources-admin.png "既存のリソースを追加。")  
  
 次に、ソリューション コンポーネントを選択します。  
  
 ![ソリューションのコンポーネントを選択。](media/solution-segmentation-select-components-admin.png "ソリューションのコンポーネントを選択。")  
  
 ウィザードに従います。 手順 1 で、アルファベット順に開始して、次のように、最初のエンティティである`Account`エンティティの資産を選択します。  
  
 ![ウィザードを開始します。](media/solution-segmentation-wizard-starts-admin.png "ウィザードを開始します。")  
  
 **フィールド**タブを開き、**取引先企業番号**フィールドを選択します。  
  
 ![取引先企業のエンティティ資産を選択します。](media/solution-segmentation-select-account-assets-admin.png "取引先企業のエンティティ資産を選択します。")  
  
 手順 2 で、**サポート案件**エンティティについて、すべての資産を追加します。  
  
 ![サポート案件のエンティティ資産を選択します。](media/solution-segmentation-select-case-assets-admin.png "サポート案件のエンティティ資産を選択します。")  
  
 手順 3 で、**取引先担当者**エンティティの**記念日**フィールドを追加します。  
  
 ![取引先担当者のエンティティ資産を選択します。](media/solution-segmentation-select-contact-assets-admin.png "取引先担当者のエンティティ資産を選択します。")  
  
 その結果、作成したセグメント化されたソリューションには、`Account`、`Case`、および`Contact`の 3 つのエンティティが含まれます。 各エンティティには選択した資産のみが含まれます。  
  
 > [!div class="mx-imgBorder"] 
 > ![エンティティを含むソリューション。](media/solution-segmentation-solution-entities-admin.png "エンティティを含むソリューション。")  
  
  
### <a name="see-also"></a>関連項目  
 [ソリューションの概要](solutions-overview.md)


