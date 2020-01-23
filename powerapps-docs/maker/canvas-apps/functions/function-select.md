---
title: Select 関数 | Microsoft Docs
description: 構文を含む Power Apps の Select 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/08/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 12e0f7e33487d5a274dea8bf666ed7d539284e92
ms.sourcegitcommit: db62bf0f8210b5ba2d1d5fc2c7d362ab23ec8c63
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2020
ms.locfileid: "76315425"
---
# <a name="select-function-in-power-apps"></a>Power Apps の Select 関数
コントロールでの選択アクションをシミュレートし、**OnSelect** 式の評価を実行させます。

## <a name="description"></a>説明
**Select** 関数では、ユーザーがコントロールをクリックまたはタップしたかのように、コントロールでの選択アクションをシミュレートします。 その結果、対象のコントロールでの **OnSelect** 式が評価されます。

**Select** を使用して、選択アクションを親コントロールに伝達します。 この種類の伝達は、ギャラリーなどでの既定の動作です。 既定では、 **[ギャラリー](../controls/control-gallery.md)** コントロールのすべてのコントロールの **OnSelect** プロパティは **Select( Parent )** に設定されています。 この方法では、ギャラリー コントロール自体の **OnSelect** プロパティの値を設定でき、ユーザーがギャラリーのどこをクリックまたはタップしたかにかかわらず、その式が評価されます。

ギャラリー内の 1 つまたは複数のコントロールでギャラリー自体とは異なるアクションを実行させる場合、そのコントロールの **OnSelect** プロパティを規定値以外に設定します。 ギャラリー自体と同じアクションを実行させる場合は、ギャラリー内のほとんどのコントロールの **OnSelect** プロパティを規定値のままにすることができます。

**Select** は、後の処理のために対象の **OnSelect** をキューに入れます。この動作は現在の式の評価が完了した後で行われる場合があります。 **Select** によって **OnSelect** がすぐに評価されたり、**Select** が **OnSelect** の評価の完了まで待機したりすることはありません。

画面をまたいで **Select** を使用することはできません。

**Select** は、**OnSelect** プロパティを持つコントロールと共にのみ使用できます。

**Select** は、[動作の数式](../working-with-formulas-in-depth.md)内でのみ使用できます。

コントロールが直接、または他のコントロールを通じて間接的に、自身を **Select** することはできません。

Select 関数はギャラリーでも使用できます。 たとえば、ギャラリーで選択する行または列や、ギャラリーのその行または列内で選択するためのコントロールを指定するために使用できます。 行または列を選択すると、ギャラリーの選択が変更され、ギャラリー コントロールの **OnSelect** 式が評価されます。 行または列内のコントロールが指定されている場合は、子コントロールの **OnSelect** 式が評価されます。 

## <a name="syntax"></a>構文
**Select**( *Control* )

* *Control* – 必須。  ユーザーの代理として選択するコントロール。

**Select**( *コントロール, 行または列, 子コントロール* )

- *Control* – 必須。 ユーザーの代理として選択するコントロール。
- *行または列* – 必須ではありません。 ユーザーの代わりに選択するギャラリー コントロール内の行または列の数 (1 から開始)。
- *子コントロール* - 必須ではありません。 選択する 'control' パラメーターで識別されるコントロールの子コントロール。 

## <a name="examples"></a>例

- *Button*

    ```Select(button1)```

- *[Gallery (ギャラリー)]* 

    ```Select(Gallery1, 1)```

    ユーザーによる Gallery1 での行 1 または列 1 の選択をシミュレートします。 

- *[Gallery (ギャラリー)]* 

    ```Select(Gallery1, 1, ChildControl1)```

    ユーザーによる Gallery1 の行 1 または列 1 内の ChildConttrol1 の選択をシミュレートします。

#### <a name="basic-usage"></a>基本的な使用方法

1. **[Button](../controls/control-button.md)** コントロールを追加し、別の名前になっている場合は **Button1** に名前を変更します。

1. **Button1** の **OnSelect** プロパティを次の数式に設定します。

    **Notify( "Hello World" )**

1. 同じ画面で、2 つ目の **Button** コントロールを追加し、その **OnSelect** プロパティを次の数式に設定します。

    **Select( Button1 )**

1. Alt キーを押しながら 2 つ目のボタンを選択します。

    通知がアプリケーションの上部に表示されます。 この通知を生成したのは、**Button1** の **OnSelect** プロパティです。

    ![2 つのボタンの OnSelect プロパティの設定と、2 つ目のボタンがクリックされたときの通知を示すアニメーション](media/function-select/basic-select.gif)

#### <a name="gallery-control"></a>ギャラリー コントロール

1. 他のコントロールを含む垂直方向の **[ギャラリー](../controls/control-gallery.md)** コントロールを追加します。

    ![コントロールを含む垂直方向のギャラリーを選択します](media/function-select/select-gallery.png)

2. ギャラリーの **OnSelect** プロパティを次の式に設定します。
 
    **Notify( "Gallery Selected" )**

3. Alt キーを押しながら、ギャラリーの背景かギャラリー内のコントロールをクリックまたはタップします。

    すべてのアクションで、アプリケーションの上部に **Gallery Selected** 通知が表示されます。

    ギャラリーの **OnSelect** プロパティを使用して、ユーザーがギャラリーの項目をクリックまたはタップしたときに実行する既定のアクションを指定します。

5. イメージ コントロールの **OnSelect** プロパティを次の式に設定します。

    **Notify( "Image Selected", Success )**

6. Alt キーを押しながら、ギャラリーのさまざまな要素をクリックまたはタップします。

    イメージ以外のギャラリーのコントロールをクリックまたはタップすると、前と同様に **Gallery Selected** が表示されます。 イメージをクリックまたはタップすると、**Image Selected** が表示されます。
 
    ギャラリーで個々のコントロールを使用して、ギャラリーの既定のアクションとは異なるアクションを実行させます。

    ![ギャラリー コントロールの OnSelect プロパティの規定値と、異なるアクションを実行するコントロールを示すアニメーション](media/function-select/gallery-select.gif)

7. 同じ画面で、**Button** コントロールを追加し、その **OnSelect** プロパティを次の数式に設定します。

    **Select( Gallery1,2,Image1 )**

8. Alt キーを押しながら、ボタンを選択します。
   
     **Image Selected** 通知がアプリの上部に表示されます。 ボタンのクリックで、ギャラリーの行 2 のイメージの選択がシミュレートされました。  

