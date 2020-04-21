---
title: 病院の緊急時対応アプリをデプロイする | Microsoft Docs
description: 病院の IT 管理者が組織用のサンプル アプリをデプロイして構成するための詳細な手順について説明します。
author: pankajarora-msft
manager: annbe
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 04/15/2020
ms.author: pankar
ms.reviewer: kvivek
searchScope:
- PowerApps
ms.openlocfilehash: 132276b88fe23e9ea4a69caeff330c10f7d32daf
ms.sourcegitcommit: 371fb08328f88f8bae7335db413d52b5c961c3e4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/17/2020
ms.locfileid: "81544017"
---
# <a name="deploy-the-hospital-emergency-response-app"></a>病院の緊急時対応アプリをデプロイする

病院の緊急時対応アプリは、少量のセットアップでお客様のニーズに合わせることができます。 この記事では、病院の IT 管理者が組織用のアプリケーションをデプロイして構成するための詳細な手順について説明します。

これらの手順の推定所要時間: **35 – 40 分**。

## <a name="demo-deploy-the-hospital-emergency-response-app"></a>デモ:病院の緊急時対応アプリをデプロイする

病院の緊急時対応アプリをデプロイして構成する方法をご覧ください。

<br/>

> [!VIDEO https://www.youtube.com/embed/-1g44wNiuWI]


## <a name="service-urls-for-us-government-customers"></a>米国政府機関のお客様向けのサービス URL

病院の緊急時対応ソリューションは、米国政府機関のお客様もご利用いただけます。 Power Apps US Government 環境および Power BI にアクセスするための、商用バージョンとは異なる URL のセットが用意されています。

この記事全体では、商用バージョンのサービス URL が使用されています。 米国政府機関のお客様は、デプロイ用に、次に記載するそれぞれの米国政府機関用 URL をご使用ください。


| **商用バージョンの URL**                | **米国政府機関バージョンの URL**  |
|-------------------------------------------|--------------------------------|
| https://make.powerapps.com                | https://make.gov.powerapps.us (GCC)<br/><br/>https://make.high.powerapps.us (GCC High)                |
| https://admin.powerplatform.microsoft.com | https://gcc.admin.powerplatform.microsoft.us (GCC)<br/><br/>https://high.admin.powerplatform.microsoft.us (GCC High) |
| https://app.powerbi.com/                  | <https://app.powerbigov.us> (GCC)<br/><br/>https://app.high.powerbigov.us (GCC High)                  |

Power Apps と Power BI の米国政府機関向けプランの詳細については、以下を参照してください。
- [米国政府機関向け Power Apps](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
- [米国政府機関向け Power BI](https://docs.microsoft.com/power-bi/service-govus-overview)


## <a name="deploy-the-hospital-emergency-response-app"></a>病院の緊急時対応アプリをデプロイする

ご自身の組織用に病院の緊急時対応サンプル アプリをデプロイするには、以下の手順を実行します。

- [ステップ 1:Power Apps にサインアップして環境を作成する](#step-1-sign-up-for-power-apps-and-create-an-environment)
- [手順 2:デプロイ パッケージをダウンロードする](#step-2-download-the-deployment-package)
- [ステップ 3:ソリューション ファイルを環境にインポートする](#step-3-import-the-solution-file-into-your-environment)
- [手順 4:組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization)
    - [手順 4.1: 必須の構成データを読み込む](#step-41-load-mandatory-configuration-data)
    - [手順 4.2: マスター データを読み込む](#step-42-load-master-data)
- [手順 5:モバイル アプリのブランドを更新する](#step-5-update-the-mobile-app-branding)
- [手順 6:モバイル アプリの同意をバイパスする](#step-6-bypass-consent-for-mobile-apps)
- [手順 7:テレメトリ用に Azure Application Insights キーをモバイル アプリに追加する (省略可能)](#step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry-optional)
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

    > [!IMPORTANT]
    > データベースの作成中に、データベースのセキュリティ グループを選択した場合は、そのセキュリティ グループのメンバーであるユーザーと*のみ*アプリを共有できます。

3.  環境に適切なユーザーを作成します。 詳細情報: [ユーザーを作成し、セキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)

### <a name="step-2-download-the-deployment-package"></a>手順 2:デプロイ パッケージをダウンロードする

病院の緊急時対応アプリ用のアプリとビジネス ロジックを設定するためのソリューション ファイル、画像、データ ファイルが含まれる、最新のデプロイ パッケージ (.zip) を <https://aka.ms/emergency-response-solution> から取得します。

> [!IMPORTANT]
> デプロイ パッケージ (.zip ファイル) を抽出する前に、ファイルのブロックを解除してください。 ブロックを解除するには:
> 1. .zip ファイルを右クリックし、 **[プロパティ]** を選択します。
> 2. [プロパティ] ダイアログ ボックスで、 **[ブロックの解除]** を選択してから、 **[適用]** 、 **[OK]** の順に選択します。

<br/>

デプロイ ファイル (.zip ファイル) のブロックを解除した後、ご自分のコンピューター上の場所にファイルを抽出します。 抽出されたフォルダーには、次のフォルダーが含まれます。

| **フォルダー/ファイル**       | **説明**  |
|-----------------------|------------------|
| **App Icons**         | モバイル アプリ (キャンバス アプリ) 用の既定のアプリ アイコンが格納されています|
| **Data Files**        | ソリューションおよびアプリが動作するためのマスター ファイルとサンプル データ ファイル (.xlsx) が格納されています。 これらのファイルからデータをインポートして、アプリでの作業を始められます。 詳細情報: [手順 4: 組織の構成データとマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization) |
| **Power BI Template** | 組織向けのレポートを構成するために使用する Power BI レポート テンプレート ファイル (.pbit) が格納されています。 詳細情報:[Power BI ダッシュボードを発行する](#publish-the-power-bi-dashboard)|
| **PowerShell**        | モバイル アプリ (キャンバス アプリ) の構成に使用するスクリプトが格納されています。 |
| **Solution File**     | 病院の緊急時対応アプリに必要なアプリとメタデータを作成する Common Data Service ソリューション ファイルが格納されています。  |

### <a name="step-3-import-the-solution-file-into-your-environment"></a>手順 3:ソリューション ファイルを環境にインポートする

1.  デプロイ ファイル (.zip) を抽出した場所に移動します。**Solution File** フォルダーが見つかります。 **Solution File** フォルダーにあるマネージド ソリューション (.zip) ファイルを環境にインポートします。

2.  [Power Apps](https://make.powerapps.com) にサインインします。

3.  右上隅で環境を選択します。

4.  左側のペインで **[ソリューション]** を選択した後、 **[インポート]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![ソリューションをインポートする](media/conf-import-solution.png "ソリューションをインポートする")

5.  **[ソリューションのインポート]** ダイアログ ボックスで、手順 1 で説明したソリューション ファイルを選択し、ウィザードの手順に従ってソリューションをインポートします。

6.  ソリューションが正常にインポートされたら、インポート ダイアログ ボックスで **[閉じる]** を選択します。

**[アプリ]** に新しいアプリが表示されるようになります。

> [!div class="mx-imgBorder"] 
> ![新しいアプリ](media/conf-apps-new-apps.png "新しいアプリ")

**Admin App** を選択して、残りのデプロイ設定を構成できるモデル駆動型アプリを開きます。 詳細情報: [モデル駆動型アプリとは](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

> [!div class="mx-imgBorder"] 
> ![管理アプリを開く](media/conf-admin-app-open.png "管理アプリを開く")

管理アプリのいくつかのエンティティで、病院システムのデータを追加したり管理したりできます。 左側のナビゲーション ペインの下部にある領域ピッカーを使用して、異なる領域を選択できます。

### <a name="step-4-load-configuration-and-master-data-for-your-organization"></a>手順 4.組織の構成データとマスター データを読み込む

病院の緊急時対応アプリに必要なすべてのデータは、抽出したデプロイ フォルダーの下にある **Data Files** フォルダーから入手できます。

**Data Files** フォルダーには、次のファイルとフォルダーがあります。

<table style="width:100%">
<tr>
<th>名前</th>
<th>Description</th>
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
<li>Apps</li>
<li>Request Roles</li>
<li>Supplies Import</li>
</ul>
<br/>これらのエンティティにデータをインポートすると、病院の緊急時対応アプリが動作するために必要な、これらのエンティティのレコードが作成されます。
<br/>
<br/>
<strong>注意</strong>: 後で説明する <strong>Apps</strong> エンティティと <strong>App Config</strong> エンティティを除き、これらのエンティティの構成値を更新しないでください。</td>
</tr>
<tr>
<td><strong>Sample Data</strong> フォルダー</td>
<td><p>このフォルダーには、インポートすることでアプリケーションにサンプル データを設定できるサンプル データ ファイル (.xlsx) が格納されています。 これらのファイルには、データをアプリにインポートする必要がある順序がわかる名前が付けられています。 </p>
<p>病院の緊急時対応アプリのマスター サンプル データを含む次のエンティティに、データをインポートします。
<ul>
<li>Systems</li>
<li>Regions</li>
<li>Facilities</li>
<li>Locations</li>
<li>部門</li>
</ul>
<p>サンプル データではなく自分の組織のデータをインポートしたい場合は、これらの Excel ファイル内のサンプル データを、自分の組織のデータに置き換えてから、アプリにデータをインポートできます。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらの各エンティティおよびエンティティ内の各フィールドについて詳しくは、「<a href="configure-data-reporting.md#configure-and-manage-master-data-for-your-organization">組織のマスター データを構成して管理する</a>」をご覧ください</p></td>
</tr>
<tr>
<td><strong>Data Template File for Master Data</strong> フォルダー</td>
<td><p>このフォルダーには、実際の組織のデータを設定してアプリにインポートするために使用できる、マスター エンティティの "空の" データ ファイル (.xlsx) が格納されています。</p>
<p>これらのファイルには、データをアプリにインポートする必要がある順序がわかる名前が付けられています。 <strong>Sample Data</strong> フォルダーについて前述したエンティティの一覧と同じです。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらの各エンティティおよびエンティティ内の各フィールドについて詳しくは、「<a href="configure-data-reporting.md#configure-and-manage-master-data-for-your-organization">組織のマスター データを構成して管理する</a>」をご覧ください</p>
</td>
</tr>
</table>

#### <a name="step-41-load-mandatory-configuration-data"></a>手順 4.1: 必須の構成データを読み込む

次の手順に進む前に、管理アプリで次のエンティティに構成データをインポートする**必要があります**。

| 領域名 | エンティティ名| ファイル名
|-|-|-
| Locations | Acuities | 00 - Acuities Import.xlsx
| Administration | Apps Config | 00 - App Config Import.xlsx
| Administration | Apps | 00 - App Import.xlsx
| Staffing | Request Roles | 00 - Request Roles Import.xlsx
| Locations | Supplies | 00 - Supplies Import.xlsx

##### <a name="how-to-load-data-from-data-files"></a>データ ファイルからデータを読み込む方法

データ ファイルの 1 つからエンティティにデータをインポートするには:

1.  管理アプリの左側のナビゲーション ペインで、データを読み込むエンティティを選択します。 たとえば、領域ピッカーで **Administration** を選択してから、**Acuities** を選択します。

2.  **[Excel からインポート]** を選択し、**Data Files** フォルダーから **00 - Acuities Import.xlsx** ファイルを選択します。

    > [!div class="mx-imgBorder"]
    > ![Excel からインポート](media/conf-import-from-excel.png "Excel からインポート")

3.  インポート ウィザードの手順に従って、データをインポートします。

4.  データがインポートされると、エンティティにインポートされたレコードが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![エンティティ レコード](media/conf-entity-record.png "インポート後のエンティティのレコード")

他の構成データ エンティティについて上記の手順を繰り返します。

または、マスター データを手動で入力する場合は、「[組織のマスター データを構成して管理する](configure-data-reporting.md#configure-and-manage-master-data-for-your-organization)」をご覧ください。

#### <a name="step-42-load-master-data"></a>手順 4.2: マスター データを読み込む

前述のように、次の操作を行うことができます。
- **Data Files/Sample Data** フォルダーにあるマスター データ エンティティのサンプル データ ファイルを使用して、必要なエンティティにサンプル データをインポートできます。 

- **Data Files/Data Template File for Master Data** フォルダーにあるマスター エンティティの "空の" データ ファイルを使用して、組織のデータを設定した後、必要なエンティティにデータをインポートできます。

マスター データは、後で手動で追加することもできます。 詳細情報: [組織のマスター データを構成して管理する](configure-data-reporting.md#configure-and-manage-master-data-for-your-organization)

### <a name="step-5-update-the-mobile-app-branding"></a>手順 5.モバイル アプリのブランドを更新する

モバイル アプリのアプリ アイコン、配色、または表示名を組織のブランドに合わせて変更することができます。

**Administration** 領域の **App** エンティティと **App Config** エンティティを使用してこの操作を行うには、デプロイ パッケージの **Data Files** フォルダーにある Excel ファイルおよび **App Icons** フォルダーにあるアイコン ファイルからアプリとアプリ構成のデータをインポートします (「[手順 2:デプロイ パッケージをダウンロードする](#step-2-download-the-deployment-package)」を参照してください)。

> [!div class="mx-imgBorder"] 
> ![Apps と App Config エンティティ](media/conf-app-app-config-entities.png "Apps エンティティと App Config エンティティ")

1.  **App Import.xlsx** ファイルと **App Config Import.xlsx** ファイルをそれぞれ使用して、**Apps** エンティティと **App Config** エンティティの構成データをインポートしたことを確認します。

1.  次に、インポートした **Apps** レコードに設定できるように、キャンバス アプリのアプリ ID をコピーします。 [Power Apps](https://make.powerapps.com) にサインインします。

1.  右上隅で環境を選択します。

1.  左側のペインで **Apps** を選択し、キャンバス アプリの省略記号 [...] を選択してから、 **[詳細]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![Apps の詳細](media/conf-environments-apps-details.png "アプリの詳細")

1.  そのアプリの **[詳細]**  ペインの下部に、アプリ ID が表示されます。 アプリ ID とその名前をメモ帳ファイルにコピーします。

    > [!div class="mx-imgBorder"] 
    > ![アプリ ID の詳細](media/conf-details-app-id.png "アプリ ID の詳細")

1.  各キャンバス アプリについて、手順 4 と 5 を繰り返します。

1.  Admin App を開き、管理アプリの左側のナビゲーション ペインの領域ピッカーで **Administration** を選択して、**Apps** を選択します。 これにより、**App Import.xlsx** ファイルからインポートしたすべてのキャンバス アプリ レコードが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![管理アプリ](media/conf-admin-app-records.png "管理アプリ")

1.  いずれかのアプリ レコードを選択して開きます。 **[Power App ID]** フィールドが空白になっていることに注意してください。

    > [!div class="mx-imgBorder"] 
    > ![[Power App ID] フィールド](media/conf-powerapp-id-field.png "アプリ情報の更新")

1.  アプリの詳細ページで、次の操作を行います。

    1. 前の手順でメモ帳にコピーしたアプリ ID を **[Power App ID]** フィールドにコピーします。

    2. アプリ アイコンをダブルクリックして、**App Icons** フォルダーからアプリのアイコン ファイルを選択します。 正しいアイコンを簡単に選択できるように、画像ファイルにはわかりやすい名前が付けられています。 たとえば、**Emergency Response App** の場合は、"Emergency Response App.png" ファイルを選択します。 また、組織のブランドに従ってカスタム イメージを選択することもできます。

    3. 必要に応じて、アプリの **[説明]** または **[表示名]** を更新します。

    4. 必要に応じて、 **[Hide App from Menu]\(メニューでアプリを非表示にする\)** の値を更新して、アプリをアプリ一覧に表示するかどうかを設定します。 **Emergency Response App** はコンテナー アプリであるため、この値は既定で **[いいえ]** に設定されています。

    5. 必要に応じて、 **[App Display Rank]\(アプリの表示順位\)** の値を更新して、アプリ一覧内のアプリの表示位置を設定します。

    6. 必要に応じて、 **[Tracking Level]\(追跡レベル\)** フィールドで値を選択し、このモバイル アプリでデータを **[Location]\(場所\)** レベルで追跡するか、または **[Facility]\(施設\)** レベルで追跡するかを指定します。 詳細情報: [モバイル アプリの追跡レベルを管理する](configure-data-reporting.md#manage-tracking-level-for-mobile-apps)

    7. **[保存]** を選択します。

1.  **Apps** にある各キャンバス アプリ レコードについて、手順 8 と 9 を繰り返します。

1.  左側のペインで、**App Config** を選択します。

1.  **Emergency Response App** レコードを選択して、編集用に開きます。

    1.  必要に応じて、アプリの色を更新します。

    2.  **[Device Sharing Enabled]\(デバイスの共有を有効にする\)** フィールドで **[はい]** または **[いいえ]** を選択して、モバイル アプリで **[サインアウト]** オプションを使用できるようにするかどうかを指定します。 **[はい]** を選択すると、 **[サインアウト]** オプションが使用できるようになります。 詳細情報: ユーザー ガイドの「[シフトの終了 - サインアウト](use.md#end-shift---sign-out)」を参照してください。

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

2.  `APPGUIDHERE` の値を、キャンバス アプリの実際のアプリ ID に置き換えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、作成した .ps ファイルを実行します。

5.  各キャンバス アプリについて、手順 2 から 4 を繰り返します。

### <a name="step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry-optional"></a>手順 7:テレメトリ用に Azure Application Insights キーをモバイル アプリに追加する (省略可能)

必要に応じて、Azure Application Insights を使用して、モバイル アプリ (キャンバス アプリ) の詳細なテレメトリを収集し、アプリの使用状況に関する分析情報を取得できます。 これについて詳しくは、「[Application Insights を使用したアプリ テレメトリの分析](https://docs.microsoft.com/powerapps/maker/canvas-apps/application-insights)」をご覧ください

### <a name="step-8-share-canvas-apps-with-users-in-your-organization"></a>手順 8:組織内のユーザーとキャンバス アプリを共有する

現場のユーザーが自分のモバイル デバイスのキャンバス アプリでデータを使用するには、アプリがユーザーと共有されている必要があります。 Azure AD グループを使用すると、ユーザーのグループと簡単にアプリを共有できます。

> [!IMPORTANT]
> アプリを共有するユーザーまたはグループが*既に*環境にアクセスできることを確認します。 通常は、[環境の設定](#step-1-sign-up-for-power-apps-and-create-an-environment)時にユーザーまたはグループを追加します。 または、ここに記載されている手順に従ってユーザーを環境に追加し、アプリを共有する前に適切なアクセスを提供することもできます。[ユーザーを作成し、セキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)

1.  [Power Apps](https://make.powerapps.com) にサインインします

2.  左側のナビゲーション ペインで **[アプリ]** を選択して、すべてのアプリの一覧を表示します。

3.  モバイル アプリ (キャンバス アプリ) を選択し、バナーで **[共有]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![キャンバス アプリを共有する](media/conf-share-canvas-apps.png "キャンバス アプリを共有する")

4.  このアプリを共有する Azure AD グループまたはユーザーを指定します。 アプリは Common Data Service のデータに接続するので、エンティティに対するアクセス許可を付与する必要もあります。 共有パネルでは、エンティティに対するセキュリティの管理を求められます。 このアプリで使用されるエンティティに **[Emergency Response User] (緊急時対応ユーザー)** および **[Common Data Service ユーザー]** のセキュリティ ロールを割り当てて、 **[共有]** を選択します。

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

2.  スクリプト内の `APPGUIDHERE` の値を、それぞれおすすめおよびヒーローとして設定するアプリの実際のアプリ ID に置き換えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、作成した .ps ファイルを実行します。
 

### <a name="step-10-share-model-driven-app-with-admins-in-your-organization"></a>手順 10: 組織内の管理者とモデル駆動型アプリを共有する

管理者ユーザーが管理アプリ (モデル駆動型アプリ) を使用できるようにするには、アプリを管理者ユーザーと共有する必要があります。 Azure AD グループを使用すると、管理者ユーザーのグループと簡単にアプリを共有できます。

> [!IMPORTANT]
> アプリを共有するユーザーまたはグループが*既に*環境にアクセスできることを確認します。 通常は、[環境の設定](#step-1-sign-up-for-power-apps-and-create-an-environment)時にユーザーまたはグループを追加します。 または、ここに記載されている手順に従ってユーザーを環境に追加し、アプリを共有する前に適切なアクセスを提供することもできます。[ユーザーを作成し、セキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)

1. [Power Apps](https://make.powerapps.com) にサインインします。

2. 左側のナビゲーション ペインで [アプリ] を選択して、すべてのアプリの一覧を表示します。

3. モデル駆動型アプリ (**Admin App – Emergency Response App**) を選択し、バナーで **[共有]** を選択します。

4. このアプリを共有する Azure AD グループまたは管理者ユーザーを指定し、**Emergency Response Admin** セキュリティ ロールを割り当てて、 **[共有]** を選択します。

## <a name="publish-the-power-bi-dashboard"></a>Power BI ダッシュボードを発行する

ダッシュボードを使用して分析情報の取得や意思決定を行うことができるように、Power BI ダッシュボードを発行し、組織内のユーザーと共有します。

Power BI ダッシュボードは、次のいずれかのオプションを使用して発行できます: AppSource のテンプレート アプリを使用する。"*または*"、デプロイ パッケージから入手できる **.pbit** ファイルを使用する。

### <a name="option-a-publish-using-the-template-app-from-appsource-preferred-option"></a>オプション A: AppSource のテンプレート アプリを使用して発行する (推奨オプション)

AppSource のテンプレート アプリの使用方法について詳しくは、次を参照してください。[病院の緊急時対応の意思決定支援ダッシュボードに接続する](https://docs.microsoft.com/power-bi/connect-data/service-connect-to-health-emergency-response)

> [!IMPORTANT]
> この方法では、.pbit ファイルのオプションを使用して発行するよりも、簡単に Power BI ダッシュボードを発行することができます。 .pbit ファイルのオプションを使用して発行するのではなく、このオプションを使用することをお勧めします。 

### <a name="option-b-publish-using-the-pbit-file-in-the-deployment-package"></a>オプション B: デプロイ パッケージの .pbit ファイルを使用して発行する

このセクションでは、デプロイ パッケージから入手できる **Emergency Response App.pbit** を使用してダッシュボードを発行する方法について説明します。

#### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに、Power BI Premium 容量または Power BI Pro ライセンスが割り当てられていること。 

- レポートを発行するワークスペースを Power BI で作成します。 Power BI にサインインしてワークスペースを作成します。 詳細情報: [Power BI で新しいワークスペースを作成する](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces)

- Windows アプリ ストア <https://aka.ms/pbidesktop> から Power BI Desktop をインストールします

   > [!NOTE] 
   > 以前に Power BI Desktop を、ダウンロード センターのページから実行可能ファイルとして直接ダウンロードしてインストールした場合は、それを削除し、Microsoft Store のものを使用してください。 Microsoft Store のバージョンは、新しいリリースが利用可能になると自動的に更新されます。
   >
   > Microsoft Store からインストールできない場合は、[ダウンロード センターのページ](https://www.microsoft.com/download/details.aspx?id=58494)から、最新の非 Microsoft Store バージョンをインストールしてください。

- アプリ ストアから Power BI Desktop をインストールした後、それを実行し、組織内で Power BI アプリを発行するためのアクセス許可を持つアカウントを使用してサインインします。

#### <a name="publish-the-dashboard-using-the-pbit-file"></a>.pbit ファイルを使用してダッシュボードを発行する

1. デプロイ パッケージを抽出した場所に移動します。 **Power BI Template** フォルダーに **Emergency Response App.pbit** ファイルがあります。

2. Power BI Desktop で **Emergency Response App.pbit** ファイルを開きます。 次の値を入力するように求められます。

    - **Organization_name**:各レポート ページの左上隅に設定される、ご自分の組織名を入力します。
    - **CDS_base_solution_URL**:ご自分の Common Data Service 環境インスタンスの URL を入力します。 例: 「 https:// *[myenv]* .crm.dynamics.com」

    > [!div class="mx-imgBorder"]
    > ![組織名とベース URL を指定する](media/pbi-pub-rep1.png)

    **[読み込み]** を選択します。

3. Common Data Service 環境に接続するための資格情報を入力するように求められます。 **[組織アカウント]**  >  **[サインイン]** を選択して、Common Data Service の資格情報を指定ます。  

    > [!div class="mx-imgBorder"]
    > ![組織アカウントを選択する](media/select-organizational-account.png)

4. サインインしたら、 **[接続]** を選択して、Common Data Service 内のデータに接続します。

5. 接続が成功すると、Power BI レポートにデータが表示されます。 クエリに対して保留中の変更を適用するように求められます。 **[変更の適用]** を選択します。

6. **[発行]** を選択し、Power BI ワークスペースにデータを発行します。 変更内容を保存するように求められます。 **[保存]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![更新の発行を選択する](media/select-refresh-publish.png)

7. Common Data Service の環境情報と共に、ファイルを .pbix ファイルとして保存するように求められます。 名前を指定し、コンピューターに保存します。

8. .pbix ファイルを保存した後、レポートを発行するように求められます。 **[Power BI へ発行]** ページで、発行するワークスペースを選択してから、 **[選択]** をクリックします。

12. ワークスペースでレポートを使用できるようになります。 次に、データセットに対するデータの更新設定を構成します。 ワークスペースでデータセットを選択し、 **[更新のスケジュール設定]** アイコンを選択します。  
    
    > [!div class="mx-imgBorder"]
    > ![更新のスケジュールを設定する](media/schedule-refresh.png)

13. データ更新設定を初めて設定しようとすると、 **[設定]** ページと共に、資格情報が無効であることを示すメッセージが表示されます。 **[データ ソースの資格情報]** の下で、 **[資格情報の編集]** を選択して、使用する資格情報を指定します。  

    > [!div class="mx-imgBorder"]
    > ![[資格情報の編集] を選択する](media/select-edit-credentials.png)

14. 次の画面で以下の操作を行います。
    - **[認証方法]** として **[OAuth2]** を選択します。
    - **[このデータ ソースのプライバシー レベルの設定]** として **[組織]** を選択します。
    - **[サインイン]** をクリックします。

    資格情報を指定してサインインするように求められます。 サインインに成功すると、 **[設定]** ページに戻ります。

15. **[設定]** ページで、 **[スケジュールされている更新]** を展開し、スケジュールに基づいてデータを更新するために必要な詳細を指定します。 **[適用]** を選びます。

    > [!div class="mx-imgBorder"]
    > ![スケジュールされた更新](media/refresh-schedule.png)

    > [!NOTE] 
    > データを更新できる回数には制限があります。 Power BI では、共有された容量にあるデータセットに対して、1 日の更新を 8 回までに制限しています。 データセットが Premium 容量にある場合は、データセットの設定で、1 日に最大 48 回まで更新をスケジュールできます。 詳細情報: [データを更新する](https://docs.microsoft.com/power-bi/refresh-data#data-refresh)

16. 左側のペインでワークスペース名を選択し、右上隅で **[アプリの作成]** を選択します。  

    > [!div class="mx-imgBorder"]
    > ![[アプリの作成] を選択する](media/select-create-app.png)

17. アプリ発行ページで次のようにします。

    1. **[セットアップ]** タブで、アプリの名前と説明を指定します。

    2. **[ナビゲーション]** タブで、発行するダッシュボードの場所を指定します。

    3. **[アクセス許可]** タブで、このアプリを表示できるユーザーまたはグループを指定します。 **[このアプリを自動的にインストールします]** チェック ボックスをオンにして、このアプリがエンド ユーザーに自動的にインストールされるようにします。 詳細情報: [エンド ユーザーにアプリを自動的にインストールする](https://docs.microsoft.com/power-bi/service-create-distribute-apps#automatically-install-apps-for-end-users)  

        > [!div class="mx-imgBorder"]
        > ![アプリの自動インストールを選択する](media/select-install-apps-automatically.png)

18. **[アプリの発行]** を選択します。 Power BI でのアプリの発行について詳しくは、「[アプリを発行する](https://docs.microsoft.com/power-bi/service-create-distribute-apps#publish-your-app)」をご覧ください。

### <a name="after-publishing-the-dashboard"></a>ダッシュボードを発行した後

発行した Power BI ダッシュボードを表示するには、「[Power BI ダッシュボードを表示する](configure-data-reporting.md#view-power-bi-dashboard)」をご覧ください

## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院の緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院の緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次のステップ

[病院の緊急時対応アプリを使用する](use.md)
