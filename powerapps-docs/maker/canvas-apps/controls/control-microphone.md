---
title: 'マイク コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含むマイク コントロールに関する情報
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
ms.openlocfilehash: 353485baf6726314f6009c57838b3aa68d145fa0
ms.sourcegitcommit: cf492063eca27fdf73459ff2f9134f2ca04ee766
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79436756"
---
# <a name="microphone-control-in-power-apps"></a>Power Apps のマイクコントロール

アプリユーザーが自分のデバイスのサウンドを録音できるようにするコントロール。

## <a name="description"></a>説明

**マイク**コントロールを使用して、デバイスのマイクでオーディオをキャプチャします。  デバイスはマイクを持っている必要があり、ユーザーはマイクを使用するようにアプリを承認する必要があります。  マイクコントロールは、web ブラウザーで実行している場合にサポートされます。  

最後に記録されたオーディオクリップは、 **audio**プロパティを通じて入手できます。 このプロパティを使用すると、録音されたオーディオは次のようになります。

- **オーディオコントロールを使用して再生します。**  [オーディオ](control-audio-video.md)コントロールを使用して、録音を待機します。 詳細については、[例](#examples)を参照してください。
- **変数またはコレクションに一時的に配置します。**  変数またはコレクションにオーディオクリップを格納するには、 [Set](../functions/function-set.md)関数または[Collect](../functions/function-clear-collect-clearcollect.md)関数を使用します。  コレクション内の複数のオーディオクリップで、デバイスのメモリが制限されている場合は、注意してください。  [SaveData](../functions/function-savedata-loaddata.md)関数と[LoadData](../functions/function-savedata-loaddata.md)関数を使用して、オーディオクリップをデバイスのローカルストレージと[オフラインのシナリオ](../offline-apps.md)に移動します。
- **データベースに格納されます。**  [Patch](../functions/function-patch.md)関数を使用して、オーディオクリップをデータベースに格納します。
- **Base64 でエンコードされたテキスト文字列として送信されます。**  [JSON](../functions/function-json.md)関数を使用して、オーディオクリップを base64 エンコードします。

録音されたオーディオの形式:

- *Android*用の*3gp*形式。
- *IOS*用の*AAC*形式。
- *Web ブラウザー*の*OGG*形式。

キャプチャしたメディアは、テキスト文字列 URI によって参照されます。 詳細については、[データ型のドキュメント](../functions/data-types.md#uris-for-images-and-other-media)を参照してください。

## <a name="key-properties"></a>主要なプロパティ

**Audio** -ユーザーがデバイスのマイクを使用して記録したときにキャプチャされたオーディオクリップ。 

**Mic** –複数のマイクを持つデバイスのマイクの数値 ID です。

**OnStop** – ユーザーがマイク コントロールで録音を終了したときの、アプリの応答方法です。

## <a name="additional-properties"></a>その他のプロパティ

[AccessibleLabel](properties-accessibility.md) – スクリーン リーダー用のラベルです。 マイクの目的を説明する必要があります。

[BorderColor](properties-color-border.md) – コントロールの境界線の色です。

[BorderStyle](properties-color-border.md) – コントロールの境界線のスタイルです (**実線**、**破線**、**点線**、または**なし**)。

[BorderThickness](properties-color-border.md) – コントロールの境界線の太さです。

[Color](properties-color-border.md) – コントロールのテキストの色です。

[DisplayMode](properties-core.md) –コントロールでユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、または無効 (**無効**) にするかを指定します。

[DisabledBorderColor](properties-color-border.md) –コントロールの[DisplayMode](properties-core.md)プロパティが**Disabled**に設定されている場合のコントロールの境界線の色です。

[DisabledColor](properties-color-border.md) –コントロールの[DisplayMode](properties-core.md)プロパティが**Disabled**に設定されている場合のテキストの色です。

[DisabledFill](properties-color-border.md) –コントロールの[DisplayMode](properties-core.md)プロパティが**Disabled**に設定されている場合のコントロールの背景色です。

[Fill](properties-color-border.md) – コントロールの背景色です。

[FocusedBorderColor](properties-color-border.md) –コントロールがフォーカスされているときのコントロールの境界線の色です。

[FocusedBorderThickness](properties-color-border.md) –コントロールがフォーカスされているときのコントロールの境界線の太さです。

[Height](properties-size-location.md) – コントロールの上端と下端の距離です。

[HoverBorderColor](properties-color-border.md) – コントロール上にユーザーがマウス ポインターを重ねているときのコントロールの境界線の色です。

[HoverColor](properties-color-border.md) – コントロールにユーザーがマウス ポインターを重ねているときのコントロール内のテキストの色です。

[HoverFill](properties-color-border.md) – コントロールにユーザーがマウス ポインターを重ねているときのコントロールの背景色です。

[Image](properties-visual.md) – イメージ、オーディオ、マイクの各コントロールに表示される画像の名前です。

[ImagePosition](properties-visual.md) – 画面またはコントロールのサイズが画像と異なる場合の、画面またはコントロール内の画像の位置です (**横幅に合わせる**、**縦幅に合わせる**、**サイズに合わせて伸縮**、**並べて表示**、または**中央に表示**)。

[Onselect](properties-core.md) –ユーザーがコントロールを選択したときにアプリがどのように応答するかを指定します。

**OnStart** – ユーザーがマイク コントロールで録音を開始したときの、アプリの応答方法です。

[PressedBorderColor](properties-color-border.md) –ユーザーがコントロールを選択したときのコントロールの境界線の色です。

[PressedColor](properties-color-border.md) –ユーザーがコントロールを選択したときのコントロール内のテキストの色です。

[PressedFill](properties-color-border.md) –ユーザーがコントロールを選択したときのコントロールの背景色です。

[Reset](properties-core.md) – コントロールを既定値に戻すかどうかを指定します。

[TabIndex](properties-accessibility.md) –他のコントロールと比較したキーボードナビゲーション順序。

[Tooltip](properties-core.md) – ポインターをコントロールに合わせたときに表示される説明テキストです。

[Visible](properties-core.md) – コントロールを表示するか非表示にするかを指定します。

[Width](properties-size-location.md) – コントロールの左端と右端の間の距離です。

[X](properties-size-location.md) –コントロールの左端とその親コンテナーまたは画面の左端の間の距離です。

[Y](properties-size-location.md) –コントロールの上端と親コンテナーまたは画面の上端との距離です。

## <a name="examples"></a>使用例

### <a name="simple-direct-playback"></a>単純な直接再生

この例では、直ちに再生するために**マイク**コントロールを**オーディオ**コントロールに直接接続します。

1. **マイク**コントロールをアプリに[追加](../add-configure-controls.md)します。
1. メッセージが表示されたら、デバイスのマイクを使用するようにアプリを承認します。
1. アプリに**オーディオ**コントロールを追加します。
1. **オーディオ**コントロールの**Media**プロパティを数式に設定します。

    ```powerapps-dot
    Microphone1.Audio
    ```

    > [!NOTE]
    > マイクコントロール名*Microphone1*を適宜置き換えます。

1. アプリをプレビューします。
1. 録音を開始する**マイク**コントロールを選択します。
1. 音声を録音します。
1. 録音を終了するには、**マイク**の制御をもう一度選択します。
1. 録音を再生する**オーディオ**コントロールを選択します。  

### <a name="add-sounds-to-a-gallery-control"></a>ギャラリーコントロールにサウンドを追加する

この例では、再生用に個別に選択できるコレクションに格納されているオーディオクリップのギャラリーを作成します。

1. **マイク**コントロールを[追加](../add-configure-controls.md)します。

1. [Collect](../functions/function-clear-collect-clearcollect.md)関数を使用して、 **OnStop**プロパティを次の数式に設定します。

    ```powerapps-dot
    Collect( MySounds, MyMic.Audio )
    ```

1. **ギャラリー**コントロールを追加し、 **MyMic**の下に移動します。

1. ギャラリーの[Items](properties-core.md)プロパティを次の数式に設定します。

    ```powerapps-dot
    MySounds
    ```

1. **カスタムギャラリー**コントロールのテンプレートで、[オーディオ](control-audio-video.md)コントロールを追加します。

1. オーディオコントロールの**Media**プロパティを次の数式に設定します。

    ```powerapps-dot
    ThisItem.Url
    ```

1. F5 キーを押してアプリをプレビューします。

1. **[MyMic]** を選択して記録を開始し、もう一度選択して記録を停止します。

1. **ギャラリー**コントロールで、**オーディオ**コントロールの再生ボタンを選択して録音を再生します。

1. 必要な数の録画を追加し、Esc キーを押して既定のワークスペースに戻ります。

1. optional**ギャラリー**コントロールのテンプレートで、[ボタン](control-button.md)コントロールを追加します。

1. その[Onselect](properties-core.md)プロパティを数式に設定します。

    ```powerapps-dot
    Remove( MySounds, ThisItem )
    ```

1. F5 キーを押し、対応する**ボタン**コントロールを選択して記録を削除します。

[SaveData](../functions/function-savedata-loaddata.md)関数を使用して記録をローカルに保存するか、 [Patch](../functions/function-patch.md)関数を使用してデータソースを更新します。

## <a name="accessibility-guidelines"></a>アクセシビリティのガイドライン

**マイク**は特殊なボタンであるため、[ボタン](control-button.md)の場合と同じガイドラインが適用されます。 また、次の点を考慮してください。

### <a name="audio-alternatives"></a>音声の代替手段

言語障碍があるユーザーまたはマイクがないユーザー向けに、代替形式の入力を追加することを検討してください。 たとえば[、テキスト入力を](control-text-input.md)ユーザーに許可します。

### <a name="color-contrast"></a>色のコントラスト

- 標準の[色のコントラストの要件](../accessible-apps-color.md)を参照してください。
- [イメージ](properties-visual.md)とボタンのテキストとアイコン (該当する場合) の間に適切な色のコントラストを確保します。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート

- [AccessibleLabel](properties-accessibility.md)が存在している必要があります。
