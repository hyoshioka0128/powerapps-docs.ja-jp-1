---
title: SharePoint を使用して共同作業を行う | Microsoft Docs
description: モデル駆動型アプリ内で SharePoint を使用して共同作業を行う方法について説明します
documentationcenter: ''
author: mduelae
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/02/2020
ms.author: matp
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 3491468724662edcac932cf37345730defd6a006
ms.sourcegitcommit: 5b6e6b41a3fc4d7f1aea46ec66c086b784efacac
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/03/2020
ms.locfileid: "78236132"
---
# <a name="collaborate-using-sharepoint"></a>SharePoint を使用した共同作業 

Common Data Service を使用すると、ドキュメントを SharePoint に保存し、アプリ内から管理できます。 アプリで作成したドキュメントは SharePoint に保存され、デスクトップとモバイル デバイスに自動的に同期されます。

SharePoint を使用してドキュメントを保存するには、システム管理者によって SharePoint が有効になっている必要があります。 詳細情報:

-   [管理者またはサポート担当者を探す](find-admin.md)  

-   [SharePoint を使用してドキュメントを管理する](https://docs.microsoft.com/power-platform/admin/manage-documents-using-sharepoint)  

## <a name="where-do-you-access-the-documents-from"></a>ドキュメントへのアクセス元となる場所

1. ドキュメント管理をサポートするレコードの種類については、レコードを開き、 **[関連]** タブを選択して、 **[ドキュメント]** を選択します。

   > [!div class="mx-imgBorder"]
   > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")

2. **[ドキュメントの場所]**  >  **[Documents on Default Site 1]\(既定のサイト 1 のドキュメント\)** を選択します。 SharePoint が有効になっている場合、既定では、場所は **[Documents on Default Site 1]\(既定のサイト 1 のドキュメント\)** に設定されます。

   > [!div class="mx-imgBorder"]
   > ![既定の場所](media/sharepoint_defualtsite.png "既定の場所")


## <a name="create-a-new-document-and-save-it-to-sharepoint"></a>新しいドキュメントを作成して SharePoint に保存する

1. レコードを開き、 **[ドキュメント関連グリッド]** ビューに移動します。 たとえば、連絡先レコードを開きます。

2. 開いているレコードで **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
 
    > [!div class="mx-imgBorder"]
    > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")

2. **[ドキュメントの場所]** を選択し、場所を **[Documents on Default Site 1]\(既定のサイト 1 のドキュメント\)** に変更します。

3. **[新規]** を選択し、Word、Excel、PowerPoint などのドキュメントの種類を選択します。

    > [!div class="mx-imgBorder"]
    > ![新しいドキュメントを作成する](media/onedrive_new_doc.png "新しいドキュメントを作成する")

4. ドキュメント名を入力し、 **[保存]** を選択します。  

## <a name="create-a-new-folder-in-the-default-sharepoint-site-location"></a>SharePoint サイトの既定の場所に新しいフォルダーを作成する

1. レコードを開き、 **[ドキュメント関連グリッド]** ビューに移動します。 たとえば、連絡先レコードを開きます。

2. 開いているレコードで **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
 
    > [!div class="mx-imgBorder"]
    > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")

2. **[ドキュメントの場所]** を選択し、場所を **[Documents on Default Site 1]\(既定のサイト 1 のドキュメント\)** に変更します。

3. **[新規]** を選択し、 **[フォルダー]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![新しいフォルダーを作成する](media/Sharepoint_new_folder.png "新しいフォルダーを作成する")
    
 4. フォルダー名を入力し、 **[保存]** を選択します。  
 
 
 ## <a name="upload-an-existing-document-to-sharepoint-from-your-app"></a>アプリから SharePoint に既存のドキュメントをアップロードする

1. ドキュメントを作成するレコードにアクセスし、 **[関連]** タブを選択して、 **[ドキュメント]** を選択します。
 
2. **[アップロード]** を選択します。

   > [!div class="mx-imgBorder"]
   > ![ドキュメントをアップロードする](media/upload_doc.png "ドキュメントのアップロード")

3. アップロードするファイルを選択します。 一度に選択できるのは 1 ファイルのみです。

   現在のドキュメントの場所に、ドキュメントが作成されます。

   > [!Note]
   > 最大 50 MB のファイルをアップロードできます。 インターネット接続の速度が遅い場合は、大きなファイルのアップロード中にエラーが発生することがあります。

4. SharePoint 内に同じ名前のファイルが存在する場合は、ファイルを上書きするかどうかを選択します。

5. **[OK]** を選択します。

## <a name="manage-sharepoint-locations"></a>SharePoint の場所の管理

Common Data Service では、アプリから新規の SharePoint の場所を作成したり、既存の SharePoint の場所を編集したりできます。

### <a name="edit-a-location"></a>場所を編集する

1. レコードを開いて **[関連]** タブを選択し、 **[ドキュメント]** を選択します。

2. **[場所の編集]** を選択し、SharePoint サイトの場所を選択します。

   **[場所の編集]** ダイアログ ボックスが表示されます。

   > [!div class="mx-imgBorder"]
   > ![場所を編集する](media/edit_location.png "場所を編集する")

3. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 新しい場所の詳細を入力し、 **[保存]** を選択します。

### <a name="add-a-new-location"></a>新しい場所を追加する

1. レコードを開いて **[関連]** タブを選択し、 **[ドキュメント]** を選択します。

2. **[場所の追加]** を選択します。 

   **[場所の追加]** ダイアログ ボックスが表示されます。

   > [!div class="mx-imgBorder"]
   > ![場所を追加する](media/add_location.png "場所を追加する")

3. 表示名、親サイト、およびフォルダー名が自動的に設定されます。 必要に応じて詳細を変更し、 **[保存]** を選択します。

## <a name="files-tab-faq"></a>[ファイル] タブに関する FAQ

*ドキュメントにアクセスする場所が移動したのはなぜですか。* 
- より少ないクリック回数でドキュメントを簡単に見つけられるように、コマンドを移動しました。

*[ドキュメント] タブは廃止されたのですか。*
- いいえ、廃止されたわけではありません。 **[関連]** メニューを選択して **[ドキュメント]** リンクをクリックするだけで、対象のレコードに関連付けられているドキュメントに以前の方法でアクセスできます。

*この変更後でも、SharePoint のサブフォルダーは自動的に作成されますか。*
- はい。 この動作は、 **[関連]** メニューの下にある **[ドキュメント]** リンクと共通しています。 ユーザーが初めて **[ファイル]** タブを選択したときに、対応する SharePoint サブフォルダーがシステムで作成されます。 

*[ファイル] タブを他のエンティティに追加または削除する方法はありますか。*
- はい。 **[ファイル]** タブを追加または削除するには、この記事の手順に従います。[エンティティのメイン フォームに SharePoint ドキュメント タブを追加する](../maker/model-driven-apps/add-documents-tab-entity-main-form.md)  
