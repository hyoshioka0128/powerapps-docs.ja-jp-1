---
title: Power BI Desktop でのエンティティ データを表示 (プレビュー) | MicrosoftDocs
description: Power BI Desktop でエンティティ データにアクセスして、表示する方法についてアクセスする方法について説明します
ms.custom: ''
ms.date: 05/01/2020
ms.reviewer: matp
ms.service: powerapps
author: Mattp123
ms.assetid: ''
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 446381f491fac0cb5d60c3945f5404983f1ed364
ms.sourcegitcommit: 0ede8e3bc795e151aa94ffcbce15cff7a949c57a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335411"
---
# <a name="view-entity-data-in-power-bi-desktop-preview"></a>Power BI Desktop でエンティティ データを表示する (プレビュー)

[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Power BI Desktop を使用して、Common Data Service で表示できます。 環境からアクセスできるエンティティ レコード データは、読み取り専用です。 データ アクセスでは、Power Apps を使用してエンティティ レコード データにアクセスするために使用されるものと同じ Common Data Service セキュリティ モデルを使用します。

> [!IMPORTANT]
> - これはプレビュー機能であり、すべての地域で利用できるわけではありません。
> - [!INCLUDE[cc_preview_features_definition](../../includes/cc-preview-features-definition.md)]

1.  [Power Apps](https://make.powerapps.com/) にサインインして、右上隅で適切な環境を選択します。

2.  左側のナビゲーションウィンドウで、**データ**を展開し、**エンティティ**を選択して、次にコマンドバー上の **Power BI で分析**を選択します。

    ご使用の環境の pbids ファイルは、ブラウザーの既定ダウンロード フォルダーにダウンロードされます。
    
    > [!NOTE]
    > Power Apps 環境内に **Power BI で分析**オプションがない場合、SQL 接続機能にまだアクセスできません。

3.  .pbids ファイルを開いて、Power BI Desktop にアクセスします。 Power BI Desktop を持っていない場合は? [今すぐ入手する](https://powerbi.microsoft.com/downloads/)。

4.  pbids ファイルは、Power BI Desktop にロードされています。 **SQL Server データベース** ダイアログ ボックスで、**マイクロソフト アカウント**を選択し、**サインイン**を選択してから、表示されるブラウザ ウィンドウに資格情報を入力します。

    > [!div class="mx-imgBorder"] 
    > ![](media/power-bi-environment-signin.png)

5.  Power BI Desktop の **SQL Server データベース** ダイアログ ボックス内にある**接続**を選択します。

    Power BI Desktop 内の**ナビゲーター** ウィンドウに環境が表示されます。 展開して、分析可能なエンティティ テーブルを表示します。 エンティティを選択して、そのデータを表示します。

    > [!div class="mx-imgBorder"] 
    > ![](media/entity-record-data-displayed.png)

> [!NOTE]
> T-SQL クエリなどの SQL オプションはサポートされていません。

Power BI Desktop の詳細については、[Power BI Desktop の概要](/power-bi/desktop-getting-started) を参照してください。

### <a name="see-also"></a>関連項目
[SQL を使用してデータを照会](../../developer/common-data-service/cds-sql-query.md)
