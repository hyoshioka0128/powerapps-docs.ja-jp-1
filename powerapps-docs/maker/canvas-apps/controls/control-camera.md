---
title: 'カメラ コントロール: リファレンス | Microsoft Docs'
description: 各種プロパティとサンプルを含むカメラ コントロールに関する情報
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 04/07/2020
ms.author: chmoncay
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 59c0f85dd71c9dc512e348d6d8ee9686d6945fa1
ms.sourcegitcommit: 6acc6ac7cc1749e9681d5e55c96613033835d294
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/08/2020
ms.locfileid: "80871122"
---
# <a name="camera-control-in-power-apps"></a>Power Apps のカメラ コントロール

ユーザーがデバイスのカメラを使用して画像を撮影できるようにするコントロール。

## <a name="description"></a>説明

**カメラ**コントロールを使用して、デバイスのカメラで画像をキャプチャします。  デバイスにはカメラが必要です。ユーザーは、カメラを使用するようにアプリを承認する必要があります。 カメラコントロールは、web ブラウザーで実行する場合にサポートされます。

最後にキャプチャした画像は、 **Photo**プロパティを通じて入手できます。 このプロパティを使用すると、イメージは次のようになります。

- **イメージコントロールで表示されます。** [イメージ](control-image.md)コントロールを使用して、キャプチャしたイメージを表示します。 詳細については、[例](#examples)を参照してください。  
- **変数またはコレクションに一時的に配置します。**  変数またはコレクションに画像を格納するには、 [Set](../functions/function-set.md)関数または[Collect](../functions/function-clear-collect-clearcollect.md)関数を使用します。  コレクション内の複数のイメージを同時に使用して、デバイスの制限されたメモリを消費する場合は注意してください。 [SaveData](../functions/function-savedata-loaddata.md)関数と[LoadData](../functions/function-savedata-loaddata.md)関数を使用して、イメージをデバイスのローカルストレージと[オフラインのシナリオ](../offline-apps.md)に移動します。
- **データベースに格納されます。**  [Patch](../functions/function-patch.md)関数を使用して、データベースに画像を格納します。
- **Base64 でエンコードされたテキスト文字列として送信されます。**  [JSON](../functions/function-json.md)関数を使用して、イメージを base64 エンコードします。

**Stream**、 **Streamrate**、および**onstream**プロパティを使用して、タイマーの画像を自動的にキャプチャします。たとえば、画像を1分ごとにスナップして、時間の経過によるシーケンスを作成します。

キャプチャしたメディアは、テキスト文字列 URI によって参照されます。 詳細については、[データ型のドキュメント](../functions/data-types.md#uris-for-images-and-other-media)を参照してください。

カメラコントロールによって生成されるイメージは、通常、カメラの解像度が完全ではありません。 完全な解像度のイメージが必要な場合は、[[画像の追加](control-add-picture.md)] コントロールを使用します。

## <a name="key-properties"></a>主要なプロパティ

利用可能な**デバイス**–デバイスで使用可能なカメラのテーブルです。

テーブルには次の2つの列があります。 
- **カメラ**のプロパティで使用する*Id*番号 
- カメラを識別するためにデバイスによって提供される*名前*。 カメラ*を特定するの*に役立つプラットフォーム*もあります*。

*注*: テーブル内のすべてのデバイスがアプリで使用できるとは限りません。  特定の目的を想定した特殊なドライバーやアプリケーションもあります。  

**カメラ**–使用するカメラの数値 ID。  複数のカメラがあるデバイスで役に立ちます。  

**OnStream** – **Stream** プロパティが更新された場合のアプリの反応を指定します。

**Photo** –ユーザーが画像を撮影したときにキャプチャされる画像です。 

**Stream** – **StreamRate** プロパティに基づいて自動的に更新された画像です。

**StreamRate** – **Stream** プロパティの画像を更新する頻度です (ミリ秒単位)。 この値の範囲は、100 (0.1 秒) から 3,600,000 (1 時間) です。

## <a name="additional-properties"></a>その他のプロパティ

[AccessibleLabel](properties-accessibility.md) – スクリーン リーダー用のラベルです。 写真撮影の目的を説明する必要があります。

[BorderColor](properties-color-border.md) – コントロールの境界線の色です。

[BorderStyle](properties-color-border.md) – コントロールの境界線のスタイルです (**実線**、**破線**、**点線**、または**なし**)。

[BorderThickness](properties-color-border.md) – コントロールの境界線の太さです。

**Brightness** – ユーザーが画像で認識する可能性のある光の量を指定します。

**Contrast** – ユーザーが画像内の似た色をどれだけ容易に区別できるかを指定します。

[DisplayMode](properties-core.md) –コントロールでユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、または無効 (**無効**) にするかを指定します。

[FocusedBorderColor](properties-color-border.md) –コントロールがフォーカスされているときのコントロールの境界線の色です。

[FocusedBorderThickness](properties-color-border.md) –コントロールがフォーカスされているときのコントロールの境界線の太さです。

[Height](properties-size-location.md) – コントロールの上端と下端の距離です。

[OnSelect](properties-core.md) – ユーザーがコントロールをタップまたはクリックした場合のアプリの反応を指定します。

[TabIndex](properties-accessibility.md) –他のコントロールと比較したキーボードナビゲーション順序。

[Tooltip](properties-core.md) – ポインターをコントロールに合わせたときに表示される説明テキストです。

[Visible](properties-core.md) – コントロールを表示するか非表示にするかを指定します。

[Width](properties-size-location.md) – コントロールの左端と右端の間の距離です。

[X](properties-size-location.md) –コントロールの左端とその親コンテナーまたは画面の左端の間の距離です。

[Y](properties-size-location.md) –コントロールの上端と親コンテナーまたは画面の上端との距離です。

## <a name="examples"></a>使用例

これらの例では、カメラ付きのデバイスが必要です。 アプリをテストするには、ブラウザーからアクセスできる web cam を使用します。 または、アプリを保存して、カメラを使用して iOS または Android デバイスに読み込むことができます。

### <a name="simple-display-of-a-captured-picture"></a>キャプチャした画像の簡易表示

1. **カメラ**コントロールを[追加](../add-configure-controls.md)します。

1. メッセージが表示されたら、デバイスのカメラを使用するようにアプリを承認します。

1. [**イメージ**](../controls/control-image.md)コントロールを追加します。

1. **イメージ**コントロールの**image**プロパティを次の式に設定します。

    ```powerapps-dot
    Camera1.Photo
    ```

    > [!NOTE]
    > 必要に応じて、カメラコントロール名*Camera1*を置き換えます。

1. F5 キーを押してアプリをプレビューします。

1. カメラコントロールを選択またはタップして画像を撮影します。 イメージコントロールに結果が表示されます。

### <a name="add-pictures-to-an-image-gallery-control"></a>画像ギャラリーコントロールへの画像の追加

1. **カメラ**コントロールを追加し、 **mycamera**という名前を指定して、その[onselect](properties-core.md)プロパティを次の数式に設定します。

    ```powerapps-dot
    Collect( MyPix, MyCamera.Photo )
    ```

    詳しくは、次のトピックをご覧ください。

    - [コントロールを追加、名前、および構成する方法](../add-configure-controls.md)
    - 関数または[その他の関数の](../formula-reference.md)[収集](../functions/function-clear-collect-clearcollect.md)の詳細については、こちらをご覧ください。

1. F5 キーを押し、 **[Mycamera]** を選択またはタップして画像を撮影します。

1. [縦方向のギャラリー](control-gallery.md)コントロールを追加します。 その後、[イメージ](control-image.md)コントロール、テンプレート、および**イメージギャラリー**コントロール自体のサイズを画面に合わせて変更します。

1. **イメージギャラリー**コントロールの[Items](properties-core.md)プロパティを次の数式に設定します。
 
    ```powerapps-dot
    MyPix
    ```

1. ギャラリー内の**イメージ**コントロールの[image](properties-visual.md)プロパティを次の数式に設定します。

    ```powerapps-dot   
    ThisItem.Url
    ```

    撮影した画像が**イメージギャラリー**コントロールに表示されます。

1. 必要な数の画像を取得し、Esc キーを押して既定のワークスペースに戻ります。

1. optional**イメージギャラリー**コントロール内の**イメージ**コントロールの**onselect**プロパティを数式に設定します。

    ```powerapps-dot
    Remove( MyPix, ThisItem )
    ```

1. F5 キーを押し、画像を選択して削除します。

画像をローカルに保存する場合は[SaveData](../functions/function-savedata-loaddata.md)関数を使用し、データソースを更新する場合は[Patch](../functions/function-patch.md)関数を使用します。

### <a name="change-the-active-camera-from-a-drop-down"></a>アクティブなカメラをドロップダウンから変更する

1. **カメラ**コントロールを[追加](../add-configure-controls.md)します。

1. メッセージが表示されたら、デバイスのカメラを使用するようにアプリを承認します。
    
1. [ドロップダウン](control-drop-down.md)コントロールを[追加](../add-configure-controls.md)します。

1. ドロップダウンリストの**項目**prroperty を次のように設定します。

    ```powerapps-dot
    Camera1.AvailableDevices
    ```

    > [!NOTE]
      > 必要に応じて、カメラコントロール名*Camera1*を置き換えます。
    
1. カメラの**カメラ**プロパティを次のように設定します。 

    ```powerapps-dot
    Dropdown1.Selected.Id
    ```

    > [!NOTE]
      > 必要に応じて、ドロップダウンコントロール名*Dropdown1*を置き換えます。

1. F5 キーを押し、ドロップダウンから項目を選択して、カメラを変更します。

## <a name="accessibility-guidelines"></a>アクセシビリティのガイドライン

カメラコントロールは、カメラのフィードを表示し、画像を撮影するボタンとしても機能します。 そのため、ボタンと同様のアクセシビリティの考慮事項があります。

### <a name="video-alternatives"></a>ビデオの代替手段

視覚障碍があるユーザー向けに、代替形式の入力を追加することを検討してください。 たとえば、[画像を追加](control-add-picture.md)して、ユーザーが自分のデバイスからイメージをアップロードできるようにします。

### <a name="color-contrast"></a>色のコントラスト

[FocusedBorderColor](properties-color-border.md)と外側の色の間には適切な色のコントラストが必要です。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート

[AccessibleLabel](properties-accessibility.md)が存在している必要があります。

### <a name="keyboard-support"></a>キーボードのサポート

- [TabIndex](properties-accessibility.md)は、キーボードユーザーが移動できるように、0以上である必要があります。

- フォーカス インジケーターは明確に表示する必要があります。 フォーカスインジケーターの表示を更新するには、 [FocusedBorderColor](properties-color-border.md)と[FocusedBorderThickness](properties-color-border.md)を使用します。
