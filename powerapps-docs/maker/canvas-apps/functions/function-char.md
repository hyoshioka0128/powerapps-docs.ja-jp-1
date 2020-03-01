---
title: Char 関数 | Microsoft Docs
description: 構文と例を含む、Power Apps の Char 関数に関するリファレンス情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/01/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 578e196bfa55f33416de1ee551d1e63e106a612a
ms.sourcegitcommit: ed583eb94720a9645bfd79776311792a958077b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2020
ms.locfileid: "78204371"
---
# <a name="char-function-in-power-apps"></a>Power Apps の Char 関数

文字コードを文字列に変換します。

## <a name="description"></a>説明

**Char**関数は、数値を対応する ASCII 文字で文字列に変換します。

## <a name="syntax"></a>構文

**Char**( *CharacterCode* )

- *CharacterCode* - 必須。 変換する ASCII 文字コード。

## <a name="examples"></a>使用例

| [数式] | 説明 | 結果 |
| --- | --- | --- |
| **Char( 65 )** |ASCII コード 65 に対応する文字を返します。 |ある |
| **Char( 105 )** |ASCII コード 105 に対応する文字を返します。 |から |
| **Char( 35 )** |ASCII コード 35 に対応する文字を返します。 |"#" |

### <a name="display-a-character-map"></a>文字コード表を表示する

1. タブレットアプリの空の画面で、横レイアウトが**空白**の[**ギャラリー**](../controls/control-gallery.md)コントロールを追加し、次のプロパティを設定します。

    - **項目**: `[0,1,2,3,4,5,6,7]`
    - **幅**: 800
    - **高さ**: 500
    - **Templatesize**: 100
    - **Templatepadding**: 0

1. そのギャラリー内で、垂直レイアウトが**空**の**ギャラリー**コントロールを追加し、次のプロパティを設定します。

    - **項目**: `ForAll( [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 )`
    - **幅**: 100
    - **高さ**: 500
    - **Templatesize**:30
    - **Templatepadding**: 0

    **Items**プロパティの値は、1つ目のギャラリーの**Items**プロパティの value 列によって指定された列番号で16を乗算します (`ThisItem.Value`では 0-7)。 次に、数式によって、2番目のギャラリー ( [**ForAll**](function-forall.md)関数によって提供されるレコードスコープ内の 0-15) のいずれかの行番号に結果が追加されます。

1. 2番目 (垂直) のギャラリー内で、**ラベル**コントロールを追加し、次のプロパティを設定します。

    - **テキスト**: `ThisItem.Value`
    - **幅**:50

1. 2番目 (垂直) のギャラリー内で別の**ラベル**コントロールを追加し、次のプロパティを設定します。

    - **テキスト**: `Char( ThisItem.Value )`
    - **幅**:50
    - **X**:50

最初の 128 ASCII 文字のグラフを作成しました。 小さい四角形として表示される文字は印刷できません。

![最初の 128 ASCII 文字](media/function-char/chart-lower.png)

拡張 ASCII 文字を表示するには、2番目のギャラリーの**Items**プロパティを次の数式に設定します。これにより、各文字値に128が追加されます。

`ForAll( [0,1,2,3,4,5,6,7,8,9,10,11,12,13,14,15], Value + ThisItem.Value * 16 + 128)`

![拡張 ASCII 文字](media/function-char/chart-higher.png)

文字を別のフォントで表示するには、2番目のラベルの **[フォント]** プロパティを **"ダンススクリプト"** などの値に設定します。

![ダンススクリプト](media/function-char/chart-higher-dancing-script.png)
