---
title: 'サンプル: ユーザー定義ワークフロー活動でクレジット スコアを計算する(Common Data Service) | Microsoft Docs'
description: このサンプルでは、ワークフロー活動は、社会保障番号 (SSN) と名前に基づいて信用度を計算します。
ms.custom: ''
ms.date: 1/28/2020
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: samples
applies_to:
- Dynamics 365 (online)
ms.assetid: 9cb7eb41-1a73-44a8-ae58-14120e84243f
caps.latest.revision: 19
author: JimDaly
ms.author: jdaly
manager: KumarVivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: cb66d92382f38a6646a80f889a97f2d6bed49e7e
ms.sourcegitcommit: 4d858e628c89d245317d6192801d136f3591ea52
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "2994603"
---
# <a name="sample-calculate-a-credit-score-with-a-custom-workflow-activity"></a>サンプル: ユーザー定義ワークフロー活動でクレジット スコアを計算する

このサンプル コードは、Common Data Service 向けです。 [WorkflowActivities](https://github.com/microsoft/PowerApps-Samples/tree/master/cds/orgsvc/C%23/WorkflowActivities) からサンプル全体をダウンロードします。

## <a name="prerequisites"></a>前提条件

[!INCLUDE [sdk-prerequisite](../../../includes/sdk-prerequisite.md)]
  
## <a name="requirements"></a>要件

このユーザー定義のワークフロー活動が機能するためには次のカスタマイズが存在している必要があります。  

-   エンティティ スキーマ名: `new_loanapplication`  
-   属性: `new_loanapplicationid` (主キーとして)  
-   属性: `int` 型の `new_creditscore` (更新される場合は最小値 0、最大値 1000)  
-   属性: money 型の `new_loanamount` (既定の最小値/最大値)  
-   属性 `new_loanapplicantid` を含めるためのフォームのカスタマイズ  
  
取引先担当者エンティティには、次のカスタマイズが含まれる必要があります。  
  
-   属性: **1 行テキスト** としての `new_ssn` (最大長 15)  
-   次のプロパティを含む一対多関連付け:  
    -   関連付けの定義のスキーマ名: `new_loanapplicant`  
    -   関連付けの定義に関連するエンティティ表示名: ローン申し込み  
    -   関連付けの属性スキーマ名: `new_loanapplicantid`  
    -   関連付け動作のタイプ: 参照  
  
## <a name="demonstrates"></a>説明

次のサンプルでは、ワークフロー活動は、社会保障番号 (SSN) と名前に基づいて信用度を計算します。  
  
## <a name="example"></a>例  

[RetrieveCreditScore.cs](https://github.com/microsoft/PowerApps-Samples/blob/master/cds/orgsvc/C%23/WorkflowActivities/WorkflowActivities/RetrieveCreditScore.cs)

### <a name="see-also"></a>関連項目

[ワークフローの拡張機能](workflow-extensions.md)<br />
[チュートリアル: ワークフロー拡張の作成](tutorial-create-workflow-extension.md)<br />
[サンプル: カスタム ワークフロー活動の作成](sample-create-custom-workflow-activity.md)<br />
[サンプル: ユーザー定義ワークフロー活動を使用した次回の誕生日の更新](sample-update-next-birthday-using-custom-workflow-activity.md)
