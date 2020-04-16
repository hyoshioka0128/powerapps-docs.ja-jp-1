---
title: 病院緊急時対応アプリをデプロイして構成する | Microsoft Docs
description: 病院の IT 管理者が、自分たちの組織のためのサンプル アプリをデプロイして構成するための詳細な手順を示します。
author: pankajarora-msft
manager: annbe
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 04/05/2020
ms.author: pankar
ms.reviewer: kvivek
searchScope:
- GetStarted
- PowerApps
ms.openlocfilehash: 624c465ea812e4fe650dda3750259acf91476bb0
ms.sourcegitcommit: 83b35be5df4864e15be9122647b17465e050284c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2020
ms.locfileid: "3229070"
---
# <a name="deploy-and-configure-the-hospital-emergency-response-app"></a>病院緊急時対応アプリをデプロイして構成する

病院緊急時対応アプリでは、ニーズに適応するために多少の設定が必要です。 この記事では、病院の IT 管理者が、自分たちの組織のためのサンプル アプリケーションをデプロイして構成するための詳細な手順を示します。

これらの手順を完了するための推定時間: **35〜40 分**。

## <a name="demo-deploy-and-configure-the-hospital-emergency-response-app"></a>デモ: 病院緊急時対応アプリをデプロイして構成する

病院緊急時対応アプリをデプロイして構成する方法を見てください。

<br/>

> [!VIDEO https://www.youtube.com/embed/-1g44wNiuWI]


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
- [ステップ 7: Azure Application Insights キーをテレメトリのモバイル アプリに追加する](#step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry)
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

デプロイ プロセスを開始するには、デプロイ ファイル（.zip）を自分のコンピューター上の場所に抽出します。 抽出されたフォルダーには、次のフォルダーが含まれます。

| **フォルダー/ファイル**       | **説明**  |
|-----------------------|------------------|
| **アプリ アイコン**         | モバイル アプリ (キャンバス アプリ) のデフォルトのアプリ アイコンが含まれています|
| **データ ファイル**        | ソリューション/アプリが機能するためのマスターとサンプル データ ファイル (.xlsx) が含まれています。 これらのファイルからデータをインポートして、アプリで作業を開始できます。 詳細については、 [ステップ 4: 組織の構成とマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization) を参照してください。 |
| **Power BI テンプレート** | 組織のレポートを構成するために使用する Power BI レポート テンプレート ファイル (.pbit) が含まれています。 詳細: [Power BI ダッシュボードを使用してインサイトを取得する](#get-insights-using-power-bi-dashboards)|
| **PowerShell**        | モバイル アプリ (キャンバス アプリ) の構成に使用するスクリプトが含まれています。 |
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
<p>病院緊急時対応アプリのマスター サンプル データを含む次のエンティティのデータをインポートする必要があります。
<ul>
<li>システム</li>
<li>領域</li>
<li>Facilities</li>
<li>場所</li>
<li>部署</li>
</ul>
<p>サンプル データの代わりに自分の組織データをインポートする場合は、これらの Excel ファイルのサンプル データを自分の組織データに置き換えてから、アプリにデータをインポートできます。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらのエンティティとこれらのエンティティのフィールドの詳細については、 <a href="#manually-configure-and-manage-master-data-for-your-organization">組織のマスター データを手動で構成および管理する</a> を参照してください</p></td>
</tr>
<tr>
<td><strong>マスター データのデータ テンプレート ファイル</strong> フォルダ</td>
<td><p>このフォルダーには、組織データを入力してアプリにインポートするために使用できるマスター エンティティ用の "空の" データ ファイル (.xlsx) が含まれています。</p>
<p>このファイルには、データをアプリにインポートする順序を示す名前が付けられています。 これは、前述の <strong>サンプル データ</strong> フォルダのエンティティのリストと同じです。</p>
<p>これらのエンティティのデータを手動で入力することもできます。 これらのエンティティとこれらのエンティティのフィールドの詳細については、 <a href="#manually-configure-and-manage-master-data-for-your-organization">組織のマスター データを手動で構成および管理する</a> を参照してください</p>
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

または、マスタ データを手動で入力する場合は [組織のマスターデータを手動で構成および管理する](#manually-configure-and-manage-master-data-for-your-organization) を参照してください。

#### <a name="step-42-load-master-data"></a>ステップ 4.2: マスターデータを読み込む

前に説明したように：
- **データ ファイル/サンプル データ** フォルダー下でマスター データ エンティティのサンプルデータファイルを使用して、必要なエンティティのサンプル データをインポートできます。 

- 組織のデータを入力するために使用できる **マスター データのデータ ファイル/データ テンプレート ファイル** フォルダー下でマスターエンティティの "空の" データ ファイルを使用して、必要なエンティティでデータをインポートします。

また、後でマスター データを手動で追加することもできます。 詳細: [組織の構成とマスター データを読み込む](#manually-configure-and-manage-master-data-for-your-organization) を参照してください

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
    > ![Power App ID フィールド ](media/conf-powerapp-id-field.png "Power App ID フィールド")

1.  アプリの詳細ページ:

    1. (前にコピーした) メモ帳から アプリ ID を **Power App ID** フィールドにコピーします。

    2. アプリ アイコンをダブルクリックして **アプリ アイコン** フォルダからのアプリのアイコン ファイルを選択します。 画像ファイルには直感的に名前が付けられるため、正しいアイコンを簡単に選択できます。 たとえば、 **緊急対応アプリ** の "緊急時対応アプリ.png" ファイルを選択します 組織のブランド化に従ってカスタム画像を選択することもできます。

    3. 必要に応じて、アプリの **説明文** または **表示名** をアップデートします。

    4. 必要に応じて、アプリをアプリ リストに表示すべき場合は **メニューからアプリを隠す** 値を更新します。 **緊急対応アプリ** はコンテナー アプリですので、この値は規定では **いいえ** に設定します。

    5. 必要に応じて、**アプリ表示ランク** 値をアプリ リストのアプリの表示位置を設定するように更新します。

    6. **保存**を選択します。

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

### <a name="step-7-add-azure-application-insights-key-to-mobile-apps-for-telemetry"></a>ステップ 7: Azure Application Insights キーをテレメトリのモバイル アプリに追加します

Azure Application Insights を使用して、モバイル アプリ (キャンバス アプリ) の詳細なテレメトリを収集して、アプリの使用状況に関するインサイトを得ることができます。 この詳細については、[Application Insights を使用してアプリのテレメトリを分析する](https://docs.microsoft.com/powerapps/maker/canvas-apps/application-insights) を参照してください

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


## <a name="manually-configure-and-manage-master-data-for-your-organization"></a>手動での構成と組織のマスター データの管理

管理者は [Power Apps](https://make.powerapps.com) のモデル駆動型アプリを使用して、組織のマスター データを作成および管理します。 このデータは病院緊急時対応アプリが機能するために必要です。

> [!NOTE]
> 組織のデータをデプロイ パッケージで利用可能なデータ ファイルにインポートしてから、これらのエンティティにインポートすることもできます。 詳細については、 [ステップ 4: 組織の構成とマスター データを読み込む](#step-4-load-configuration-and-master-data-for-your-organization) を参照してください

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

### <a name="systems-data"></a>システム データ

**システム** エンティティを使用すると、病院システムのエントリを作成および管理できます。 これにより、同じ組織内の複数の病院システムを管理できます。

レコードを作成するには:

1. 左ウィンドウで **システム** を選択して **新規** を選択します。  
    > [!div class="mx-imgBorder"]
    > ![select-systems-new](media/select-systems-new.png)

2. **新しいシステム** ページで、次の適切な値を指定します。  
   > [!div class="mx-imgBorder"]
   > ![enter-details-new-system](media/enter-details-new-system.png)

   | **フィールド**            | **説明**                                    |
   |----------------------|----------------------------------------------------|
   | システム名          | 自分の病院の名前を入力します。                     |
   | 説明          | オプションの説明を入力します。                      |
   | 有効開始日データ | この病院システムの開始日時を入力します。 |
   | 有効終了日   | この病院システムの終了日時を入力します。   |

3. **保存して閉じる**を選択します。 新しく作成されたレコードは **システム** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="regions-data"></a>地域データ

**地域** エンティティを使用することで、病院システムの地理的領域を管理できます。

レコードを作成するには:

1. 左ウィンドウで **地域** を選択して、 **新規** を選択します。

2. **新しい地域** ページで、次の適切な値を指定します。  

    > [!div class="mx-imgBorder"]
    > ![enter-details-new-region](media/enter-details-new-region.png)

    | **フィールド**            | **説明**                                                                                          |
    |----------------------|----------------------------------------------------------------------------------------------------------|
    | System               | 病院システムを選択します。 このリストは、以前に作成した **システム** データに基づいて入力されます。 |
    | 地域名          | 地域名を入力します。 例えば、シアトルです。                                                              |
    | 説明          | オプションの説明を入力します。                                                                            |
    | 有効開始日データ | この地域の開始日時を入力します。                                                       |
    | 有効終了日   | この地域の終了日時を入力します。                                                         |

3. **保存して閉じる**を選択します。 新しく作成されたレコードは **地域** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="facilities-data"></a>設備データ

**設備** エンティティを使用すると、各地域内の病院の場所を管理できます。 例えば、**シアトル** 地域内の **レドモンド** と **ベルビュー** です。

レコードを作成するには:

1. 左ウィンドウで **設備** を選択して、 **新規** を選択します。

2. **新しい設備** ページで、次の適切な値を指定します。 

    > [!div class="mx-imgBorder"] 
    > ![enter-details-new-facility](media/enter-details-new-facility.png)

    | **フィールド**            | **説明**                                                                                 |
    |----------------------|-------------------------------------------------------------------------------------------------|
    | 地域               | 地域を選択してください。 このリストは、以前に作成した **地域** データに基づいて入力されます。 |
    | 設備名        | 設備名を入力します。 例えば、ベルビューです。                                                  |
    | 説明          | オプションの説明を入力します。                                                                   |
    | 人工呼吸器の総数          | 施設で利用可能な人工呼吸器の総数を入力してください                                  |
    | 有効開始日データ | この設備の開始日時を入力します。                                                     |
    | 有効終了日   | この設備の終了日時を入力します。                                                       |

    必要に応じて、設備の住所を入力します。

3. **保存して閉じる**を選択します。 新しく作成されたレコードは **設備** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="locations-data"></a>場所データ

**場所** エンティティを使用すると、各病院設備内の特定場所を管理できます。

> [!NOTE]
> **場所** レコードを作成する前に、[ステップ 4: 組織の構成とマスター データを読み込みます](#step-4-load-configuration-and-master-data-for-your-organization) で説明されているように **00 - 視覚インポート.xlsx** ファイルを使用して視覚データがインポートされていることを確認します。 これは、視覚情報が **場所** レコードを作成するために必要だからです。

レコードを作成するには:

1. 左ウィンドウで **場所** を選択して、 **新規** を選択します。

2. **新しい場所** ページで、次の適切な値を指定します。  
 
    > [!div class="mx-imgBorder"]
    > ![enter-details-new-location](media/enter-details-new-location.png)

    | **フィールド**            | **説明**                                                                                      |
    |----------------------|------------------------------------------------------------------------------------------------------|
    | 場所の名前        | 場所の名前を入力します。                                                                       |
    | 設備             | 設備を選択します。 このリストは、以前に作成した **設備** データに基づいて入力されます。 |
    | 下限                | 設備の下限情報を入力します。                                                         |
    | 出荷単位                 | 設備の単位情報を入力します                                                           |
    | 視覚      | この場所に関連付けられている視覚レコードを選択します。                                                                                                     |
    | COVID 場所      | この場所を COVID 患者の治療に使用するかどうかを選択します (**はい** または **番号**。)                                                                                                      |
    | 総ベッド数           | 設備で利用可能なベッドの総数を入力します。                                                       |
    | サージ ベッド           | その設備のサージ ベッド数を入力します。 サージ ベッドは、患者を受け入れる必要がある場合に、認可されたベッド数を超えてスタッフを配備できるベッドです。                                                      |
    | ブロックされたベッド         | この設備のブロックされたベッド数を入力します。                                                     |
    | 前回の国勢調査          | 作成されている前回の国勢調査レコードに基づいて入力されます。                                             |
    | 占有率 | 最新の国勢調査と総ベッド数に基づいて自動的に計算                                         |
    | 有効開始日データ | この設備の開始日時を入力します。                                                   |
    | 有効終了日   | この場所の終了日時を入力します。                                                     |
    | 場所オーダー       | 場所のドロップダウン リストで場所を並べ替える番号を入力します。                               |
    | 代替サイト フラグ  | 内部使用のみ。                                                                                     |

3. **保存して閉じる**を選択します。 新しく作成されたレコードは **場所** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

### <a name="departments-data"></a>部署データ

**部署** エンティティを使用すると、病院の部門情報を管理できます。

レコードを作成するには:

1. 左ウィンドウで **部署** を選択して、 **新規** を選択します。

2. **新しい部署** ページで、次の適切な値を指定します。

    > [!div class="mx-imgBorder"]
    > ![enter-details-new-department](media/enter-details-new-department.png)

    | **フィールド**            | **説明**                                    |
    |----------------------|----------------------------------------------------|
    | 部署名      | 部署名を入力します。                            |
    | 説明          | オプションの説明を入力します。                      |
    | 有効開始日データ | この部署の開始日時を入力します。 |
    | 有効終了日   | この部署の終了日時を入力します。   |

3. **保存して閉じる**を選択します。 新しく作成されたレコードは **部署** リストで使用できるようになります。

このレコードを編集するには、レコードを選択し、必要に応じて値を更新して、**保存して閉じる** を選択します。

## <a name="get-insights-using-common-data-service-dashboards"></a>Common Data Service ダッシュボードを使用してインサイトを取得する

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

1. [Power Apps](https://make.powerapps.com) にサインインして、自分の管理アプリを検索します。

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

## <a name="get-insights-using-power-bi-dashboards"></a>Power BI ダッシュボードを使用してインサイトを取得する

Power BI ダッシュボードを公開し、組織内のユーザーと共有することで、インサイトと意思決定のためにダッシュボードを使用できます。

### <a name="prerequisites"></a>前提条件

- レポートにアクセスするユーザーに割り当てられる Power BI Premium 容量または Power BI Pro ライセンス。 

- レポートを公開する Power BI でワークスペースを作成します。 Power BI にサインインして、ワークスペースを作成します。 詳細: [Power BI で新しいワークスペースを作成する](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces)

- Windows の App Store: <https://aka.ms/pbidesktop> からの Power BI Desktop のインストール

   > [!NOTE] 
   > 過去に Power BI サイトから実行可能ファイルとして直接ダウンロードして Power BI をインストールした場合、App Store からのものを使用してください。 App Stpre のバージョンは、新しいリリースが利用可能になると自動的に更新されます。

- App Store から Power BI Desktop をインストールし、実行し、組織内で Power BI アプリを公開するための権限を持つアカウントを使用してログインします。

### <a name="publish-the-power-bi-dashboard"></a>Power BI ダッシュボードの公開

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

### <a name="view-the-power-bi-dashboard"></a>Power BI のダッシュボードの表示

[Power BI](https://apps.powerbi.com) にサインインして Power BI ダッシュボードにアクセスして表示します。

> [!div class="mx-imgBorder"]
> ![Power BI ダッシュボードの表示](media/view-power-dashboard.png)

レポートの上部にあるフィルターを使用して、病院システム、地域、設備のデータをフィルターできます。 COVID の場所をフィルターすることもできます。

> [!div class="mx-imgBorder"]
> ![レポート フィルター](media/report-filters.png)

#### <a name="system-at-a-glance-page"></a>システム一覧ページ 

**システム一覧ページ** は、全体ビューを提供する来てのまたは最上位のページです。  

このページには、以下の要約ビューが表示されます。 

- **COVID 患者**: COVID 患者の総数、COVID-19 で陽性と判明した患者の数、調査中の患者の数を示します。 

- **ベッド管理**: ベッドの可用性、占有率、サージベッドの数、およびベッドの総数を示します。 下のグリッドを使用して、鋭単位で数値を表示することもできます。 

- **看護師人材管理**: ICU の患者数、割り当てられた看護師、患者と看護師の比率を示します。  

- **退院**: 長期滞在患者の総数、退院が予想される患者の数、および実際の退院を示します。 

- **機器**: 人工呼吸器の総数、使用中の人工呼吸器の数、および使用可能な人工呼吸器が表示されます。 

- **サプライ**: 手元にあるサプライの数を日別に表示します。

> [!NOTE]
> - 要約された領域のいずれかで情報アイコン (i) を選択すると、その領域のそれぞれの詳細ページが表示されます。 
> - データのフィルターや並べ替え、レポートの PDF や PowerPoint へのエクスポート、スポットライトの追加など、レポートに対して他のアクションを実行することもできます。 Power BI でのレポート機能の詳細については、[ Power BIのレポート](https://docs.microsoft.com/power-bi/consumer/end-user-reports) を参照してください
> - これらのレポートの一部の最新更新または最後に更新された列には、データが最後に更新された日時が表示されます。 これらの列で日付と時刻の値の色を確認することで、鮮度を簡単に特定することもできます。
>    - 黒: データは 20 時間以内に更新されます
>    - 灰色: データは 20〜24 時間前に更新されます
>    - 赤: データは 24 時間以上空けて更新されます 
 
#### <a name="system-view-page"></a>システム ビュー ページ

**システム ビュー** ページには、病院システムに関する以下の情報を含むグラフが表示されます。
- 使用中の人工呼吸器と使用可能な人工呼吸器
- ベッドと救急医療ベッドの可用性と占有率
- リクエストされたスタッフの総数、患者数 (国勢調査)、看護師と患者の比率。
- 手持ちサプライがある日数

> [!div class="mx-imgBorder"]
> ![システム ビュー](media/report-system-view.png)

#### <a name="location-details-page"></a>場所の詳細ページ 

場所別にレポートをドリルダウンするには、右上隅の **場所の詳細** にあります。 **場所の詳細** ページには、ベッドの総数、使用可能なベッド、サージベッド、COVID 患者などの場所ごとのデータが表示されます。 

> [!div class="mx-imgBorder"]
> ![場所の詳細](media/report-location-details.png) 

#### <a name="covid-patient-details-page"></a>COVID 患者詳細ページ 

**COVID 患者の詳細** ページには、各場所の患者、調査中の患者 (PUI) の数のピークと谷を示す経時的な患者の傾向、陽性と判明した患者の数など、COVID 患者に関するドリルダウン情報が表示され、患者が病院内のどこにいるのかを把握できます。

> [!div class="mx-imgBorder"]
> ![COVID 患者詳細](media/report-covid-details.png)

#### <a name="bed-management-page"></a>ベッド管理ページ 

**ベッド管理** ページでは、利用可能なベッドの総数や占有率など、場所ごとのドリルダウン情報を提供します。

> [!div class="mx-imgBorder"]
> ![ベッド管理](media/report-bed-details.png)

#### <a name="staff-details-page"></a>スタッフ詳細ページ  

**スタッフ詳細** ページには、スタッフの場所、割り当てられた看護師の数、患者の総数、COVID 患者の数などの詳細が表示されます。 また、一定期間の看護師と患者の比率および ICU 看護師と患者の比率も表示します。

> [!div class="mx-imgBorder"]
> ![スタッフ詳細](media/report-staff-details.png)

#### <a name="equipment-details-page"></a>機器の詳細ページ 

**機器の詳細** ページには、場所ごとの機器、使用中の人工呼吸器の総数、COVID 患者の数、および使用中の人工呼吸器、充電器、使用中のフードなどのその他の機器の詳細が表示されます。

> [!div class="mx-imgBorder"]
> ![機器の詳細ページ](media/report-equipment-details.png)

#### <a name="discharge-details-page"></a>退院詳細ページ 

**退院詳細** ページでは、長期の患者、一定期間における退院の障壁、および実際の退院と予想される退院に関する差異について詳しく説明しています。

> [!div class="mx-imgBorder"]
> ![機器の詳細ページ](media/report-discharge-details.png)

#### <a name="supplies-on-hand-details-page"></a>手持サプライの詳細ページ 

**手持サプライの詳細** ページには、場所とサプライごとの供給に関する詳細が表示されます。また、一定期間の手持サプライに関するデータも提供します。

> [!div class="mx-imgBorder"]
> ![機器の詳細](media/report-discharge-details.png)

## <a name="view-and-manage-app-feedback"></a>アプリ フィードバックの表示および管理

最前線のスタッフがモバイル デバイス上でキャンバス アプリを使用して提供するすべてのフィードバックは、**アプリのフィードバック** エンティティに保管され、管理者は管理アプリのナビゲーション ウィンドウの **管理** 領域を使用して表示および管理できます。

アプリ フィードバックを表示および管理するには:

1. [Power Apps](https://make.powerapps.com) にサインインして、自分の管理アプリを検索します。

2. ナビゲーション ウィンドウで、エリアピッカーから **管理** を選択します。

3. **アプリ フィードバック** を選択して、ユーザーが送信したアプリのフィードバックのリストを表示します。 レコードをクリックして詳細を表示し、レビュー済みかどうかをマークできます。  

    > [!div class="mx-imgBorder"]
    > ![select-app-feedback](media/select-app-feedback.png)

## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

## <a name="next-step"></a>次の手順

[病院緊急時対応アプリを使用する](use.md)
