---
title: Power Apps、Power の自動化、および Power BI と SharePoint Online の統合 (概要) |Microsoft Docs
description: この一連のチュートリアルでは、SharePoint リストに基づいてプロジェクト管理用の基本的なキャンバスアプリを構築する方法と、SharePoint Online と統合される3つの主要テクノロジである Power Apps、Power Apps、Power BI について説明します。
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/05/2019
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 45f33285b288dc273caeff1e85591210cc3deb8c
ms.sourcegitcommit: d194d2fa009ca7bfcbe95e5f31473832a130e0a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "74959543"
---
# <a name="integrate-power-apps-power-automate-and-power-bi-with-sharepoint-online"></a>Power Apps、Power オートメーション、および Power BI を SharePoint Online と統合する
SharePoint Online をご利用で、ビジネス プロセスの自動化と効率化をお望みですか? Power Apps、Power オートメーション、または Power BI を使用しましたが、SharePoint Online でそれらを使用する方法がわからない場合は、 お探しのものはここにあります。 この一連のチュートリアルでは、SharePoint リストに基づいてプロジェクト管理用の基本的なキャンバスアプリを構築する方法と、SharePoint Online と統合される3つの主要テクノロジである Power Apps、Power Apps、Power BI について説明します。 これらのテクノロジの連携により、お客様のビジネスの *測定* 、結果に基づく *行動* 、ワークフローの *自動化* が容易に可能です。 このシリーズを終了すると、次のようなすばらしいシナリオが完成します。

![完成シナリオの図](./media/sharepoint-scenario-intro/composite-with-background.png)

## <a name="business-scenario"></a>ビジネス シナリオ
このチュートリアル シリーズでは、SharePoint Online のサイトを持つ Contoso という会社が、このサイトでプロジェクトの申請、承認、開発、最終確認のライフサイクル全体を管理しています。 *プロジェクト申請者* (各部門のトップなど) が SharePoint リストに項目を追加して、IT プロジェクトを申請します。 *プロジェクト承認者* (IT マネージャーなど) によってプロジェクトが検討され、承認または却下されます。 承認されると、プロジェクトは *プロジェクト管理者* に割り当てられ、同じアプリを使用して追加の詳細が 2 つ目のリストに追加されます。 SharePoint に埋め込まれた Power BI レポートを使用して、  *ビジネス アナリスト* が現在および完了したプロジェクトの見直しを行います。  Power の自動化は、承認の電子メールを送信して Power BI アラートに応答するために使用されます。

## <a name="getting-started-quickly"></a>すぐに始める
このチュートリアル シリーズで紹介するシナリオは、本格的なプロジェクト管理や分析アプリと比べると単純ですが、それでもすべてのタスクを完了するには時間がかかります。 Power Apps の使用について簡単に説明し、Power の自動化と、SharePoint での Power BI については、次の記事をご覧ください。

* **PowerApps**: [Power Apps を使用して sharepoint 内からアプリを作成](app-from-sharepoint.md#create-an-app-from-within-sharepoint-online)し、 [sharepoint リストのデータを管理するアプリを作成する](app-from-sharepoint.md)
* **電力自動化**: [power の自動化による承認の待機](https://docs.microsoft.com/flow/wait-for-approvals)
* **Power BI**: 「[SharePoint Online にレポート Web パーツを埋め込む](https://docs.microsoft.com/power-bi/service-embed-report-spo)」

完了したら、このページに戻って完全なシナリオをご確認ください。

このシナリオ内でも関心のあるタスクに取り組んで、時間がある場合はタスクを完了することができます。 タスク 1 で SharePoint リストを設定したら、お好きな順序でタスク 2 ～ 5 に取り組むことができます。そのあとのタスク 6 ～ 8 は順番に取り組んでください。 最後に、このシナリオの[ダウンロード パッケージ](https://aka.ms/o4ia0f)の一部として、完成した 2 つのアプリと Power BI Desktop レポートが 1 つ含まれています。 各タスクのすべての手順を完了していない場合でも、これらをご覧になって例から学ぶことができます。

## <a name="prerequisites"></a>前提条件
シナリオを完了するには、次のサブスクリプションとデスクトップ ツールが必要です。 Office 365 Business Premium サブスクリプションには、Power Apps と Power の自動化が含まれています。

| **サブスクリプションまたはツール** | **リンク** |
| --- | --- |
| Office 365 Business Premium のサブスクリプション |[無料試用版のサブスクリプション](https://signup.microsoft.com/Signup?OfferId=467eab54-127b-42d3-b046-3844b860bebf&dl=O365_BUSINESS_PREMIUM&ali=1) |
| Power BI Pro のサブスクリプション |[無料試用版のサブスクリプション](https://powerbi.microsoft.com/get-started/) (**無料試用版**をクリック) |
| Power BI Desktop |[無料ダウンロード](https://powerbi.microsoft.com/get-started/) (**無料ダウンロード**をクリック) |

各テクノロジの基本的な知識があることが望ましいですが、これらのテクノロジの一部になじみがない場合でも、シナリオを完了できます。 次のコンテンツを使用すると、すばやく習得できます。

* [SharePoint の使用を開始する](https://support.office.com/article/Get-started-with-SharePoint-909ec2f0-05c8-4e92-8ad3-3f8b0b6cf261)
* [Power Apps ガイド付き学習](../../guided-learning/index.md)
* [ガイド付き学習の自動化機能](https://docs.microsoft.com/flow/guided-learning/)
* [Power BI ガイド付き学習](https://docs.microsoft.com/power-bi/guided-learning/)

## <a name="next-steps"></a>次の手順
このチュートリアル シリーズの次の手順では、シリーズ全体で使用する [SharePoint Online リストを設定](sharepoint-scenario-setup.md)します。

