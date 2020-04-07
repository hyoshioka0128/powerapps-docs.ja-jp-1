---
title: Remove および RemoveIf 関数 | Microsoft Docs
description: 構文と例を含む、Power Apps の Remove および RemoveIf 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/02/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bddce14842d111757859b836c0137b35111805d1
ms.sourcegitcommit: 49b69129262a9b530e69508e84c3822b742066df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80759875"
---
# <a name="remove-and-removeif-functions-in-power-apps"></a>Power Apps の remove および RemoveIf 関数
[データ ソース](../working-with-tables.md#records)から[レコード](../working-with-data-sources.md)を削除します。

## <a name="description"></a>説明
### <a name="remove-function"></a>Remove 関数
**Remove** 関数を使用して、1 つまたは複数の特定のレコードをデータ ソースから削除します。  

[コレクション](../working-with-data-sources.md#collections)の場合には、レコード全体が一致している必要があります。 レコードのコピー全部を削除する場合には、**All** 引数を使用します。この引数を使用しなかった場合には、レコードのコピーが 1 つだけ削除されます。

### <a name="removeif-function"></a>RemoveIf 関数
**RemoveIf** 関数を使用して、1 つの条件または一連の条件に基づき、1 つまたは複数のレコードを削除します。 各条件には、結果が **true** または **false** になるものであれば、どのような数式でも指定できます。また、データ ソースの[列](../working-with-tables.md#columns)を、名前を使って参照することもできます。 各条件はレコードごとに個別に評価され、すべての条件が **true** と評価された場合にそのレコードが削除されます。

**Remove** と **RemoveIf** は、変更後のデータ ソースを[テーブル](../working-with-tables.md)として返します。 これらの関数は、いずれも[動作の数式](../working-with-formulas-in-depth.md)内でのみ使用できます。

また、 **[Clear](function-clear-collect-clearcollect.md)** 関数を使用して、データ ソースのすべてのレコードを削除することもできます。

### <a name="delegation"></a>委任
[!INCLUDE [delegation-no](../../../includes/delegation-no.md)]

## <a name="syntax"></a>構文
**Remove**( *DataSource*, *Record1* [, *Record2*, ... ] [, **All** ] )

* *DataSource* – 必須。 削除の対象となるレコードが含まれるデータ ソース。
* *Record(s)* – 必須。 削除する 1 つまたは複数のレコード。
* **All** – 省略可能。 コレクションでは、同じレコードが複数存在することがあります。  レコードのコピーをすべて削除するために、**All** 引数を追加できます。

**Remove**( *DataSource*, *Table* [, **All** ] )

* *DataSource* – 必須。 削除の対象となるレコードが含まれるデータ ソース。
* *Table* – 必須。 削除するレコードのテーブル。
* **All** – 省略可能。 コレクションでは、同じレコードが複数存在することがあります。  レコードのコピーをすべて削除するために、**All** 引数を追加できます。

**RemoveIf**( *DataSource*, *Condition* [, ... ] )

* *DataSource* – 必須。 削除の対象となるレコードが含まれるデータ ソース。
* *Condition(s)* – 必須。 削除の対象とするレコードについて評価結果が **true** となる数式。  数式では、*DataSource* の列名を使用できます。  複数の *Condition* を指定する場合、削除の対象とするレコードについて、評価結果がすべて **true** となる必要があります。

## <a name="examples---single-formulas"></a>例-1 つの式

ここで紹介する例では、**IceCream** という名前のデータ ソースの 1 つまたは複数のレコードを削除します。このデータ ソースは次のテーブルのデータから始まります。

![](media/function-remove-removeif/icecream.png)

#### <a name="create-a-collection-with-sample-records"></a>サンプルレコードを使用してコレクションを作成する

このデータを使用してコレクションを作成するには:

1. [**ボタン**](../controls/control-button.md)コントロールを挿入します。
1. ボタンコントロールの**Onselect**プロパティを次の式に設定します。

    ```powerapps-dot
    ClearCollect( IceCream,
                  { ID: 1, Flavor: "Chocolate",  Quantity: 100 },
                  { ID: 2, Flavor: "Vanilla",    Quantity: 200 },
                  { ID: 3, Flavor: "Strawberry", Quantity: 300 }
    )
    ```
1. [Alt キーを押し](../keyboard-shortcuts.md#alternate-behavior)ながらボタンを選択します。


#### <a name="remove-sample-records-from-collection-using-a-formula"></a>式を使用してコレクションからサンプルレコードを削除する

| [数式] | 説明 | 結果 |
| --- | --- | --- |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) )** |データ ソースの **Chocolate** レコードを削除します。 |<style>img {max width: none}</style> ![](media/function-remove-removeif/icecream-no-chocolate.png)<br><br>**IceCream** データ ソースの内容が変更されました。 |
| **Remove(&nbsp;IceCream,<br>First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Chocolate"&nbsp;)&nbsp;) First(&nbsp;Filter(&nbsp;IceCream,&nbsp;Flavor="Strawberry"&nbsp;)&nbsp;) )** |データ ソースから 2 つのレコードを削除します。 |![](media/function-remove-removeif/icecream-only-vanilla.png)<br><br>**IceCream** データ ソースの内容が変更されました。 |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150 )** |**Quantity** の値が **150** よりも大きいレコードを対象として削除を実行します。 |![](media/function-remove-removeif/icecream-only-chocolate.png)<br><br>**IceCream** データ ソースの内容が変更されました。 |
| **RemoveIf(&nbsp;IceCream, Quantity&nbsp;>&nbsp;150, Left(&nbsp;Flavor,&nbsp;1&nbsp;) = "S" )** |**Quantity** の値が 150 よりも大きく、**Flavor** が **S** で始まるレコードを対象として削除を実行します。 |![](media/function-remove-removeif/icecream-no-strawberry.png)<br><br><br>**IceCream** データ ソースの内容が変更されました。 |
| **RemoveIf(&nbsp;IceCream, true )** |データ ソースからすべてのレコードを削除します。 |![](media/function-remove-removeif/icecream-empty.png)<br><br>**IceCream** データ ソースの内容が変更されました。 |

## <a name="examples---remove-button-outside-a-gallery"></a>例-ギャラリー外のボタンを削除する

この例では、 [**ギャラリー**コントロール](../controls/control-gallery.md)を使用して、テーブル内のレコードを一覧表示します。 次に、 **remove**関数を使用して項目を選択的に削除します。  

### <a name="prepare-for-sample-data"></a>サンプルデータの準備

この例では、*サンプルアプリとデータ*で使用できる Common Data Service の**Contacts**エンティティを使用します。 [環境を作成](https://docs.microsoft.com/power-platform/admin/create-environment#create-an-environment-with-a-database)するときに、*サンプルアプリとデータ*を配置できます。 代わりに、他のデータソースを使用することもできます。

### <a name="remove-button-outside-a-gallery"></a>ギャラリー外のボタンを削除する

この例では、ギャラリーの外部にある*ボタン*を使用して項目を削除します。

1. 電話レイアウトを使用して、[新しい空のキャンバスアプリ](../data-platform-create-app-scratch.md)を作成します。

    ![携帯電話レイアウトを使用する空のキャンバスアプリ](media/function-remove-removeif/gallery-new.png)

1. 左側のウィンドウから **[挿入]** を選択します。

1. **[縦組みギャラリー]** を選択します。 <br>
    **ギャラリー**コントロールが画面に追加されます。

    ![[ツールの挿入] ペインを使用して縦方向のギャラリーコントロールを追加する](media/function-remove-removeif/gallery-add.png)

1. 使用可能なデータソースからデータソースを選択できるデータソースを選択するように求められます。 <br>
    たとえば、*サンプルデータ*を使用する**連絡先**エンティティを選択します。  

    ![ギャラリーに表示する連絡先エンティティの選択](media/function-remove-removeif/gallery-datasource.png)

    ギャラリーには、このエンティティの項目が表示されます。 

    ![Contacts エンティティを表示するギャラリーが追加されました](media/function-remove-removeif/gallery-data.png)

1. 左ペインから[**ボタン**](../controls/control-button.md)コントロールを挿入します。
    
    ![[ツールの挿入] ペインを使用してボタンコントロールを追加する](media/function-remove-removeif/gallery-addbutton.png)

1. [追加] ボタンをギャラリー項目の下に移動します。

    ![移動ボタン](media/function-remove-removeif/move-button-down.png)

1. ボタンテキストプロパティを更新して*レコードを削除*します。 任意のテキストを使用することもできます。

    ![[名前の変更] ボタン](media/function-remove-removeif/button-text.png)

1. このボタンコントロールの**Onselect**プロパティを次の数式に設定します。

    ```powerapps-dot
    Remove( Contacts, Gallery1.Selected )
    ```

    ![ボタンコントロールの OnSelect プロパティの設定](media/function-remove-removeif/gallery-button-onselect.png)

    ギャラリーコントロールは、**選択した**プロパティを使用して現在選択されているレコードを使用できるようにします。 **Remove**関数は、この選択されたレコードを参照して削除します。

1. 右上にある [*再生*] ボタンを使用してアプリをプレビューするか、キーボードの*F5*キーを押します。

    ![アプリのプレビュー](media/function-remove-removeif/preview-app.png)

1. 削除するレコードを選択します (この例では、*ナンシー*のレコードなど)。

    ![レコードの選択](media/function-remove-removeif/select-nancy-record.png)

1. **[レコードの削除]** を選択します。

    ![連絡先のギャラリーです。削除されたナンシーレコードがありません。](media/function-remove-removeif/gallery-activatebutton.png)

    このボタンを選択すると、選択したレコード (この例では、ナンシーのレコード) が削除されます。

1. アプリのプレビューを閉じます。

    > [!TIP]
    > [*再生*] ボタンまたは*F5*キーでアプリのプレビューを使用する代わりに、 [*Alt キー*](../keyboard-shortcuts.md#alternate-behavior)で代替動作を使用することもできます。

## <a name="examples---trash-can-icon-inside-a-gallery"></a>例-ギャラリー内のごみ箱アイコン

この例では、ギャラリー内に配置された*アイコン*を使用して項目を削除します。

### <a name="create-a-collection-with-sample-data"></a>サンプルデータを使用してコレクションを作成する

既に[サンプルデータを準備](#prepare-for-sample-data)している場合は、この手順をスキップして、[ギャラリー内のごみ箱アイコン](#trash-can-icon-inside-a-gallery)に移動します。

1. 画面に[**ボタン**](../controls/control-button.md)コントロールを追加します。
1. **OnSelect** プロパティを次の式に設定します。

    ```powerapps-dot
    ClearCollect( SampleContacts, 
          { 'Full Name': "Yvonne McKay (sample)",      'Primary Email': "someone_a@example.com" },
          { 'Full Name': "Susanna Stubberod (sample)", 'Primary Email': "someone_b@example.com" },
          { 'Full Name': "Nancy Anderson (sample)",    'Primary Email': "someone_c@example.com" },
          { 'Full Name': "Maria Campbell (sample)",    'Primary Email': "someone_d@example.com" },
          { 'Full Name': "Robert Lyon (sample)",       'Primary Email': "someone_e@example.com" },
          { 'Full Name': "Paul Cannon (sample)",       'Primary Email': "someone_f@example.com" },
          { 'Full Name': "Rene Valdes (sample)",       'Primary Email': "someone_g@example.com" } 
    )
    ```
1. [Alt キーを押し](../keyboard-shortcuts.md#alternate-behavior)ながらボタンを選択します。

サンプルコレクションは、次の例で使用できるように作成されています。

### <a name="trash-can-icon-inside-a-gallery"></a>ギャラリー内のごみ箱アイコン

1. 電話レイアウトを使用して、[新しい空のキャンバスアプリ](../data-platform-create-app-scratch.md)を作成します。

    ![携帯電話レイアウトを使用する空のキャンバスアプリ](media/function-remove-removeif/gallery-new.png)

1. 左側のウィンドウから **[挿入]** を選択します。

1. **[縦組みギャラリー]** を選択します。 <br>
    **ギャラリー**コントロールが画面に追加されます。

    ![[ツールの挿入] ペインを使用して縦方向のギャラリーコントロールを追加する](media/function-remove-removeif/gallery-add.png)

1. 使用可能なデータソースからデータソースを選択できるデータソースを選択するように求められます。 <br>
    たとえば、*サンプルデータ*を使用する**連絡先**エンティティを選択します。  

    ![ギャラリーに表示する連絡先エンティティの選択](media/function-remove-removeif/gallery-datasource.png)

    [コレクション](#create-a-collection-with-sample-data)を作成した場合は、代わりにコレクションを選択します。

    ![サンプル連絡先コレクション](media/function-remove-removeif/sample-contacts.png)

1. ギャラリーの一番上の項目内のコントロールを選択します。 <br>
    
    次のステップによってギャラリーのテンプレートに項目が挿入され、ギャラリーの外部ではないことを確認するには、次の手順に進む前に、この手順に従ってください。
    
    ![ギャラリーでトップレコードを選択する](media/function-remove-removeif/gallery-select-template.png)

1. 左側のウィンドウから [**追加] アイコン**を選択します。 <br>
    
    ![[ツールの挿入] ペインを使用してアイコンコントロールを追加する](media/function-remove-removeif/gallery-addicon.png)

    > [!NOTE]
    > [**追加] アイコン**ギャラリーの左側に **+** アイコンが挿入されます。ギャラリーの各項目に対してレプリケートされます。 

1. 一番上の項目で、アイコンを画面の右側に移動します。

    ![[移動] アイコン](media/function-remove-removeif/move-icon.png)

1. アイコンの**アイコンプロパティを選択し、次**の数式に設定して、アイコンイメージをごみ箱アイコンとして更新します。

    ```powerapps-dot 
    Icon.Trash
    ```
    
    > [!NOTE]
    > **アイコン。** プレフィックスは、数式をアクティブに編集している場合にのみ表示されます。

    ![アイコンをごみ箱アイコンに変更する](media/function-remove-removeif/gallery-icontrash.png)

1. **OnSelect** プロパティを次の式に設定します。

    ```powerapps-dot
    Remove( [@Contacts], ThisItem )
    ```

    > [!NOTE]
    > グローバルなあいまいを解消する[演算子](operators.md#disambiguation-operator) **[@** ... **]** この例では、*一対多*リレーションシップとの競合を避けるために*Contacts*エンティティを使用するサンプルデータを使用しています。 SharePoint リストや SQL Server テーブルなどのデータソースを使用する場合は、*グローバル disambgulation 演算子*を使用する必要はありません。

    ![OnSelect for ごみ箱アイコン](media/function-remove-removeif/gallery-onselect.png)

1. 右上にある [*再生*] ボタンを使用してアプリをプレビューするか、キーボードの*F5*キーを押します。

1. レコードの横にあるごみ箱アイコンを選択します。たとえば、「*マリア*」のようにします。

    ![いずれかの連絡先が削除されたギャラリー](media/function-remove-removeif/gallery-activateicon.png)

    レコードが削除されます。

    ![削除されたレコード](media/function-remove-removeif/deleted-record.png)

1. アプリのプレビューを閉じます。
