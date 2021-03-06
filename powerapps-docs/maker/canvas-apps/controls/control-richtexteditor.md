---
title: 'リッチ テキスト エディター コントロール: リファレンス | Microsoft Docs'
description: プロパティとサンプルを含むリッチ テキスト エディター コントロールに関する情報
author: chmoncay
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/24/2018
ms.author: chmoncay
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1c9bbfd724f588dce86c5ba2e620404f554d2bcd
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74732118"
---
# <a name="rich-text-editor-control-in-power-apps"></a>Power Apps のリッチテキストエディターコントロール
エンドユーザーが WYSIWYG 編集領域内のテキストを書式設定できるようにします。  出力形式は、HTML です。

## <a name="description"></a>Description
**リッチ テキスト エディター** コントロールにより、アプリのユーザーにテキストの書式設定のための WYSIWYG 編集領域が提供されます。  コントロールの入出力形式は HTML です。

コントロールにより、(Web ブラウザーまたは Word から) コピーしたリッチ テキストを コントロールに貼り付けることができます。  

コントロールの目的はテキストの書式設定であるため、入力 HTML の整合性の保持は保証されません。  すべてのスクリプト、スタイル、オブジェクト、その他の影響を受ける可能性のあるタグがエディターによって削除されます。  これは、リッチテキストが Power Apps 以外で作成された場合、それが作成された製品と同じように見えない可能性があることを意味します。

現在サポートされている機能は次のとおりです。
- 太字、斜体、下線
- テキストの色、色の強調表示
- テキスト サイズ
- 番号付きリスト、箇条書きリスト
- ハイパーリンク
- 書式のクリア

フォーム内のコントロールを使用するには、"複数行テキストの編集" カードを選択し、RTE コントロールを挿入してカスタマイズします。

## <a name="key-properties"></a>主要なプロパティ
**[Default](properties-core.md)** – エディターに表示される最初のテキスト値の入力プロパティ。

**HtmlText** – HTML 形式で作成されたリッチ テキストの出力プロパティ。


## <a name="additional-properties"></a>その他のプロパティ
**[AccessibleLabel](properties-accessibility.md)** – スクリーン リーダー用のラベルです。 添付ファイルの目的を説明する必要があります。

**[DisplayMode](properties-core.md)** – コントロールで、ファイルの追加と削除を許可するか (**Edit**)、データの表示のみを許可するか (**View**)、許可しないか (**Disabled**) を設定します。

**EnableSpellCheck** –ブラウザーのスペルチェックを有効にするかどうかを指定します。 この機能は、ブラウザーの既定の言語でのみスペルチェックを行うことに注意してください。  Windows 用の Power Apps では、このプロパティはサポートされていません。

**[Height](properties-size-location.md)** – コントロールの上端と下端の距離です。

**[TabIndex](properties-accessibility.md)** – 他のコントロールに関連するキーボード ナビゲーションの順序です。

**[Visible](properties-core.md)** – コントロールを表示するか非表示にするかです。

**[Width](properties-size-location.md)** – コントロールの左端と右端の間の距離です。

**[X](properties-size-location.md)** – コントロールの左端とその親コンテナー (親コンテナーがない場合は画面) の左端間の距離です。

**[Y](properties-size-location.md)** – コントロールの上端とその親コンテナー (親コンテナーがない場合は画面) の上端間の距離です。


## <a name="accessibility-guidelines"></a>アクセシビリティ ガイドライン
### <a name="screen-reader-support"></a>スクリーン リーダーのサポート
* **[AccessibleLabel](properties-accessibility.md)** が存在する必要があります。

### <a name="keyboard-support"></a>キーボードのサポート
* **[TabIndex](properties-accessibility.md)** を 0 以上にして、キーボード ユーザーがそこに移動できるようにする必要があります。

> [!TIP]
> 他のキーボードショートカットについては、エディターにフォーカスがあるときに**Alt + 0**を使用します。
