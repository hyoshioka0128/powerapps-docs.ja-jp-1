---
title: Common Data Service でビジネス ロジックを適用する | MicrosoftDocs
description: アプリで使用可能なビジネス ロジックのさまざまな種類について説明する
ms.custom: ''
ms.date: 12/20/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9267f8385e19d3c0b87a36b495a4ff2b88b4d420
ms.sourcegitcommit: f70be39855e4931312fe0035525586a15ed4487b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2019
ms.locfileid: "2922374"
---
# <a name="apply-business-logic-in-common-data-service"></a>Common Data Service でビジネス ロジックを適用する
Common Data Service にビジネスロジックを適用するには、いくつかの選択肢があります。 

## <a name="business-rules"></a>業務ルール
業務ルールおよびビジネス レコメンデーションを作成し、 コードの記述またはプラグインの作成を行わずにロジックおよび検証を適用できます。業務ルールは、変化が急速で、よく使用される業務ルールを実装および保守するための、単純なインターフェイスを提供します。

すべてのエンティティ フォームおよびサーバー レベルで当てはまるエンティティの*業務ルール*を定義します。 エンティティに対して定義された業務ルールは、エンティティがアプリで使用される場合、*キャンバス アプリ*および*モデル駆動型アプリ*の両方に適用されます。 詳細: [エンティティに対する業務ルールの作成](data-platform-create-business-rule.md)

> [!NOTE]
> モデル駆動型アプリのフォームに適用される業務ルールを定義するには、[モデル駆動型アプリ フォームに対する業務ルールを作成する](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md) を参照してください。

## <a name="power-automate"></a>Power Automate
Power Automate には、 Common Data Service 内や Common Data Service と他のアプリやサービスとの間で自動化されたワークフローを作成するためのフローがいくつか用意されており、ファイルの同期、通知の取得、データの収集などに使用できます。 


|フローの種類  |説明  |詳細  |
|---------|---------|---------|
|業務プロセス フロー     | Power Apps のモデル駆動型アプリで実行される一連のステップを定義し、人々がそれに従うことで望ましい結果が得られるようにします。        | [詳細](/power-automate/create-business-process-flow)     |
|自動化されたフロー     |  イベントによってトリガーされたら 1 つまたは複数のタスクを自動的に実行するフローを作成します。    | [詳細](/power-automate/get-started-logic-flow)        |
|ボタン フロー   | モバイル デバイス の フロー アプリを介することで、いつでもどこからでも定型タスクを実行することができます。        | [詳細](/power-automate/introduction-to-button-flows)        |
|スケジュールされたフロー   | スケジュール上で1つ以上のタスクを実行するフローを作成します。    | [詳細](/power-automate/run-scheduled-tasks)        |
|UI フロー   | 従来のソフトウェアで行われていた手動ステップを記録し自動再生します。    | [詳細](/power-automate/ui-flows/overview)     |


## <a name="classic-common-data-service-processes"></a>Common Data Service プロセス の クラス
ワークフローと操作である従来の Common Data Service プロセスも使用できます。 詳細: [Power Automate: ワークフロー プロセスの使用](/flow/workflow-processes) と [Power Automate: 操作の概要](/flow/actions)。

### <a name="see-also"></a>関連項目

[モデル駆動型アプリでビジネス ロジックの適用](../model-driven-apps/guide-staff-through-common-tasks-processes.md)
