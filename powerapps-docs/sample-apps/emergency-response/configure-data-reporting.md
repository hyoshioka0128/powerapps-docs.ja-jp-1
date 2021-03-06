---
title: Hospital Emergency Response アプリでマスター データを構成し、ダッシュボードを表示する | Microsoft Docs
description: 病院の IT 管理者が、自分たちの組織のためのサンプル アプリをデプロイして構成するための詳細な手順を示します。
author: pankajarora-msft
manager: annbe
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 05/01/2020
ms.author: pankar
ms.reviewer: kvivek
searchScope:
- PowerApps
ms.openlocfilehash: dc58fcf20d79e0557e2f2e1a2999ac669e089c95
ms.sourcegitcommit: b75b29d58adf1547c9fcd3ddd1f14f69fb7f572b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/02/2020
ms.locfileid: "3330254"
---
# <a name="configure-master-data-and-view-dashboards"></a>マスター データの構成とダッシュボードの表示

この記事では、管理アプリ（モデル駆動型アプリ）を使用して、ソリューションのマスター データを追加および管理し、 Power BI ダッシュボードを使用して主要な分析情報や指標を表示する方法をご紹介します。

これらのタスクは通常、業務の管理者が実行します。

## <a name="configure-and-manage-master-data-for-your-organization"></a>組織のマスター データを構成、管理する

管理アプリを使用して、組織のマスター データを作、管理します。 このデータは病院緊急時対応アプリが機能するために必要です。

> [!IMPORTANT]
> IT 管理者が組織内にソリューションを展開し、ビジネス管理者が管理者アプリを使用するための適切な権限を付与していることを確認してください。 詳しくは：[Hospital Emergency Response アプリを展開する](deploy-configure.md) を参照してください

次の順序でこれらのエンティティにマスター データを追加する必要があります。

1. [システム](#systems-data)

1. [地域](#regions-data)

1. [Facilities](#facilities-data)

1. [場所](#locations-data)

1. [部署](#departments-data)

マスター データは、管理アプリの左側のナビゲーションにある **場所** エリアから管理します。

> [!div class="mx-imgBorder"]
> ![locations-area](media/locations-area.png)

**階層** 領域下のエンティティは、データを入力する順序でリストされています。

> [!NOTE]
> アプリの新規インストール中に、精度データが自動的にインポートされます。 詳細: [アプリのインストール](deploy-configure.md#step-3-install-the-app)

### <a name="systems-data"></a>システム データ

**システム** エンティティを使用すると、病院システムのエントリを作成および管理できます。 これにより、同じ組織内の複数の病院システムを管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左ウィンドウで **システム** を選択して **新規** を選択します。  
    > [!div class="mx-imgBorder"]
    > ![select-systems-new](media/select-systems-new.png)

1. **新しいシステム** ページで、次の適切な値を指定します。  
   > [!div class="mx-imgBorder"]
   > ![enter-details-new-system](media/enter-details-new-system.png)

   | **フィールド**            | **説明**                                    |
   |----------------------|----------------------------------------------------|
   | システム名          | 自分の病院の名前を入力します。                     |
   | 説明          | オプションの説明を入力します。                      |
   | 有効開始日データ | この病院システムの開始日時を入力します。 |
   | 有効終了日   | この病院システムの終了日時を入力します。   |

1. **保存して閉じる**を選択します。 新しく作成されたレコードは **システム** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="regions-data"></a>地域データ

**地域** エンティティを使用することで、病院システムの地理的領域を管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左ウィンドウで **地域** を選択して、 **新規** を選択します。

1. **新しい地域** ページで、次の適切な値を指定します。  

    > [!div class="mx-imgBorder"]
    > ![enter-details-new-region](media/enter-details-new-region.png)

    | **フィールド**            | **説明**                                                                                          |
    |----------------------|----------------------------------------------------------------------------------------------------------|
    | System               | 病院システムを選択します。 このリストは、以前に作成した **システム** データに基づいて入力されます。 |
    | 地域名          | 地域名を入力します。 例えば、シアトルです。                                                              |
    | 説明          | オプションの説明を入力します。                                                                            |
    | 有効開始日データ | この地域の開始日時を入力します。                                                       |
    | 有効終了日   | この地域の終了日時を入力します。                                                         |

1. **保存して閉じる**を選択します。 新しく作成されたレコードは **地域** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="facilities-data"></a>設備データ

**設備** エンティティを使用すると、各地域内の病院の場所を管理できます。 例えば、**シアトル** 地域内の **レドモンド** と **ベルビュー** です。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左ウィンドウで **設備** を選択して、 **新規** を選択します。

1. **新しい設備** ページで、次の適切な値を指定します。 

    > [!div class="mx-imgBorder"] 
    > ![enter-details-new-facility](media/enter-details-new-facility.png)

    | **フィールド**            | **説明**                                                                                 |
    |----------------------|-------------------------------------------------------------------------------------------------|
    | 地域               | この施設が関連付けられている地域を選択します。 このリストは、以前に作成した **地域** データに基づいて入力されます。 |
    | 設備名        | 設備名を入力します。 例えば、ベルビューです。                                                  |
    | 人工呼吸器の総数          | 施設で利用可能な人工呼吸器の総数を入力してください。                                  |
    | 説明          | オプションの説明を入力します。                                                                   |
    | 有効開始日データ | この設備の開始日時を入力します。                                                     |
    | 有効終了日   | この設備の終了日時を入力します。                                                       |
    |総ベッド数      | 自動的に算出されます。|
    |占有済み合計      | 自動的に算出されます。|
    |施設の住所      | 施設の番地、市、郡、州、郵便番号、緯度、経度を入力します。|

    必要に応じて、設備の住所を入力します。

1. **保存して閉じる**を選択します。 新しく作成されたレコードは **設備** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="locations-data"></a>場所データ

**場所** エンティティを使用すると、各病院設備内の特定場所を管理できます。

> [!NOTE]
> **場所**記録を作成する前に、精度データがあることを確認します。 これは、視覚情報が **場所** レコードを作成するために必要だからです。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左ウィンドウで **場所** を選択して、 **新規** を選択します。

1. **新しい場所** ページで、次の適切な値を指定します。  
 
    > [!div class="mx-imgBorder"]
    > ![enter-details-new-location](media/enter-details-new-location.png)

    | **フィールド**            | **説明**                                                                                      |
    |----------------------|------------------------------------------------------------------------------------------------------|
    | 場所の名前        | 場所の名前を入力します。                                                                       |
    | 設備             | 設備を選択します。 このリストは、以前に作成した **設備** データに基づいて入力されます。 |
    | 下限                | 設備の下限情報を入力します。                                                         |
    | 出荷単位                 | 設備の単位情報を入力します。                                                           |
    | 占有率 | 最新の国勢調査と総病床数の値をもとに自動的に計算されます。                                         |
    | 視覚      | この場所に関連付けられている視覚レコードを選択します。                                                                                                     |
    | COVID 場所      | この場所を COVID 患者の治療に使用するかどうかを選択します (**はい** または **番号**)。                                                                                                      |
    | 総ベッド数           | 設備で利用可能なベッドの総数を入力します。                                                       |
    | サージ ベッド           | その設備のサージ ベッド数を入力します。 サージ ベッドは、患者を受け入れる必要がある場合に、認可されたベッド数を超えてスタッフを配備できるベッドです。                                                      |
    | ブロックされたベッド         | この設備のブロックされたベッド数を入力します。                                                     |
    | 前回の国勢調査          | 作成されている前回の国勢調査レコードに基づいて入力されます。                                             |
    | 有効開始日データ | この設備の開始日時を入力します。                                                   |
    | 有効終了日   | この場所の終了日時を入力します。                                                     |
    | 場所オーダー       | 場所のドロップダウン リストで場所を並べ替える番号を入力します。                               |
    | 代替サイト フラグ  | 内部使用のみ。                                                                                     |

1. **保存して閉じる**を選択します。 新しく作成されたレコードは **場所** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

既存のロケーション レコードを開き、それぞれのタブを選択することで、次のような場所の関連データを表示できます。**国勢調査**、**COVID トラッキング**、**機器の需要**。 関連付けられたデータは、[モバイル アプリ](use.md) を使用して前線で対応するスタッフが入力します。

> [!div class="mx-imgBorder"]
> ![場所関連レコード](media/location-related-records.png)


### <a name="departments-data"></a>部署データ

**部署** エンティティを使用すると、病院の部門情報を管理できます。

レコードを作成するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左ウィンドウで **部署** を選択して、 **新規** を選択します。

1. **新しい部署** ページで、次の適切な値を指定します。

    > [!div class="mx-imgBorder"]
    > ![enter-details-new-department](media/enter-details-new-department.png)

    | **フィールド**            | **説明**                                    |
    |----------------------|----------------------------------------------------|
    | 部署名      | 部署名を入力します。                            |
    | 説明          | オプションの説明を入力します。                      |
    | 有効開始日データ | この部署の開始日時を入力します。 |
    | 有効終了日   | この部署の終了日時を入力します。   |

1. **保存して閉じる**を選択します。 新しく作成されたレコードは **部署** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

## <a name="manage-tracking-level-for-mobile-apps"></a>モバイル アプリのトラッキン グレベルを管理する

現場の従業員は、モバイルアプリ（キャンバスアプリ）を使用することで、*ロケーション* または *施設* の情報を追跡できます 各モバイル アプリの既定のトラッキング レベルは次のとおりです： 

|App  |既定のトラッキング レベル  |
|--|--|
|COVID トラッキング|場所|
|スタッフ|場所|
|機器|場所|
|ベッドのキャパシティ|設備|
|消耗品|設備|
|スタッフのニーズ|設備|
|退院のトラッキング|設備|

管理者は、モバイル アプリの既定のトラッキング レベルを変更できます。

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

1. 左側のナビゲーションで、**行政** エリアを選択し、続いて **アプリ** を選択します。 

    > [!div class="mx-imgBorder"]
    > ![config-admin-app-records](media/admin-apps.png)

1. キャンバス アプリのいずれかを選択して、レコードを開きます。

1. アプリのレコードで、**追跡レベル** フィールドに適切な値を選択します。

    > [!div class="mx-imgBorder"]
    > ![アプリのトラッキング レベル](media/app-tracking-level.png)

    - もしアプリに**ロケーション** が選択されている場合、モバイル アプリを使用して作成されたレコードには、他のデータとともに場所情報や施設情報が含まれます。 さらに、**ロケーション** がモバイル アプリで利用できるようになり、ユーザーがデータを追跡する場所を選択できるようになります。

    - もしアプリに **施設** が選択されている場合、モバイル アプリを使用して作成されたレコードには、他のデータとともに施設情報のみが含まれます。

    - **追跡レベル** フィールドの値を選択しない場合、前述の *既定*のトラッキング レベルがモバイル アプリに適用されます。

1. 変更を保存するには、画面の右下隅にある **保存** を選択します。

## <a name="view-common-data-service-dashboards"></a>Common Data Service ダッシュボードを表示する

以下のダッシュボードは、規定で病院緊急時対の管理 (モデル駆動型) アプリで使用できます。

- **ベッド管理**

   ベッドの空き状況、占有率、さまざまな設備のベッド総数を表示します。

- **機器とサプライ**

  使用中のクリティカルな機器と、さまざまな施設で利用可能な消耗品を表示します。

- **スタッフ管理**

  さまざまな設備全体で、要求、割り当て、および利用可能なスタッフ メンバーの数を示します。

- **COVID 患者**

  検査結果待ちの患者数を示し、さまざまな施設で COVID-19 陽性が発見されました。

- **退院**

  退院が予想される患者と実際に退院する患者の数を表示します。

規定で使用可能なダッシュボードに加え、自分自身のダッシュボードを作成することもできます。

### <a name="manage-dashboards"></a>ダッシュボードの管理

ダッシュボードを管理するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

2. 左側のナビゲーション ウィンドウで、エリアピッカーから **ダッシュボード** を選択します。

    > [!div class="mx-imgBorder"]
    > ![ダッシュボードの選択](media/select-dashboards.png)

3. 左側のナビゲーションでダッシュボード名を選択して、グラフを表示します。

    > [!div class="mx-imgBorder"]
    > ![ビュー チャート](media/view-charts.png)

    > [!NOTE]
    > 画面の下部でデータをフィルタ―し、上部のグラフはフィルターされた値で自動的に更新されます。

4. **展開する** オプションを選択して、全画面モードでグラフを表示します。

    > [!div class="mx-imgBorder"]
    > ![select-expand](media/select-expand.png)

### <a name="additional-analysis"></a>追加分析

- **ドリルダウン**: エンティティの追加の属性 (フィールド) を使用して、チャートエリアをドリルダウンすることを選択できます。

    > [!div class="mx-imgBorder"]
    > ![select-chart-area-drill-down](media/select-chart-area-drill-down.png)

- **リフレッシュ**: ダッシュボードを更新して、更新されたデータを最新の情報に更新できます。 特定のダッシュボード上で **すべて更新** を選択してすべてのグラフ、または **最新の情報に更新** を使って選択したチャートを最新の状態に更新できます。

    > [!div class="mx-imgBorder"]
    > ![refresh-dashboards](media/refresh-dashboards.png)

- **レコードを表示する**: **その他のコマンド** (**…**) を選択して、その後 **レコードを表示** を選択して、特定のグラフに関連付けられているすべてのレコードを表示します。

    > [!div class="mx-imgBorder"]
    > ![select-more-commands](media/select-more-commands.png)

    > [!NOTE] 
    > **レコードを表示する** を選択する場合、エンティティのビューがグラフとレコードに分割されて表示されます。 右側のレコードのフィルターを変更すると、画面左側のグラフが自動的に更新されます。

既存のダッシュボードの編集とグラフのプロパティの更新の詳細については、[既存のダッシュボードを編集する](https://docs.microsoft.com/powerapps/maker/model-driven-apps/create-edit-dashboards#edit-an-existing-dashboard) をお読みください。

### <a name="create-new-dashboards"></a>新しいダッシュボードの作成

自身のダッシュボードの作成やニーズに合わせてカスタマイズすることもできます。 新しいダッシュボードを作成するには、**新規** を選択して、次に **Dynamics 365 ダッシュボード** を選択します。

> [!div class="mx-imgBorder"]
> ![select-new-dynamics-dashboard](media/select-new-dynamics-dashboard.png)

新しいダッシュボードの作成については、[新しいダッシュボードの作成](https://docs.microsoft.com/powerapps/maker/model-driven-apps/create-edit-dashboards#create-a-new-dashboard) をお読みください。

## <a name="view-power-bi-dashboard"></a>Power BI ダッシュボードの表示

Power BI ダッシュボードを表示して情報分析と意思決定に使用する。

### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに割り当てられる Power BI Premium 容量または Power BI Pro ライセンス。 

- IT 管理者は Power BI レポートを公開し、それに対するアクセス権限を付与する必要があります。 詳細：[ Power BI ダッシュボードを公開する](deploy-configure.md#step-10-publish-the-power-bi-dashboard) を参照してください 

### <a name="view-the-dashboard"></a>ダッシュボードを表示する

[Power BI](https://apps.powerbi.com) にサインインして Power BI ダッシュボードにアクセスして表示します。

> [!div class="mx-imgBorder"]
> ![Power BI ダッシュボードの表示](media/view-powerbi-dashboard.png)

右側のフィルターを使用して、COVID の場所、施設、地域、および病院システムのデータをフィルターできます。

#### <a name="system-at-a-glance-page"></a>システム一覧ページ 

**システム一覧ページ** は、全体ビューを提供する来てのまたは最上位のページです。  

このページには、以下の要約ビューが表示されます。 

- **COVID 患者情報**：COVID 患者の総数、COVID-19 で陽性と判明した患者数、検査中の患者数（PUI）を示します。

- **ベッド管理**: ベッドの可用性、占有率、サージベッドの数、およびベッドの総数を示します。 下のグリッドを使用して、鋭単位で数値を表示することもできます。

- **人員配置情報**：ICU の患者数、割り当てられた看護師、患者と看護師の比率を示します。  

- **患者の退院情報**：長期滞在患者の総数、退院が予想される患者の数、実際の退院数を表示します。

- **設備情報**：人工呼吸器の総数、使用中の工呼吸器の数、使用可能な工呼吸器の数が表示されます。 

- **サプライ品情報**：所持している供給品の数を日別に表示します。

> [!NOTE]
> - 要約された領域のいずれかでタイトルを選択すると、その領域のそれぞれの詳細ページに移動します。 
> - データのフィルターや並べ替え、レポートの PDF や PowerPoint へのエクスポート、スポットライトの追加など、レポートに対して他のアクションを実行することもできます。 Power BI でのレポート機能の詳細については、[ Power BIのレポート](https://docs.microsoft.com/power-bi/consumer/end-user-reports) を参照してください
> - これらのレポートの一部の最新更新または最後に更新された列には、データが最後に更新された日時が表示されます。 これらの列で日付と時刻の値の色を確認することで、鮮度を簡単に特定することもできます。
>    - 黒: データは 20 時間以内に更新されます
>    - 灰色: データは 20〜24 時間前に更新されます
>    - 赤: データは 24 時間以上空けて更新されます 
 
#### <a name="system-view-page"></a>システム ビュー ページ

**システム ビュー** ページには、病院システムに関する以下の情報を含むグラフが表示されます。
- 使用中の人工呼吸器と使用可能な人工呼吸器
- ベッドと救急医療ベッドの可用性と占有率
- 要求されたスタッフの総数、患者数（調査）、患者と看護師の比率
- 一定期間の所持している供給品

> [!div class="mx-imgBorder"]
> ![システム ビュー](media/report-system-view.png)

#### <a name="location-details-page"></a>場所の詳細ページ 

**システムの概要** ページにて、右上の **i** を選択します。 **場所の詳細** ページには、ベッドの総数、使用可能なベッド、療養ベッド、COVID 患者などの場所ごとのデータが表示されます。 

> [!div class="mx-imgBorder"]
> ![場所の詳細](media/report-location-details.png) 

#### <a name="covid-patients-page"></a>COVID 患者のページ 

このページには、各場所の患者、調査中の患者数（PUI）のピークと谷間がわかる経時的な患者の傾向、陽性と判明した患者の数など、COVID患者に関するドリルダウン情報が表示され、院内の患者がどこにいるのかを把握することができます。

> [!div class="mx-imgBorder"]
> ![COVID 患者詳細](media/report-covid-details.png)

#### <a name="bed-management-page"></a>ベッドの管理ページ 

このページでは、利用可能なベッドの総数、利用可能な救急医療ベッド、占有率などの場所ごとのドリルダウン情報が提供されます。

> [!div class="mx-imgBorder"]
> ![ベッド管理](media/report-bed-details.png)

#### <a name="staffing-details-page"></a>要員の詳細ページ  

このページでは、勤務場所別のスタッフの詳細、看護師の配置人数、総患者数、COVID の患者数などを掲載しています。 また、一定期間の看護師と患者の比率および ICU 看護師と患者の比率も表示します。

> [!div class="mx-imgBorder"]
> ![スタッフ詳細](media/report-staff-details.png)

#### <a name="equipment-page"></a>備品ページ 

このページには、場所ごとの機器の詳細、使用中の人工呼吸器の総数、COVID患者の数、使用中のベルト、充電器、フードなどその他の機器が表示されます。

> [!div class="mx-imgBorder"]
> ![機器の詳細ページ](media/report-equipment-details.png)

#### <a name="discharges-page"></a>退院した患者のページ 

このページには、長期入院患者の詳細、期間中の退院障壁、退院実績と退院予想に関する差異の詳細が記載されています。

> [!div class="mx-imgBorder"]
> ![機器の詳細ページ](media/report-discharge-details.png)

#### <a name="supplies-page"></a>救急品のページ 

このページには、場所ごとの供給品に関する詳細が表示されます。 また、供給と施設ごとの手元の日数、一定期間にわたって手元にある供給品についてのチャートも提供します。

> [!div class="mx-imgBorder"]
> ![機器の詳細ページ](media/report-supplies.png)

## <a name="view-and-manage-app-feedback"></a>アプリ フィードバックの表示および管理

最前線のスタッフがモバイル デバイス上でキャンバス アプリを使用して提供するすべてのフィードバックは、**アプリのフィードバック** エンティティに保管され、管理者は管理アプリのナビゲーション ウィンドウの **管理** 領域を使用して表示および管理できます。

アプリ フィードバックを表示および管理するには:

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

2. ナビゲーション ウィンドウで、エリアピッカーから **管理** を選択します。

3. **アプリ フィードバック** を選択して、ユーザーが送信したアプリのフィードバックのリストを表示します。 レコードをクリックして詳細を表示し、レビュー済みかどうかをマークできます。  

    > [!div class="mx-imgBorder"]
    > ![select-app-feedback](media/select-app-feedback.png)

## <a name="view-the-admin-app-in-your-language"></a>使用している言語で管理アプリを表示する

[!include[cc-lang](includes/cc-lang.md)]

### <a name="enable-languages-for-your-environment"></a>使用している環境で言語を有効にする

サポートされている言語のいずれかで管理アプリを表示する前に、使用している環境のシステムの管理者で言語を有効にする必要があります。 システム管理者は、*一度*構成ステップを実行し、管理アプリでサポートされている言語の 1 つから必要な言語を有効にできます。

1. [Power Platform 管理センター](https://aka.ms/ppac) にサイン インします。

2. 左側のウィンドウで**環境**を選び、[Your Environment] > **設定** > **製品** > **言語** を選択します。

    > [!div class="mx-imgBorder"]
    > ![ppac-settings](media/ppac-settings.png)

3. **言語設定**ページで、先に述べたサポートされている言語のいずれかから有効にする言語を選び、右下隅にある**申し込む**を選択します。 たとえば、**フランス語**および**ドイツ語**の言語が有効です。

    > [!div class="mx-imgBorder"]
    > ![ppac-lang-settings](media/ppac-lang-settings.png)

4. **言語の変更の確認**ダイアログ ボックスで、**OK** を選択します。

    > [!IMPORTANT]
    > 選択した各言語の有効化には数分かかることがあります。

### <a name="set-the-language-of-your-choice"></a>選択した言語を設定する

必要な言語がシステム管理者によって有効にされた後、各管理ユーザーは管理アプリの表示を希望する言語を選択できます。

1. IT 管理者から提供された URL を使用して、管理アプリ（モデル駆動型アプリ）にログインします。

2. スクリーンの右上隅にある**設定**ボタンを選び、**個人設定**を選択します。

    > [!div class="mx-imgBorder"]
    > ![personal-settings](media/personal-settings.png)

3. **個人用オプションを設定**ページで、**言語**タブを選び、**ユーザー インターフェース言語**の一覧から選択した言語をクリックします。 リストには、システム管理者によって使用している環境に対して有効化されるすべての言語が表示されます。

    > [!div class="mx-imgBorder"]
    > ![select-lang](media/select-lang.png)

4. ウィンドウ右下の **OK** を選択します。

管理アプリの UI は、選択した言語の表示に切り替わります。

## <a name="extend-mobile-app-labels-experimental"></a>モバイル アプリのラベルを拡張する (試験段階)

Hospital Emergency Response モバイル アプリのラベルをカスタム テキストで拡張できます。 これを行うには、**キャンバス アプリの文字列**ソリューションをインポートする必要があります。 このソリューションでは、**キャンバス アプリ ラベル管理**とういう名のモデル駆動型アプリを追加して、Hospital Emergency Response モバイル アプリ ラベルのカスタマイズに使用できます。 モデル駆動型アプリを使用して、ソリューションでサポートされる新しい言語と対応するモバイル アプリ ラベルのテキストを追加します。 段階的な手順とソリューションのダウンロードについては、[Hospital Emergency Response モバイル アプリ ラベルを拡張する (試験段階)](https://github.com/microsoft/powerapps-tools/tree/master/Apps/EmergencyResponse/Experimental/LabelCustomizations) を参照してください。

## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次の手順

[Hospital Emergency Response モバイル アプリを使用する](use.md)
