---
title: Power Platform 用の病院の緊急時対応サンプル ソリューションの概要 | Microsoft Docs
description: 病院の緊急時対応ソリューションの概要について説明します。
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
ms.openlocfilehash: 1923c9a39fe4cc820de05acc8d8225500c2711af
ms.sourcegitcommit: 263a12aefa72a3d73e07b2660bf1e89eba532a16
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2020
ms.locfileid: "81441261"
---
# <a name="hospital-emergency-response---power-platform-sample-solution"></a>病院の緊急時対応 - Power Platform サンプル ソリューション

病院の緊急時対応サンプル ソリューションには、医療機関向けの一連の機能が用意されており、使用可能なベッドと消耗品、COVID-19 関連の患者、スタッフ配置、退院待ちに関する状況を把握するためのデータを収集できます。 また、このソリューションには、主要なデータと分析情報をまとめるダッシュボードが備わっており、情報に基づいた意思決定を行って効率的なリソースの展開と使用を実現することができます。

> [!div class="mx-imgBorder"] 
> ![病院の緊急時対応アプリ](media/conf-ermerg-response-solution-overview.png)

病院の緊急時対応ソリューションの主要なコンポーネントは次のとおりです。

- **現場スタッフ向けのモバイル アプリ**:看護師や医師などの現場スタッフは、モバイル アプリを使用して、必要に応じてすばやく情報の表示と入力を行うことができます。
- **病院の管理者向けの Web アプリ**:病院の管理者は、このアプリを使用して、ソリューションを機能させるために必要なシステム データの追加と管理を行うことができます。
- **医療の意思決定者向けのダッシュボード**:ダッシュボードを使用すると、効率的な意思決定に役立つ重要なデータとメトリックをすばやく表示できます。

病院の緊急時対応サンプル ソリューションは、次の言語でご利用いただけます。英語、フランス語、ドイツ語、イタリア語、日本語、ポルトガル語 - ブラジル、スペイン語。


## <a name="demo-quick-overview"></a>デモ:簡単な概要

病院の緊急時対応ソリューションの簡単な概要をご覧ください。

<br/>

> [!VIDEO https://www.youtube.com/embed/Dg-i3F9G01I]

## <a name="licensing-requirements"></a>ライセンス要件

- Power Apps ライセンス。
- このソリューションの一部として利用可能な Power BI ダッシュボードを使用する場合は、Power BI ライセンス。

ライセンスに関する質問については、ご自分のローカル Microsoft アカウント担当者にお問い合わせください。

参照:[Power Platform のライセンスの概要](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)

## <a name="start-here"></a>ここから開始

|タスク | 対象読者|データの|
|--|--|--|
|サンプル アプリとダッシュボードをデプロイする|IT 管理者|[病院の緊急時対応アプリをデプロイする](deploy-configure.md)|
|管理アプリを使用してマスター データの追加、管理を行う|ビジネス管理者|[組織のマスター データを構成して管理する](configure-data-reporting.md#configure-and-manage-master-data-for-your-organization)|
|分析情報と意思決定のためにダッシュボードを使用する|ビジネス管理者|[Common Data Service ダッシュボードを表示する](configure-data-reporting.md#view-common-data-service-dashboards)<br/><br/>[Power BI ダッシュボードを表示する](configure-data-reporting.md#view-power-bi-dashboard)|
|モバイル アプリを使用して、人工呼吸器、スタッフ配置、退院待ち、および COVID-19 関連の患者に関するデータを追跡する|現場スタッフ|[病院の緊急時対応モバイル アプリを使用する](use.md)
|管理アプリを使用してモバイル アプリからのフィードバックを追跡する|ビジネス/IT 管理者|[アプリのフィードバックを表示して管理する](configure-data-reporting.md#view-and-manage-app-feedback)|


## <a name="issues-and-feedback"></a>問題とフィードバック

- 病院の緊急時対応サンプル アプリに関する問題を報告するには、<https://aka.ms/emergency-response-issues> にアクセスしてください。

- 病院の緊急時対応サンプル アプリに関するフィードバックについては、<https://aka.ms/emergency-response-feedback> にアクセスしてください。

### <a name="disclaimer"></a>免責事項

これはサンプル ソリューションであり、参照用情報の頒布のみを目的として、Microsoft Power Apps および Microsoft Power BI と共に使用することができます。 このアプリは、病気やその他の疾患の診断、治療、軽減、手当て、または防止のために使用することを想定した医療デバイス、臨床サポート、診断ツール、またはその他のテクノロジとして使用することを意図したものではありません。このアプリをそのような目的のために使用するためのライセンスや権限は、Microsoft によって付与されていません。 このアプリは、専門的な医療のアドバイス、診断、手当て、または判断の代替となるように設計または意図されたものではないため、そのようには使用しないでください。 お客様は、このアプリのいかなる使用に関しても単独でリスクと責任を負うものとします。 Microsoft では、このアプリまたはアプリと共に提供される関連資料が、何らかの医療目的のために適切であることや、任意の人物の健康または医療に関する要求を満たすものであることを保証しません。
