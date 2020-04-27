---
title: 病院の緊急時対応アプリでマスター データを構成し、ダッシュボードを表示する | Microsoft Docs
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
ms.openlocfilehash: 5a622a7d945fa78536c3addb75cfa64d327c7c90
ms.sourcegitcommit: 263a12aefa72a3d73e07b2660bf1e89eba532a16
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81448275"
---
# <a name="configure-master-data-and-view-dashboards"></a>マスター データの構成とダッシュボードの表示

この記事では、管理アプリ (モデル駆動型アプリ) を使用してソリューションのマスター データの追加と管理を行い、Power BI ダッシュボードを使用して重要な分析情報とメトリックを表示する方法について説明します。

通常、これらのタスクは、組織内のビジネス管理者が実行します。

## <a name="configure-and-manage-master-data-for-your-organization"></a>組織のマスター データを構成して管理する

管理アプリを使用して、組織のマスター データの作成と管理を行います。 病院の緊急時対応アプリが動作するためには、このデータが必要です。

> [!IMPORTANT]
> - IT 管理者が組織内にソリューションをデプロイし、ビジネス管理者が管理アプリを使用するための適切なアクセス許可を付与していることを確認してください。 詳細情報: [病院の緊急時対応アプリをデプロイする](deploy-configure.md#deploy-the-hospital-emergency-response-app)
> 
> - また、デプロイ パッケージから入手できるデータ ファイルからデータをインポートすることもできます。 詳細情報: [手順 4:組織の構成データとマスター データを読み込む](deploy-configure.md#step-4-load-configuration-and-master-data-for-your-organization)

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

> [!NOTE]
> 救急度データは、ソリューションのデプロイ時にインポートされます。 詳細情報: [手順 4:組織の構成データとマスター データを読み込む](deploy-configure.md#step-4-load-configuration-and-master-data-for-your-organization)

### <a name="systems-data"></a>Systems のデータ

**Systems** エンティティを使用すると、病院システムのエントリを作成して管理できます。 これにより、同じ組織内で複数の病院システムを管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のペインで **Systems** を選択し、 **[+ 新規]** を選択します。  
    > [!div class="mx-imgBorder"]
    > ![Systems で [+ 新規] を選択する](media/select-systems-new.png)

1. **[New System]\(新しい System\)** ページで、適切な値を指定します。  
   > [!div class="mx-imgBorder"]
   > ![新しいシステムの詳細を入力する](media/enter-details-new-system.png)

   | **フィールド**            | **説明**                                    |
   |----------------------|----------------------------------------------------|
   | System Name          | 病院の名前を入力します。                     |
   | Description          | 説明 (省略可能) を入力します。                      |
   | 有効期限の開始日 | この病院システムの開始日時を入力します。 |
   | 有効期限の終了日   | この病院システムの終了日時を入力します。   |

1. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Systems** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="regions-data"></a>Regions のデータ

**Regions** エンティティを使用すると、病院システムの地理的リージョンを管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のペインで **Regions** を選択し、 **[+ 新規]** を選択します。

1. **[New Region]\(新しい Region\)** ページで、適切な値を指定します。  

    > [!div class="mx-imgBorder"]
    > ![新しいリージョンの詳細を入力する](media/enter-details-new-region.png)

    | **フィールド**            | **説明**                                                                                          |
    |----------------------|----------------------------------------------------------------------------------------------------------|
    | System               | 病院システムを選択します。 この一覧は、前に作成した **Systems** データを基にして設定されます。 |
    | Region Name          | リージョン名を入力します。 たとえば、Seattle などです。                                                              |
    | Description          | 説明 (省略可能) を入力します。                                                                            |
    | 有効期限の開始日 | この地域の開始日時を入力します。                                                       |
    | 有効期限の終了日   | この地域の終了日時を入力します。                                                         |

1. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Regions** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="facilities-data"></a>Facilities のデータ

**Facilities** エンティティを使用すると、各リージョン内の病院の場所を管理できます。 たとえば、**Seattle** リージョン内の **Redmond** や **Bellevue** などです。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のペインで **Facilities** を選択し、 **[+ 新規]** を選択します。

1. **[New Facility]\(新しい Facility\)** ページで、適切な値を指定します。 

    > [!div class="mx-imgBorder"] 
    > ![新しい施設の詳細を入力する](media/enter-details-new-facility.png)

    | **フィールド**            | **説明**                                                                                 |
    |----------------------|-------------------------------------------------------------------------------------------------|
    | リージョン               | この施設が関連付けられている地域を選択します。 この一覧は、前に作成した **Regions** データを基にして設定されます。 |
    | Facility Name        | 施設の名前を入力します。 たとえば、Bellevue などです。                                                  |
    | Total Vents          | 施設内で使用可能な人工呼吸器の合計数を入力します。                                  |
    | Description          | 説明 (省略可能) を入力します。                                                                   |
    | 有効期限の開始日 | この施設の開始日時を入力します。                                                     |
    | 有効期限の終了日   | この施設の終了日時を入力します。                                                       |
    |Total Beds      | 自動的に計算されます。|
    |Total Occupied (占有合計)      | 自動的に計算されます。|
    |Facility Address (施設の住所)      | 施設の番地、市区町村、国、都道府県、郵便番号、緯度、経度を入力します。|

    必要に応じて、施設の住所を入力します。

1. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Facilities** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

### <a name="locations-data"></a>Locations のデータ

**Locations** エンティティを使用すると、各病院施設内の特定の場所を管理できます。

> [!NOTE]
> **Locations** レコードを作成する前に、**00 - Acuities Import.xlsx** ファイルを使用して救急度データをインポートしたことを確認します。これについては、以下で説明されています: [手順 4: 組織の構成データとマスター データを読み込む](deploy-configure.md#step-4-load-configuration-and-master-data-for-your-organization)。 これは、**Location** レコードを作成するには、救急情報が必要であるためです。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のペインで **Locations** を選択し、 **[+ 新規]** を選択します。

1. **[New Location]\(新しい Location\)** ページで、適切な値を指定します。  
 
    > [!div class="mx-imgBorder"]
    > ![新しい場所の詳細を入力する](media/enter-details-new-location.png)

    | **フィールド**            | **説明**                                                                                      |
    |----------------------|------------------------------------------------------------------------------------------------------|
    | Location Name        | 場所の名前を入力します。                                                                       |
    | Facility             | 施設を選択します。 この一覧は、前に作成した **Facilities** データを基にして設定されます。 |
    | Floor                | 施設のフロア情報を入力します。                                                         |
    | Unit                 | 施設のユニット情報を入力します。                                                           |
    | Occupancy Percentage | 最後の人数と総ベッド数の値に基づいて自動的に計算されます。                                         |
    | Acuity (救急度)      | この場所に関連付けられている救急度レコードを選択します。                                                                                                     |
    | COVID Location (COVID 用の場所)      | この場所が COVID 患者の治療用に使用されているかどうかを選択します ( **[はい]** または **[いいえ]** )。                                                                                                      |
    | Total Beds           | 施設内のベッドの合計数を入力します。                                                       |
    | Surge Beds (サージ ベッド)           | 施設内のサージ ベッドの台数を入力します。 サージ ベッドとは、患者を収容する必要があれば、認可されたベッド容量を超えて収容できるベッドのことです。                                                      |
    | Blocked beds         | 施設内でブロックされているベッドの数を入力します。                                                     |
    | Last Census          | 最後に作成された人数レコードに基づいて設定します。                                             |
    | 有効期限の開始日 | この場所の開始日時を入力します。                                                   |
    | 有効期限の終了日   | この場所の終了日時を入力します。                                                     |
    | Location Order       | 場所のドロップダウン リストで場所を並べ替える数値を入力します。                               |
    | Alternate Site Flag  | 内部使用です。                                                                                     |

1. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Locations** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

既存の場所のレコードを開き、それぞれのタブを選択することによって、 **[Census]\(人数\)** 、 **[COVID Tracking]\(COVID の追跡\)** 、 **[Equipment Needs]\(機器のニーズ\)** など、場所に関連付けられたデータを表示できます。 関連付けられたデータは、現場スタッフが[モバイル アプリ](use.md)を使用することによって入力されます。

> [!div class="mx-imgBorder"]
> ![場所に関連するレコード](media/location-related-records.png)


### <a name="departments-data"></a>Departments のデータ

**Departments** エンティティを使用すると、病院の部門情報を管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のペインで **Departments** を選択し、 **[+ 新規]** を選択します。

1. **[New Department]\(新しい Department\)** ページで、適切な値を指定します。

    > [!div class="mx-imgBorder"]
    > ![新しい部門の詳細を入力する](media/enter-details-new-department.png)

    | **フィールド**            | **説明**                                    |
    |----------------------|----------------------------------------------------|
    | Department Name      | 部門の名前を入力します。                            |
    | Description          | 説明 (省略可能) を入力します。                      |
    | 有効期限の開始日 | この部署の開始日時を入力します。 |
    | 有効期限の終了日   | この部署の終了日時を入力します。   |

1. **[保存して閉じる]** を選択します。 新しく作成したレコードは、**Departments** の一覧に表示されます。

レコードを編集するには、レコードを選択し、必要に応じて値を更新して、 **[保存して閉じる]** を選択します。

## <a name="manage-tracking-level-for-mobile-apps"></a>モバイル アプリの追跡レベルを管理する

現場の職員は、モバイル アプリ (キャンバス アプリ) を使用して、"*場所*" または "*施設*" 別に情報を追跡できます。 各モバイル アプリの既定の追跡レベルを次に示します。 

|アプリ  |既定の追跡レベル  |
|--|--|
|COVID tracking (COVID の追跡)|場所|
|[Staff]|場所|
|Equipment (機器)|場所|
|Bed capacity (ベッド容量)|Facility|
|Supplies (消耗品)|Facility|
|Staffing needs (スタッフ配置のニーズ)|Facility|
|Discharge tracking (退院の追跡)|Facility|

管理者は、モバイル アプリの既定の追跡レベルを変更できます。

1. IT 管理者から提供された URL を使用して、管理アプリ (モデル駆動型アプリ) にサインインします。

1. 左側のナビゲーションで **[管理]** 領域を選択し、 **[アプリ]** を選択します。 

    > [!div class="mx-imgBorder"]
    > ![管理アプリのレコードを構成する](media/admin-apps.png)

1. キャンバス アプリの 1 つを選択して、レコードを開きます。

1. アプリ レコードで、 **[追跡レベル]** フィールドに適切な値を選択します。

    > [!div class="mx-imgBorder"]
    > ![アプリの追跡レベル](media/app-tracking-level.png)

    - アプリに対して **[場所]** が選択されている場合、モバイル アプリを使用して作成されたレコードには、場所と施設の情報が他のデータと共に含まれます。 さらに、ユーザーがデータを追跡する場所を選択するために、モバイル アプリで **[場所]** ドロップダウンを使用できるようになります。

    - アプリに対して **[施設]** が選択されている場合、モバイル アプリを使用して作成されたレコードには、施設の情報だけが他のデータと共に含まれます。

    - **[追跡レベル]** フィールドに値を選択しなかった場合、前に説明した "*既定の*" 追跡レベルがモバイル アプリに適用されます。

1. 右下隅にある **[保存]** を選択して、変更を保存します。

## <a name="view-common-data-service-dashboards"></a>Common Data Service ダッシュボードを表示する

病院の緊急時対応管理者アプリ (モデル駆動型) では、次のダッシュボードを既定で利用できます。

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

## <a name="view-power-bi-dashboard"></a>Power BI ダッシュボードを表示する

分析情報と意思決定のために Power BI ダッシュボードを表示します。

### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに、Power BI Premium 容量または Power BI Pro ライセンスが割り当てられていること。 

- IT 管理者によって Power BI レポートが発行され、それにアクセスするためのアクセス許可が自分に付与されていること。 詳細情報: [Power BI ダッシュボードを発行する](deploy-configure.md#publish-the-power-bi-dashboard) 

### <a name="view-the-dashboard"></a>ダッシュボードの表示

Power BI ダッシュボードにアクセスして表示するには、[Power BI](https://apps.powerbi.com) にサインインします。

> [!div class="mx-imgBorder"]
> ![Power BI ダッシュボードを表示する](media/view-powerbi-dashboard.png)

右側にあるフィルターを使用して、COVID の場所、施設、地域、および病院システムに対してデータをフィルター処理できます。

#### <a name="system-at-a-glance-page"></a>[System at a glance]\(システムの概要\) ページ 

**[System at a glance]\(システムの概要\) ページ**は、全体像を提供する既定の、またはトップレベルのページです。  

このページには、次の要約ビューが表示されます。 

- **[COVID Patient Information]\(COVID 患者情報\)** :COVID 患者の合計数、COVID-19 陽性だった患者の数、および検査中の患者 (PUI) の数が表示されます。

- **[Bed Management]\(ベッド管理\)** :使用可能なベッドの台数、占有率、サージ ベッドの台数、ベッドの合計台数が表示されます。 下のグリッドを使用して、救急度の単位別の数を確認することもできます。

- **[Staffing Information]\(スタッフ配置情報\)** :ICU の患者数、割り当て済みの看護師数、看護師と患者の比率が表示されます。  

- **[Patient Discharge Information]\(患者の退院情報\)** :長期入院患者数、退院が予定されている患者数、実際に退院した患者数が表示されます。

- **[Equipment Information]\(機器情報\)** :人工呼吸器の総数、使用中の人工呼吸器の数、使用可能な人工呼吸器の数が表示されます。 

- **[Supplies Information]\(消耗品情報\)** :消耗品の手持ち日数が表示されます。

> [!NOTE]
> - 任意の要約領域のタイトルを選択すると、該当する領域の詳細ページが表示されます。 
> - レポートに対して、データのフィルター処理と並べ替え、PDF および PowerPoint へのレポートのエクスポート、Spotlight の追加など、その他のアクションを実行することもできます。 Power BI のレポート機能の詳細については、「[Power BI のレポート](https://docs.microsoft.com/power-bi/consumer/end-user-reports)」をご覧ください
> - これらのレポートの一部では、最新の列または最後に更新された列に、データが最後に更新された日時が表示されます。 それらの列の日時の値の色を確認することでも、鮮度を簡単に識別することができます。
>    - 黒:20 時間以内にデータが更新されました
>    - 灰色:20 - 24 時間前にデータが更新されました
>    - 赤:24 時間より前にデータが更新されました 
 
#### <a name="system-view-page"></a>[System view]\(システム ビュー\) ページ

**[System View]\(システム ビュー\)** ページには、病院システムの次の情報を含むグラフが表示されます。
- 使用中の人工呼吸器の数と使用可能な人工呼吸器の数
- ベッドと救急治療ベッドの使用可能な台数、占有率
- 要請されたスタッフの総数、患者数 (人数)、看護師と患者の比率
- 一定期間の手持ちの消耗品

> [!div class="mx-imgBorder"]
> ![[System View]\(システム ビュー\)](media/report-system-view.png)

#### <a name="location-details-page"></a>[Location details]\(場所の詳細\) ページ 

**[System at a glance]\(システムの概要\)** ページから、右上隅にある **[i]** を選択します。 **[Location details]\(場所の詳細\)** ページには、ベッドの合計台数、使用可能なベッド台数、サージ ベッド台数、COVID 患者数などのデータが場所別に表示されます。 

> [!div class="mx-imgBorder"]
> ![[Location Details]\(場所の詳細\)](media/report-location-details.png) 

#### <a name="covid-patients-page"></a>[COVID patients]\(COVID 患者\) ページ 

このページには、場所ごとの患者数、検査中の患者 (PUI) 数の上下動を示す時間経過に伴う患者の傾向、陽性と判明した患者数など、COVID 患者に関する詳細な情報が表示されます。また、病院内のどこに患者が配置されているかについての概要を得られます。

> [!div class="mx-imgBorder"]
> ![[COVID Patient Details]\(COVID 患者の詳細\)](media/report-covid-details.png)

#### <a name="bed-management-page"></a>[Bed management]\(ベッド管理\) ページ 

このページには、使用可能なベッドの合計台数、使用可能な救急治療ベッド台数、占有率などの詳細な情報が場所別に表示されます。

> [!div class="mx-imgBorder"]
> ![Bed Management](media/report-bed-details.png) (ベッド管理)

#### <a name="staffing-details-page"></a>[Staffing details]\(スタッフ配置の詳細\) ページ  

このページには、場所別のスタッフ、割り当て済みの看護師数、合計患者数、COVID 患者数に関する詳細が表示されます。 また、一定期間にわたる看護師と患者の比率と、ICU の看護師と患者の比率も表示されます。

> [!div class="mx-imgBorder"]
> ![[Staff Details]\(スタッフの詳細\)](media/report-staff-details.png)

#### <a name="equipment-page"></a>[Equipment]\(機器\) ページ 

このページには、場所別の機器、使用中の人工呼吸器の数とその上に重ねられた COVID 患者数や、使用中のベルト、充電器、フードなどのその他の機器に関する詳細が表示されます。

> [!div class="mx-imgBorder"]
> ![[Equipment Details]\(機器の詳細\)](media/report-equipment-details.png)

#### <a name="discharges-page"></a>[Discharges]\(退院\) ページ 

このページには、長期入院患者数、一定期間にわたる退院の障壁、実際の退院数と予想された退院数の差異に関する詳細が表示されます。

> [!div class="mx-imgBorder"]
> ![[Equipment Details]\(機器の詳細\)](media/report-discharge-details.png)

#### <a name="supplies-page"></a>[Supplies]\(消耗品\) ページ 

このページには、消耗品に関する詳細が場所別に表示されます。 また、消耗品および施設別の手持ち日数と、一定期間に使用可能な手持ちの消耗品に関するグラフも表示されます。

> [!div class="mx-imgBorder"]
> ![[Equipment Details]\(機器の詳細\)](media/report-supplies.png)

## <a name="view-and-manage-app-feedback"></a>アプリのフィードバックを表示して管理する

モバイル デバイスでキャンバス アプリを使用している現場のスタッフによって提供されるすべてのフィードバックは、**App Feedback** エンティティに格納されます。管理者は、管理アプリの左側のナビゲーション ペインにある **[Administration]\(管理\)** 領域を使用して、これを表示および管理できます。

アプリのフィードバックを表示して管理するには:

1. [Power Apps](https://make.powerapps.com) にサインインし、管理アプリを参照します。

2. 左側のナビゲーション ペインの領域ピッカーで、 **[Administration]\(管理\)** を選択します。

3. ユーザーによって送信されたアプリのフィードバックの一覧を表示するには、**App Feedback** を選択します。 レコードをクリックして詳細を表示し、レビュー済みとしてマークすることができます。  

    > [!div class="mx-imgBorder"]
    > ![アプリのフィードバックを選択する](media/select-app-feedback.png)

## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院の緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院の緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次のステップ

[病院の緊急時対応モバイル アプリを使用する](use.md)
