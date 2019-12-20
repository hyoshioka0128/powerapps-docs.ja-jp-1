---
title: ダッシュボードで Power BI の視覚エフェクトを追加または編集する |MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/15/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c386e53569b942cbc539438f9cf30cabab15bb65
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "75203929"
---
# <a name="add-or-edit-power-bi-visualizations-on-your-dashboard"></a>ダッシュボードで Power BI の視覚エフェクトを追加または編集する

個人用ダッシュボードに追加した [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードとタイルを使用して、豊富で対話型のレポートとリアルタイムの視覚化を作成します。  
  
> [!NOTE]
> モデル駆動型アプリで個人用ダッシュボードに [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトを追加するには、次のことを行う必要があります。  
> 
> - 組織の視覚エフェクトを有効にする**設定** > **管理** > **システム設定** > [**レポート**] タブで >**視覚化の埋め込みを許可**[!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ます。  
> - [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] アカウントを持ち、少なくとも1つの [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードにアクセスできる。  
> - [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] の視覚エフェクトをシステムダッシュボードに追加しないようにします。サポートされていません。
  

## <a name="create-a-personal-power-bi-dashboard"></a>個人用 Power BI ダッシュボードを作成する
  モデル駆動型アプリに [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードを追加するには、次の手順に従います。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] サービスに接続する場合は、アカウントが必要であり、データソースとして Common Data Service インスタンスを選択している必要があります。 データソースの登録と接続の詳細については、「 [Microsoft Power BI](https://powerbi.microsoft.com/)」を参照してください。  

1. アプリを開き、[**ダッシュボード**] にアクセスします。
  
2. [**新規**] を選択し、[ **Power BI ダッシュボード**] を選択します。  

   
    > [!div class="mx-imgBorder"] 
    > ![新しい Power BI ダッシュボードの追加](media/pbi_1.png "新しい Power BI ダッシュボードの追加") 

3. **Power BI ダッシュボードのプロパティ**] ダイアログボックスでワークスペースを選択し、ダッシュボードに埋め込む [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードを選択します。 ダッシュボードを [!INCLUDE[pn_moca_full](../includes/pn-moca-full.md)] と [!INCLUDE[pn_Microsoft_Dynamics_CRM_Mobile](../includes/pn-dyn-365-phones.md)]に使用できるようにする場合は、[**モバイルに対して有効に**する] を選択します。

    
    > [!div class="mx-imgBorder"] 
    > ![Power BI タイルを個人用ダッシュボードに追加する](media/workspace-add-power-bi-dashboard.png "Power BI タイルを個人用ダッシュボードに追加する") 

4. [**保存**] を選択してダッシュボードを保存します。
 
## <a name="embed--power-bi-tiles-on-your-personal-dashboard"></a>個人用ダッシュボードにタイルを埋め込む Power BI  
 1つまたは複数の [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイルを個人用ダッシュボードに追加するには、次の手順に従います。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] サービスに接続する場合は、アカウントが必要であり、データソースとして Common Data Service インスタンスを選択している必要があります。 データソースの登録と接続の詳細については、「 [Microsoft Power BI](https://powerbi.microsoft.com/)」を参照してください。  
  
1. アプリを開き、[**ダッシュボード**] にアクセスします。 
  
2. 既存の個人用ダッシュボードを選択するか、[**新規**作成] を選択して作成します。  
  
3. ダッシュボードで、タイルを表示する領域を選択し、ツールバーの [Power BI]**タイル**を選択します。  

   > [!div class="mx-imgBorder"] 
   > ![新しい Power BI タイルの追加](media/pbi_2.png "新しい Power BI タイルの追加") 
  
4. [ **Power BI タイル**] ダイアログボックスで、ワークスペースを選択し、ダッシュボードに表示する [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイルを選択します。 タイルを [!INCLUDE[pn_moca_full](../includes/pn-moca-full.md)] と [!INCLUDE[pn_Microsoft_Dynamics_CRM_Mobile](../includes/pn-dyn-365-phones.md)]に使用できるようにする場合は、[**モバイルに対して有効に**する] を選択します。  
  
     ダッシュボードの別の領域を選択し、この手順を繰り返して、別の [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイル、またはグラフやリストなどの他のコンポーネントをダッシュボードに追加します。  
  
5. [**保存**] を選択してダッシュボードを保存します。  
  
  
### <a name="things-you-can-do-with-power-bi-embedded-tiles-in-personal-dashboards"></a>個人用ダッシュボードで Power BI 埋め込みタイルを使用して実行できる操作 

[!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] の視覚エフェクトで使用できる機能を表示するには、視覚化の右上にマウスポインターを合わせて、次の機能を表示します。  
  
   > [!div class="mx-imgBorder"] 
   >![タイル機能の埋め込み Power BI](media/embed-powerbi-tile-features.png "タイル機能の埋め込み Power BI")  
  
1. [**更新**] ボタンの![更新ボタン](media/embed-pbi-tile-refresh-button.png "[更新] ボタン")を選択して、タイルの基になるレポートデータを更新します。  
  
2. [ **Power BI で開く**] ボタンをクリックして![Power BI] ボタン](media/open-in-power-bi.png "Power BI ボタンで開く")をクリックすると、新しいブラウザータブに視覚化を含む [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードが開きます。  
  
3. [**拡大**] ボタンをクリックして、![視覚化を展開](media/embed-pbi-tile-enlarge-button.png "タイルの拡大")し、ここに表示されている [販売パイプライン] タイルなど、視覚エフェクトの表示領域を増やします。  
  
    > [!div class="mx-imgBorder"] 
    >![拡大した埋め込み Power BI タイル](media/embed-power-bi-tile-features.png "拡大した埋め込み Power BI タイル")  
  
 
## <a name="share-a-personal-dashboard-that-contains-power-bi-visualizations"></a>Power BI の視覚エフェクトを含む個人用ダッシュボードを共有する  
 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] の視覚エフェクトが含まれている個人用ダッシュボードを共有するには Common Data Service と [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)]の両方で共有を構成する必要があります。また、ユーザーまたはグループには、両方のサービスで同じ資格情報と適切なアクセスレベルが設定されている必要があります。 アプリで個人用ダッシュボードを共有するには、**ダッシュボード**にアクセスします。 ダッシュボードの一覧で、目的の個人用ダッシュボードを選択し、[ダッシュボードの**共有**] を選択します。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)]でのダッシュボードの共有の詳細については、「 [Power BI: ダッシュボードを同僚や他のユーザーと共有する](https://powerbi.microsoft.com/documentation/powerbi-service-share-unshare-dashboard/)」を参照してください。  
  
<a name="privacy"></a>   
## <a name="privacy-notice"></a>プライバシーに関する声明  
[!INCLUDE[cc_privacy_powerbi_tiles_dashboards](../includes/cc-privacy-powerbi-tiles-dashboards.md)]
  

