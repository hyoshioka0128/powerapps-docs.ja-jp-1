---
title: モデル駆動型アプリでメールの作成中に電子メール テンプレートを挿入 | MicrosoftDocs
description: メールの作成中に、フォーマット済みの電子メール メッセージを挿入します。
ms.date: 04/09/2020
ms.service:
- dynamics-365-sales
ms.topic: article
author: sbmjais
ms.author: shjais
manager: shujoshi
ms.openlocfilehash: 8f5b607375cccd03b3bcea2bd5d50664e7033ae4
ms.sourcegitcommit: 2484ebce6563cfd1c849e1e2f66dd2d29fdb7b64
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/10/2020
ms.locfileid: "3303601"
---
# <a name="insert-an-email-template"></a>電子メール テンプレートを挿入する

電子メール テンプレート—フォーマット済み電子メール メッセージ—を使用して、電子メール メッセージを迅速に作成、送信できます。 コマンドバーで **テンプレートの挿入** を選択して、メールの作成中にテンプレートを挿入できます。 利用可能なテンプレートの一覧は、**電子メール テンプレート** ウィンドウに表示されます。 **最近使った項目** セクションに、最近使用した 4 つのテンプレートが表示されます。 **すべてのテンプレート** セクションには、すぐに使用できるすべての電子メール テンプレート (グローバルおよびエンティティ固有) のリストがアルファベット順に表示されます。 グローバル テンプレートは、ユーザーの種類として表示されます。 ユーザー定義電子メール テンプレートを作成した場合は、こちらからも利用できます。 ユーザー定義電子メール テンプレートの作成に関する詳細は、[電子メールのテンプレートの作成](https://docs.microsoft.com/power-platform/admin/create-templates-email) を参照してください。

**言語** 一覧から言語を選択すると、特定の言語のテンプレートを表示できます。 テンプレートを検索するか一覧を参照して、選択できます。 電子メール テンプレートを選択すると、ウィンドウの右側にプレビューが表示されます。 プレビューにはコンテンツが表示されるため、ニーズに最適なテンプレートを選択できます。 電子メール テンプレートを挿入した後、必要に応じてコンテンツを変更し、メールを送信できます。

> [!NOTE]
> 検索は正規表現をサポートしておらず、テンプレート名でのみ機能します。

**電子メール テンプレートを挿入するには**

1.  メール エディターで、コマンドバーの **テンプレートの挿入** を選択します。

     > [!div class="mx-imgBorder"]
     > ![テンプレート ボタンの挿入](media/insert-email-template-button.png "テンプレート ボタンの挿入") 

    **電子メール テンプレート** ウィンドウが開きます。

2.  別のロケールのテンプレートを表示するには、**言語** 一覧から言語を選択します。 選択した言語に従ってテンプレートがロードされます。    

3.  必要なテンプレートを参照します。 テンプレートを選択し、テンプレートのコンテンツをプレビューします。

4.  必要に応じて、テンプレートの名前にある下矢印を選択して、コンテンツの説明を確認します。

5.  **テンプレートの適用** を選択して、メールにコンテンツを挿入します。

     > [!div class="mx-imgBorder"]
     > ![電子メール テンプレート ウィンドウ](media/email-templates-window.png "電子メール テンプレート ウィンドウ")

画面サイズの小さいデバイスに電子メール テンプレートを挿入しようとすると、テンプレートを検索して選択するオプションしか表示されません。

> [!div class="mx-imgBorder"]
> ![テンプレートの検索](media/search-template.png "テンプレートの検索") 

### <a name="see-also"></a>関連項目

[拡張電子メールの設定](https://docs.microsoft.com/power-platform/admin/system-settings-dialog-box-email-tab)<br>
[拡張電子メール エクスペリエンスを使用して、電子メールの作成および送信を行う](enhanced-email.md)
