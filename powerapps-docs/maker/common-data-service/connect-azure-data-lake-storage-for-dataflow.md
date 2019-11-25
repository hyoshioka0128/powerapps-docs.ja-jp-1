---
title: Azure Data Lake Storage Gen2 をデータフロー ストレージに接続する | MicrosoftDocs
description: Azure Data Lake Storage Gen2 をデータフロー ストレージに接続する方法
ms.custom: ''
ms.date: 09/05/2019
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
ms.assetid: ''
caps.latest.revision: ''
ms.author: matp
manager: kvivek
tags: ''
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: d7957f048613045a64af0caf5696e540dbb8f883
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2754788"
---
# <a name="connect-azure-data-lake-storage-gen2-for-dataflow-storage"></a>Azure Data Lake Storage Gen2 をデータフロー ストレージに接続する

[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

データフローの構成をすることでそのデータをAzure Data Lake Storage Gen2 のアカウントに保存することが出来ます。 この記事では、そのために必要となる一般的な手順を説明し、その手順に沿ったガイダンスとベスト・プラクティスを記載しています。 

定義およびデータ ファイルを data lake に格納するようにデータ フローを構成すると、以下のような利点があります。
- Azure Data Lake Storage Gen2は、きわめて拡張性の高いデータのストレージ機能を提供します。
- Azure データサービスの GitHub サンプルが示しているように、IT部門の開発者は Dataflow データと定義ファイルを利用して、Azure データと人工知能(AI) サービスを利用することができます。
- これにより、開発者のリソースをデータフローと Azure に使用して、データフローのデータを内部アプリケーションと基幹業務ソリューションに統合することができます。

## <a name="requirements"></a>要件
データフローに Azure Data Lake Storage Gen2 を使用するには、以下が必要となります:
- PowerApps の新しい環境 PowerApps では、 Azure Data Lake Storage Gen2 を処理の対象先として使用してデータフローを作成することができます。 この作業を行うに当たっては環境内での認証が必要になります。 
- Azure のサブスクリプション ID。 Azure Data Lake Storage Gen2 を使用するには、Azure のサブスクリプションが必要となります。
- リソース グループ。 既存のリソースグループを使用するか、新規で作成することが出来ます。
- Azure Storage アカウント。 ストレージのアカウントは Data Lake Storage Gen2 の機能を有効にしておく必要があります。

> [!TIP]
> Azure サブスクリプションがない場合は、 [無料の試用アカウント](https://azure.microsoft.com/free/) を作成してください。

## <a name="prepare-your-azure-data-lake-storage-gen2-for-power-platform-dataflows"></a>Power Platform データフロー の Azure Data Lake Storage Gen2 を準備します。
お使いの環境を Azure Data Lake Storage Gen2 のアカウントと構成する前に、ストレージ アカウントの作成および設定が必要となります。 Power Platform のデータフロー要件は以下のとおりです。
1.  ストレージのアカウントは、 PowerApps のテナントと同じ Azure Active Directory テナントに作成する必要があります。
2.  ストレージアカウントは、使用する PowerApps 環境と同じ領域で作成することを推奨します。 PowerApps 環境の場所を確認するには、管理者に問い合わせてください。
3.  ストレージのアカウントは 階層型名前空間の機能を有効にしておく必要があります。
4.  ストレージのアカウントの所有者権限が付与されている必要があります。

以下のセクションでは、 Azure Data Lake Storage Gen2アカウントの構成に必要な手順について説明します。

## <a name="create-the-storage-account"></a>ストレージ アカウントを作成する
[Azure Data Lake Storage Gen2 ストレージアカウントを作成する](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account) に記載されている手順に従ってください。
1.  環境と同じリージョンを選択し、ストレージを StorageV2 (汎用 v2) として設定してください。
2.  階層型名前空間を有効にしている必要があります。 
3.  レプリケーション設定に地理冗長ストレージへの読み取りアクセス権を指定しておくことを推奨します。

## <a name="connect-your-azure-data-lake-storage-gen2-to-powerapps"></a>Azure Data Lake Storage Gen2 を PowerApps に接続する
Azure ポータルで Azure Data Lake Storage Gen2 のアカウントを設定が完了したら、特定のデータフローまたは PowerApps 環境に接続することができます。 レイクを環境に接続することで、環境内の他の作業者や管理者がデータフローを作成することができ、レイク内のデータを保存することができます。 

Azure Data Lake Storage Gen2 のアカウントとデータフローを接続するには、以下の手順に従ってください:
1.  [PowerApps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)にサインインし、どの環境に接続したのかを確認します。 環境切り替え機能はヘッダーの右側に配置されています。 
2. 左側のナビゲーション ウィンドウで、 **データ**の横にある矢印を選択します。

   ![PowerApps  メーカー ポータルデータ タブ](media/powerapps-portal-data.png)

3. 表示されたリストにて、 **データフロー** を選択し、コマンド バー上の **新規データフロー**を選択します。

   ![新規データフローの作成](media/new-dataflow.png) 

4. 分析エンティティを選択します。 これらのエンティティは、Azure Data Lake Store Gen2 アカウントに保存するデータを指定します。 

   ![分析エンティティの選択](media/select-analytical-entities.png)

## <a name="select-the-storage-account-to-use-for-dataflow-storage"></a>データフロー ストレージを使用するストレージアカウントを選択する
ストレージアカウントが環境と関連付けられていない場合は、 **data lake に関連付ける** のダイアログ ボックスが表示されます。 サインインを行い、前述の手順で作成した data lake を確認する必要があります。 この例では、data lake は環境に関連付けらていないため、環境追加を促すメッセージが表示されます。 


1. ストレージ アカウントを選択します。

    **ストレージ アカウントの選択**画面が表示されます。
    
    ![ストレージ アカウントの選択](media/select-storage-account.png)
    
2. ストレージ アカウントの**サブスクリプション ID** を選択します。
3. ストレージ アカウントが作成された**リソース グループ名**を選択します。
4. **ストレージ アカウント名**を入力します。
5. **保存**を選択します。

これらの手順が正常に完了すると、Azure Data Lake Storage Gen2 アカウントは Power Platform Dataflows に接続され、データフローの作成を続行できます。

## <a name="considerations-and-limitations"></a>考慮事項と制限
データフロー ストレージを使用する際に留意すべき考慮事項と制限がいくつかあります。
- データフロー ストレージ用の Azure Data Lake Store Gen2 アカウントのリンクは、既定の環境ではサポートされていません。
- データフロー ストレージの場所をデータフロー用に構成したら、変更することはできません。
- 既定では、環境のどのメンバーも Power Platform Dataflows Connector を使用してデータフロー データにアクセスできます。 ただし、データフローの所有者のみが Azure Data Lake Storage Gen2 のファイルに直接アクセスできます。 追加のユーザーがレイクのデータフロー データに直接アクセスすることを承認するには、Data Lake 内または Data Lake 自体のデータフローの **CDM フォルダ**にそれらのユーザーを承認する必要があります。
- データフローが削除されると、レイクの **CDM フォルダ**も削除されます。 

> [!IMPORTANT]
> 組織のレイクのデータフローによって作成されたファイルを変更したり、データフローの **CDM フォルダ**にファイルを追加したりしないでください。 ファイルを変更するとデータフローに損害を与えるか動作を変更する恐れがあり、サポートされていません。 Power Platform Dataflows は、レイクで作成したファイルへの読み取りアクセスのみを許可します。 Power Platform Dataflows が使用するファイル システムに対して他のユーザーまたはサービスを承認する場合、そのファイル システム内のファイルまたはフォルダーへの読み取りアクセスのみを許可します。

## <a name="frequently-asked-questions"></a>よくあるご質問
*以前に組織の Azure Data Lake Storage Gen2 でデータフローを作成していて、そのストレージの場所を変更したい場合はどうなりますか?*

   ワークフローを作成した後にストレージの場所を変更することはできません。

*環境のデータフロー ストレージの場所はいつ変更できますか?*

   環境のデータフロー ストレージの場所の変更は現在サポートされていません。 

## <a name="next-steps"></a>次のステップ
この記事では、Azure Data Lake Storage Gen2 アカウントをデータフロー ストレージに接続する方法に関するガイダンスを提供しました。 

データフロー、Common Data Model、Azure Data Lake Storage Gen2 に関する詳細については、次の記事を参照してください。
- [データフローでセルフサービス データを準備する](https://go.microsoft.com/fwlink/?linkid=2099972)
- [PowerApps でのデータフローの作成と使用](https://go.microsoft.com/fwlink/?linkid=2100076)
- [Azure Data Lake Storage Gen2 をデータフロー ストレージに接続する](https://go.microsoft.com/fwlink/?linkid=2099973)
- [Common Data Service のエンティティにデータを追加する](https://go.microsoft.com/fwlink/?linkid=2100075)

Azure Storage の詳細については、次の記事を参照してください。
- [Azure Storage セキュリティ ガイド](https://docs.microsoft.com/azure/storage/common/storage-security-guide)

Common Data Model に関する詳細については、次の記事を参照してください。
- [Common Data Model - 概要](https://docs.microsoft.com/powerapps/common-data-model/overview) 
- [Common Data Mode フォルダ](https://go.microsoft.com/fwlink/?linkid=2045304)
- [CDM モデル ファイル定義](https://go.microsoft.com/fwlink/?linkid=2045521)

[PowerApps コミュニティ](https://go.microsoft.com/fwlink/?linkid=2099971)で質問できます。
