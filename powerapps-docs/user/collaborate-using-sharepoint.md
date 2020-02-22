---
title: SharePoint を使用して共同作業を行う | Microsoft Docs
description: モデル駆動型アプリ内で SharePoint を使用して共同作業を行う方法について説明します
documentationcenter: ''
author: Mattp123
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 11/20/2019
ms.author: matp
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 428291712f91e90cea515723a93e1871ec94de2e
ms.sourcegitcommit: 8f32eed48adf4b24b9ca607bbf6db3d19749c46f
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74418283"
---
# <a name="collaborate-using-sharepoint"></a>SharePoint を使用した共同作業 

Word、Excel、PowerPoint などの一般的な種類のドキュメントを管理し、モデル駆動型アプリ内から SharePoint にシームレスに格納されるこれらのドキュメントを保存および管理するためのフォルダーを作成します。 

> [!NOTE]
> この機能を使用するには、システム管理者が SharePoint ドキュメント管理を有効にしている必要があります。 詳細情報: [SharePoint を使用してドキュメントを管理する](/power-platform/admin/manage-documents-using-sharepoint)

アカウントと連絡先レコードについては、 **[ファイル]** タブに初めてアクセスしたときに、SharePoint で既定のドキュメントの場所のフォルダーが自動的に作成されます。その他の標準またはカスタムのエンティティ レコードについては、 **[関連]**  >  **[ドキュメント]** タブに移動してください。ドキュメントの場所の名前は、<record_name>_<record_id> の形式になっています。

既定では、場所は既定のサイト 1 のドキュメントに設定されています。

## <a name="add-a-document"></a>ドキュメントの追加
1.  アカウントまたは連絡先レコードを開き、 **[ファイル]** タブを選択します。ドキュメント管理が有効になっているその他の標準またはカスタムのエンティティについては、 **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
2.  次のオプションから選択します。 
    - 新しいドキュメントを作成するには、 **[新規]** を選択し、Word、Excel、OneNote などのドキュメントの種類を選択して、名前を入力します。 **[保存]** を選択します。 新しいタブに空のドキュメントが表示されます。 
    - 既存のドキュメントを追加するには、 **[アップロード]** を選択し、 **[ファイルの選択]** を選択して、目的のファイルを参照して選択し、 **[開く]** を選択します。 **[OK]** を選択します。 

ドキュメント ファイルが **[ドキュメント関連グリッド]** ビューに表示されます。 

> [!div class="mx-imgBorder"] 
> ![](media/add-doc-sharepoint.png "Add document to SharePoint")

このドキュメントは、SharePoint サイトのフォルダーの場所にも表示されます。 

> [!div class="mx-imgBorder"] 
> ![](media/doc-on-sharepoint.png "Document on SharePoint")

## <a name="manage-sharepoint-locations"></a>SharePoint の場所の管理
モデル駆動型アプリから SharePoint の場所を新規作成するか、または既存の場所を編集できます。

1. コマンド バーの **[ファイル]** リストで **[場所を開く]** を選択し、場所を選択します。
2. 場所を編集するには、コマンド バーで **[場所の編集]** <location name> を選択します。
**[場所の編集]** ダイアログ ボックスが表示されます。
3. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 新しい場所の詳細を入力し、 **[保存]** を選択します。
4. 場所を追加するには、コマンド バーで **[場所の追加]** を選択します。
5. **[場所の追加]** ダイアログ ボックスが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![](media/add-location-dialog-box.png "Add location dialog box")
6. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 必要に応じて詳細を変更し、 **[保存]** を選択します。

## <a name="actions-on-documents"></a>ドキュメントに対するアクション
[ドキュメント] リストで 1 つ以上のドキュメントを選択すると、ドキュメントに対して次のその他の一般的な SharePoint アクションを実行できます。
- 編集
- 削除
- チェックイン
- 次のページを確認してください
- チェックアウトの破棄
- プロパティの編集

## <a name="files-tab-faq"></a>[ファイル] タブに関する FAQ
*ドキュメントにアクセスする場所が移動したのはなぜですか。* 
- より少ないクリック回数でドキュメントを簡単に見つけられるように、コマンドを移動しました。

*[ドキュメント] タブは廃止されたのですか。*
- いいえ、廃止されたわけではありません。 関連するメニューをクリックして [ドキュメント] リンクをクリックするだけで、対象のレコードに関連付けられているドキュメントに以前の方法でアクセスできます。

*この変更後でも、SharePoint のサブフォルダーは自動的に作成されますか。*
- はい。 この動作は、 **[関連]** メニューの下にある **[ドキュメント]** リンクと共通しています。 ユーザーが初めて **[ファイル]** タブを選択したときに、対応する SharePoint サブフォルダーがシステムで作成されます。 

*[ファイル] タブを他のエンティティに追加または削除する方法はありますか。*
- はい。 [ファイル] タブを追加または削除するには、この記事の手順に従います。 [エンティティのメイン フォームに SharePoint ドキュメント タブを追加する](../maker/model-driven-apps/add-documents-tab-entity-main-form.md)  

*この変更に関するフィードバックはどこで送信できますか。*
- 次の電子メール アドレスを使用して、Dynamics 365 Sales オフィスおよび Teams 統合チームにフィードバックを送信できます:d365_ot_crew@microsoft.com

### <a name="see-also"></a>関連項目
[SharePoint、OneNote、OneDrive と Common Data Service の統合](../maker/common-data-service/sharepoint-onedrive-onenote-intro.md)