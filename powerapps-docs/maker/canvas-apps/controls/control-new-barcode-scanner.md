---
title: 'バーコード-スキャナーコントロール: リファレンス |Microsoft Docs'
description: プロパティと例を含む、バーコードスキャナーコントロールに関する情報
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 11/25/2018
ms.author: chmoncay
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d2499a597295147cea1b39bb18fee2cbb056b413
ms.sourcegitcommit: ebb4bb7ea7184e31dc95f0c301ebef75fae5fb14
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2020
ms.locfileid: "80624983"
---
# <a name="barcode-scanner-control-for-canvas-apps"></a>バーコード-キャンバスアプリのスキャナーコントロール

Android または iOS デバイスのバーコード、QR コード、およびデータマトリックスコードをスキャンします。 Web ブラウザーではサポートされていません。

## <a name="description"></a>説明

コントロールは、Android または iOS デバイスでネイティブスキャナーを開きます。 スキャナーは、表示されているときに、バーコード、QR コード、またはデータマトリックスコードを自動的に検出します。 コントロールは、web ブラウザーでのスキャンをサポートしていません。

## <a name="key-properties"></a>主要なプロパティ

**Value** –最近スキャンされたコードのテキスト値を含む出力プロパティ。

**Type** –最近スキャンされたコードの種類を含む出力プロパティ。

**Onscan** –バーコードが正常にスキャンされた場合にアプリがどのように応答するかを示します。

**OnCancel** –ユーザーがバーコードスキャンをキャンセルした場合のアプリの反応を示します。

**Barcodetype** -スキャンするバーコードの種類。 複数のバーコードの種類を連結してターゲットを付けることができます。 例: Code128 & BarcodeType. Code39**既定値: Auto**

**PreferFrontCamera** -フロント接続カメラが使用可能な場合、スキャンに使用されるかどうか。

**FlashlightEnabled** -スキャナーを開いたときに、懐中電灯を自動的に有効にするかどうかを指定します。

## <a name="additional-properties"></a>その他のプロパティ

スキャナーをアクティブにするボタンに表示される**テキスト**テキスト。

**[BorderColor](properties-color-border.md)** – コントロールの境界線の色です。

**[BorderStyle](properties-color-border.md)** – コントロールの境界線を **Solid** (実線)、**Dashed** (破線)、**Dotted** (点線)、**None** (なし) のいずれに指定します。

**[BorderThickness](properties-color-border.md)** – コントロールの境界線の太さです。

**[DisplayMode](properties-core.md)** – コントロールで、ユーザー入力を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**[Height](properties-size-location.md)** –スキャナーをアクティブにするボタンの高さ。

**[Tooltip](properties-core.md)** – ユーザーがポインターをコントロールに合わせたときに表示される説明テキストです。

**Type** -最後に成功したスキャンで検出されたコードの種類。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかを指定します。

**[Width](properties-size-location.md)** –スキャナーをアクティブにするボタンの幅。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。

## <a name="accessibility-guidelines"></a>アクセシビリティのガイドライン
**[ボタン](control-button.md)** コントロールの同じガイドラインが**バーコードスキャナー**コントロールにも適用されます。これは、スキャンを起動するボタンであるためです。

### <a name="visual-alternatives"></a>ビジュアルの代替
* バーコードスキャナーは、スキャン結果を表示しないボタンです。 **[ラベル](control-text-box.md)** コントロールを使用してスキャン結果を表示することを検討してください。 ラベルの **[Text](properties-core.md)** プロパティをバーコードスキャナーの**値**プロパティに設定します。 スクリーンリーダーのユーザーに変更が通知されるように、ラベルの **[Live](properties-accessibility.md)** プロパティを "**丁寧**" に設定します。 この変更により、スキャンした値は、視覚機能に関係なくすべてのユーザーがアクセスできるようになります。

* 視覚障碍のあるユーザーは、バーコードでカメラをポイントしたくない場合があります。 ユーザーがバーコードを入力するには、 **[テキスト入力](control-text-input.md)** コントロールなど、別の形式の入力を追加することを検討してください。

## <a name="barcode-availability-by-device"></a>デバイス別のバーコードの可用性

| バーコードの種類 | Android | iOS |
|--------------|:-------:|:---:|
|QR_CODE|✔|✔|
|DATA_MATRIX|✔|✔|
|UPC_A|✔|✔|
|UPC_E|✔|✔|
|EAN_8|✔|✔|
|EAN_13|✔|✔|
|CODE_39|✔|✔|
|CODE_93|✔|✔|
|CODE_128|✔|✔|
|CODABAR|✔|✖|
|ITF|✔|✔|
|RSS14|✔|✖|
|PDF_417|✔|✔|
|RSS_EXPANDED|✔|✖|
|MSI|✖|✖|
|アズ|✔|✔|

**注:** PDF_417 およびアステカは Auto モードではサポートされていません
