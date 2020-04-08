---
title: 'ギャラリー コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含むギャラリー コントロールに関する情報
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/16/2020
ms.author: chmoncay
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ca48ccaf4aca72301d3a8b7f2eb79885d7c7cdf5
ms.sourcegitcommit: 6acc6ac7cc1749e9681d5e55c96613033835d294
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80871329"
---
# <a name="gallery-control-in-canvas-apps"></a>キャンバスアプリのギャラリーコントロール

その他のコントロールが含まれており、一連のデータを表示するコントロールです。

## <a name="description"></a>説明

**ギャラリー** コントロールを使用して、データ ソースの複数のレコードを表示できます。各レコードには、複数の種類のデータを含めることができます。 たとえば、**ギャラリー**コントロールを使用して複数の連絡先を表示し、各連絡先の名前、住所、電話番号などの連絡先情報を表示します。

各データフィールドは、**ギャラリー**コントロール内の個別のコントロールに表示されます。 これらのコントロールは、テンプレートで構成できます。 テンプレートは、ギャラリー内の最初の項目として表示されます。

- 水平/横向きの**ギャラリー**コントロールの左端。
- また、縦/縦向きの**ギャラリー**コントロールの上部にあります。 

テンプレートで行った変更は、**ギャラリー** コントロール全体に反映されます。

ギャラリーに画像やテキストを表示するための定義済みテンプレートと、可変高さ項目のギャラリーが用意されています。

## <a name="limitations"></a>制限事項

ユーザーが、すべての項目が読み込まれる前に、**柔軟な高さ**のギャラリーコントロールをスクロールすると、データの読み込みが完了すると、現在表示されているアイテムが表示されなくなることがあります。 この問題を回避するには、**柔軟な高さ**バリアントではなく、標準の**ギャラリー**コントロールを使用します。

## <a name="key-properties"></a>主要なプロパティ

[[既定](properties-core.md)] –アプリの起動時にギャラリーで選択されるデータソースの項目またはレコード。

[Items](properties-core.md) – ギャラリー、リスト、グラフなどのコントロールに表示されるデータのソースです。

**Selected** – 選択された項目です。

## <a name="additional-properties"></a>その他のプロパティ

[AccessibleLabel](properties-accessibility.md) –スクリーンリーダー用のギャラリーのラベル (含まれる項目ではありません)。 項目の一覧の内容を説明する必要があります。

**AllItems** – ギャラリーのテンプレートの一部である追加のコントロール値を含む、ギャラリーのすべての項目です。

[BorderColor](properties-color-border.md) – コントロールの境界線の色です。

[BorderStyle](properties-color-border.md) – コントロールの境界線のスタイルです (**実線**、**破線**、**点線**、または**なし**)。

[BorderThickness](properties-color-border.md) – コントロールの境界線の太さです。

**Delayitemloading** -画面が最初に読み込まれるまで項目 (行) の遅延読み込みを実行します。

[DisplayMode](properties-core.md) –コントロールでユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、または無効 (**無効**) にするかを指定します。

[Fill](properties-color-border.md) – コントロールの背景色です。

[Height](properties-size-location.md) – コントロールの上端と下端の距離です。

**ItemAccessibleLabel** –スクリーンリーダー用の各ギャラリー項目のラベルです。 各項目の内容を説明する必要があります。

**Loadingspinner ボタン**(**なし**、**コントロール**、または**データ**)-none の場合、スピンボタンは表示されません。 When Controls |データは、表示されている空の行を生成するレンダリングパスが発生すると表示されます。

**Loadingspinnercolor** -読み込みスピンボタンの塗りつぶしの色。  既定値は BorderColor に設定されています。

**NavigationStep** – **ShowNavigation** プロパティが **true** に設定されている場合、ギャラリーの端にあるナビゲーション矢印の選択操作でギャラリーをどの程度スクロールするかを指定します。

選択**可能**–ギャラリー項目を選択できるかどうかを指定します。 **True**に設定すると、スクリーンリーダーはギャラリーを選択可能なリストとして識別します。 項目を選択して選択します。 **False**に設定すると、スクリーンリーダーはギャラリーを標準の一覧として識別し、項目を選択しても選択されません。

**Shownavigation** –ギャラリーの各端に矢印を表示するかどうかを指定します。ユーザーは、矢印を選択してギャラリー内の項目をスクロールできます。

**ShowScrollbar** – ユーザーがポインタをギャラリーに合わせたときにスクロール バーを表示するかどうかを指定します。

**Snap** – ユーザーがギャラリーをスクロールするとき、次の項目が完全に表示されるように自動的にスナップするかどうかを指定します。

**TemplateFill** – ギャラリーの背景色です。

**TemplatePadding** – ギャラリー内の項目間の距離です。

**Templatesize** –垂直/縦向きのギャラリーのテンプレートの高さです。 水平/横向きのギャラリーのテンプレートの幅。

**Transition** – ユーザーがポインタをギャラリー内の項目に合わせたときの視覚効果 (**ポップ**、**プッシュ**、または **None**) を指定します。

[Visible](properties-core.md) – コントロールを表示するか非表示にするかを指定します。

[Width](properties-size-location.md) – コントロールの左端と右端の間の距離です。

**WrapCount** – 水平または垂直レイアウトに合わせて行または列ごとに表示される項目の数です。

[X](properties-size-location.md) –コントロールの左端とその親コンテナーまたは画面の左端の間の距離です。

[Y](properties-size-location.md) –コントロールの上端と親コンテナーまたは画面の上端との距離です。

## <a name="related-functions"></a>関連する関数

[Filter ( *DataSource*、 *Formula* )](../functions/function-filter-lookup.md)

[Reset (*コントロール*)](../functions/function-reset.md) -ギャラリーを初期状態に戻します。 初期状態では、最初の項目へのスクロールと最初の項目の選択が含まれます (存在する場合)。 

  > [!NOTE]
  > **Reset**コントロールは、ギャラリーのすべての子を再帰的にリセットしません。

## <a name="examples"></a>使用例

### <a name="show-and-filter-data"></a>データを表示およびフィルター処理する

- [テキストを表示します](control-text-box.md#show-data-in-a-gallery)
- [イメージを表示します](control-image.md#show-a-set-of-images-from-a-data-source)
- [リスト オプションを選択してデータをフィルター処理します](control-drop-down.md#example)
- [スライダーを調整してデータをフィルター処理します](control-slider.md#example)

### <a name="get-data-from-the-user"></a>ユーザーからデータを取得する

- [テキストを取得します](control-text-input.md#collect-data)
- [イメージを取得します](control-add-picture.md#add-images-to-an-image-gallery-control)
- [写真を取得します](control-camera.md#examples)
- [サウンドを取得します](control-microphone.md#examples)
- [図面を取得します](control-pen-input.md#create-a-set-of-images)

## <a name="accessibility-guidelines"></a>アクセシビリティのガイドライン

### <a name="color-contrast"></a>色のコントラスト

ギャラリー項目内のどこかをクリックすると、その項目が選択される場合、以下の間に適切な色のコントラストが必要です。

- [BorderColor](properties-color-border.md)とギャラリーの外側の色 (境界線がある場合)。
- [塗りつぶし](properties-color-border.md)とギャラリー外の色 (境界線がない場合)。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート

- [AccessibleLabel](properties-accessibility.md)が存在している必要があります。

    > [!NOTE]
    > ギャラリー内の項目が変更されると、スクリーンリーダーによってアナウンスされます。 **AccessibleLabel** についても通知されます。 これによって通知のコンテキストがわかるので、同じスクリーン上に複数のギャラリーがある場合にはさらに重要です。

- ギャラリー項目に複数のコントロールが含まれている場合は、 **ItemAccessibleLabel**を使用して、ギャラリー項目の内容を表示します。

- ユーザーがギャラリー項目を選択できるようにする場合は、 **[選択可能]** の値を **[true]** に設定します。 それ以外の場合は、その値を**false**に設定します。

- ギャラリーアイテムに複数のコントロールが含まれている場合は、 **ItemAccessibleLabel**を使用して、ギャラリーアイテムのコンテンツの概要を指定します。

- ユーザーがギャラリーアイテムを選択することになっているかどうかに応じて、**選択可能**な項目を適切に設定する必要があります。

### <a name="keyboard-support"></a>キーボードのサポート

- **ShowScrollbar** を **true** に設定することを検討してください。 ほとんどのタッチスクリーンデバイスでは、スクロールが開始されるまでスクロールバーは表示されません。
- ギャラリー項目内のどこかをクリックすると、その項目が選択される場合、キーボード ユーザーがギャラリー項目を選択できる方法も必要です。 たとえば、 **Onselect**プロパティが**select (Parent)** に設定されている[ボタン](control-button.md)を追加します。

    > [!NOTE]
  > ギャラリーの外部のコントロールは、ギャラリー内のキーボード ナビゲーション順では考慮されません。 ギャラリー内の[TabIndex](properties-accessibility.md)コントロールはスコープが設定されています。 詳細については、[アクセシビリティのプロパティ](properties-accessibility.md)に関するページを参照してください。
