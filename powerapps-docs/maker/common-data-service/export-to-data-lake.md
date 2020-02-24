---
title: データ レイクへのエクスポート | MicrosoftDocs
description: エンティティデータを Power Appsの Azure データレイクにエクスポートする方法を解説します
ms.custom: ''
ms.date: 01/28/2020
ms.reviewer: Mattp123
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- powerapps
author: sabinn-msft
ms.assetid: ''
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 152fc65e69ccb728727f92ed77d6495f6dc5dcab
ms.sourcegitcommit: 303d5aed44f2bbb406cabeb6b9c8474d738d9114
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "3005283"
---
# <a name="export-entity-data-to-azure-data-lake-gen-2"></a>エンティティデータ をAzure データ レイク Gen 2 にエクスポートする

データ レイク サービスへのエクスポートは、Common Data Service Azure データ レイク Gen 2へデータを継続的にエクスポートするためのパイプラインとして機能します。 データ レイク サービスへのエクスポートは、災害復旧機能を備えたスケーラブルな高可用性を提供することにより、エンタープライズ ビッグデータの分析用に設計されています。 データは Common Data Model (CDM) のフォーマットで保存されます。これにより、アプリと展開間で意味上の一貫性が提供されます。 

![データ レイクへのエクスポートの概要](media/export-data-lake-overview.png)

データ レイクへのエクスポートには、次の機能が実装されています。 
- Common Data Service 環境を Azure サブスクリプション内の データ レイク gen 2 にリンクまたはリンク解除します。 
- Azure データ レイク Gen 2へのエンティティの継続的なレプリケーション。
- データとメタデータの最初の書込みとその後の増分の書込み。 
- 標準エンティティとカスタム エンティティの両方を複製します。 
- トランザクションの作成、更新、削除。 
- 大規模な分析シナリオの継続的なスナップショット更新。 
- Power BI、Azure Data Factory、Azure Databricks、Azure 機械学習サービスなどの、メタデータの検出、およびデータの作成者と利用者間の相互運用性を促進します。

## <a name="how-data-and-metadata-are-exported"></a>データとメタデータのエクスポート方法
データ レイク サービスへのエクスポートは、エンティティ データとメタデータの初期および増分の書き込みに対応しています。 Common Data Service でのデータまたはメタデータの変更は、追加アクションなしで自動的にデータレイクにプッシュされます。 これは、プル操作ではなくプッシュ操作となります。 更新の間隔を設定する必要なく、変更が宛先にプッシュされます。 

標準エンティティとカスタム エンティティの両方をエクスポートすることができます。 Common Data Service の変更追跡のエンティティ属性は、データが最初に抽出されてから、または最後に同期されてからどのデータが変更されたかを検出することによって、データの同期を効率の良い方法で維持します。 

すべての作成、更新、削除 (CrUD) 操作が Common Data Service からデータレイクへエクスポートされます。 たとえば、ユーザーが Common Data Service のアカウント エンティティ レコードを削除すると、トランザクションは宛先のデータレイクに複製されます。

## <a name="prerequisites"></a>前提条件
Common Data Service のデータを データレイクにエクスポートする前に、Azure StorageV2（汎用v2）ストレージアカウントを作成して構成する必要があります。 

 [Azure ストレージ アカウントを作成する](/azure/storage/blobs/data-lake-storage-quickstart-create-account) に記載の手順に従い、以下のの要件に留意してください。 
- ストレージのアカウントの所有者権限が付与されている必要があります。 
- ストレージ タイプを **Storagev2 (汎用v2)** に設定します。 
- ストレージのアカウントは **階層型名前空間** の機能を有効にしておく必要があります。 
 - レプリケーションの設定にgeo 冗長ストレージへの読み取りアクセス権を指定しておくことを推奨します。 詳しくは [読み取りアクセスのgeo 冗長ストレージ](/azure/storage/common/storage-redundancy-grs#read-access-geo-redundant-storage)を参照してください 
>   ![ストレージ アカウント のプロパティ](media/storage-account-properties.png)

> [!NOTE]
> - ストレージのアカウントは、 PowerApps のテナントと同じ Azure AD テナントに作成する必要があります。  
> - ストレージ アカウントは、使用する機能の存在する PowerApps 環境を同じ領域で作成することを推奨します。  
>  - Common Data Service 環境を Azure データ レイク gen 2 へとリンクするには、 Common Data Service 管理者である必要があります。 
>  - エクスポートが可能となっているのは、変更の追跡が有効になっているエンティティのみです。 


## <a name="select-and-export-common-data-service-entity-data-to-azure-data-lake-gen-2"></a>Common Data Service エンティティ データを選択し、 Azure データ レイク gen 2 へとエクスポートする
1. [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)にサインインし、 **データ**を展開し、続いて **エンティティ**を選択します。 
2. コマンドバーで、**データ レイクへエクスポートする**を選択し、続いて **データ レイクへエクスポートする** ページの、**データレイクへの新しいリンク**を選択します。 
3. 以下の設定を選び、続いて **次へ** を選択します。 
   - **サブスクリプション**。 Azure のサブスクリプションを選択します。 
   - **リソース - グループ**。 Storagev2 (汎用v2) ストレージ アカウントを含むリソース グループを選択します。
   - **ストレージ アカウント**。 エクスポートに使用する、Storagev2 (汎用v2) ストレージ アカウントを選択します。 
4. データ レイクにエクスポートするエンティティを選択し、**保存**を選択します。 エクスポートが可能となっているのは、変更の追跡が有効になっているエンティティのみです。 詳細については、 [エンティティの変更追跡を有効化する](/dynamics365/customer-engagement/admin/enable-change-tracking-control-data-synchronization) を参照してください

   > [!div class="mx-imgBorder"] 
   > ![エクスポートするエンティティの選択](media/export-data-lake-select-entity.png)

ご利用の Common Data Service 環境は Azure データ レイク gen 2 のストレージ アカウントにリンクされています。 Azure ストレージ アカウントのファイル システムは、データ レイクに複製するために選択した各エンティティーのフォルダーを使用して作成されます。 

## <a name="manage-entity-data-to-the-data-lake"></a>データレイクへのエンティティデ ータを管理する
サブスクリプションで Azure データ レイク gen2 へのデータのエクスポートを設定後、次の2つの方法のいずれかで、データ レイクへのエンティティ データのエクスポートを管理できます。 

- Power Apps メーカー ポータルの **データレイクへのエクスポート** 領域で、 コマンドバーで **エンティティを管理する** を選択し、1つ以上のリンクされたエンティティを追加、削除します。
- Power Apps のメーカーポータルの **エンティティ** 領域で、 **…** を選択します エンティティの横に位置する、エンティティ データをエクスポートするリンクされたデータ レイクを選択します。 
   ![エクスポートをするエンティティを選択します](media/select-entity-export.png)


リンクされたエンティティのリンクを解除するには、 Power Apps メーカーのポータルである  **データレイク領域へのエクスポート** にて、 **データレイクのリンク解除**を選択します。 

## <a name="view-your-data-in-the-azure-data-lake-gen-2"></a>Azure データ レイク Gen 2 でデータを表示する
1. [Azure](https://portal.azure.com) にサインインし、ストレージ アカウントを選択してから、左側のナビゲーション ウィンドウで**ストレージ エクスプローラー**を選択します。 
2. **ファイル システム**を展開し、続いて commondataservice-*environmentName*-org-*Id* を選択します。 

model.json ファイルは、名前とバージョンとともに、レイク にエクスポートされたエンティティのリストを含んでいます。 model.json ファイルには、初回の同期状態と完了時間も含まれています。 

データレ イクにエクスポートされた各エンティティにフォルダーが表示されます。このフォルダには、スナップショット コマンド区切り形式 (csv) のファイルが含まれています。 
   > [!div class="mx-imgBorder"] 
   > ![レイク内のエンティティ データ](media/entity-data-in-lake.png) 

### <a name="continuous-snapshot-updates"></a>スナップショットの継続的な更新
Common Data Serviceデータは、トランザクションの作成、更新、削除を通じて継続的に変更できます。 スナップショットは、定期的な間隔 (1時間ごと) で更新されるデータの読み取り専用のスナップショットのコピーを提供します。 これにより、任意の時点で、データ分析の利用者がレイクのデータを確実に消費できるようになります。   

![スナップショットの継続的な更新](media/snapshot-updates.png)

エンティティが初期エクスポートの一部として追加されると、エンティティ データがレイクに対応するフォルダー配下の entity.csv ファイルに書き込まれます。 これは T1 サイクル間隔であり、スナップショット読み取り専用ファイルには、 *エンティティ*-T1.csv というファイル名がつけられます。例えば 取引先企業-T1.csv や 連絡先-T1.csv などです。 さらに、これらのスナップショット ファイルをポイントするように model.json ファイルが更新されます。 model.json を開くと、スナップショットの詳細を表示できます。 

次に、レイクの Account.csv パーティションファイルとスナップショット フォルダーの例を示します。
![アカウント エンティティのスナップショット](media/export-data-lake-account-snapshots.png) 

Common Data Service の変更は、トリクル フィードエンジンを使用して、対応する csv ファイルに継続的にプッシュされます。 これは T2 サイクル間隔で、別のスナップショットが取得されます。 取引先企業-T2.csv や 連絡先-T2.csv のような、*エンティティ* -T2.csv と、 model.json は新しいスナップショットファイルに更新されます (これら両方のエンティティに変更があると仮定した場合)。 T2 以降のスナップショット データを表示する新しいユーザーは、新しいスナップショット ファイルに送信されます。 これにより、元のスナップショット ビューアは古いスナップショット T1 ファイルで引き続き動作し、新しいビューアは最新の更新を読み取ることができます。 これは、下流のプロセスの実行時間が長い場合に有用です。 

model.json ファイルの例を次に示します。このファイルは、常に最新のタイムスタンプ付きアカウントスナップショットファイルを示します。 

![サンプル スナップショット JSON](media/sample-snapshot-json.png) 

## <a name="transporting-export-to-data-lake-configuration-across-environments"></a>環境間でのデータ レイク コンフィグレーションへのエクスポートの転送
Power Apps では、別の環境にアプリケーションおよびコンポーネントを移動したり、既存のアプリケーションに一連のカスタマイズを適用するために、ソリューションが利用されます。 データ レイク へのエクスポート設定のソリューションを認識させるには、データ レイク コアへのエクスポート ソリューションを環境に読み込みます。 これにより、配布、データ レイク 構成へのエクスポートのバックアップや復元などの、基本的なアプリケーション ライフサイクル管理 (ALM) 機能が可能となります。 

### <a name="import-the-export-to-data-lake-core-solution"></a>Export to データ レイク Core ソリューションをインポートする 
1.  Power Apps メーカー ポータルから、データ レイク構成にエクスポートを配布する環境を選択します。
2.  左側のナビゲーション ウィンドウで、**ソリューション**を選択し、**AppSource** を開き、**データ レイク コアへエクスポートする**という名称のソリューションを検索し、続いてソリューションをインポートします。

### <a name="add-an-export-to-data-lake-configuration-to-a-solution"></a>データレーク構成へのエクスポートをソリューションに追加する

> [!IMPORTANT]
> エクスポートを データ レイク 構成に追加する前に、前述の [データ レイク コアへエクスポートする ] ソリューションをインストールする必要があります。 

1.  Power Apps メーカー ポータルから、データ レイク構成にエクスポートを配布する環境を選択し、左側のナビゲーション ウィンドウで、 **ソリューション** を選択します。 
2.  **新しいソリューション** を選択し、名前を入力して公開元を選択してから、バージョン番号を指定します。  
3.  前述の手順で作成したソリューションを開き、**既存の追加** > **その他** > **データレイク構成へのエクスポート**を選択します。 
4.  リンクされたデータ レイク構成を選択し、続いて **追加** を選択します。 
5.  **ソリューション** 領域にて、ソリューションを選択し、コマンドバーで **エクスポート** を選択します。 
6.  **エクスポートする前に** ウィンドウで、 **公開する** を選択してエクスポートする前にすべての変更を公開し、続いて **次へ**を選択します。 

### <a name="import-the-solution-that-contains-the-export-to-data-lake-configuration"></a>データ レイクへのエクスポート設定を含むソリューションをインポートする
ソリューションのインポートを実行する環境で、Power Apps メーカーポータル **ソリューション** 領域でソリューションをインポートします。 

#### <a name="verify-the-export-to-data-lake-configuration"></a>データ レイクへのエクスポート設定を確認する
[データ レイクへエクスポートする] の構成をインポートした環境の Power Apps メーカー ポータルから、リンクされたデータレイクと、他の環境から転送したエンティティが表示されていることを確認します。
> [!div class="mx-imgBorder"] 
> ![インポートされた [データ レイクへエクスポートする] エンティティ](media/imported-export-entities.png) 

### <a name="see-also"></a>関連項目
[ブログ: Azure データ レイク に CDS データをエクスポートする](https://powerapps.microsoft.com/blog/exporting-cds-data-to-azure-data-lake-preview/)