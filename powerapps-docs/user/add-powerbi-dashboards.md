---
title: ダッシュボードで Power BI 視覚エフェクトを追加または編集する | MicrosoftDocs
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
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "75203929"
---
# <a name="add-or-edit-power-bi-visualizations-on-your-dashboard"></a>ダッシュボードで Power BI 視覚エフェクトを追加または編集する

[!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードと個人ダッシュボードに追加するタイルを利用し、中身の充実したインタラクティブ レポートやリアルタイム視覚エフェクトを作成します。  
  
> [!NOTE]
> モデル駆動型アプリで個人ダッシュボードに [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトを追加するには、次を行う必要があります。  
> 
> - **[設定]** 、 **[管理]** 、 **[システム設定]** 、 **[レポート]** タブ、 **[Power BI のビジュアル化の埋め込みを許可する]** の順に選択し、組織の [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトを有効にします。  
> - [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] アカウントを用意し、少なくとも 1 つの [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードにアクセスできるようにします。  
> - [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトをシステム ダッシュボードに追加しないでください。サポートされていません。
  

## <a name="create-a-personal-power-bi-dashboard"></a>個人 Power BI ダッシュボードを作成する
  次の手順でモデル駆動型アプリに [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードを追加します。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] サービスに接続する場合、アカウントが必要であり、また、データ ソースとして Common Data Service インスタンスを選択しておく必要があります。 データ ソースを登録し、接続する方法については、「[Microsoft Power BI](https://powerbi.microsoft.com/)」を参照してください。  

1. アプリを開き、 **[ダッシュボード]** に進みます。
  
2. **[新規]** を選択し、 **[Power BI ダッシュボード]** を選択します。  

   
    > [!div class="mx-imgBorder"] 
    > ![新しい Power BI ダッシュボードを追加する](media/pbi_1.png "新しい Power BI ダッシュボードを追加する") 

3. **[Power BI ダッシュボードのプロパティ]** ダイアログでワークスペースを選択し、ダッシュボードに埋め込む [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードを選択します。 [!INCLUDE[pn_moca_full](../includes/pn-moca-full.md)] と [!INCLUDE[pn_Microsoft_Dynamics_CRM_Mobile](../includes/pn-dyn-365-phones.md)] でダッシュボードを利用できるようにするには、 **[モバイルの有効化]** を選択します。

    
    > [!div class="mx-imgBorder"] 
    > ![個人ダッシュボードに Power BI タイルを追加する](media/workspace-add-power-bi-dashboard.png "個人ダッシュボードに Power BI タイルを追加する") 

4. **[保存]** を選択してダッシュボードを保存します。
 
## <a name="embed--power-bi-tiles-on-your-personal-dashboard"></a>個人ダッシュボードに Power BI タイルを埋め込む  
 次の手順で個人ダッシュボードに 1 つまたは複数の [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイルを追加します。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] サービスに接続する場合、アカウントが必要であり、また、データ ソースとして Common Data Service インスタンスを選択しておく必要があります。 データ ソースを登録し、接続する方法については、「[Microsoft Power BI](https://powerbi.microsoft.com/)」を参照してください。  
  
1. アプリを開き、 **[ダッシュボード]** に進みます。 
  
2. 既存の個人ダッシュボードを選択するか、 **[新規]** を選択してダッシュボードを作成します。  
  
3. ダッシュボード上で、タイルを表示する領域を選択し、ツール バーの **[Power BI タイル]** を選択します。  

   > [!div class="mx-imgBorder"] 
   > ![新しい Power BI タイルを追加する](media/pbi_2.png "新しい Power BI タイルを追加する") 
  
4. **[Power BI タイル]** ダイアログでワークスペースを選択し、ダッシュボードに表示する [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイルを選択します。 [!INCLUDE[pn_moca_full](../includes/pn-moca-full.md)] と [!INCLUDE[pn_Microsoft_Dynamics_CRM_Mobile](../includes/pn-dyn-365-phones.md)] でタイルを利用できるようにするには、 **[モバイルの有効化]** を選択します。  
  
     ダッシュボードの別の領域を選択してこの手順を繰り返し、別の [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] タイル、あるいはグラフやリストなど、他のコンポーネントをダッシュボードに追加します。  
  
5. **[保存]** を選択してダッシュボードを保存します。  
  
  
### <a name="things-you-can-do-with-power-bi-embedded-tiles-in-personal-dashboards"></a>個人ダッシュボードの Power BI 埋め込みタイルでできること 

[!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトで利用できる機能を表示するには、視覚エフェクトの右上にカーソルを合わせます。次の機能が表示されます。  
  
   > [!div class="mx-imgBorder"] 
   >![Power BI タイル機能を埋め込む](media/embed-powerbi-tile-features.png "Power BI タイル機能を埋め込む")  
  
1. **[更新]** ボタン ![更新ボタン](media/embed-pbi-tile-refresh-button.png "[最新の情報に更新] ボタン") を選択すると、タイルの基礎になっているレポート データが更新されます。  
  
2. **[Power BI で開く]** ボタン ![Power BI で開くボタン](media/open-in-power-bi.png "[Power BI で開く] ボタン") を選択すると、視覚エフェクトが含まれる [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] ダッシュボードが新しいブラウザー タブで開きます。  
  
3. **[拡大]** ボタン ![拡大タイル](media/embed-pbi-tile-enlarge-button.png "[拡大] タイル") を選択すると、視覚エフェクトが展開され、ここに表示されている [Sales Pipeline] タイルのように、視覚エフェクトの表示領域が増えます。  
  
    > [!div class="mx-imgBorder"] 
    >![埋め込まれた Power BI タイルの拡大](media/embed-power-bi-tile-features.png "埋め込まれた Power BI タイルの拡大")  
  
 
## <a name="share-a-personal-dashboard-that-contains-power-bi-visualizations"></a>Power BI 視覚エフェクトが含まれる個人ダッシュボードを共有する  
 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] 視覚エフェクトが含まれる個人ダッシュボードを共有するには、Common Data Service と [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] の両方で共有を構成する必要があります。また、ユーザーかグループに両方のサービスで同じ資格情報と適切なアクセス レベルを与える必要があります。 アプリで個人ダッシュボードを共有するには、 **[ダッシュボード]** に移動します。 ダッシュボードの一覧で、必要な個人ダッシュボードを選択し、 **[ダッシュボードの共有]** を選択します。 [!INCLUDE[pn_power_bi_for_office_365_short](../includes/pn-power-bi-for-office-365-short.md)] でダッシュボードを共有する方法については、[Power BI の同僚や他のユーザーとダッシュボードを共有する](https://powerbi.microsoft.com/documentation/powerbi-service-share-unshare-dashboard/)方法に関するページを参照してください。  
  
<a name="privacy"></a>   
## <a name="privacy-notice"></a>プライバシーに関する声明  
[!INCLUDE[cc_privacy_powerbi_tiles_dashboards](../includes/cc-privacy-powerbi-tiles-dashboards.md)]
  

