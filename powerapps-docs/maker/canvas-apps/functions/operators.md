---
title: 演算子と識別子 |Microsoft Docs
description: 構文と例を含む Power Apps の演算子と識別子の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 02/29/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8c7f982f4d2eca1b097a312f74aff70063bf3396
ms.sourcegitcommit: 129d004e3d33249b21e8f53e0217030b5c28b53f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78265122"
---
# <a name="operators-and-identifiers-in-power-apps"></a>Power Apps の演算子と識別子

これらの演算子の一部は、作成者の言語に依存します。  詳細については、[グローバル アプリ](../global-apps.md)に関する記事を参照してください。


|                               シンボル                                |                        種類                         |                                                                                    構文                                                                                    |                                                                                                                           説明                                                                                                                            |
|---------------------------------------------------------------------|-----------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                **.**                                |                  プロパティ セレクター                  |                                                               **Slider1.Value<br>Color.Red<br>Acceleration.X**                                                               |                                               [テーブル](../working-with-tables.md)、コントロール[、シグナル](signals.md)または列挙からプロパティを抽出します。  旧バージョンとの互換性のために **!** を使用することもできます。                                                |
| **.**<br>[[言語依存](../global-apps.md)]  |                  小数点                  |                                                             **1.23**                                                           |                                                                              数値の整数部分と小数部分の区切り記号。 文字は言語によって異なります。                                                                              |
|                               **( )**                               |                     かっこ                     |                                                               **Filter(T, A &lt; 10)**<br><br>**(1 + 2) \* 3**                                                               |                                                                                           優先順位を変更し、式の中の副次式をグループ化します。                                                                                           |
|                                **+**                                |                算術演算子                 |                                                                                  **1 + 2**                                                                                   |                                                                                                                             追加                                                                                                                             |
|                                **-**                                |                       &nbsp;                        |                                                                                  **2 - 1**                                                                                   |                                                                                                                       減算および符号                                                                                                                       |
|                              *                               |                       &nbsp;                        |                                                                                  **2 \* 3**                                                                                  |                                                                                                                          乗算                                                                                                                          |
|                                **/**                                |                       &nbsp;                        |                                                                                  **2 / 3**                                                                                   |                                                                                                   除算 ( **[Mod](function-mod.md)** 関数も参照してください)                                                                                                    |
|                                **^**                                |                       &nbsp;                        |                                                                                  **2 ^ 3**                                                                                   |                                                                                          累乗。 **[Power](function-numericals.md)** 関数に相当します                                                                                          |
|                                **%**                                |                       &nbsp;                        |                                                                                   **20%**                                                                                    |                                                                                                         百分率 (&quot;\* 1/100&quot; に相当します)                                                                                                          |
|                                **=**                                |                比較演算子                 |                                                                               **Price = 100**                                                                                |                                                                                                                             等価です。                                                                                                                             |
|                              **&gt;**                               |                       &nbsp;                        |                                                                              **Price &gt; 100**                                                                              |                                                                                                                           より大きい                                                                                                                           |
|                              **&gt;=**                              |                       &nbsp;                        |                                                                             **Price &gt;= 100**                                                                              |                                                                                                                     以上                                                                                                                     |
|                              **&lt;**                               |                       &nbsp;                        |                                                                              **Price &lt; 100**                                                                              |                                                                                                                            次の値未満                                                                                                                             |
|                              **&lt;=**                              |                       &nbsp;                        |                                                                             **Price &lt;= 100**                                                                              |                                                                                                                      以下                                                                                                                       |
|                            **&lt;&gt;**                             |                       &nbsp;                        |                                                                            **Price &lt;&gt; 100**                                                                            |                                                                                                                           次の値に等しくない                                                                                                                           |
|                              **&amp;**                              |            文字列連結演算子            |                                                      **&quot;hello&quot; &amp; &quot; &quot; &amp; &quot;&quot;**                                                       |                                                                                                             複数の文字列を続けて表示します                                                                                                             |
|                      **&amp;&amp;** または **And**                      |                  論理演算子                  |                                       **Price &lt; 100 &amp;&amp; Slider1.Value = 20**<br>または **Price &lt; 100 And Slider1.Value = 20**                                       |                                                                                         論理積。 **[And](function-logicals.md)** 関数に相当します                                                                                          |
|                     **&#124;&#124;** または **Or**                      |                       &nbsp;                        |                                        **Price &lt; 100 &#124;&#124; Slider1.Value = 20** または **Price &lt; 100 Or Slider1.Value = 20**                                        |                                                                                          論理和。 **[Or](function-logicals.md)** 関数に相当します                                                                                          |
|                          **!** または **Not**                           |                       &nbsp;                        |                                                              **!(Price &lt; 100)** または **Not (Price &lt; 100)**                                                               |                                                                                           論理否定。 **[Not](function-logicals.md)** 関数に相当します                                                                                           |
|                             **exactin**                             |  [メンバーシップ演算子](#in-and-exactin-operators)  |                                                                   **Gallery1.Selected exactin SavedItems**                                                                   |                                                                                       [コレクション](../working-with-data-sources.md#collections)またはテーブルに属しています                                                                                        |
|                             **exactin**                             |                       &nbsp;                        |                                           **&quot;Windows&quot; exactin “To display windows in the Windows operating system...”**                                            |                                                                                                                 部分文字列をテストします (大文字小文字を区別します)                                                                                                                  |
|                               **in**                                |                       &nbsp;                        |                                                                     **Gallery1.Selected in SavedItems**                                                                      |                                                                                                               コレクションまたはテーブルに属しています                                                                                                               |
|                               **in**                                |                       &nbsp;                        |                                                      **&quot;The&quot; in &quot;The keyboard and the monitor...&quot;**                                                      |                                                                                                                部分文字列をテストします (大文字小文字を区別しません)                                                                                                                 |
|                                **@**                                | [曖昧性除去演算子](#disambiguation-operator) |                                                                           **MyTable[@fieldname]**                                                                            |                                                                                                                       フィールドの曖昧性を除去します                                                                                                                       |
|                                **@**                                |                       &nbsp;                        |                                                                              **[@MyVariable]**                                                                               |                                                                                                                      グローバルの曖昧性を除去します                                                                                                                       |
| **,**<br>[[言語依存](../global-apps.md)]  |                   リストの区切り記号                    | **If( X < 10, "Low", "Good" )**<br>**{ X: 12, Y: 32 }**<br>**[ 1, 2, 3 ]** | 以下の要素を区切ります。 <ul><li>関数呼び出しの引数</li><li>[レコード](../working-with-tables.md#elements-of-a-table)のフィールド</li><li>[テーブル](../working-with-tables.md#inline-value-tables)内のレコード</li></ul> この文字は言語によって異なります。 |
| **;**<br>[[言語依存](../global-apps.md)] |                  数式のチェーン                   |                                     **Collect(T, A); Navigate(S1, &quot;&quot;)**                                     |                                                                          関数の呼び出しの動作プロパティを区切ります。 チェーン演算子は言語に依存します。                                                                          |
|                             **Parent**                              |         [Parent 演算子](#parent-operator)         |                                                                               **Parent.Fill**                                                                                |                                                                                                           コントロール コンテナーのプロパティにアクセスします                                                                                                            |
|                            **ThisItem**                             |       [ThisItem 演算子](#thisitem-operator)       |                                                                            **ThisItem.FirstName**                                                                            |                                                                                                          ギャラリーまたはフォーム コントロールのフィールドにアクセスします                                                                                                           |

## <a name="in-and-exactin-operators"></a>in 演算子と exactin 演算子
**[in](operators.md#in-and-exactin-operators)** 演算子と **[exactin](operators.md#in-and-exactin-operators)** 演算子を使用して、コレクションやインポートされたテーブルなどの[データ ソース](../working-with-data-sources.md)内の文字列を検索できます。 **[in](operators.md#in-and-exactin-operators)** 演算子は、大文字小文字を無視して一致する文字列を識別し、 **[exactin](operators.md#in-and-exactin-operators)** 演算子は、大文字小文字が一致する文字列のみを識別します。 次に例を示します。

1. **Inventory** という名前のコレクションを作成するかインポートし、「[Show images and text in a gallery](../show-images-text-gallery-sort-filter.md)」 (イメージとテキストをギャラリーに表示する) の最初の手順に従って、ギャラリーに表示します。
2. ギャラリーの **[Items](../controls/properties-core.md)** プロパティを次の数式に設定します。
   <br>**Filter(Inventory, "E" in ProductName)**

    ギャラリーには、指定した文字が名前に含まれていない唯一の製品である Callisto を除くすべての製品が表示されます。
3. ギャラリーの **[Items](../controls/properties-core.md)** プロパティを次の数式に変更します。
   <br>**Filter(Inventory, "E" exactin ProductName)**

    ギャラリーには、指定した大文字が名前に含まれている唯一の製品である Europa のみが表示されます。

## <a name="thisitem-operator"></a>ThisItem 演算子
**[ギャラリー](../controls/control-gallery.md)** 、 **[編集フォーム](../controls/control-form-detail.md)** 、または **[表示フォーム](../controls/control-form-detail.md)** コントロールをテーブルまたはコレクションにバインドすることによって、テーブルまたはコレクションのデータを表示することができます。  これらのコントロールは、他のカードまたはコントロールのコンテナーです。  コンテナー内のカードまたはコントロールは、 **[ThisItem](operators.md#thisitem-operator)** 演算子を通して、バインドされているデータにアクセスできます。   

この **[item](operators.md#thisitem-operator)** 演算子を使用して、外側のコントロール内の各カードまたはコントロールに表示されるデータの[列](../working-with-tables.md#columns)を指定します。 たとえば、「[Show images and text in a gallery](../show-images-text-gallery-sort-filter.md)」 (イメージとテキストをギャラリーに表示する) の製品ギャラリーでは、この演算子は、製品のデザインを表示するイメージ コントロール、製品名を表示する上のラベル、および在庫数を示す下のラベルを指定しています。

入れ子になっているギャラリーでは、 **[ThisItem](operators.md#thisitem-operator)** は、最も内側のギャラリー アイテムを参照します。 内側と外側のギャラリーの行フィールドが競合していないことを前提として、修飾されていないフィールド (列) 名を直接使用することもできます。 この方法によって、内側のギャラリーが外側のギャラリーのアイテムを参照するというルールが有効になります。

## <a name="parent-operator"></a>Parent 演算子
一部のコントロールは、その他のコントロールをホストします。 たとえば、 **[画面](../controls/control-screen.md)** **[ギャラリー](../controls/control-gallery.md)** **[カード](../controls/control-card.md)** **[編集フォーム](../controls/control-form-detail.md)** および **[表示フォーム](../controls/control-form-detail.md)** コントロールは、すべてがコントロールのコンテナーです。 ホストしているコントロールは、その中に含まれているコントロールの "親" と呼ばれます。

アプリ内の任意の場所から、Power Apps の任意のコントロールを名前で参照できます。 **Screen1** がアプリの画面名であるとします。 この画面の背景色を取得するには、**Screen1.Fill** を使用できます。

この画面上のコントロールには、別のオプションがあります。 それらは、相対参照である **Parent.Fill** を使用することができます。 **[Parent](operators.md#parent-operator)** 演算子は、コントロールをホストしているコントロールを参照して、ホストしているコントロールのすべてのプロパティを使用できるようにします。 **[Parent](operators.md#parent-operator)** コントロールはコントロールの名前に依存しないため、便利に使用できます。 コンテナー コントロールは、コンテナー内の参照の調整なしで、コピーして貼り付けることができます。 さらに、この演算子は、数式を読み取るときに、コントロールの親子関係を理解しやすくします。

## <a name="identifier-names"></a>識別子名

変数、データソース、列、およびその他のオブジェクトの名前には、任意の[Unicode](https://en.wikipedia.org/wiki/Unicode)を含めることができます。

空白またはその他の特殊文字を含む名前を引用符で囲んでください。  2つの単一引用符を一緒に使用して、名前の1つの一重引用符を表します。  特殊文字を含まない名前では、単一引用符は必要ありません。

ここでは、テーブルで発生する可能性のある列名の例と、それらが数式でどのように表現されるかを示します。

| データベース内の列名   | 数式内の列参照 |
|-----------------------------|-------------------------------|
| SimpleName                  | ```SimpleName``` |
| NameWith123Numbers          | ```NameWith123Numbers``` |
| 名前とスペース            | ```'Name with spaces'``` |
| 二重引用符で囲まれる名前   | ```'Name with "double" quotes'``` |
| ' Single ' 引用符を含む名前   | ```'Name with ''single'' quotes'``` |
| @ アットマークの付いた名前      | ```'Name with an @ at sign'``` |

二重引用符は、[テキスト文字列を指定](data-types.md#embedded-text)するために使用されます。  

## <a name="display-names-and-logical-names"></a>表示名と論理名
SharePoint や Common Data Service などの一部のデータソースには、同じテーブルまたはデータ列を参照する2つの異なる名前があります。

* **論理名**-一意であることが保証されている名前。作成後には変更されません。通常、スペースやその他の特殊文字は使用できず、異なる言語にローカライズされません。  結果として、名前がやや不可解になることがあります。  これらの名前は、プロの開発者によって使用されます。  たとえば、 **cra3a_customfield**です。  この名前は、"**スキーマ名**" または "**名前**" と呼ばれることもあります。

* **[表示名]** -ユーザーフレンドリで、エンドユーザーに表示されることを意図した名前。  この名前は一意ではなく、時間の経過と共に変わる可能性があります。また、スペースと Unicode 文字を含めることができ、異なる言語にローカライズされる可能性があります。  上記の例に対応して、表示名は、単語の間にスペースがある**カスタムフィールド**にすることができます。
 
表示名はわかりやすくなるため、キャンバスアプリでは、これらを選択肢として提示し、論理名を提案しません。  論理名は推奨されませんが、直接に入力した場合は使用できます。

たとえば、Common Data Service のエンティティに**カスタムフィールド**を追加したとします。  論理名は、フィールドの作成時にのみ変更できるシステムによって割り当てられます。  結果は次のようになります。

> [!div class="mx-imgBorder"]  
> カスタムフィールドが追加された ![Accounts エンティティ。 "カスタムフィールド" の表示名と "cr5e3_customfield" の論理名を示し](media/operators/customfield_portal.png)

アカウントのフィールドへの参照を作成する場合は、 **' カスタムフィールド '** を使用するように提案されます。これは表示名であるためです。  この名前にはスペースが含まれているため、単一引用符を使用する必要があることに注意してください。

> [!div class="mx-imgBorder"]  
> ![Studio の数式バーには、表示名が ' カスタムフィールド ' になっているアカウントのフィールド名の候補が強調表示されてい](media/operators/customfield_suggest_display.png)

提案を選択すると、数式バーに "カスタムフィールド" が表示され、データが取得されます。 

> [!div class="mx-imgBorder"]  
> フィールドに対して表示名 ' Custom Field ' が使用されていることを示す ![Studio の数式バー](media/operators/customfield_display.png)

これは推奨されませんが、このフィールドには論理名を使用することもできます。  これにより、同じデータが取得されます。  この名前にはスペースまたは特殊文字が含まれていないため、単一引用符は必要ありません。

> [!div class="mx-imgBorder"]  
> フィールドに論理名 cr5e3_customfield が使用されていることを示す ![Studio の数式バー](media/operators/customfield_logical.png)

バックグラウンドでは、式に表示される表示名と基になる論理名の間でマッピングが維持されます。  論理名はデータソースとの対話に使用する必要があるため、このマッピングを使用して現在の表示名から論理名に自動的に変換され、ネットワークトラフィックに表示されます。  このマッピングは、新しい表示名に切り替えるために論理名への変換にも使用されます。たとえば、表示名が変更されたり、別の言語のメーカーがアプリを編集したりした場合などです。

> [!NOTE] 
> 環境間でアプリを移動する場合、論理名は変換されません。  Common Data Service システムエンティティとフィールド名については、論理名が環境間で一貫しているため、これは問題にはなりません。  ただし、上記の例の**cra3a_customfield**などのカスタムフィールドには、異なる環境プレフィックス (この場合は**cra3a** ) を使用できます。  表示名は、新しい環境の表示名と照合できるため、優先されます。 

## <a name="name-disambiguation"></a>名前のあいまい性
表示名は一意ではないため、同じエンティティ内で同じ表示名が複数回表示されることがあります。  この場合、競合している名前の1つのうち、論理名がかっこ内の表示名の末尾に追加されます。  上記の例を基にして、同じ表示名を持つ2番目のフィールドがあり、 **cra3a_customfieldalt**の論理名を持つ**カスタムフィールド**がある場合、提案は次のように表示されます。

> [!div class="mx-imgBorder"]  
> "カスタムフィールド" の2つのバージョンを明確に区別するために、論理名 cr5e3_customfieldalt の使用を示す ![Studio の数式バー](media/operators/customfield_suggest_alt.png)

名前のあいまいさを解消するための文字列は、エンティティの名前、オプションセット、およびその他の Common Data Service 項目など、名前の競合が発生した場合に追加されます。 

## <a name="disambiguation-operator"></a>曖昧性除去演算子
一部の関数では、各レコードの処理中に、テーブルのフィールドにアクセスするための[レコード スコープ](../working-with-tables.md#record-scope)を作成します (**Filter**、**AddColumns**、**Sum** など)。  レコード スコープによって追加されたフィールド名は、アプリの別の場所にある同じ名前をオーバーライドします。  これが発生した場合でも、 **@** 曖昧性除去演算子を使用して、レコード スコープの外部の値にアクセスできます。

* 入れ子になったレコード スコープの値にアクセスするには、次のパターンを使用した操作対象のテーブルの名前の **@** 演算子を使います。<br>_Table_ **[@** _フィールド名_ **]**
* データ ソース、コレクション、コンテキスト変数などのグローバル値にアクセスするには、 **[@** _オブジェクト名_ **]** のパターンを使用します (テーブルは指定しません)。

詳細と例については、「[レコード スコープ](../working-with-tables.md#record-scope)」を参照してください。

