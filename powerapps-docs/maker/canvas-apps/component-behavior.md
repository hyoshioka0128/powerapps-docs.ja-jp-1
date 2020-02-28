---
title: コンポーネントの動作の数式 |Microsoft Docs
description: コンポーネントベースのアクションが発生したときに、canvas アプリで1つ以上のタスクを実行します。
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 02/20/2020
ms.author: yifwang
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 28ea432e5d09684029f104d69f593e24dcc4cc14
ms.sourcegitcommit: 59f0b3adc56279b5673cbf04b4a55bd7678e1ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2020
ms.locfileid: "77910994"
---
# <a name="behavior-formulas-for-components"></a>コンポーネントの動作に関する数式

> [!IMPORTANT]
> この機能は依然としてパブリックプレビューの段階にあります。 詳細については、[試験的な機能とプレビュー機能](working-with-experimental.md)に関する記事を参照してください。

イベントによってコンポーネントインスタンスの変更がトリガーされたときに実行される1つまたは複数の[動作の数式](working-with-formulas-in-depth.md)を指定します。 

たとえば、コンポーネントの**Onreset**プロパティを初期化を行う1つまたは複数の数式に設定し、入力をクリアします。 コンポーネントインスタンスで**reset**関数を実行すると、値がリセットされます。

## <a name="onreset"></a>OnReset

コンポーネントマスターを選択した状態で、プロパティのドロップダウンリスト (数式バーの左側) で **[Onreset]** を選択し、1つまたは複数の数式を入力します。

> [!div class="mx-imgBorder"]
> ![OnReset の例](./media/component-behavior/example-onreset.png)

**Onreset**をテストするには、コンポーネントをリセットするようにコントロールを構成します。 たとえば、ボタンの**Onselect**プロパティを「 **Reset**(*ComponentName*)」という数式に設定します。

### <a name="example---reset-timer"></a>例-タイマーのリセット

> [!div class="mx-imgBorder"]
> ![OnReset の例](./media/component-behavior/Resettimer.gif)

このタイムピッカーコンポーネントでは、時間 _selectedHour と _selectedMinute を表示するために2つの変数が使用されます。 ピッカーがリセットされたら、これらの変数を既定値にリセットします (たとえば、12:12)。  コンポーネントの OnReset プロパティには、次の式があります。 **Set (_selectedHour, 12);セット (_selectedMinute、12)**

リセットをトリガーするには、画面にアクセスし、コンポーネントのインスタンスを挿入します。 ボタンを追加し、 **reset (TimerComponent_instance)** を呼び出して onselect をトリガーするボタンの onselect を構成します。

> [!div class="mx-imgBorder"]
> ![リセットボタン](./media/component-behavior/reset-button.png)

## <a name="update-onreset-using-custom-property"></a>カスタムプロパティを使用して OnReset を更新する

コンポーネントの外部からコンポーネントインスタンスをリセットするだけでなく、内部から OnReset をトリガーするもう1つの方法もあります。 "**値の変更時に OnReset を発生させる**" は、カスタム入力プロパティを作成するときのオプションです。 また、このプロパティの値を変更して、コンポーネントの OnReset をトリガーすることができます。 このメソッドは、既定値を簡単に設定およびリセットするように設計されています。 

> ![OnReset の例](./media/component-behavior/property-trigger.png)

### <a name="example"></a>例

> [!div class="mx-imgBorder"]
> ![OnReset の例](./media/component-behavior/updateordernumber2.gif)

上記の例では、注文番号を確認し、数値を更新しています。 数値の上下のコンポーネントは、注文の数を増減するために使用されます。 左側のギャラリーを選択すると、既定の数値の上下のコンポーネントがリセットされ、選択したツールの順序番号が表示されます。 "**値の変更時に OnReset を発生させる" と**、入力の変更時に既定値をリセットできるようになりました。 

これを行うには、"既定の入力" プロパティの [値が変更され**たときに OnReset を発生させる**] チェックボックスをオンにします。 コンポーネントの**Onreset**が set **(_NumericValue、' Numeric up down ' に設定されます。DefaultValue)** 。 _numericValue は、現在の順序の値を格納する変数です。 テキスト入力コントロールの**既定値**を**If (isblank (_numericValue), ' Numeric up down ' に設定します。DefaultValue、_numericValue)** 。 

### <a name="see-also"></a>参照

- [キャンバスアプリのコンポーネントの概要](create-component.md)
- [キャンバスアプリのコンポーネントライブラリ](component-library.md)
