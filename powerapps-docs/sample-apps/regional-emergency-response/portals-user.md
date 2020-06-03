---
title: 地域政府機関の緊急応答およびモニタリング ポータルを使用する | Microsoft Docs
description: 地域政府機関の緊急応答およびモニタリング ポータルを医療従事者として使用する方法を学びます。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 05/04/2020
ms.author: tapanm
ms.reviewer: tapanm
searchScope:
- PowerApps
ms.openlocfilehash: 115cf6a5c1c622374de42230e07e09462cc6de41
ms.sourcegitcommit: c424a17b9c658f4571b5ea26ab6fc8a486051d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "3341757"
---
# <a name="use-the-regional-governmentemergency-response-and-monitoring-portal"></a>地域政府機関の緊急応答およびモニタリング ポータルを使用する

病院のスタッフは、緊急時にサプライチェーンを管理しながら、患者数の増加に対応する必要があります。 地域政府機関の緊急応答およびモニタリング ポータルを使用ことにより、医療従事者は人工呼吸器、スタッフの配置、退院待ち、および新型コロナウイルス関連の患者に関するデータの表示や追加を迅速に行うことができます。

## <a name="portal-at-a-glance"></a>ポータルの概要

スタッフの配置、備品、消耗品、患者、およびその他の領域を扱うため Power Apps ポータルを参照します。 次のセクションでは、ポータルの医療ユーザーとしてアクセス、送信、または更新できる内容を手順を追って説明します。

![ポータルの概要 ](media/portal-user-at-glance.png)

地域政府機関の緊急応答およびモニタリング ポータルを使用する場合、Apple iPad を除き、最新のモバイル デバイスや Web ブラウザーを使用できます。

[!include[cc-getting-started](includes/cc-getting-started.md)]

[!include[cc-manage-user-profile](includes/cc-manage-user-profile.md)]

## <a name="portal-components"></a>ポータル コンポーネント

地域政府機関の緊急応答およびモニタリング ポータルは、次のコンポーネントで構成されます。

- **ベッドのキャパシティ**  
  ベッドのライセンス、容量、鋭敏さ、スタッフのベッド、および急増データに関する詳細を収集します。

- **スタッフ**  
  設備の場所ごとに RN の状態を収集します。

- **備品**  
  人工呼吸器や NIPPV デバイスなどの備品の詳細を収集します。

- **消耗品**  
  在庫の追跡、管理、および予測をより効果的に行うために、主要な消耗品を収集します。 

- **COVID-19 の統計**  
  COVID-19 の検査中である患者数と、検査が陽性と判定された患者数についての状態を収集します。


## <a name="bed-capacity"></a>ベッドのキャパシティ

選択された場所の患者の情報、ベッド、およびスタッフのキャパシティを更新するには**ベッドのキャパシティ**を選択します。

![ベッドのキャパシティ](media/portal-user-bed-capacity.png)

### <a name="options-and-description"></a>オプションおよび説明

| **オプション名**                                               | **説明**                                                                       |
|---------------------------------------------------------------|---------------------------------------------------------------------------------------|
| 現在使用中の許可ベッド数  | この施設で現在使用されている認可された病床数。                            |
| 現在使用中の ICU ベッド数 (空気感染隔離室)               | この設備で現在使用中の空気感染隔離室 (AIIR) の ICU ベッド数。                                      |
| 現在使用中の (空気感染隔離室でない) ICU ベッド数           | この設備で現在使用中の (空気感染隔離室でない) ICU ベッド数。                                  |
| 現在使用中の重症治療ベッドの数 (空気感染隔離室)        | この設備で現在使用中の重症治療ベッド数 (空気感染隔離室)。                               |
| 現在使用中の重症治療ベッド数 (空気感染隔離室以外)    | この設備で現在使用中の重症治療ベッド数 (空気感染隔離室以外)。                           |
| 現在使用中の小児 ICU ベッド数 (空気感染隔離室)               | この設備で現在使用中の小児 ICU ベッド数 (空気感染隔離室)。                                      |
| 現在使用中の小児 ICU ベッド数 (空気感染隔離室以外)           | この設備で現在使用中の小児 ICU ベッド数 (空気感染隔離室以外)。                                  |
| 現在使用中の小児重症治療ベッド数 (空気感染隔離室)        | この設備で現在使用中の小児重症治療ベッド数 (空気感染隔離室)。                               |
| 現在使用中の小児重症治療ベッドの数 (空気感染隔離室以外)    | この設備で現在使用中の小児重症治療ベッド数 (空気感染隔離室以外)。                           |
| 設備は許可ベッドの全キャパシティまでスタッフが配置されていますか?    | はい/いいえ。 答えがいいえの場合、次の中から 1 つまたは複数の理由を選択できます。 <br> - スタッフ <br> - スペース <br> - 個人保護具 (PPE) <br> - 備品 <br> - 小規模な患者数  |
| 許可ベッド数を超えて急増できますか?              | はい/いいえ。 答えがいいえの場合、次の中から 1 つまたは複数の理由を選択できます。 <br> - スタッフ <br> - スペース <br> - 個人保護具 (PPE) <br> - 備品 <br> - 小規模な患者数  |
| 現在使用中の急増対応ベッドの数                         | この設備で現在使用中の急増対応ベッドの数。 
| 現在使用中の霊安室の数                                            | この設備で現在使用中の霊安室の数。 <br> **注意**: 選択された設備の*合計霊安室のキャパシティ*が少なくとも 1 つの場合のみ表示されます。

### <a name="previous-submissions"></a>前の送信

**ベッドのキャパシティ**、または **スタッフ**、**備品**、**消耗品**、または**新型コロナウイルス 統計**などの他のコンポーネントを開いた場合、最終送信日、時間、および送信者を確認できます。

**ベッドのキャパシティ**で*現在使用中の認可ベッドの数*などの、個別のフィールドを選択した場合、そのフィールドに対して送信された前の値も表示されます。

![前の値](media/previous-submissions.png)

## <a name="staff"></a>スタッフ

欠勤などのスタッフの具体的な詳細、および、*勤務中*および*現在必要*などの正看護師に関連する詳細を**スタッフ**のフォームで送信します。

![スタッフの詳細](media/portal-user-staff-details.png)

### <a name="options-and-description"></a>オプションおよび説明

| **オプション名**                               | **説明**                                                                |
|-----------------------------------------------|--------------------------------------------------------------------------------|
| 必須治療スタッフの欠勤率 | パーセンテージ形式での必須治療スタッフの欠勤。                  |
| 現在勤務中の RN の数                                    | 選択した設備で現在勤務中の正看護師の数。                 |
| 現在必要な RN の数                                  | 選択した設備で現在必要な正看護師の数。 |

## <a name="equipment"></a>備品

人工呼吸器や NIPPV デバイスなどの備品の詳細を送信します。

![機器の詳細](media/portal-user-equipment-details.png)

### <a name="options-and-description"></a>オプションおよび説明

| **オプション名** | **説明**                 |
|-----------------|---------------------------------|
| 人工呼吸器     | 使用中の人工呼吸器の数。   |
| NIPPV (非侵襲的陽圧換気)          | 使用中のNIPPV (非侵襲的陽圧換気) デバイスの数。 |

## <a name="supplies"></a>消耗品

過去 24 時間に在庫があり使用された消耗品在庫を送信します。

![消耗品の詳細](media/portal-user-supplies-details.png)

### <a name="options-and-description"></a>オプションおよび説明

消耗品アプリの項目一覧は、組織の要件によって異なる場合があります。 消耗品名の説明については、組織のリソースを参照してください。

> [!NOTE]
> 消耗品在庫の項目の値は、数値形式である必要があります。 供給番号は**個別のコンポーネント**のものです。 たとえば N-95 マスクは、マスクを含むボックスの数ではなく、各個別のマスクごとにカウントされます。

## <a name="covid-19-stats"></a>COVID-19 の統計

 **新型コロナウイルス** フォームを使用して新型コロナウイルス固有の詳細を送信します。

![統計](media/portal-user-stats.png)

### <a name="options-and-description"></a>オプションおよび説明

| **オプション名**                                                   | **説明**                                                    |
|-------------------------------------------------------------------|--------------------------------------------------------------------|
| 検査中の患者の数 (PUI)                     | この設備で検査中の患者の数。                            |
| 新型コロナウイルスが確定した患者の数                        | この設備で新型コロナウイルスが確定した患者の数。                        |
| 挿管された患者の数                                      | この設備で挿管された患者の数。                                      |
| 過去 24 時間に退院した新型コロナウイルス患者の数 | この設備で過去 24 時間に退院した新型コロナウイルス患者の数。 |

## <a name="general-portal-options"></a>全般 ポータル オプション

[!include[cc-general-options](includes/cc-general-options.md)]

## <a name="issues-and-feedback"></a>問題とフィードバック

- 地域政府機関の緊急応答およびモニタリング ソリューションに関する問題を報告するには、<https://aka.ms/rer-issues> を参照してください。

- 地域政府機関の緊急応答およびモニタリング ソリューションに関するフィードバックについては、<https://aka.ms/rer-feedback> を参照してください。