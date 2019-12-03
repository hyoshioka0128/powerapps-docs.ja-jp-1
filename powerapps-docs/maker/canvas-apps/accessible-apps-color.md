---
title: キャンバス アプリのアクセシビリティ対応色 | Microsoft Docs
description: PowerApps のキャンバス アプリ向けカラー コントラスト ガイドライン
author: tahoon
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/23/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 44c94a712402ef26a4fa6b36d84e287d3fa506e1
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74679295"
---
# <a name="accessible-colors-for-canvas-apps-in-powerapps"></a>PowerApps のキャンバス アプリ向けのアクセシビリティ対応色
キャンバス アプリで使用する色は、色覚や視力に障碍のあるユーザーでも認識できるものにする必要があります。 既定では、すべての Power Apps テーマにアクセスできます。 アプリで使う色を変更するときは、この記事のガイドラインに従って、アクセシビリティを維持するようにしてください。 色コントラストの問題の特定に役立つ、オンラインで入手できるツールがいくつかあります。

## <a name="minimum-contrast-for-text"></a>テキストの最低限のコントラスト
* テキストとその背景のコントラスト比を、4.5:1 以上にする必要があります
* 大きなテキストは、コントラスト比を 3:1 以上にする必要があります
* 無効になっているテキストについては、コントラストの要件はありません

実際には、すべての対話型コントロールで次のものの間が適切な色コントラストになっている必要があります。
* **[色](controls/properties-color-border.md)** と **[塗りつぶし](controls/properties-color-border.md)**
* **[PressedColor](controls/properties-color-border.md)** と **[PressedFill](controls/properties-color-border.md)**
* **[HoverColor](controls/properties-color-border.md)** と **[HoverFill](controls/properties-color-border.md)**

## <a name="minimum-contrast-for-non-text"></a>テキスト以外の最低限のコントラスト

> [!NOTE]
> [WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-contrast.html) 標準では、コントラストの要件はテキストのみに適用されます。 アクセシビリティをよりよくするため、アイコン ボタンのような基本的なユーザー インターフェイス コンポーネントについては、今後の [WCAG 2.1 コントラスト ガイドライン](https://www.w3.org/TR/WCAG21/#non-text-contrast)を検討してください。 これらのコンポーネントの場合は、3:1 以上の比率にすることをお勧めします。 このセクションで説明するガイドラインは、WCAG 2.0 準拠のための**オプション**です。

### <a name="user-interface-components"></a>ユーザー インターフェイスのコンポーネント
すべての対話型コントロールで次のものの間が適切な色コントラストになっている必要があります。
* **[FocusedBorderColor](controls/properties-color-border.md)** とコントロールの外側の色

領域全体が対話型または情報提供型であるコントロールについては、追加の色コントラスト チェックが適用されます。 たとえば、 **[ボタン](controls/control-button.md)** や、ボタンとして使われている **[アイコン](controls/control-shapes-icons.md)** などです。 これにより、コントロールの境界が明確になり、ユーザーはどこをクリックまたはタップすればよいかがわかります。

そのようなコントロールの境界がある場合は、次のものの間の色コントラストを適切にする必要があります。
* **[BorderColor](controls/properties-color-border.md)** とコントロールの外側の色
* **[PressedBorderColor](controls/properties-color-border.md)** とコントロールの外側の色
* **[HoverBorderColor](controls/properties-color-border.md)** とコントロールの外側の色

境界がない場合は、次のものの間の色コントラストを適切にする必要があります。
* **[Fill](controls/properties-color-border.md)** とコントロールの外側の色
* **[PressedFill](controls/properties-color-border.md)** とコントロールの外側の色
* **[HoverFill](controls/properties-color-border.md)** とコントロールの外側の色

### <a name="graphical-objects"></a>グラフィック オブジェクト
画像が重要な情報を伝達する場合は、画像についてコントラストの問題を確認することを検討します。 これは、 **[オーディオ](controls/control-audio-video.md)** 、 **[イメージ](controls/control-image.md)** 、 **[マイク](controls/control-microphone.md)** 、 **[ビデオ](controls/control-audio-video.md)** など、画像を表示できるコントロールに当てはまります。

ビデオ コンテンツの場合、コントラストの問題を確認することを検討します。 その代わりに、またはそれに加えて、ビデオについて説明する[クローズド キャプション](controls/control-audio-video.md)を提供します。

## <a name="provide-other-visual-cues"></a>他の視覚的な手掛かりを提供する
アプリが色だけで情報を伝達していないことを確認します。 たとえば、赤緑の色覚に障碍があるユーザーは、赤のエラー メッセージと緑の成功メッセージを区別できません。

**[アイコン](controls/control-shapes-icons.md)** または **[斜体](controls/properties-text.md)** や **[下線](controls/properties-text.md)** などのテキスト スタイルといった追加の手掛かりは、意味を伝えるのに役立ちます。

## <a name="next-steps"></a>次の手順
Power Apps コントロールの[アクセシビリティのプロパティ](controls/properties-accessibility.md)について学習し、[アクセシビリティチェッカーを使用](accessibility-checker.md)してみてください。
