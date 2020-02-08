---
title: 'プレビュー: モデル駆動型アプリの電子メールの機能強化を使用して電子メールを送信する |MicrosoftDocs'
description: 強化された電子メールエクスペリエンスを使用して、作業内容のコンテキストを離れることなく電子メールを作成します。
ms.date: 02/03/2020
ms.service:
- dynamics-365-sales
ms.topic: article
author: shubhadaj
ms.author: shujoshi
manager: annbe
ms.openlocfilehash: 6f3c603284e5f5d53380f5caa932cafac11e2d7a
ms.sourcegitcommit: 68a31e3fa4d1635ccf4cd8bd9da5fba1bfecefa4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051938"
---
# <a name="preview-send-email-using-the-enhanced-email-experience"></a>プレビュー: 電子メールの拡張機能を使用して電子メールを送信する

強化された電子メールエクスペリエンスを使用した電子メールの送信は、早期アクセス機能です。 環境でこれらの機能を有効にするために、早い段階で選択できます。 これにより、これらの機能をテストして、環境全体に導入することができます。 これらの機能を有効にする方法の詳細については、「 [2020 リリース wave 1 更新プログラムのオプトイン](https://docs.microsoft.com/power-platform/admin/opt-in-early-access-updates)」を参照してください。

モデル駆動型アプリの電子メールエクスペリエンスの向上により、作業中のレコードを離れることなく電子メールを作成できます。 電子メールエクスペリエンスの向上により、次のことが可能になりました。

- 電子メールの内容が失われないように、別のページに移動します。
- 電子メールウィンドウを最小化して、作業中のレコードに戻ります。
- 電子メールエディターのポップアップウィンドウを展開すると、さらに多くの電子メールオプションが表示されます。
- 同時に、3つの電子メールを作成するポップアップウィンドウを開きます。
- 事前に定義したテンプレートを検索して、作成している電子メールに適用します。
- 電子メールに添付ファイルを挿入します。


> [!IMPORTANT]
> - システム管理者は、使用する前に、強化された電子メールエクスペリエンスを有効にする必要があります。
> - [!INCLUDE[cc_preview_features_definition](../includes/cc-preview-features-definition.md)]  
> - [!INCLUDE[cc_preview_features_expect_changes](../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE[cc-preview-features-no-ms-support](../includes/cc-preview-features-no-ms-support.md)]

強化されたエクスペリエンスを使用して電子メールを作成します。

1. アカウント や 連絡先 などのレコードの **タイムライン** セクションで、 **+** を選択し、**活動** で **電子メール** を選択します。

   新しい電子メールのポップアップウィンドウが開きます。 

   > [!div class="mx-imgBorder"]
   > ![強化された電子メールのポップアップウィンドウ](media/enhanced-email-pop-up.png "強化された電子メールのポップアップウィンドウ")

   **[開始]** **および [移動] フィールドは**、ユーザーと、元のレコードのアカウントと連絡先に基づいて自動的に設定されます。

2. メールを最初から作成するか、 **[テンプレートの挿入]** を選択して、テンプレートを検索して適用します。 電子メールテンプレートの挿入の詳細については、「[電子メールテンプレートを挿入する](insert-email-template.md)」を参照してください。

3. 添付**ファイル**を追加する場合は、[ファイルの添付] を選択します。

4. **[署名の挿入]** を選択して、署名を検索し、追加します。

5. 完了したら、 **[送信]** を選択します。 

> [!IMPORTANT]
> - 強化された電子メールエクスペリエンスは、モデル駆動型アプリの**タイムライン**セクションから作成された電子メールアクティビティに対してのみ使用できます。 
> - [電子メールの拡張] ポップアップウィンドウは、画面サイズの高さと幅が 400 x 650 ピクセル以上になっている場合にのみ表示されます。 低い場合は、電子メールエクスペリエンスの向上ではなく標準フォームに移動します。 

### <a name="see-also"></a>参照

[強化された電子メールのセットアップ](https://docs.microsoft.com/power-platform/admin/system-settings-dialog-box-email-tab)<br>
[電子メールテンプレートを挿入する](insert-email-template.md)
