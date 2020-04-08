---
title: '画像の追加コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含む画像の追加コントロールに関する情報
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/25/2016
ms.author: chmoncay
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3f2afd3a1097ec0b201b5857509f1ff42d1fedad
ms.sourcegitcommit: 6acc6ac7cc1749e9681d5e55c96613033835d294
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80871283"
---
# <a name="add-picture-control-in-power-apps"></a>Power Apps に画像コントロールを追加する
写真を撮影したり、ローカルのデバイスから画像を読み込んだりします。

## <a name="description"></a>説明
このコントロールを使用すると、ユーザーは写真を撮影したり、デバイスから画像ファイルをアップロードしたりして、このコンテンツでデータ ソースを更新できます。 モバイル デバイスでは、デバイスの選択ダイアログが表示され、ユーザーは写真を撮影するか、既存の画像を使用するかを選択できます。

このコントロールは、**イメージ**と [**画像の追加] ボタン**の2つのコントロールを含むグループ化されたコントロールです。 **イメージ** コントロールには、アップロードされたイメージか、イメージがアップロードされていない場合はプレースホルダーが表示されます。 [**画像の追加] ボタンをクリック**すると、アップロードする画像が表示されます。

[Image](control-image.md) プロパティについては、**イメージ コントロールのリファレンス**を参照してください。

## <a name="add-picture-button-properties"></a>画像ボタンのプロパティの追加
**[AccessibleLabel](properties-accessibility.md)** – スクリーン リーダー用のラベルです。 画像追加の目的を説明する必要があります。

**[Align](properties-text.md)** – コントロールの水平方向の中心に対するテキストの位置です。

**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**ChangePictureText** – 画像がアップロードされているときにボタンに表示されるテキスト。

**[Color](properties-color-border.md)** – コントロールのテキストの色です。

**[DisabledBorderColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの境界線の色です。

**[DisabledColor](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロール内のテキストの色です。

**[DisabledFill](properties-color-border.md)** – コントロールの **[DisplayMode](properties-core.md)** プロパティが **Disabled** に設定されている場合のコントロールの背景色です。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**Error** - 画像のアップロードで問題が発生した場合、このプロパティには該当するエラー文字列が含まれます。

**[Fill](properties-color-border.md)** – コントロールの背景色です。

**[FocusedBorderColor](properties-color-border.md)** – コントロールにフォーカスがあるときのコントロールの境界線の色です。

**[FocusedBorderThickness](properties-color-border.md)** – コントロールにフォーカスがあるときのコントロールの境界線の太さです。

**[Font](properties-text.md)** – テキストを表記するフォントのファミリー名です。

**[FontWeight](properties-text.md)** – コントロール内のテキストの太さです。**Bold** (太字)、**Semibold** (中太)、**Normal** (標準)、**Lighter** (細字) から指定します。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**[HoverBorderColor](properties-color-border.md)** – コントロール上にユーザーがマウス ポインターを重ねているときのコントロールの境界線の色です。

**[HoverColor](properties-color-border.md)** – コントロールにユーザーがマウス ポインターを重ねているときのコントロール内のテキストの色です。

**[HoverFill](properties-color-border.md)** – コントロールにユーザーがマウス ポインターを重ねているときのコントロールの背景色です。

**[Italic](properties-text.md)** – コントロール内のテキストを斜体にするかどうかを指定します。

**Media** - オーディオまたはビデオ コントロールが再生するクリップの ID です。

**[OnChange](properties-core.md)** – ユーザーが (スライダーを調整するなどして) コントロールの値を変更した場合のアプリの反応を指定します。

**[OnSelect](properties-core.md)** – ユーザーがコントロールをタップまたはクリックした場合のアプリの反応を指定します。

**[Padding](properties-size-location.md)** – [インポート] ボタンまたは [エクスポート] ボタンのテキストと、ボタンの縁との距離です。

**[PressedBorderColor](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロールの境界線の色です。

**[PressedColor](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロール内のテキストの色です。

**[PressedFill](properties-color-border.md)** – コントロールをユーザーがタップまたはクリックしたときのコントロールの背景色です。

**[Reset](properties-core.md)** – コントロールを既定値に戻すかどうかを指定します。

**[Size](properties-text.md)** – コントロールに表示されるテキストのフォント サイズです。

**[Strikethrough](properties-text.md)** – コントロールに表示されるテキストに取り消し線を付けるかどうかを指定します。

**[TabIndex](properties-accessibility.md)** – 他のコントロールに関連するキーボード ナビゲーションの順序です。

**[Text](properties-core.md)** – イメージがアップロードされていないときにボタンに表示されるテキスト。

**[Tooltip](properties-core.md)** – ユーザーがポインターをコントロールに合わせたときに表示される説明テキストです。

**[Underline](properties-text.md)** – コントロールに表示されるテキストの下に線を引くかどうかを指定します。

**[VerticalAlign](properties-text.md)** – コントロールの垂直方向の中心に対するコントロール上でのテキストの位置です。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="related-functions"></a>関連する関数
[**Patch**( *DataSource*, *BaseRecord*, *ChangeRecord* )](../functions/function-patch.md)

## <a name="examples"></a>使用例
### <a name="add-images-to-an-image-gallery-control"></a>イメージ ギャラリー コントロールへの画像の追加
1. **画像の追加**コントロールを追加し、それをトリプル クリックします。
   
    [コントロールの追加、命名、構成についてはこちらをご覧ください](../add-configure-controls.md)。
1. **[Open (開く)]** ダイアログ ボックスで、画像ファイルをクリックまたはタップしてから、 **[Open (開く)]** をクリックまたはタップします。
1. **[ボタン](control-button.md)** コントロールを追加して**画像の追加**コントロールの下に移動し、 **[ボタン](properties-core.md)** コントロールの **[OnSelect](control-button.md)** プロパティを次の数式に設定します。<br>
   **Collect(MyPix, AddMediaButton1.Media)**
   
    **[Collect](../functions/function-clear-collect-clearcollect.md)** 関数または[その他の関数](../formula-reference.md)については各関連記事を参照してください。
1. 縦の**ギャラリー**コントロールを追加し、 **[Items](properties-core.md)** プロパティを**mypix**に設定します。
1. ギャラリーで **[イメージ](control-image.md)** コントロールを選択し、 **[イメージ]** プロパティを この **[項目の値]** に設定します。
1. F5 キーを押して、 **[ボタン](control-button.md)** コントロールをクリックまたはタップします。
   
    **画像の追加**コントロールの画像は、**垂直方向**のコントロールに表示されます。 イメージの縦横比が、**縦方向のギャラリー**コントロール **[のイメージ](control-image.md)** コントロールと同じでない場合は、 **[イメージ](control-image.md)** コントロールの **[imageposition](properties-visual.md)** プロパティを**合わせ**て設定します。
1. **画像の追加**コントロールをクリックまたはタップし、別の画像ファイルをクリックまたはタップし、 **[Open (開く)]** をクリックまたはタップしてから、追加した **[ボタン](control-button.md)** コントロールをクリックまたはタップします。
   
    2 番目の画像が**イメージ ギャラリー** コントロールに表示されます。
1. (オプション) 前の手順を 1 回以上繰り返してから、Esc キーを押して既定のワークスペースに戻ります。

**[SaveData](../functions/function-savedata-loaddata.md)** 関数を使用して画像をローカルに保存するか、 **[Patch](../functions/function-patch.md)** 関数を使用してデータ ソースを更新します。


## <a name="accessibility-guidelines"></a>アクセシビリティのガイドライン
**[ボタン](control-button.md)** および **[イメージ](control-image.md)** と同じガイドラインが適用されます。 さらに次の点について考慮してください。

### <a name="color-contrast"></a>色のコントラスト
* **[画像の追加] ボタン**のテキストと背景の間には適切なコントラストが必要です。 アップロードされたイメージは色が異なる場合があるため、[**画像の追加] ボタン**の不透明な **[塗りつぶし](properties-color-border.md)** を使用して、一貫したコントラストを確保します。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート
* [**画像の追加] ボタン**には、画像を追加または変更するようにユーザーに求める**テキスト**と**ChangePictureText**が必要です。

### <a name="keyboard-support"></a>キーボードのサポート
* **[画像の追加] ボタン**は、キーボードユーザーが移動できるように、 **[TabIndex](properties-accessibility.md)** が0以上の値である必要があります。
* **[画像の追加] ボタン**には、明確に表示されるフォーカスインジケーターが必要です。 これを実現するには **[FocusedBorderColor](properties-color-border.md)** と **[FocusedBorderThickness](properties-color-border.md)** を使用します。
 
