---
title: DateValue、TimeValue、および DateTimeValue 関数 | Microsoft Docs
description: Power Apps の DateValue、TimeValue、DateTimeValue 関数のリファレンス情報、構文、および例
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/16/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fc28b370b36be8d309c292e110d0b927d08c4a11
ms.sourcegitcommit: cf492063eca27fdf73459ff2f9134f2ca04ee766
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79436719"
---
# <a name="datevalue-timevalue-and-datetimevalue-functions-in-power-apps"></a>Power Apps の DateValue、TimeValue、および DateTimeValue 関数

*文字列*内の日付、時刻、またはその両方を*日付/時刻*値に変換します。

## <a name="description"></a>説明

- **DateValue**関数は、*日付文字列*("10/01/2014" など) を*日付/時刻*値に変換します。

- **Timevalue**関数は、*時刻文字列*(たとえば、"12:15 PM") を*日付/時刻*値に変換します。

- **DateTimeValue**関数は、*日付と時刻の文字列*(たとえば、"January 10, 2013 12:13 AM") を*日付/時刻*値に変換します。

**DateValue**関数は、日付文字列内のすべての時刻情報を無視し、 **timevalue**関数は、時刻文字列のすべての日付情報を無視します。

> [!NOTE]
> DateValue、TimeValue、および DateTimeValue 関数は、既定で現在のユーザーの設定の言語を使用します。 これをオーバーライドして、文字列が正しく解釈されるようにすることができます。 たとえば、"10/1/1920" は、"*en*" では*10 月 1<sup>st</sup>*  、"*Fr*" では*1 月10日<sup>th</sup>* と解釈されます。

日付は、以下の形式のいずれかである必要があります。

- MM/DD/YYYY
- DD/MM/YYYY
- DD Mon YYYY
- Month DD, YYYY

数値の日付、月、年のコンポーネントから変換する場合は、読み取り[日](function-date-time.md)を指定します。 <br>
時間、分、および秒の数値から変換するには、読み取り[時間](function-date-time.md)。

詳細については、次を参照してください。

- [日付と時刻の使用](../show-text-dates-times.md)。
- [日付/時刻とデータ型](data-types.md#date-time-and-datetime)。

## <a name="syntax"></a>構文

**DateValue**( *String* [, *Language* ])<br>
**DateTimeValue**( *String* [, *Language* ])<br>
**TimeValue**( *String* [, *Language* ])

* *String* - 必須。 日付、時刻、または日付と時刻の組み合わせの値を含むテキスト文字列。
* *Language* - 省略可能。 [言語関数の](function-language.md)最初の2文字によって、などの言語文字列が返されます。  指定しない場合は、現在のユーザーの設定の言語が使用されます。  

## <a name="examples"></a>使用例

### <a name="datevalue"></a>DateValue

" **Startdate**" という名前のテキスト入力コントロールに「 **10/11/2014** 」と入力し、ラベルの[text](../controls/properties-core.md)プロパティを次の数式に設定します。

- ユーザーのロケールの文字列から日付を変換し、その結果を長い日付として表示します。

    ```powerapps-dot
    Text( DateValue( Startdate.Text ), DateTimeFormat.LongDate )
    ```

    [ **En** locale に設定されたデバイス] ラベルを、 **2014 年10月 11**日の土曜日として表示します。
  
    > [!NOTE]
    > **Longdatetime**と比較して、 **DateTimeFormat**ではいくつかのオプションを使用できます。 オプションの一覧を表示するには、数式バーにパラメーターを入力し、その後に感嘆符 ( **!** ) を入力します。

- フランス語のロケールの文字列から日付を変換し、その結果を長い日付として表示します。 この例では、月と日は英語とは異なる方法で解釈されます。

    ```powerapps-dot
    Text( DateValue( Startdate.Text, "fr" ), DateTimeFormat.LongDate )
    ```
  
    [ **En** locale] に設定されている場合、ラベルは、 **2014 年11月10日の月曜日**として表示されます。

**2014 年10月20日を**入力した場合は、次のようになります。

- ユーザーのロケールの文字列から日付を変換し、2日 (日数) の差を計算します。

    ```powerapps-dot
    DateDiff( DateValue( Startdate.Text ), Today() )
    ```
  
    [ **En** locale に設定されたデバイス] ラベルを**9**として表示し、10月11日から10月20日までの日数を示します。 [DateDiff](function-dateadd-datediff.md)関数では、月、四半期、または年の差を示すこともできます。

### <a name="datetimevalue"></a>DateTimeValue

「 **Start**」という名前のテキスト入力コントロールに**10/11/2014 1:50: 24.765 PM**を入力し、ラベルの[text](../controls/properties-core.md)プロパティを次の式に設定したとします。

- 現在のロケールの日付と時刻の両方の文字列を変換します。
 
    ```powerapps-dot
    Text( DateTimeValue( Start.Text ), DateTimeFormat.LongDateTime )
    ```    
    
    [ **En** locale に設定されたデバイス] ラベルを、 **2014 年10月11日 1:50:24 PM**として表示します。
  
  > [!NOTE]
  > **Longdatetime**と比較して、 **DateTimeFormat**ではいくつかのオプションを使用できます。 オプションの一覧を表示するには、数式バーにパラメーターを入力し、その後に感嘆符 ( **!** ) を入力します。

- フランス語のロケールで日付と時刻の両方の文字列を変換します。 月と日は異なる方法で解釈されます。

    ```powerapps-dot
    Text( DateTimeValue( Start.Text, "fr"), DateTimeFormat.LongDateTime )
    ```
  
    [ **En** locale] に設定されている場合、ラベルは、 **2014 年11月10日 1:50:24 PM**として表示されます。

- ユーザーのロケールで日付と時刻の文字列の両方を変換し、秒の小数部を使用して結果を表示します。

    ```powerapps-dot
    Text( DateTimeValue( Start.Text ), "dddd, mmmm dd, yyyy hh:mm:ss.fff AM/PM" )
    ```
  
    [ **En** locale] に設定されている場合、ラベルは "**土曜日, 10 月11日 2014 01:50: 24.765 PM**" と表示されます。
  
    別の方法として、 **hh: mm: ss. f**または**hh: mm: ff**を指定して、時刻<sup>を10番目また</sup>は<sup>100 番</sup>目の最も近い秒に丸めることができます。

### <a name="timevalue"></a>TimeValue

テキスト入力コントロールに**finishedat**という名前を付け、ラベルの[text](../controls/properties-core.md)プロパティを次の数式に設定します。

```powerapps-dot
If( TimeValue( FinishedAt.Text ) < TimeValue( "5:00:00.000 PM" ), 
    "You made it!", 
    "Too late!"
)
```

- **Finishedat**コントロールに「 **4:59: 59.999 まで PM** 」と入力すると、ラベルに "*作成しまし*た" と表示されます。
- **Finishedat**コントロールに「 **5:00: 00.000 PM** 」と入力すると、ラベルに "*遅すぎ*ます" と表示されます。
