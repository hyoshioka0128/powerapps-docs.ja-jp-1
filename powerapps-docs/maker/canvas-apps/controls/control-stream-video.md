---
title: 'Microsoft Stream ビデオコントロール: リファレンス |Microsoft Docs'
description: プロパティと例を含む Microsoft Stream ビデオコントロールに関する情報
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/26/2019
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 00c13a3b57cce0f7c8831b0932f7e17bbb32efe7
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2019
ms.locfileid: "75203952"
---
# <a name="microsoft-stream-video-control-in-power-apps"></a>Power Apps でのビデオコントロールの Microsoft Stream
Microsoft Stream ビデオとチャンネルのビデオプレーヤー。

## <a name="description"></a>Description
コントロールを使用すると、アプリユーザーはビデオを再生し、Microsoft Stream サービスからチャネルを参照できます。

## <a name="limitations"></a>制限事項
コントロールは、現在、Power Apps 用のネイティブ Windows プレーヤーではサポートされていません。  Web ブラウザーと Android および iOS の Power Apps プレーヤーでも正常に動作します。

## <a name="key-properties"></a>主要なプロパティ
**Streamurl** –コントロールに表示される Microsoft Stream ビデオまたはチャネルの url です。

**Showcontrols** –ビデオ再生コントロールをエンドユーザーに表示するかどうかを指定します。

## <a name="additional-properties"></a>その他のプロパティ
**[AccessibleLabel](properties-accessibility.md)** – スクリーン リーダー用のラベルです。 ビデオまたはオーディオ クリップのタイトルにする必要があります。

**AutoStart** – ユーザーがオーディオまたはビデオ コントロールを含む画面に移動したときに、自動的にクリップの再生を開始するかどうかを指定します。

**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**[Fill](properties-color-border.md)** – コントロールの背景色です。

**[FocusedBorderColor](properties-color-border.md)** – コントロールにフォーカスがあるときのコントロールの境界線の色です。

**[FocusedBorderThickness](properties-color-border.md)** – コントロールにフォーカスがあるときのコントロールの境界線の太さです。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**StartTime** – クリップの再生が開始するとき、オーディオまたはビデオ クリップの開始後の時刻です。

**[TabIndex](properties-accessibility.md)** – 他のコントロールに関連するキーボード ナビゲーションの順序です。

**[Tooltip](properties-core.md)** – ポインターをコントロールに合わせたときに表示される説明テキストです。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="example"></a>例

### <a name="play-an-audio-or-video-file-from-microsoft-stream"></a>Microsoft Stream からオーディオまたはビデオファイルを再生する

1. [**ファイル**] メニューの [**挿入**] をポイントし、[**メディア**を開く] ドロップダウンメニューをクリックします。 
2. メディアコントロールの一覧から**Microsoft Stream**を選択します。

    ![Microsoft Stream](./media/control-stream-video/stream-icon.png "Microsoft Stream")

3. 左側の [**ストリーム URL** ] プロパティ内にビデオリンクを貼り付けます。

    ![StreamUrl プロパティのカスタマイズ](./media/control-stream-video/stream-url.png "StreamUrl プロパティのカスタマイズ")

4. F5 キーを押して、追加したコントロールの [再生] ボタンを選択します。

    > [!NOTE]
   > **Microsoft Stream**には、ビデオを再生するための認証が必要です。 アプリユーザーに必要なアクセス許可があることを確認します。
5. Esc キーを押して、プレビューモードを終了します。

## <a name="browser-considerations"></a>ブラウザーに関する考慮事項

### <a name="ios"></a>iOS
IOS プレーヤーでは、アプリに埋め込まれているビデオの直接再生はサポートされていません。  ビデオを見るには、ストリームアイコンをクリックして、ビデオプレーヤーを全画面表示モードで起動します。

### <a name="safari"></a>Safari

Safari ブラウザーでアプリの Microsoft Stream ビデオを表示するには、[クロスサイトトラッキング](https://support.apple.com/guide/safari/sfri40732/mac)を使用しないようにするために、このオプションをオフにする必要があります。

## <a name="accessibility-guidelines"></a>アクセシビリティ ガイドライン
### <a name="audio-and-video-alternatives"></a>オーディオおよびビデオの代替手段
* ユーザーが自分のペースでマルチメディアを視聴できるように、**ShowControls** を true にする必要があります。 これにより、ユーザーはビデオ プレーヤーでクローズド キャプションや全画面モードを切り替えることもできます。
* クローズド キャプションがビデオに対して提供されている必要があります。
 * 次のいずれかの方法を使用して、オーディオまたはビデオのトランスクリプトを提供することを検討してください。
  1. **[ラベル](control-text-box.md)** にテキストを挿入し、マルチメディア プレーヤーの隣に配置します。 必要に応じて、テキストの表示を切り替える **[ボタン](control-button.md)** を作成します。
  2. 別の画面にテキストを配置します。 その画面に移動する **[ボタン](control-button.md)** を作成し、マルチメディア プレーヤーの隣にボタンを配置します。
  3. 説明が短い場合は、**[AccessibleLabel](properties-accessibility.md)** に格納できます。

### <a name="color-contrast"></a>色のコントラスト
以下の間には適切な色のコントラストが必要です。
* **[FocusedBorderColor](properties-color-border.md)** と外側の色
* **[Fill](properties-color-border.md)** とマルチメディア プレーヤーのコントロール (背景色を表示する場合)

ビデオ コンテンツに色のコントラストの問題がある場合は、クローズド キャプションまたはトランスクリプトを提供します。

### <a name="screen-reader-support"></a>スクリーン リーダーのサポート
* **[AccessibleLabel](properties-accessibility.md)** が存在する必要があります。

### <a name="keyboard-support"></a>キーボードのサポート
* **[TabIndex](properties-accessibility.md)** を 0 以上にして、キーボード ユーザーがそこに移動できるようにする必要があります。
* フォーカス インジケーターは明確に表示する必要があります。 これを実現するには **[FocusedBorderColor](properties-color-border.md)** と **[FocusedBorderThickness](properties-color-border.md)** を使用します。
* **AutoStart** は、キーボード ユーザーが再生をすばやく停止するのが難しい場合があるので、false にする必要があります。
