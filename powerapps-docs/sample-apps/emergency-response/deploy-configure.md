---
title: 緊急時対応アプリをデプロイして構成する | Microsoft Docs
description: 病院の IT 管理者が組織用のサンプル アプリをデプロイして構成するための詳細な手順について説明します。
author: KumarVivek
manager: annbe
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 03/26/2020
ms.author: kvivek
ms.reviewer: kvivek
searchScope:
- GetStarted
- PowerApps
ms.openlocfilehash: e58b23503e1730c8606a833cb05f7253b5b96f49
ms.sourcegitcommit: 77e00640a59a7db9d67d3ac52f74d264cbe3a494
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2020
ms.locfileid: "80327772"
---
# <a name="deploy-and-configure-the-emergency-response-app"></a>緊急時対応アプリをデプロイして構成する

緊急時対応アプリの場合、少量のセットアップでニーズに適合させられる必要があります。 この記事では、病院の IT 管理者が組織用のアプリケーションをデプロイして構成するための詳細な手順について説明します。

これらの手順の推定所要時間: **35 – 40 分**。

## <a name="demo-deploy-and-configure-the-emergency-response-app"></a>デモ:緊急時対応アプリをデプロイして構成する

緊急時対応アプリをデプロイして構成する方法をご覧ください。

<br/>

> [!VIDEO https://www.youtube.com/embed/-1g44wNiuWI]


## <a name="deploy-the-emergency-response-app"></a>緊急時対応アプリをデプロイする

組織用の緊急時対応サンプル アプリをデプロイするには、以下の手順を実行します。

- [ステップ 1:Power Apps にサインアップして環境を作成する](#step-1-sign-up-for-power-apps-and-create-an-environment)
- [手順 2:デプロイ パッケージをダウンロードする](#step-2-download-the-deployment-package)
- [ステップ 3:ソリューション ファイルを環境にインポートする](#step-3-import-the-solution-file-into-your-environment)
- [手順 4:組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization)
    - [手順 4.1: データ ファイルからデータを読み込む方法](#step-41-how-to-load-data-from-data-files)
    - [手順 4.2: 必須の構成データをインポートする](#step-42-import-mandatory-configuration-data)
- [手順 5:モバイル アプリのブランドを更新する](#step-5-update-the-mobile-app-branding)
- [手順 6:モバイル アプリの同意をバイパスする](#step-6-bypass-consent-for-mobile-apps)
- [手順 7:テレメトリ用に Azure Application Insights キーをモバイル アプリに追加する](#step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry)
- [手順 8: 組織内のユーザーとキャンバス アプリを共有する](#step-8-share-canvas-apps-with-users-in-your-organization)
- [手順 9:モバイル アプリをヒーロー アプリおよびおすすめアプリとして設定する](#step-9-set-your-mobile-app-as-hero-and-featured-app)
- [手順 10: 組織内の管理者とモデル駆動型アプリを共有する](#step-10-share-model-driven-app-with-admins-in-your-organization)

### <a name="step-1-sign-up-for-power-apps-and-create-an-environment"></a>手順 1:Power Apps にサインアップして環境を作成する

Power Apps をまだ持っていない場合は、Power Apps にサインアップし、適切なライセンスを購入します。

詳細情報:

-   [Power Apps の価格](https://powerapps.microsoft.com/pricing/)
-   [Power Apps を購入する](https://docs.microsoft.com/power-platform/admin/signup-for-powerapps-admin)

Power Apps を購入した後、Common Data Service データベースを使用して環境を作成します。

1.  [Power Platform 管理センター](https://aka.ms/ppac)にサインインします。

2.  データベースを使用して Common Data Service 環境を作成します。 詳細情報: [環境を作成および管理する](https://docs.microsoft.com/power-platform/admin/create-environment)

3.  環境に適切なユーザーを作成します。 詳細情報: [ユーザーを作成し、セキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)

### <a name="step-2-download-the-deployment-package"></a>手順 2:デプロイ パッケージをダウンロードする

緊急時対応アプリ用のアプリとビジネス ロジックを設定するためのソリューション ファイル、画像、データ ファイルが含まれる最新のデプロイ パッケージ (.zip) を <https://aka.ms/emergency-response-solution> から取得します。

デプロイ プロセスを始めるには、お使いのコンピューター上の場所にデプロイ ファイル (.zip) を抽出します。 抽出されたフォルダーには、次のフォルダーが含まれます。

| **フォルダー/ファイル**       | **説明**  |
|-----------------------|------------------|
| **App Icons**         | モバイル アプリ (キャンバス アプリ) 用の既定のアプリ アイコンが格納されています|
| **Data Files**        | ソリューションおよびアプリが動作するためのマスター ファイルとサンプル データ ファイル (.xlsx) が格納されています。 これらのファイルからデータをインポートして、アプリでの作業を始められます。 詳細情報: [手順 4: 組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization) |
| **Power BI Template** | 組織向けのレポートを構成するために使用する Power BI レポート テンプレート ファイル (.pbit) が格納されています。 詳細情報:[Power BI ダッシュボードを使用して分析情報を取得する](#get-insights-using-power-bi-dashboards)|
| **PowerShell**        | モバイル アプリ (キャンバス アプリ) の構成に使用するスクリプトが格納されています。 |
| **Solution File**     | 緊急時対応アプリに必要なアプリとメタデータを作成する Common Data Service ソリューション ファイルが格納されています。  |

### <a name="step-3-import-the-solution-file-into-your-environment"></a>手順 3:ソリューション ファイルを環境にインポートする

1.  デプロイ ファイル (.zip) を抽出した場所に移動します。**Solution File** フォルダーが見つかります。 **Solution File** フォルダーにあるマネージド ソリューション (.zip) ファイルを環境にインポートします。

2.  [Power Apps](https://make.powerapps.com) にサインインします。

3.  右上隅で環境を選択します。

4.  左側のペインで **[ソリューション]** を選択した後、 **[インポート]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![ソリューションをインポートする](media/conf-import-solution.png "ソリューションをインポートする")

5.  **[ソリューションのインポート]** ダイアログ ボックスで、手順 1 で説明したソリューション ファイルを選択し、ウィザードの手順に従ってソリューションをインポートします。

6.  ソリューションが正常にインポートされたら、インポート ダイアログ ボックスで **[閉じる]** を選択し、 **[すべてのカスタマイズの発行]** を選択します。 完了するまでに時間がかかることがあります。

**[アプリ]** に新しいアプリが表示されるようになります。

> [!div class="mx-imgBorder"] 
> ![新しいアプリ](media/conf-apps-new-apps.png "新しいアプリ")

**Admin App** を選択して、残りのデプロイ設定を構成できるモデル駆動型アプリを開きます。 詳細情報: [モデル駆動型アプリとは](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

> [!div class="mx-imgBorder"] 
> ![管理アプリを開く](media/conf-admin-app-open.png "管理アプリを開く")

管理アプリのいくつかのエンティティで、病院システムのデータを追加したり管理したりできます。 左側のナビゲーション ペインの下部にある領域ピッカーを使用して、異なる領域を選択できます。

### <a name="step-4-load-configuration-and-master-data-for-your-organization"></a>手順 4:組織の構成データとマスター データを読み込む

緊急時対応アプリに必要なすべてのデータは、抽出したデプロイ フォルダーの下にある **Data Files** フォルダーから入手できます。

**Data Files** フォルダーには、次のファイルとフォルダーがあります。

<table style="width:100%">
<tr>
<th>名前</th>
<th>説明</th>
</tr>
<tr>
<td>ルートには次のファイルがあります。
<ul>
<li>00 - Acuities Import.xlsx</li>
<li>00 - App Config Import.xlsx</li>
<li>00 - App Import.xlsx</li>
<li>00 - Request Roles Import.xlsx</li>
<li>00 - Supplies Import.xlsx</li>
</ul>
</td>
<td>これらは構成データ ファイルであり、管理アプリを使用して次のエンティティにインポートする必要があります。
<ul>
<li>Acuities</li>
<li>App Config</li>
<li>アプリケーション</li>
<li>Request Roles</li>
<li>Supplies Import</li>
</ul>
<br/>これらのエンティティにデータをインポートすると、緊急時対応アプリが動作するために必要なこれらのエンティティのレコードが作成されます。
<br/>
<br/>
<strong>注意</strong>: 後で説明する <strong>Apps</strong> エンティティと <strong>App Config</strong> エンティティを除き、これらのエンティティの構成値を更新しないでください。</td>
</tr>
<tr>
<td><strong>Sample Data</strong> フォルダー</td>
<td><p>このフォルダーには、インポートすることでアプリケーションにサンプル データを設定できるサンプル データ ファイル (.xlsx) が格納されています。 これらのファイルには、データをアプリにインポートする必要がある順序がわかる名前が付けられています。 </p>
<p>緊急時対応アプリのマスター サンプル データを含む次のエンティティにデータをインポートする必要があります。
<ul>
<li>システム</li>
<li>リージョン</li>
<li>Facilities</li>
<li>場所</li>
<li>Departments</li>
</ul>
<p>サンプル データではなく自分の組織のデータをインポートしたい場合は、これらの Excel ファイル内のサンプル データを、自分の組織のデータに置き換えてから、アプリにデータをインポートできます。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらの各エンティティおよびエンティティ内の各フィールドについて詳しくは、「<a href="#manually-configure-and-manage-master-data-for-your-organization">組織のマスター データを手動で構成して管理する</a>」をご覧ください。</p></td>
</tr>
<tr>
<td><strong>Data Template File for Master Data</strong> フォルダー</td>
<td><p>このフォルダーには、実際の組織のデータを設定してアプリにインポートするために使用できる、マスター エンティティの "空の" データ ファイル (.xlsx) が格納されています。</p>
<p>これらのファイルには、データをアプリにインポートする必要がある順序がわかる名前が付けられています。 <strong>Sample Data</strong> フォルダーについて前述したエンティティの一覧と同じです。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらの各エンティティおよびエンティティ内の各フィールドについて詳しくは、「<a href="#manually-configure-and-manage-master-data-for-your-organization">組織のマスター データを手動で構成して管理する</a>」をご覧ください。</p>
</td>
</tr>
</table>

#### <a name="step-41-how-to-load-data-from-data-files"></a>手順 4.1: データ ファイルからデータを読み込む方法

データ ファイルの 1 つからエンティティにサンプル データを読み込むには:

1.  管理アプリの左側のナビゲーション ペインで、データを読み込むエンティティを選択します。 たとえば、領域ピッカーで **Location** を選択してから、**Systems** を選択します。

2.  **[Excel からインポート]** を選択し、**Sample Data** フォルダーから **01 - Load Systems.xlsx** ファイルを選択します。

    > [!div class="mx-imgBorder"] 
    > ![Excel からインポート](media/conf-import-from-excel.png "Excel からインポート")

3.  インポート ウィザードの手順に従って、データをインポートします。

4.  サンプル データがインポートされると、エンティティにインポートされたレコードが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![エンティティ レコード](media/conf-entity-record.png "インポート後のエンティティのレコード")

他のエンティティについて上記の手順を繰り返します。

または、マスター データを手動で入力する場合は、「[組織のマスター データを手動で構成して管理する](#manually-configure-and-manage-master-data-for-your-organization)」をご覧ください。

#### <a name="step-42-import-mandatory-configuration-data"></a>手順 4.2: 必須の構成データをインポートする

次の手順に進む前に、管理アプリで次のエンティティに構成データをインポートする**必要があります**。

| 領域名 | エンティティ名| ファイル名
|-|-|-
| 場所 | Acuities | 00 - Acuities Import.xlsx
| 管理 | Apps Config | 00 - App Config Import.xlsx
| 管理 | アプリケーション | 00 - App Import.xlsx
| Staffing | Request Roles | 00 - Request Roles Import.xlsx
| 場所 | Supplies | 00 - Supplies Import.xlsx

他のエンティティのデータは、後で[手動](#manually-configure-and-manage-master-data-for-your-organization)で、または前に説明したサンプル データ ファイルを使用して、追加することができます。

### <a name="step-5-update-the-mobile-app-branding"></a>手順 5:モバイル アプリのブランドを更新する

モバイル アプリのアイコンや配色を、組織のブランドに合わせて変更することができます。

これを行うには、前の手順で説明したように、デプロイ パッケージの **Data Files** フォルダーにある Excel ファイルからアプリとアプリ構成のデータをインポートして、**Administration** 領域の **App** エンティティと **App Config** エンティティを使用します。

> [!div class="mx-imgBorder"] 
> ![Apps と App Config エンティティ](media/conf-app-app-config-entities.png "Apps エンティティと App Config エンティティ")

1.  抽出したデプロイ パッケージのそれぞれ **App Import.xlsx** ファイルと **App Config Import.xlsx** ファイルから、**Apps** エンティティと **App Config** エンティティの構成データをインポートしたことを確認します。

1.  次に、インポートした **Apps** レコードに設定できるように、キャンバス アプリのアプリ ID をコピーします。 [Power Apps](https://make.powerapps.com) にサインインします。

1.  右上隅で環境を選択します。

1.  左側のペインで **Apps** を選択し、キャンバス アプリの省略記号 [...] を選択してから、 **[詳細]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![Apps の詳細](media/conf-environments-apps-details.png "アプリの詳細")

1.  そのアプリの **[詳細]**  ペインの下部に、アプリ ID が表示されます。 アプリ ID とその名前をメモ帳ファイルにコピーします。

    > [!div class="mx-imgBorder"] 
    > ![アプリ ID の詳細](media/conf-details-app-id.png "アプリ ID の詳細")

1.  各キャンバス アプリについて、手順 3 と 4 を繰り返します。

1.  Admin App を開き、管理アプリの左側のナビゲーション ペインの領域ピッカーで **Administration** を選択して、**Apps** を選択します。 これにより、**App Import.xlsx** ファイルからインポートしたすべてのキャンバス アプリ レコードが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![管理アプリ](media/conf-admin-app-records.png "管理アプリ")

1.  いずれかのアプリ レコードを選択して開きます。 [Power App ID] フィールドが空白になっていることに注意してください。

    > [!div class="mx-imgBorder"] 
    > ![[Power App ID] フィールド](media/conf-powerapp-id-field.png "[Power App ID] フィールド")

1.  前の手順 2-6 でメモ帳にコピーしたアプリ ID を、 **[Power App ID]** フィールドにコピーします。 アプリ アイコンをダブルクリックして別の画像を指定することで、アプリ アイコンを更新することもできます。 レコードを保存します。

1.  **Apps** の下にある各キャンバス アプリ レコードに対して手順 9 を繰り返し、**Power App ID** の値を追加します。

1.  左側のペインで、**App Config** を選択します。

1.  **Emergency Response App** レコードを選択して、編集用に開きます。

    1.  アイコンをダブルクリックし、アプリ アイコンとして新しい画像を指定します。

    2.  アプリの名前と色を更新します。

    3.  **[Device Sharing Enabled]\(デバイスの共有を有効にする\)** フィールドで **[はい]** または **[いいえ]** を選択して、モバイル アプリで **[サインアウト]** オプションを使用できるようにするかどうかを指定します。 **[はい]** を選択すると、 **[サインアウト]** オプションが使用できるようになります。

    > [!div class="mx-imgBorder"] 
    > ![[Device Sharing Enabled]\(デバイスの共有を有効にする\) フィールド](media/conf-device-sharing-enabled-field.png "[Device Sharing Enabled]\(デバイスの共有を有効にする\) フィールド")

1.  右下隅にある **[保存]** を選択して、変更を保存します。

### <a name="step-6-bypass-consent-for-mobile-apps"></a>手順 6:モバイル アプリの同意をバイパスする

この手順を完了するには、テナント管理者である必要があります。 また、この手順を実行する前に、各モバイル アプリ (キャンバス アプリ) のアプリ ID を確認しておく必要があります。

アプリのアプリ ID を確認するには、管理アプリの左側のナビゲーション ペインの領域ピッカーで **Administration** を選択して、**Apps** を選択します。 これにより、すべてのモバイル アプリ (キャンバス アプリ) が表示されます。 モバイル アプリを選択して、そのアプリ ID を表示します。 各アプリのアプリ ID をメモ帳ファイルにコピーします。

> [!div class="mx-imgBorder"] 
> ![アプリ ID を調べる](media/conf-admin-get-app-id.png "アプリ ID を調べる")

続けて次の作業を行います。

1.  メモ帳を開き、次の PowerShell スクリプトをコピーします。

    ```powershell
    # MUST BE A TENANT ADMIN TO RUN THIS
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber
    Import-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Import-Module -Name Microsoft.PowerApps.PowerShell
    
    # This call opens prompt to collect credentials 
    # (Azure Active Directory account and password) 
    # used by the commands
    Add-PowerAppsAccount
    
    # Change the App ID for each new app (APPGUIDHERE)
    Set-AdminPowerAppApisToBypassConsent -AppName APPGUIDHERE
    ```

2.  各行の `APPGUIDHERE` の値を、キャンバス アプリの実際のアプリ ID に置き換えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、作成した .ps ファイルを実行します。

5.  各キャンバス アプリについて、手順 2 から 4 を繰り返します。

### <a name="step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry"></a>手順 7:テレメトリ用に Azure Application Insights キーをモバイル アプリに追加する

Azure Application Insights を使用して、モバイル アプリ (キャンバス アプリ) の詳細なテレメトリを収集し、アプリの使用状況に関する分析情報を取得できます。 これについて詳しくは、「[Azure Application Insights を使用したアプリのログ テレメトリ](https://powerapps.microsoft.com/blog/log-telemetry-for-your-apps-using-azure-application-insights/)」をご覧ください

### <a name="step-8-share-canvas-apps-with-users-in-your-organization"></a>手順 8:組織内のユーザーとキャンバス アプリを共有する

現場のユーザーが自分のモバイル デバイスのキャンバス アプリでデータを使用するには、アプリがユーザーと共有されている必要があります。 Azure AD グループを使用すると、ユーザーのグループと簡単にアプリを共有できます。

1.  [Power Apps](https://make.powerapps.com) にサインインします

2.  左側のナビゲーション ペインで **[アプリ]** を選択して、すべてのアプリの一覧を表示します。

3.  モバイル アプリ (キャンバス アプリ) を選択し、バナーで **[共有]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![キャンバス アプリを共有する](media/conf-share-canvas-apps.png "キャンバス アプリを共有する")

4.  このアプリを共有する Azure AD グループまたはユーザーを指定します。 アプリは Common Data Service のデータに接続するので、エンティティに対するアクセス許可を付与する必要もあります。 共有パネルでは、エンティティに対するセキュリティの管理を求められます。 このアプリで使用されるエンティティに **[COVID 19 End User]\(COVID 19 エンド ユーザー\)** および **[Common Data Service ユーザー]** セキュリティ ロールを割り当てて、 **[共有]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![Azure AD のグループまたはユーザーとアプリを共有する](media/conf-share-app-groups-users.png "Azure AD のグループまたはユーザーとアプリを共有する")

5.  各モバイル アプリについて、手順 3 と 4 を繰り返します。

アプリの共有に関する詳細情報: [キャンバス アプリを共有する](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)

### <a name="step-9-set-your-mobile-app-as-hero-and-featured-app"></a>手順 9:モバイル アプリをヒーロー アプリおよびおすすめアプリとして設定する

この手順では、**Power Apps** モバイル アプリ内のヒーロー アプリおよびおすすめアプリとして、モバイル アプリを設定します。 この手順を完了するには、テナント管理者である必要があります。

この手順を実行する前に、ヒーロー アプリおよびおすすめアプリとして設定する各モバイル アプリ (キャンバス アプリ) のアプリ ID を、確認しておく必要があります。 キャンバス アプリのアプリ ID を取得する方法については、次のセクションを参照してください: [手順 6: モバイル アプリの同意をバイパスする](#step-6-bypass-consent-for-mobile-apps)

続けて次の作業を行います。

1.  メモ帳を開き、次の PowerShell スクリプトをコピーします。


    ```powershell
    # MUST BE A TENANT ADMIN TO RUN THIS
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber
    Import-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Import-Module -Name Microsoft.PowerApps.PowerShell

    # This call opens prompt to collect credentials 
    # (Azure Active Directory account and password) 
    # used by the commands
    Add-PowerAppsAccount

    # Use the "Emergency Response App" App ID
    # To clear a featured app use Clear-AdminPowerAppAsFeatured

    #Change the App ID for each new app (APPGUIDHERE)
    Set-AdminPowerAppAsFeatured -AppName APPGUIDHERE

    # To clear a hero app use Clear-AdminPowerAppAsHero
    # Change the App ID for each new app (APPGUIDHERE)
    Set-AdminPowerAppAsHero -AppName APPGUIDHERE
    ```

2.  各行の `APPGUIDHERE` の値を、それぞれおすすめおよびヒーローとして設定するアプリの実際のアプリ ID に置き換えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、作成した .ps ファイルを実行します。

### <a name="step-10-share-model-driven-app-with-admins-in-your-organization"></a>手順 10: 組織内の管理者とモデル駆動型アプリを共有する

管理者ユーザーが管理アプリ (モデル駆動型アプリ) を使用できるようにするには、アプリを管理者ユーザーと共有する必要があります。 Azure AD グループを使用すると、管理者ユーザーのグループと簡単にアプリを共有できます。

1. [Power Apps](https://make.powerapps.com) にサインインします。

2. 左側のナビゲーション ペインで [アプリ] を選択して、すべてのアプリの一覧を表示します。

3. モデル駆動型アプリ (**Admin App – Emergency Response App**) を選択し、バナーで **[共有]** を選択します。

4. このアプリを共有する Azure AD グループまたは管理者ユーザーを指定し、**Emergency Response Admin** セキュリティ ロールを割り当てて、 **[共有]** を選択します。


## <a name="manually-configure-and-manage-master-data-for-your-organization"></a>組織のマスター データを手動で構成して管理する

管理者は、[Power Apps](https://make.powerapps.com) のモデル駆動型アプリを使用して、組織のマスター データを作成および管理できます。 緊急時対応アプリが動作するためには、このデータが必要です。

> [!NOTE]
> また、デプロイ パッケージで使用可能なデータ ファイルに組織のデータをインポートし、これらのエンティティにインポートすることもできます。 詳細情報: [手順 4:組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization)

次の順序でこれらのエンティティにマスター データを追加する必要があります。

1. [Systems](#systems-data)

1. [リージョン](#regions-data)

1. [Facilities](#facilities-data)

1. [場所](#locations-data)

1. [Departments](#departments-data)

マスター データは、管理アプリの左側のナビゲーションにある **Locations** 領域から管理します。

> [!div class="mx-imgBorder"]
> ![Locations 領域](media/locations-area.png)

**[階層]** 領域の下のエンティティは、データを設定する必要がある順序で一覧表示されます。

### <a name="systems-data"></a>Systems のデータ

**Systems** エンティティを使用すると、病院システムのエントリを作成して管理できます。 これにより、同じ組織内で複数の病院システムを管理できます。

レコードを作成するには:

1. 左側のペインで **Systems** を選択し、 **[+ 新規]** を選択します。  
    > [!div class="mx-imgBorder"]
    > ![Systems で [+ 新規] を選択する](media/select-systems-new.png)

2. **[New System]\(新しい System\)** ページで、適切な値を指定します。  
   > [!div class="mx-imgBorder"]
   > ![新しいシステムの詳細を入力する](media/enter-details-new-system.png)

   | **フィールド**            | **説明**                                    |
   |----------------------|----------------------------------------------------|
   | システム名          | 病院の名前を入力します。                     |
   | 説明          | 説明 (省略可能) を入力します。                      |
   | 有効期限の開始日 | この病院システムの開始日時を入力します。 |
   | 有効期限の終了日   | この病院システムの終了日時を入力します。   |

3. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Systems** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="regions-data"></a>Regions のデータ

**Regions** エンティティを使用すると、病院システムの地理的リージョンを管理できます。

レコードを作成するには:

1. 左側のペインで **Regions** を選択し、 **[+ 新規]** を選択します。

2. **[New Region]\(新しい Region\)** ページで、適切な値を指定します。  

    > [!div class="mx-imgBorder"]
    > ![新しいリージョンの詳細を入力する](media/enter-details-new-region.png)

    | **フィールド**            | **説明**                                                                                          |
    |----------------------|----------------------------------------------------------------------------------------------------------|
    | システム               | 病院システムを選択します。 この一覧は、前に作成した **Systems** データを基にして設定されます。 |
    | リージョン名          | リージョン名を入力します。 たとえば、Seattle などです。                                                              |
    | 説明          | 説明 (省略可能) を入力します。                                                                            |
    | 有効期限の開始日 | この病院システムの開始日時を入力します。                                                       |
    | 有効期限の終了日   | この病院システムの終了日時を入力します。                                                         |

3. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Regions** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="facilities-data"></a>Facilities のデータ

**Facilities** エンティティを使用すると、各リージョン内の病院の場所を管理できます。 たとえば、**Seattle** リージョン内の **Redmond** や **Bellevue** などです。

レコードを作成するには:

1. 左側のペインで **Facilities** を選択し、 **[+ 新規]** を選択します。

2. **[New Facility]\(新しい Facility\)** ページで、適切な値を指定します。 

    > [!div class="mx-imgBorder"] 
    > ![新しい施設の詳細を入力する](media/enter-details-new-facility.png)

    | **フィールド**            | **説明**                                                                                 |
    |----------------------|-------------------------------------------------------------------------------------------------|
    | リージョン               | リージョンを選択します。 この一覧は、前に作成した **Regions** データを基にして設定されます。 |
    | Facility Name        | 施設の名前を入力します。 たとえば、Bellevue などです。                                                  |
    | 説明          | 説明 (省略可能) を入力します。                                                                   |
    | Total Vents          | 施設で使用可能な人工呼吸器の合計数を入力します                                  |
    | 有効期限の開始日 | この施設の開始日時を入力します。                                                     |
    | 有効期限の終了日   | この施設の終了日時を入力します。                                                       |

    必要に応じて、施設の住所を入力します。

3. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Facilities** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="locations-data"></a>Locations のデータ

**Locations** エンティティを使用すると、各病院施設内の特定の場所を管理できます。

> [!NOTE]
> **Locations** レコードを作成する前に、**00 - Acuities Import.xlsx** ファイルを使用して救急度データをインポートしたことを確認します。これについては、以下で説明されています: [手順 4: 組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization)。 これは、**Location** レコードを作成するには、救急情報が必要であるためです。

レコードを作成するには:

1. 左側のペインで **Locations** を選択し、 **[+ 新規]** を選択します。

2. **[New Location]\(新しい Location\)** ページで、適切な値を指定します。  
 
    > [!div class="mx-imgBorder"]
    > ![新しい場所の詳細を入力する](media/enter-details-new-location.png)

    | **フィールド**            | **説明**                                                                                      |
    |----------------------|------------------------------------------------------------------------------------------------------|
    | 場所の名前        | 場所の名前を入力します。                                                                       |
    | Facility             | 施設を選択します。 この一覧は、前に作成した **Facilities** データを基にして設定されます。 |
    | 床                | 施設のフロア情報を入力します。                                                         |
    | ユニット                 | 施設のユニット情報を入力します                                                           |
    | Location Acuity      | この場所に関連付けられている救急度レコードを選択します。                                                                                                     |
    | Total Beds           | 施設内のベッドの合計数を入力します。                                                       |
    | Blocked beds         | 施設内でブロックされているベッドの数を入力します。                                                     |
    | Last Census          | 最後に作成された人数レコードに基づいて設定します。                                             |
    | Occupancy Percentage | 最後の人数と総ベッド数に基づいて自動的に計算されます                                         |
    | 有効期限の開始日 | この病院システムの開始日時を入力します。                                                   |
    | 有効期限の終了日   | この病院システムの終了日時を入力します。                                                     |
    | Location Order       | 場所のドロップダウン リストで場所を並べ替える数値を入力します。                               |
    | Alternate Site Flag  | 内部で使用します                                                                                     |

3. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Locations** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="departments-data"></a>Departments のデータ

**Departments** エンティティを使用すると、病院の部門情報を管理できます。

レコードを作成するには:

1. 左側のペインで **Departments** を選択し、 **[+ 新規]** を選択します。

2. **[New Department]\(新しい Department\)** ページで、適切な値を指定します。    

    > [!div class="mx-imgBorder"]
    > ![新しい部門の詳細を入力する](media/enter-details-new-department.png)

    | **フィールド**            | **説明**                                    |
    |----------------------|----------------------------------------------------|
    | Department Name      | 部門の名前を入力します。                            |
    | 説明          | 説明 (省略可能) を入力します。                      |
    | 有効期限の開始日 | この病院システムの開始日時を入力します。 |
    | 有効期限の終了日   | この病院システムの終了日時を入力します。   |

3. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Departments** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

## <a name="get-insights-using-common-data-service-dashboards"></a>Common Data Service ダッシュボードを使用して分析情報を得る

緊急時対応管理者 (モデル駆動型) アプリでは、次のダッシュボードを既定で利用できます。

- **Bed Management** (ベッド管理)

   各施設の使用可能ベッド数、占有率、総ベッド数が表示されます。

- **Equipment and Supply** (機器と供給)

  各施設で使用中の重要な機器と、利用可能な供給品が表示されます。

- **Staff Management** (スタッフ管理)

  各施設で、要求された、割り当てられた、および利用可能なスタッフの数が表示されます。

- **COVID Patients** (COVID 患者)

  各施設で COVID-19 の検査中および陽性の患者の数が表示されます。

- **Discharges** (退院)

  退院が予定されている患者および実際に退院した患者の数が表示されます。

既定で利用可能なダッシュボードに加えて、独自のダッシュボードを作成することもできます。

### <a name="manage-dashboards"></a>ダッシュボードの管理

ダッシュボードを管理するには:

1. [Power Apps](https://make.powerapps.com) にサインインし、管理アプリを参照します。

2. 左側のナビゲーション ペインの領域ピッカーで **[ダッシュボード]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![ダッシュボードを選択する](media/select-dashboards.png)

3. 左側のナビゲーションでダッシュボード名を選択すると、グラフが表示されます。

    > [!div class="mx-imgBorder"]
    > ![グラフを表示する](media/view-charts.png)

    > [!NOTE]
    > 画面の下部でデータをフィルター処理でき、上のグラフはフィルター処理された値で自動的に更新されます。

4. グラフを全画面表示モードで表示するには、 **[展開]** オプションを選択します。

    > [!div class="mx-imgBorder"]
    > ![展開を選択する](media/select-expand.png)

### <a name="additional-analysis"></a>その他の分析

- **ドリルダウン**: グラフ領域を選択し、エンティティの追加の属性 (フィールド) でさらにドリルダウンできます。

    > [!div class="mx-imgBorder"]
    > ![グラフ領域のドリルダウンを選択する](media/select-chart-area-drill-down.png)

- **[更新]** :ダッシュボードを最新の情報に更新し、更新されたデータを反映することができます。 **[すべて最新の情報に更新]** で特定のダッシュボードのすべてのグラフを更新するか、または **[最新の情報に更新]** で選択したグラフだけを更新することができます。

    > [!div class="mx-imgBorder"]
    > ![ダッシュボードを更新する](media/refresh-dashboards.png)

- **レコードの表示**: **[その他のコマンド]** ( **[...]** ) を選択し、 **[View Records]\(レコードの表示\)** を選択すると、特定のグラフに関連付けられているすべてのレコードが表示されます。

    > [!div class="mx-imgBorder"]
    > ![[その他のコマンド] を選択する](media/select-more-commands.png)

    > [!NOTE] 
    > **[View records]\(レコードの表示\)** を選択すると、グラフとレコードに分割されたエンティティのビューが表示されます。 右側でレコードのフィルターを変更すると、画面左側のグラフに更新が自動的に反映されます。

既存のダッシュボードの編集と、グラフのプロパティの更新について詳しくは、「[既存のダッシュボードの編集](https://docs.microsoft.com/powerapps/maker/model-driven-apps/create-edit-dashboards#edit-an-existing-dashboard)」をご覧ください。

### <a name="create-new-dashboards"></a>ダッシュボードの新規作成

独自のダッシュボードを作成したり、ニーズに合わせてカスタマイズしたりすることもできます。 新しいダッシュボードを作成するには、 **[新規]** を選択し、 **[Dynamics 365 Dashboard]\(Dynamics 365 ダッシュボード\)** を選択します。

> [!div class="mx-imgBorder"]
> ![新しい Dynamics ダッシュボードを選択する](media/select-new-dynamics-dashboard.png)

新しいダッシュボードの作成について詳しくは、「[新しいダッシュボードを作成します](https://docs.microsoft.com/powerapps/maker/model-driven-apps/create-edit-dashboards#create-a-new-dashboard)」をご覧ください。

## <a name="get-insights-using-power-bi-dashboards"></a>Power BI ダッシュボードを使用して分析情報を取得する

ダッシュボードを使用して分析情報の取得や意思決定を行うことができるように、Power BI ダッシュボードを発行し、組織内のユーザーと共有します。

### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに、Power BI Premium 容量または Power BI Pro ライセンスが割り当てられていること。 

- レポートを発行するワークスペースを Power BI で作成します。 Power BI にサインインしてワークスペースを作成します。 詳細情報: [Power BI で新しいワークスペースを作成する](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces)

- Windows アプリ ストア <https://aka.ms/pbidesktop> から Power BI Desktop をインストールします

   > [!NOTE] 
   > 以前に Power BI を Power BI サイトから実行可能ファイルとして直接ダウンロードしてインストールした場合は、それを削除し、アプリ ストアのものを使用します。 アプリ ストアのバージョンは、新しいリリースが利用可能になると自動的に更新されます。

- アプリ ストアから Power BI Desktop をインストールした後、それを実行し、組織内で Power BI アプリを発行するためのアクセス許可を持つアカウントを使用してサインインします。

### <a name="publish-the-power-bi-dashboard"></a>Power BI ダッシュボードを発行する

1. デプロイ パッケージを抽出した場所に移動します。 **Power BI Template** フォルダーに **Emergency Response App.pbit** ファイルがあります。

2. Power BI Desktop で **Emergency Response App.pbit** ファイルを開きます。 このファイルを Power BI Desktop で開くと、データ更新が失敗したことを示す **[最新の情報に更新]** ダイアログ ボックスが表示されます。 これは、Common Data Service 環境への接続の詳細をまだ指定していないためです。

3. Common Data Service 環境への接続を指定するには、 **[データの変換]** を選択します。  
    
    > [!div class="mx-imgBorder"]
    > ![[データの変換] を選択する](media/select-transform-data.png)

4. クエリ エディターで、**CDSBaseURL** パラメーターを Common Data Service 環境の URL に更新します。 **CDSBaseURL** を右クリックし、 **[詳細エディター]** を選択してから、適切な値を指定します。  

    > [!div class="mx-imgBorder"]
    > ![詳細エディターを選択する](media/select-advanced-editor.png)

5. 変更を保存します。 保留中の変更をクエリに適用することを求めるメッセージが表示されます。 **[適用]** を選択します。

6. Common Data Service 環境に接続するための資格情報を入力するように求められます。 **[組織アカウント]**  >  **[サインイン]** を選択して、Common Data Service の資格情報を指定ます。  

    > [!div class="mx-imgBorder"]
    > ![組織アカウントを選択する](media/select-organizational-account.png)

7. **[接続]** を選択して、接続を確立します。

8. 接続に成功すると、Common Data Service の環境情報と共に、ファイルを .pbix ファイルとして保存するように求められます。 名前を指定し、コンピューターに保存します。

9. **[ホーム]** タブの **[閉じて適用]** を選択します。

10. **[最新の情報に更新]** を選択し、Common Data Service 環境からのデータで更新します。 **[発行]** を選択し、Power BI ワークスペースにデータを発行します。  
    
    > [!div class="mx-imgBorder"]
    > ![更新の発行を選択する](media/select-refresh-publish.png)

11. **[Power BI へ発行]** ページで、発行するワークスペースを選択します。

12. ワークスペースでレポートを使用できるようになります。 ここでは、データセットに対するデータの更新を構成します。 ワークスペースでデータセットを選択し、 **[更新のスケジュール設定]** アイコンを選択します。  
    
    > [!div class="mx-imgBorder"]
    > ![更新のスケジュールを設定する](media/schedule-refresh.png)

13. データセットの設定ページで、 **[データ ソースの資格情報]** を展開し、 **[資格情報の編集]** を選択して、データ ソースに接続するための接続の詳細が正しいことを確認します。  

    > [!div class="mx-imgBorder"]
    > ![[資格情報の編集] を選択する](media/select-edit-credentials.png)

14. **[スケジュールされている更新]** を展開し、スケジュールに基づいてデータを更新するために必要な詳細を指定します。

    > [!NOTE] 
    > データを更新できる回数には制限があります。 Power BI では、共有された容量にあるデータセットに対して、1 日の更新を 8 回までに制限しています。 データセットが Premium 容量にある場合は、データセットの設定で、1 日に最大 48 回まで更新をスケジュールできます。 詳細情報: [データを更新する](https://docs.microsoft.com/power-bi/refresh-data#data-refresh)

15. 左側のペインでワークスペース名を選択し、右上隅で **[アプリの作成]** を選択します。  

    > [!div class="mx-imgBorder"]
    > ![[アプリの作成] を選択する](media/select-create-app.png)

16. アプリ発行ページで次のようにします。

    1. **[セットアップ]** タブで、アプリの名前と説明を指定します。

    2. **[ナビゲーション]** タブで、発行するダッシュボードの場所を指定します。

    3. **[アクセス許可]** タブで、このアプリを表示できるユーザーまたはグループを指定します。 **[このアプリを自動的にインストールします]** チェック ボックスをオンにして、このアプリがエンド ユーザーに自動的にインストールされるようにします。 詳細情報: [エンド ユーザーにアプリを自動的にインストールする](https://docs.microsoft.com/power-bi/service-create-distribute-apps#automatically-install-apps-for-end-users)  

        > [!div class="mx-imgBorder"]
        > ![アプリの自動インストールを選択する](media/select-install-apps-automatically.png)

17. **[アプリの発行]** を選択します。 Power BI でのアプリの発行について詳しくは、「[アプリを発行する](https://docs.microsoft.com/power-bi/service-create-distribute-apps#publish-your-app)」をご覧ください。

### <a name="view-the-power-bi-dashboard"></a>Power BI ダッシュボードを表示する

Power BI ダッシュボードにアクセスして表示するには、[Power BI](https://apps.powerbi.com) にサインインします。

> [!div class="mx-imgBorder"]
> ![Power BI ダッシュボードを表示する](media/view-power-dashboard.png)

## <a name="view-and-manage-app-feedback"></a>アプリのフィードバックを表示して管理する

モバイル デバイスでキャンバス アプリを使用している現場のスタッフによって提供されるすべてのフィードバックは、**App Feedback** エンティティに格納されます。管理者は、管理アプリの左側のナビゲーション ペインにある **[Administration]\(管理\)** 領域を使用して、これを表示および管理できます。

アプリのフィードバックを表示して管理するには:

1. [Power Apps](https://make.powerapps.com) にサインインし、管理アプリを参照します。

2. 左側のナビゲーション ペインの領域ピッカーで、 **[Administration]\(管理\)** を選択します。

3. ユーザーによって送信されたアプリのフィードバックの一覧を表示するには、**App Feedback** を選択します。 レコードをクリックして詳細を表示し、レビュー済みとしてマークすることができます。  

    > [!div class="mx-imgBorder"]
    > ![アプリのフィードバックを選択する](media/select-app-feedback.png)

## <a name="issues-and-feedback"></a>問題とフィードバック

- 緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次のステップ

[緊急時対応アプリを使用する](use.md)
