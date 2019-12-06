---
title: SharePoint を使用して共同作業を行う |Microsoft Docs
description: モデル駆動型アプリ内で SharePoint を使用して共同作業する方法について説明します
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
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2019
ms.locfileid: "74418283"
---
# <a name="collaborate-using-sharepoint"></a>SharePoint を使用した共同作業 

Word、Excel、PowerPoint などの一般的なドキュメントの種類を管理し、フォルダーを作成して、モデル駆動型アプリ内から SharePoint にシームレスに格納されているドキュメントを保存および管理します。 

> [!NOTE]
> この機能を使用するには、システム管理者が SharePoint ドキュメント管理を有効にしている必要があります。 詳細情報: [SharePoint を使用してドキュメントを管理する](/power-platform/admin/manage-documents-using-sharepoint)

アカウントと連絡先のレコードについては、**ファイル** タブに初めてアクセスしたときに、既定のドキュメントの場所フォルダーが SharePoint で自動的に作成されます。その他の標準またはカスタムエンティティレコードについては、**関連**する > **ドキュメント** タブを参照してください。ドキュメントの場所の名前は、< record_name > _ < record_id > の形式になっています。

既定では、場所は既定のサイト1の [ドキュメント] に設定されています。

## <a name="add-a-document"></a>ドキュメントを追加する
1.  アカウントまたは連絡先レコードを開き、 **[ファイル]** タブを選択します。ドキュメント管理が有効になっているその他の標準またはカスタムエンティティについては、 **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
2.  次のいずれかのオプションを選択します。 
    - 新しいドキュメントを作成するには、[**新規**作成] を選択し、Word、Excel、OneNote などのドキュメントの種類を選択して、名前を入力します。 **[保存]** を選択します。 新しいタブに空のドキュメントが表示されます。 
    - 既存のドキュメントを追加するには、 **[アップロード]** を選択し、 **[ファイルの選択]** を選択して、目的のファイルを参照して選択し、 **[開く]** を選択します。 **[OK]** を選択します。 

ドキュメントファイルは、ドキュメントに**関連付けら**れたグリッドビューに表示されます。 

> [!div class="mx-imgBorder"] 
> ![](media/add-doc-sharepoint.png "Add document to SharePoint")

このドキュメントは、SharePoint サイトフォルダーの場所にも表示されます。 

> [!div class="mx-imgBorder"] 
> ![](media/doc-on-sharepoint.png "Document on SharePoint")

## <a name="manage-sharepoint-locations"></a>SharePoint の場所の管理
モデル駆動型アプリから既存の SharePoint の場所を新規作成または編集できます。

1. コマンドバーの **[ファイル]** ボックスの一覧で **[場所を開く]** を選択し、場所を選択します。
2. 場所を編集するには、コマンドバーで [**場所の編集**<location name>] を選択します。
**[場所の編集]** ダイアログボックスが表示されます。
3. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 新しい場所の詳細を入力し、 **[保存]** を選択します。
4. 場所を追加するには、コマンドバーで **[場所の追加]** を選択します。
5. **[場所の追加]** ダイアログボックスが表示されます。

    > [!div class="mx-imgBorder"] 
    > ![](media/add-location-dialog-box.png "Add location dialog box")
6. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 必要に応じて詳細を変更し、 **[保存]** を選択します。

## <a name="actions-on-documents"></a>ドキュメントに対するアクション
ドキュメントの一覧で1つ以上のドキュメントを選択すると、次の他の一般的な SharePoint 操作をドキュメントに対して実行できます。
- 編集
- 削除
- チェックイン
- 「
- チェックアウトの破棄
- プロパティの編集

## <a name="files-tab-faq"></a>[ファイル] タブの FAQ
*移動したドキュメントにアクセスする場所はなぜですか。* 
- コマンドを移動して、数回クリックするだけでドキュメントを見つけやすくしました。

*[ドキュメント] タブが消えていますか。*
- いいえ、ありません。 ユーザーは、関連するメニューをクリックして [ドキュメント] リンクをクリックするだけで、そのレコードに関連付けられているドキュメントにも以前の方法でアクセスできます。

*この変更により、SharePoint のサブフォルダーも自動的に作成されますか。*
- はい。 動作は、**関連**するメニューの **[ドキュメント]** リンクに似ています。 ユーザーが初めて **[ファイル]** タブを選択すると、対応する SharePoint サブフォルダーがシステムによって作成されます。 

*[ファイル] タブを他のエンティティに追加したり、削除したりする方法はありますか。*
- はい。 [ファイル] タブを追加または削除するには、この記事の手順に従います。 [エンティティのメインフォームに [SharePoint ドキュメント] タブを追加する](../maker/model-driven-apps/add-documents-tab-entity-main-form.md)  

*この変更に関するフィードバックはどこで送信できますか。*
- 次の電子メールアドレスを使用して、Dynamics 365 Sales Office および Teams 統合チームにフィードバックを送信できます: d365_ot_crew@microsoft.com

### <a name="see-also"></a>関連項目
[SharePoint、OneNote、OneDrive と Common Data Service の統合](../maker/common-data-service/sharepoint-onedrive-onenote-intro.md)