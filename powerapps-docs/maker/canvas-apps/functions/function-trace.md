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
ms.openlocfilehash: 86d28400e0eaea89b59286df173d0e67655bb7a5
ms.sourcegitcommit: 6b2961308c41867756ecdd55f55eccbebf70f7f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "76541246"
---
# <a name="trace-function"></a>Trace 関数 

Trace は、テスト スタジオで使用する場合、**OnTestCaseComplete** イベントからのテスト結果で追加情報を提供するために使用できる省略可能な式です。 トレース イベント メッセージおよび合格と不合格両方のアサーションに対するメッセージが、TestCaseResult レコードの Traces テーブルに含まれます。 Traces テーブルには、Message と Timestamp の 2 つのプロパティがあります。 

アプリで Azure Application Insights にテレメトリ データを送信できるようにした場合、Trace 関数を使用して、Application Insights リソースにイベントまたは診断のカスタム情報を送信することもできます。 Application Insights でこのデータを調べて、問題を診断したり、アプリと機能の使用状況を把握したりすることができます。 Tests で使用されるトレース情報も、Application Insights に記録されます。 すべてのトレース メッセージは Power Apps Monitor ツールでも表示でき、アプリのリアルタイム診断セッションでの問題のデバッグまたは特定に役立ちます。   

## <a name="syntax"></a>構文

*Trace(message, severity, custom_record )*

- *Message* – 必須。 トレースされる情報。 テストでは、これにより TestCaseResult レコードの Traces テーブルにレコードが作成されます。 
- *Severity* - 省略可能。 Application Insights に記録されたトレースの重大度レベル。 オプションは、Information、Warning、または Error です。 
- *custom_record* - 省略可能。 Application Insights に記録されるカスタム データを含むレコード。 
  

### <a name="see-also"></a>参照

[テスト スタジオの概要](../test-studio.md) <br>
[テスト スタジオの操作](../working-with-test-studio.md)
