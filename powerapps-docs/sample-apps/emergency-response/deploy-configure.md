---
title: Hospital Emergency Response アプリを展開する | Microsoft Docs
description: 病院の IT 管理者が、自分たちの組織のためのサンプル アプリをデプロイして構成するための詳細な手順を示します。
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
ms.locfileid: "3266813"
---
# <a name="deploy-the-hospital-emergency-response-app"></a>病院緊急時対応アプリをデプロイする

病院緊急時対応アプリでは、ニーズに適応するために多少の設定が必要です。 この記事では、病院の IT 管理者が、自分たちの組織のためのサンプル アプリケーションをデプロイして構成するための詳細な手順を示します。

これらの手順を完了するための推定時間: **35〜40 分**。

## <a name="demo-deploy-the-hospital-emergency-response-app"></a>デモ：Hospital Emergency Response アプリを展開する

病院緊急時対応アプリをデプロイして構成する方法を見てください。

<br/>

> [!VIDEO https://www.youtube.com/embed/-1g44wNiuWI]


## <a name="service-urls-for-us-government-customers"></a>米国政府機関のユーザー向けのサービス URL

Hospital Emergency Response ソリューションは、米国政府機関のユーザーにご利用いただけます。 Power Apps米国政府機関の環境や Power BI にアクセスする URL が市販製品とは異なる設定になっています。

このサポート記事では、市販製品版のサービス URL を使用しています。 米国政府機関のユーザーは、展開の際に以下に記載する米国政府機関の URL を使用してください：


| **商用バージョンの URL**                | **US Government バージョンの URL**  |
|-------------------------------------------|--------------------------------|
| https://make.powerapps.com                | https://make.gov.powerapps.us (GCC)<br/><br/>https://make.high.powerapps.us (GCC High)                |
| https://admin.powerplatform.microsoft.com | https://gcc.admin.powerplatform.microsoft.us (GCC)<br/><br/>https://high.admin.powerplatform.microsoft.us (GCC High) |
| https://app.powerbi.com/                  | <https://app.powerbigov.us> (GCC)<br/><br/>https://app.high.powerbigov.us (GCC High)                  |

Power Apps と Power BI についての、米国政府機関の計画の詳細については次を参照してください：
- [米国政府機関用 Power Apps ](https://docs.microsoft.com/power-platform/admin/powerapps-us-government)
- [米国政府機関用 Power BI ](https://docs.microsoft.com/power-bi/service-govus-overview)


## <a name="deploy-the-hospital-emergency-response-app"></a>病院緊急時対応アプリをデプロイする

組織に病院緊急時対応サンプル アプリを展開するには、次の手順を実行します。

- [ステップ 1: Power Apps にサインアップして、環境を作成する](#step-1-sign-up-for-power-apps-and-create-an-environment)
- [ステップ 2: パッケージの展開後のステップ](#step-2-download-the-deployment-package)
- [ステップ 3: ソリューション ファイルを環境にインポートする](#step-3-import-the-solution-file-into-your-environment)
- [ステップ 4: 組織の構成とマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization)
    - [ステップ 4.1: 必須構成データを読み込む](#step-41-load-mandatory-configuration-data)
    - [ステップ 4.2: マスターデータを読み込む](#step-42-load-master-data)
- [ステップ 5: モバイル アプリのブランド名を更新する](#step-5-update-the-mobile-app-branding)
- [ステップ 6: モバイル アプリの同意をバイパスする](#step-6-bypass-consent-for-mobile-apps)
- [手順 7：Azure Application Insights キーをテレメトリ用モバイルアプリのキーに追加する（オプション）](#step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry-optional)
- [ステップ 8: 組織内のユーザーとキャンバス アプリを共有する](#step-8-share-canvas-apps-with-users-in-your-organization)
- [ステップ 9: モバイルアプリをヒーローおよびおすすめアプリとして設定する](#step-9-set-your-mobile-app-as-hero-and-featured-app)
- [ステップ10: モデル駆動型アプリを組織の管理者と共有する](#step-10-share-model-driven-app-with-admins-in-your-organization)

### <a name="step-1-sign-up-for-power-apps-and-create-an-environment"></a>ステップ 1: Power Apps にサインアップして、環境を作成する

Power Apps をまだ持っていない場合は Power Apps にサインアップして適切なライセンスを購入します。

詳細:

-   [Power Apps 価格設定](https://powerapps.microsoft.com/pricing/)
-   [購入Power Apps](https://docs.microsoft.com/power-platform/admin/signup-for-powerapps-admin)

Power Apps を購入後、Common Data Service データベースで環境を作成します。

1.  [Power Platform 管理センター](https://aka.ms/ppac) にサインインします。

2.  データベースで Common Data Service 環境を作成します。 詳細: [環境の作成と管理](https://docs.microsoft.com/power-platform/admin/create-environment)

    > [!IMPORTANT]
    > データベースの作成中に、データベースのセキュリティ グループを選択すると、セキュリティ グループのメンバーであるユーザーと *のみ* アプリを共有できます。

3.  自分の環境に適切なユーザーを作成します。 詳細情報: [ユーザーを作成し、セキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)

### <a name="step-2-download-the-deployment-package"></a>ステップ 2: デプロイ パッケージのダウンロード

病院緊急時対応アプリのアプリとビジネス ロジックを設定するためのソリューション ファイル、画像、データ ファイルが含まれている <https://aka.ms/emergency-response-solution> から最新のデプロイ パッケージ (.zip) を取得します。

> [!IMPORTANT]
> 展開パッケージ（.zipファイル）を抽出する前に、ファイルのブロックを解除してください。 ブロックの解除方法：
> 1. zip ファイルを右クリックし、**プロパティ** を選択します。
> 2. プロパティ ダイアログボックスで **ブロック解除** を選択し、続いて **適用** を選択し、**OK** をクリックします。

<br/>

展開ファイル（.zip ファイル）のブロックを解除した後は、ファイルをコンピューター上の任意の場所に展開します。 抽出されたフォルダーには、次のフォルダーが含まれます。

| **フォルダー/ファイル**       | **説明**  |
|-----------------------|------------------|
| **アプリ アイコン**         | モバイル アプリ (キャンバス アプリ) のデフォルトのアプリ アイコンが含まれています|
| **データ ファイル**        | ソリューション/アプリが機能するためのマスターとサンプル データ ファイル (.xlsx) が含まれています。 これらのファイルからデータをインポートして、アプリで作業を開始できます。 詳細については、 [ステップ 4: 組織の構成とマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization) を参照してください。 |
| **Power BI テンプレート** | 組織のレポートを構成するために使用する Power BI レポート テンプレート ファイル (.pbit) が含まれています。 詳細：[ Power BI ダッシュボードを公開する](#publish-the-power-bi-dashboard) を参照してください|
| **PowerShell**        | モバイル アプリ（キャンバス アプリ）の構成に使用するスクリプトが含まれています。 |
| **ソリューション ファイル**     | 病院緊急時対応アプリのアプリとメタデータを作成する Common Data Service ソリューション ファイルが含まれています。  |

### <a name="step-3-import-the-solution-file-into-your-environment"></a>ステップ 3: ソリューション ファイルを自分の環境にインポートする

1.  展開ファイル (.zip) を抽出した場所に移動し、そうすると **ソリューション ファイル** フォルダがあります。 **ソリューション ファイル** の管理ソリューション (.zip) ファイルを弊社の環境へインポートします。

2.  [Power Apps](https://make.powerapps.com) にサインインします。

3.  右上隅から自分の環境を選択します。

4.  左ウィンドウで **ソリューション** を選択して、その後 **インポート** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![ソリューションのインポート](media/conf-import-solution.png "ソリューションのインポート")

5.  **インポート ソリューション** ダイアログ ボックスで、ステップ 1 で説明したソリューション ファイルを選択し、ウィザードの手順に従ってソリューションをインポートします。

6.  ソリューションが正常にインポートされたら、インポート ダイアログ ボックスで **閉じる** を選択します。

これで **アプリ** に次の新しいアプリが表示されます。

> [!div class="mx-imgBorder"] 
> ![新しいアプリ](media/conf-apps-new-apps.png "新しいアプリ")

**管理アプリ** を選択して、残りのデプロイ設定を構成できるモデル駆動型アプリを開きます。 詳細: [モデル駆動型アプリとは](https://docs.microsoft.com/powerapps/maker/model-driven-apps/model-driven-app-overview)

> [!div class="mx-imgBorder"] 
> ![管理アプリを開く](media/conf-admin-app-open.png "管理アプリを開く")

管理アプリには、自分の病院システムのデータを追加および管理できるエンティティがいくつかあります。 左側のナビゲーション ウィンドウの下部にあるエリア ピッカーを使用して、別のエリアを選択できます。

### <a name="step-4-load-configuration-and-master-data-for-your-organization"></a>ステップ 4: 組織の構成とマスター データを読み込む

病院緊急時対応アプリに必要なすべてのデータは、抽出したデプロイ フォルダーの **データファイル** フォルダーにあります。

**データファイル** フォルダには、次のファイルとフォルダがあります。

<table style="width:100%">
<tr>
<th>名前</th>
<th>説明</th>
</tr>
<tr>
<td>ルートには、次のファイルが使用可能です。
<ul>
<li>00 - 視覚インポート.xlsx</li>
<li>00 - アプリ構成インポート.xlsx</li>
<li>00 - アプリインポート.xlsx</li>
<li>00 - ロール要求インポート.xlsx</li>
<li>00 - サプライインポート.xlsx</li>
</ul>
</td>
<td>これらは、管理アプリを使用して次のエンティティにインポートする必要がある構成データファイルです。
<ul>
<li>視覚</li>
<li>アプリ構成</li>
<li>アプリ</li>
<li>要求 ロール</li>
<li>サプライのインポート</li>
</ul>
<br/>これらのエンティティにデータをインポートすると、病院緊急時対応アプリが機能するために必要なこれらのエンティティのレコードが作成されます。
<br/>
<br/>
<strong>注意</strong>: 後に説明する <strong>アプリ</strong> そして <strong>アプリ構成</strong> エンティティを除いて、これらのエンティティの構成値を更新しないでください。</td>
</tr>
<tr>
<td><strong>サンプル データ</strong> フォルダー</td>
<td><p>このフォルダーには、アプリケーションにサンプル データを入力するためにインポートできるサンプル データ ファイル (.xlsx) が含まれています。 このファイルには、データをアプリにインポートする順序を示す名前が付けられています。 </p>
<p>Hospital Emergency Response アプリのマスタ ーサンプルデータを含む、次のエンティティのデータをインポートします：
<ul>
<li>システム</li>
<li>領域</li>
<li>Facilities</li>
<li>場所</li>
<li>部署</li>
</ul>
<p>サンプル データの代わりに自分の組織データをインポートする場合は、これらの Excel ファイルのサンプル データを自分の組織データに置き換えてから、アプリにデータをインポートできます。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらエンティティとエンティティのフィールドに関する詳細については、<a href="configure-data-reporting.md#configure-and-manage-master-data-for-your-organization">組織のマスター データを構成、管理する</a> を参照してください。</p></td>
</tr>
<tr>
<td><strong>マスター データのデータ テンプレート ファイル</strong> フォルダ</td>
<td><p>このフォルダーには、組織データを入力してアプリにインポートするために使用できるマスター エンティティ用の "空の" データ ファイル (.xlsx) が含まれています。</p>
<p>このファイルには、データをアプリにインポートする順序を示す名前が付けられています。 これは、前述の <strong>サンプル データ</strong> フォルダのエンティティのリストと同じです。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらエンティティとエンティティのフィールドに関する詳細については、<a href="configure-data-reporting.md#configure-and-manage-master-data-for-your-organization">組織のマスター データを構成、管理する</a> を参照してください。</p>
</td>
</tr>
</table>

#### <a name="step-41-load-mandatory-configuration-data"></a>ステップ 4.1: 必須構成データを読み込む

管理アプリの次のエンティティ下にある構成データのインポートは、次のステップに進む前に **必須** です。

| 領域名 | エンティティ名| ファイル名
|-|-|-
| 場所 | 視覚 | 00 - 視覚インポート.xlsx
| 管理 | アプリ構成 | 00 - アプリ構成インポート.xlsx
| 管理 | アプリ | 00 - アプリインポート.xlsx
| スタッフ | 要求 ロール | 00 - ロール要求インポート.xlsx
| 場所 | サプライ | 00 - サプライインポート.xlsx

##### <a name="how-to-load-data-from-data-files"></a>データ ファイルからデータを読み込む方法は?

データ ファイルの 1 つからエンティティにデータをインポートするには:

1.  管理アプリの左側のナビゲーション ウィンドウで、データをロードするエンティティを選択します。 たとえば、エリアピッカーから **管理** を選択して、その後 **視覚** を選択します。

2.  **Excel からインポート** を選択して、さらに **データ ファイル** フォルダーから **00 - 視覚インポート.xlsx** ファイルを選択します。

    > [!div class="mx-imgBorder"]
    > ![Excel からのインポート](media/conf-import-from-excel.png "Excel からのインポート")

3.  インポート ウィザードへと進んで、データをインポートします。

4.  データがインポートされると、インポートされたレコードがエンティティに表示されます。

    > [!div class="mx-imgBorder"] 
    > ![エンティティ レコード](media/conf-entity-record.png "インポート後にエンティティに記録する")

上記のステップをその他の構成データ エンティティで繰り返します。

または、マスターデータを手動で入力する場合は、[組織のマスターデータを構成、管理する](configure-data-reporting.md#configure-and-manage-master-data-for-your-organization) を参照してください。

#### <a name="step-42-load-master-data"></a>ステップ 4.2: マスターデータを読み込む

前に説明したように：
- **データ ファイル/サンプル データ** フォルダー下でマスター データ エンティティのサンプルデータファイルを使用して、必要なエンティティのサンプル データをインポートできます。 

- 組織のデータを入力するために使用できる **マスター データのデータ ファイル/データ テンプレート ファイル** フォルダー下でマスターエンティティの "空の" データ ファイルを使用して、必要なエンティティでデータをインポートします。

また、後でマスター データを手動で追加することもできます。 詳細情報：[組織のマスター データを構成、管理する](configure-data-reporting.md#configure-and-manage-master-data-for-your-organization)

### <a name="step-5-update-the-mobile-app-branding"></a>ステップ 5: モバイル アプリのブランド名を更新する

モバイル アプリのアプリ アイコン、配色、または表示名を変更して、組織のブランドに合わせることができます。

これは **データ ファイル** フォルダー、または [ステップ 2: デプロイ パッケージのダウンロード](#step-2-download-the-deployment-package) で説明されているデプロイ パッケージ下にある **アプリ アイコン** 下のアイコン ファイルで使用可能な Excel ファイルからアプリやアプリ構成データをインポートすることで、 **管理** 領域の **アプリ** と **アプリ構成** エンティティを使用することでおこないます。

> [!div class="mx-imgBorder"] 
> ![アプリとアプリ構成エンティティ](media/conf-app-app-config-entities.png "アプリとアプリ構成エンティティ")

1.  **アプリのインポート.xlsx** と **アプリ構成インポート.xlsx** ファイルをそれぞれ使用して **アプリ** と **アプリ構成** エンティティの構成データをインポートしたことを確認してください。

1.  次に、キャンバス アプリのアプリ ID をコピーして、インポートした **アプリ** レコードに入力できます。 [Power Apps](https://make.powerapps.com) にサインインします。

1.  右上隅から自分の環境を選択します。

1.  左側のウィンドウで **アプリ** を選択し、次に **詳細** に続いてキャンバス アプリの省略記号 (…) を選択します。

    > [!div class="mx-imgBorder"] 
    > ![アプリの詳細](media/conf-environments-apps-details.png "アプリの詳細")

1.  アプリ ID はアプリの **詳細** ウィンドウの下部に表示されます。 アプリ ID とその名前をメモ帳ファイルにコピーします。

    > [!div class="mx-imgBorder"] 
    > ![詳細のアプリ ID](media/conf-details-app-id.png "詳細のアプリ ID")

1.  キャンバス アプリごとにステップ 4 と 5 を繰り返します。

1.  管理アプリを開き、管理アプリの左側のナビゲーション ウィンドウで、エリアピッカーから **管理** を選択し、次に **アプリ** を選択します。 これにより **アプリ インポート.xlsx** ファイルからインポートしたすべてのキャンバス アプリ レコードが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![管理アプリ](media/conf-admin-app-records.png "管理アプリ")

1.  アプリレコードの1つを選択して開きます。 **Power App ID** フィールドは空白ですのでご留意ください。

    > [!div class="mx-imgBorder"] 
    > ![Power App ID フィールド ](media/conf-powerapp-id-field.png "アプリの更新情報")

1.  アプリの詳細ページ:

    1. (前にコピーした) メモ帳から アプリ ID を **Power App ID** フィールドにコピーします。

    2. アプリ アイコンをダブルクリックして **アプリ アイコン** フォルダからのアプリのアイコン ファイルを選択します。 画像ファイルには直感的に名前が付けられるため、正しいアイコンを簡単に選択できます。 たとえば、 **緊急対応アプリ** の "緊急時対応アプリ.png" ファイルを選択します 組織のブランド化に従ってカスタム画像を選択することもできます。

    3. 必要に応じて、アプリの **説明文** または **表示名** をアップデートします。

    4. 必要に応じて、アプリをアプリ リストに表示すべき場合は **メニューからアプリを隠す** 値を更新します。 **緊急対応アプリ** はコンテナー アプリですので、この値は規定では **いいえ** に設定します。

    5. 必要に応じて、**アプリ表示ランク** 値をアプリ リストのアプリの表示位置を設定するように更新します。

    6. 必要に応じて、このモバイル アプリのデータを **場所** や **施設** レベルで追跡するかどうかを指定するには、**追跡レベル** フィールドの値を選択してください。 詳細については、[モバイル アプリのトラッキン グレベルを管理する](configure-data-reporting.md#manage-tracking-level-for-mobile-apps) を参照してください

    7. **保存**を選択します。

1.  **アプリ** 下の各キャンバス アプリ レコードに対してステップ 8 と 9 を繰り返します。

1.  左側のウィンドウで、**アプリの構成** を選択します。

1.  **緊急対応アプリ** レコードを選択して、編集のために開きます。

    1.  必要に応じて、自分のアプリの色を更新します。

    2.  **デバイス共有を有効にする** フィールドで **はい** または **いいえ** を選択して、モバイルアプリで **サインアウト** オプションが利用できるかどうかを指定します。 **はい** を選ぶと **サインアウト** オプションが使用可能になります。 詳細については、ユーザーガイドの [シフト終了 - サインアウト](use.md#end-shift---sign-out) を参照してください。

    > [!div class="mx-imgBorder"] 
    > ![デバイス共有有効化フィールド](media/conf-device-sharing-enabled-field.png "デバイス共有有効化フィールド")

1.  変更を保存するには、画面の右下隅にある **保存** を選択します。

### <a name="step-6-bypass-consent-for-mobile-apps"></a>ステップ 6: モバイル アプリの同意をバイパスする

このステップを完了するには、テナント管理者である必要があります。 また、このステップを実行する前に、各モバイル アプリ (キャンバス アプリ) のアプリ ID が必要になります。

自分のアプリにアプリ ID を取得するには、管理アプリの左側のナビゲーション ウィンドウで、エリアピッカーから **管理** を選択し、次に **アプリ** を選択します。 これにより、すべてのモバイル アプリ (キャンバス アプリ) が表示されます。 アプリ ID を表示するには、モバイル アプリを選択します 各アプリのアプリ ID をメモ帳ファイルにコピーします。

> [!div class="mx-imgBorder"] 
> ![アプリ ID を取得する](media/conf-admin-get-app-id.png "アプリ ID を取得する")

次に以下のステップを実行します。

1.  メモ帳を開いて、この PowerShell スクリプトをコピーします:

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

2.  キャンバスアプリの実際のアプリ ID を持つ `APPGUIDHERE` 値を置き替えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、今作成した .ps ファイルを実行します。

5.  各キャンバス アプリごとにステップ 2 - 4 を繰り返します。

### <a name="step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry-optional"></a>手順 7：Azure Application Insights キーをテレメトリ用モバイル アプリのキーに追加する（オプション）

オプションで、Azure Application Insights を使用してモバイル アプリ（キャンバス アプリ）の詳細なテレメトリを収集し、アプリの使用状況についての分析情報を得ることができます。 この詳細については、[Application Insights を使用してアプリのテレメトリを分析する](https://docs.microsoft.com/powerapps/maker/canvas-apps/application-insights) を参照してください

### <a name="step-8-share-canvas-apps-with-users-in-your-organization"></a>ステップ 8: 組織内のユーザーとキャンバス アプリを共有する

最前線にいるユーザーがモバイル デバイスのキャンバス アプリを使用してデータを使用するには、アプリが共有されていなければなりません。 Azure AD グループを使用すると、ユーザーのグループとアプリをより簡単に共有できます。

> [!IMPORTANT]
> アプリを共有する予定のユーザーまたはグループが *既に* 自分の環境へのアクセスができていることを確認してください。 通常、[環境を設定する](#step-1-sign-up-for-power-apps-and-create-an-environment) 間には、ユーザーまたはグループはすでに追加されています。 または、こちらのステップに従ってユーザーを環境に追加し、アプリをユーザーと共有する前に適切なアクセスを提供できます: [ユーザーを作成してセキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)。

1.  [Power Apps](https://make.powerapps.com) へのサインイン

2.  左側のナビゲーション ウィンドウで **アプリ** を選択して、すべてのアプリのリストを表示します。

3.  モバイル アプリ (キャンバス アプリ) を選択し、バナーの **共有** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![キャンバス アプリを共有する](media/conf-share-canvas-apps.png "キャンバス アプリを共有する")

4.  このアプリを共有する Azure AD グループまたはユーザーを指定します。 アプリが Common Data Service データに接続するので、エンティティへのアクセス許可も提供する必要もあります。 共有パネルでは、エンティティのセキュリティを管理するように求められます。 **緊急対応ユーザー** と **Common Data Service ユーザー** のセキュリティ ロールをこのアプリを使用してエンティティに割り当て、**共有** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![アプリを Azure AD グループまたはユーザーと共有する](media/conf-share-app-groups-users.png "アプリを Azure AD グループやユーザーと共有する")

5.  各モバイル アプリごとにステップ 3 と 4 を繰り返します。

アプリの共有に関する詳細情報: [キャンバス アプリを共有する](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app)

### <a name="step-9-set-your-mobile-app-as-hero-and-featured-app"></a>ステップ 9: モバイル アプリをヒーローおよびおすすめアプリとして設定する

このステップでは、モバイル アプリを **Power Apps** モバイル アプリ内でヒーローおよびお薦めアプリとして設定できます。 このステップを完了するには、テナント管理者である必要があります。

このステップを実行する前に、ヒーローおよびおすすめアプリとして設定する各モバイル アプリ (キャンバス アプリ) のアプリ ID が必要です。 キャンバス アプリのアプリ ID の取得については、[ステップ 6: モバイル アプリの同意をバイパスする](#step-6-bypass-consent-for-mobile-apps) を参照してください

次に以下を実行します。

1.  メモ帳を開いて、この PowerShell スクリプトをコピーします:


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

2.  スクリプトの `APPGUIDHERE` 値を、それぞれお薦めやヒーローとして設定するアプリの実際のアプリ ID と置き換えます。

3.  ファイルを .ps ファイルとして保存します。

4.  管理者として PowerShell を実行し、今作成した .ps ファイルを実行します。
 

### <a name="step-10-share-model-driven-app-with-admins-in-your-organization"></a>ステップ10: モデル駆動型アプリを組織の管理者と共有する

管理ユーザーが管理アプリ (モデル駆動型アプリ) を使用するには、それを管理者と共有する必要があります。 Azure AD グループを使用すると、管理ユーザーのグループとアプリをより簡単に共有できます。

> [!IMPORTANT]
> アプリを共有する予定のユーザーまたはグループが *既に* 環境へのアクセスができていることを確認してください。 通常、[環境を設定する](#step-1-sign-up-for-power-apps-and-create-an-environment) 間には、ユーザーまたはグループはすでに追加されています。 または、こちらのステップに従ってユーザーを環境に追加し、アプリをユーザーと共有する前に適切なアクセスを提供できます: [ユーザーを作成してセキュリティ ロールを割り当てる](https://docs.microsoft.com/power-platform/admin/create-users-assign-online-security-roles)。

1. [Power Apps](https://make.powerapps.com) にサインインします。

2. 左側のナビゲーション ウィンドウで、アプリ を選択してすべてのアプリのリストを表示します。

3. モデル駆動型アプリ (**管理アプリ – 緊急対応アプリ**) を選択して、バナーで **共有** を選択します。

4. このアプリを共有する Azure AD グループまたは管理ユーザーを指定して、**緊急対応管理者** セキュリティ ロールを割り当て、**共有** を選択します。

## <a name="publish-the-power-bi-dashboard"></a>Power BI ダッシュボードの公開

Power BI ダッシュボードを公開し、組織内のユーザーと共有することで、インサイトと意思決定のためにダッシュボードを使用できます。

Power BI ダッシュボードを公開するには、次のいずれかのオプションを使用てください：AppSource のテンプレートアプリを使用する、*または* デプロイメント パッケージで利用可能な **.pbit** ファイルを使用します。

### <a name="option-a-publish-using-the-template-app-from-appsource-preferred-option"></a>オプション A：AppSource のテンプレートアプリを使用して公開する（推奨オプション）

AppSource のテンプレート アプリの使用に関する詳細情報は、[病院の緊急対応意思決定サポート ダッシュボードに接続する](https://docs.microsoft.com/power-bi/connect-data/service-connect-to-health-emergency-response) を参照してください。

> [!IMPORTANT]
> これは、.pbit ファイルのオプションを使用して公開するよりも、 Power BI のダッシュボードを簡単に公開することができます。 .pbit ファイルのオプションを使用して発行するよりも、このオプションの使用を推奨しています。 

### <a name="option-b-publish-using-the-pbit-file-in-the-deployment-package"></a>オプションB：展開パッケージの .pbit ファイルを使用して公開する

このセクションでは、デプロイメント パッケージで利用可能な **Emergency Response App.pbit** を使用してダッシュボードを公開する方法について説明します。

#### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに割り当てられる Power BI Premium 容量または Power BI Pro ライセンス。 

- レポートを公開する Power BI でワークスペースを作成します。 Power BI にサインインして、ワークスペースを作成します。 詳細: [Power BI で新しいワークスペースを作成する](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces)

- Windows の App Store: <https://aka.ms/pbidesktop> からの Power BI Desktop のインストール

   > [!NOTE] 
   > 既にダウンロード センターのページから実行ファイルとして直接ダウンロードし、 Power BI Desktop をインストールしていた場合は、削除して Microsoft Store のものを使用してください。 Microsoft Store のバージョンは、バージョンは新しいリリースがされると自動的に更新されます。
   >
   > Microsoft Store からインストールできない場合は、[ダウンロード センター ページ](https://www.microsoft.com/download/details.aspx?id=58494) から Microsoft Store 以外の最新バージョンをインストールしてください。

- App Store から Power BI Desktop をインストールし、実行し、組織内で Power BI アプリを公開するための権限を持つアカウントを使用してログインします。

#### <a name="publish-the-dashboard-using-the-pbit-file"></a>.pbit ファイルを使用してダッシュボードを公開する

1. デプロイ パッケージを抽出する場所に移動します。 **Power BI テンプレート** フォルダー下に **緊急時対応アプリ.pbit** ファイルがあります。

2. Power BI Desktop で **緊急時対応アプリ.pbit** ファイルを開きます。 次の値を入力するように求められます。

    - **組織名**: 各レポート ページの左上隅に表示される組織名を入力します。
    - **CDS_base_solution_URL**: Common Data Service 環境インスタンスの URL を入力します。 例: https://*[myenv]*.crm.dynamics.com

    > [!div class="mx-imgBorder"]
    > ![組織名とベースURLを指定する](media/pbi-pub-rep1.png)

    **読み込み** を選択します。

3. Common Data Service 環境に接続するための資格情報を入力するように求められます。 **組織アカウント** > **サインイン** を選択して、自分の Common Data Service 資格情報を指定します。  

    > [!div class="mx-imgBorder"]
    > ![select-organizational-account](media/select-organizational-account.png)

4. サインイン後、**接続** を選択して、Common Data Service のデータに接続します。

5. 接続に成功すると、データが Power BI レポートに表示されます。 保留中の変更をクエリに適用するように求められ、**変更を適用** を選択します。

6. **公開** を選択してデータを自分の Power BI ワークスペースに公開します。 変更を保存するように求められますので **保存** を選択します。

    > [!div class="mx-imgBorder"]
    > ![select-refresh-publish](media/select-refresh-publish.png)

7. ファイルを Common Data Service 環境情報とともに、 .pbix ファイルとして保存するように求められます。 名前を入力して、コンピューターに保存します。

8. .pbix ファイルを保存すると、レポートを公開するように求められます。 **Power BI** へ公開ページで、公開するワークスペースを選択して **選択する** をクリックします。

12. レポートがワークスペースで使用可能になります。 次に、データセットのデータ更新設定を構成します。 ワークスペースでデータセットを選択し **更新のスケジュール** アイコンを選択します。  
    
    > [!div class="mx-imgBorder"]
    > ![schedule-refresh](media/schedule-refresh.png)

13. データ更新設定を初めて設定しようとすると、**設定** ページに認証情報が無効であることを示すメッセージが表示されます。 **データ ソース資格情報** から **資格情報を編集する** を選択して、自分の資格情報を指定します。  

    > [!div class="mx-imgBorder"]
    > ![select-edit-credentials](media/select-edit-credentials.png)

14. 次の画面で次の操作を行います。
    - **認証方法** を **OAuth2** として選択します。
    - **このデータ ソースのプライバシー レベルの設定** を **組織的** として設定します。
    - **サインイン**を選択します。

    資格情報を指定してサインインするように求められます。 サインインに成功すると **設定** ページに戻ります。

15. **設定** ページで **スケジュールされた更新** を展開して、スケジュールに基づいてデータを更新するために必要な詳細を指定します。 **適用**を選択します。

    > [!div class="mx-imgBorder"]
    > ![スケジュールされた更新](media/refresh-schedule.png)

    > [!NOTE] 
    > データを更新できる回数には制限があります。 Power BI は共有容量のデータセットを 1 日 8 回の更新に制限します。 データセットが Premium 容量にある場合、データセット設定で 1 日あたり最大 48 回の更新をスケジュールできます。 詳細: [データを差真の状態に更新](https://docs.microsoft.com/power-bi/refresh-data#data-refresh)

16. 左側のウィンドウでワークスペース名を選択し、次に右上隅にある **アプリを作成** を選択します。  

    > [!div class="mx-imgBorder"]
    > ![select-create-app](media/select-create-app.png)

17. アプリ公開ページで次のことをおこないます。

    1. **セットアップ** タブで、アプリの名前と説明を指定します。

    2. **ナビゲーション** タブで、ダッシュボードを公開する場所を指定します。

    3. **許可** タブで、このアプリを表示できるユーザーまたはグループを指定します。 エンドユーザー向けにこのアプリを自動的にインストールするために **このアプリを自動的にインストール** チェックボックスをオンにします。 詳細: [エンドユーザー向けのアプリを自動的にインストールする](https://docs.microsoft.com/power-bi/service-create-distribute-apps#automatically-install-apps-for-end-users)  

        > [!div class="mx-imgBorder"]
        > ![select-install-apps-automatically](media/select-install-apps-automatically.png)

18. **アプリの公開** を選択します。 Power BI でのアプリの公開についての詳細は [アプリの公開](https://docs.microsoft.com/power-bi/service-create-distribute-apps#publish-your-app) を参照してください。

### <a name="after-publishing-the-dashboard"></a>ダッシュボードの公開後

公開された Power BI ダッシュボードを表示するには、[Power BI のダッシュボードを表示する](configure-data-reporting.md#view-power-bi-dashboard) を参照してください

## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次の手順

[病院緊急時対応アプリを使用する](use.md)
