---
title: 'プレビュー: モデル駆動型アプリで強化された電子メール エクスペリエンスを使用して電子メールを送信する | MicrosoftDocs'
description: 強化された電子メール エクスペリエンスを使用して、作業中の内容を離れることなく電子メールを作成します。
ms.date: 02/03/2020
ms.service:
- dynamics-365-sales
ms.topic: article
author: shubhadaj
ms.author: shujoshi
manager: annbe
ms.openlocfilehash: 6f3c603284e5f5d53380f5caa932cafac11e2d7a
ms.sourcegitcommit: 68a31e3fa4d1635ccf4cd8bd9da5fba1bfecefa4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77051938"
---
# <a name="preview-send-email-using-the-enhanced-email-experience"></a>プレビュー:強化された電子メール エクスペリエンスを使用した電子メールの送信

強化された電子メール エクスペリエンスを使用した電子メールの送信は、先行アクセス機能です。 お使いの環境でこれらの機能を有効にするために、先行してオプトインできます。 これらの機能をテストして環境全体に導入することができるようになります。 これらの機能を有効にする方法の詳細については、[2020 リリース ウェーブ 1 更新プログラムへのオプトイン](https://docs.microsoft.com/power-platform/admin/opt-in-early-access-updates)に関するページをご覧ください。

モデル駆動型アプリの強化された電子メール エクスペリエンスにより、作業中のレコードを離れることなく電子メールを作成できます。 強化された電子メール エクスペリエンスにより、次のことが可能になりました。

- 電子メールの内容を失うことなく、別のページに移動する。
- 電子メール ウィンドウを最小化して、作業中のレコードに戻る。
- 電子メール エディターのポップアップ ウィンドウを展開して、さらに多くの電子メール オプションを表示する。
- 同時に 3 つの電子メールを作成するポップアップ ウィンドウを開く。
- 事前定義されたテンプレートを検索して、作成している電子メールに適用する。
- 電子メールに添付ファイルを挿入する。


> [!IMPORTANT]
> - 強化された電子メール エクスペリエンスを使用するには、事前にシステム管理者が有効にする必要があります。
> - [!INCLUDE[cc_preview_features_definition](../includes/cc-preview-features-definition.md)]  
> - [!INCLUDE[cc_preview_features_expect_changes](../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE[cc-preview-features-no-ms-support](../includes/cc-preview-features-no-ms-support.md)]

強化された電子メール エクスペリエンスを使用した電子メールの作成:

1. アカウントや連絡先などのレコードの **[タイムライン]** セクションで、 **+** を選択し、 **[アクティビティ]** の **[電子メール]** を選択します。

   新しい電子メールのポップアップ ウィンドウが開きます。 

   > [!div class="mx-imgBorder"]
   > ![強化された電子メールのポップアップ ウィンドウ](media/enhanced-email-pop-up.png "強化された電子メールのポップアップ ウィンドウ")

   **[From]\(差出人\)** フィールドと **[To]\(宛先\)** フィールドは、ユーザーと、元のレコードのアカウントと連絡先に基づいて自動的に設定されます。

2. 電子メールを最初から作成するか、 **[テンプレートの挿入]** を選択して、テンプレートを検索して適用します。 電子メール テンプレートの挿入の詳細については、「[電子メール テンプレートを挿入する](insert-email-template.md)」を参照してください。

3. 添付ファイルを追加する場合は、 **[ファイルを添付]** を選択します。

4. 署名を検索して追加するには、 **[署名の挿入]** を選択します。

5. 完了したら、 **[送信]** を選択します。 

> [!IMPORTANT]
> - 強化された電子メール エクスペリエンスは、モデル駆動型アプリの **[タイムライン]** セクションから作成された電子メール アクティビティに対してのみ使用できます。 
> - 強化された電子メールのポップアップ ウィンドウは、画面サイズの高さと幅が 400 x 650 ピクセル以上の場合にのみ表示されます。 それより小さい場合は、強化された電子メール エクスペリエンスではなく、標準フォームに移動します。 

### <a name="see-also"></a>関連項目

[強化された電子メールを設定する](https://docs.microsoft.com/power-platform/admin/system-settings-dialog-box-email-tab)<br>
[電子メール テンプレートを挿入する](insert-email-template.md)
