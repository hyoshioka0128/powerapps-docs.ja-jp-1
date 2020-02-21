---
title: Trace 関数 | Microsoft Docs
description: 構文など、Power Apps テスト スタジオの Trace 関数のリファレンス情報
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/19/2018
ms.author: aheneay
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 23bfbb3b97764a427d5422e4ad207d4af7cc1589
ms.sourcegitcommit: 3b68c4e29be4e8f68c0bfb88abdd1bbdf0187c57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "77530790"
---
# <a name="trace-function"></a>Trace 関数 

Trace は、テスト スタジオで使用する場合、**OnTestCaseComplete** イベントからのテスト結果で追加情報を提供するために使用できる省略可能な式です。 トレース イベント メッセージおよび合格と不合格両方のアサーションに対するメッセージが、TestCaseResult レコードの Traces テーブルに含まれます。 Traces テーブルには、Message と Timestamp の 2 つのプロパティがあります。 

アプリでトレースメッセージを定義することもできます。 これらは、アプリのリアルタイム診断情報に関する問題をデバッグまたは特定するのに役立つ、他のアプリアクティビティと共に、Power Apps Monitor ツールで表示できます。 アプリで Azure Application Insights にテレメトリ データを送信できるようにした場合、Trace 関数を使用して、Application Insights リソースにイベントまたは診断のカスタム情報を送信することもできます。 Application Insights でこのデータを調べて、問題を診断したり、アプリと機能の使用状況を把握したりすることができます。 Tests で使用されるトレース情報も、Application Insights に記録されます。 テストトレース情報は、[モニター] ツールでは使用できません。これは、モニターが Canvas studio から再生されるときにアプリに接続されるためです。 

## <a name="syntax"></a>構文

*Trace(message, severity, custom_record )*

- *Message* – 必須。 トレースされる情報。 テストでは、これにより TestCaseResult レコードの Traces テーブルにレコードが作成されます。 
- *Severity* - 省略可能。 Application Insights に記録されたトレースの重大度レベル。 オプションは、Information、Warning、または Error です。 
- *custom_record* - 省略可能。 Application Insights に記録されるカスタム データを含むレコード。 
  

### <a name="see-also"></a>関連項目

[テスト スタジオの概要](../test-studio.md) <br>
[テスト スタジオの操作](../working-with-test-studio.md)
