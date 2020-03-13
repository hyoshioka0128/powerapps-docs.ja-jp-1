---
title: OneDrive for Business を使用する |MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 03/02/2020
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 5cfbed161ca920db3ce474371aa435189dc12543
ms.sourcegitcommit: a1b54333338abbb0bc3ca0d7443a5a06b8945228
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "79240007"
---
# <a name="use-onedrive-for-business"></a>OneDrive for Business を使用する 

OneDrive for Business を使用して Common Data Service アプリ内からプライベート ドキュメントを作成し、管理します。 詳細情報: [OneDrive for Business とは?](https://support.office.com/article/What-is-OneDrive-for-Business-187f90af-056f-47c0-9656-cc0ddca7fdc2)


OneDrive for Business を使用するには、システム管理者によって有効になっている必要があります。 詳細情報:

-   [管理者またはサポート担当者を探す](find-admin.md)  

-   [OneDrive for Business を有効にする](https://docs.microsoft.com/power-platform/admin/enable-onedrive-for-business)  


## <a name="the-first-time-you-view-your-documents"></a>ドキュメントを初めて表示するとき  

1. レコードを開き、 **[ドキュメント関連グリッド]** ビューに移動します。 たとえば、連絡先レコードを開きます。

2.  開いているレコードで **[関連]** タブを選択し、 **[ドキュメント]** を選択します。

     > [!div class="mx-imgBorder"]
     > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")

3.  **[ドキュメントの場所]**  >  **[OneDrive]** を選択します。

     > [!div class="mx-imgBorder"]
     > ![[ドキュメント] タブを開いて [OneDrive] を選択する](media/onedrive_menu.png "[ドキュメント] タブを開いて [OneDrive] を選択する")

4. OneDrive for Business が有効になった後、 **[ドキュメント]** タブにアクセスして Common Data Service でドキュメントを表示したり、OneDrive にファイルをアップロードしたり、新しいドキュメントやフォルダーを作成しようとすると、次のダイアログボックスが表示されます。  

    > [!div class="mx-imgBorder"]
    > ![OneDrive フォルダーを変更する](media/setup_onedrive.png "OneDrive フォルダーを変更する")  

5. OneDrive ドキュメントを保存する新しい場所を選択する場合は、 **[フォルダーの場所の変更]** を選択します。既定のフォルダーの場所をそのまま使用する場合は、 **[続行]** を選択します。

  
## <a name="view-existing-onedrive-documents"></a>既存の OneDrive ドキュメントを表示する 
 
1. レコードを開き、 **[ドキュメント関連グリッド]** ビューに移動します。 たとえば、連絡先レコードを開きます。

2. 開いているレコードで **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
 
    > [!div class="mx-imgBorder"]
    > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")
 
3. ドキュメントの一覧をフィルター処理するには、 **[ドキュメントの場所]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![[ドキュメントの場所] を開く](media/onedrive_doc_location.png "[ドキュメントの場所] を開く")

4.  次の表の説明に従って場所を選択します。  

   |    ドキュメントの場所      |  説明                                   |
   |---------------------------|------------------------------------------------|
   |      従来の OneDrive             | OneDrive for Business に保存されたドキュメント      |
   | 既定のサイトのドキュメント | 既定の SharePoint サイトに格納されているドキュメント  |
   | 自分と共有            | このレコードに関連付けられている、他のユーザーと共有されているドキュメント<!--note from editor: Edit okay? I haven't seen an "app record" defined.-->    |
   |  すべての場所            |     このレコードに関連付けられているすべてのドキュメントの場所     |

5. 場所を選択すると、その場所に保存されたドキュメントが表示されます。

## <a name="create-a-new-document-and-save-it-to-onedrive"></a>新しいドキュメントを作成して OneDrive に保存する

1. レコードを開き、 **[ドキュメント関連グリッド]** ビューに移動します。 たとえば、連絡先レコードを開きます。

2. 開いているレコードで **[関連]** タブを選択し、 **[ドキュメント]** を選択します。
 
    > [!div class="mx-imgBorder"]
    > ![レコードで [ドキュメント] タブを開く](media/onedrive_nav.png "レコードで [ドキュメント] タブを開く")

2. **[ドキュメントの場所]** を選択し、場所を **[OneDrive]** に変更します。

3. **[新規]** を選択し、PowerPoint や Word などのドキュメントの種類を選択します。 

    > [!div class="mx-imgBorder"]
    > ![新しいドキュメントを作成する](media/onedrive_new_doc.png "新しいドキュメントを作成する")

4. ドキュメント名を入力し、 **[保存]** を選択します。  


## <a name="things-to-consider"></a>考慮事項 

Common Data Service の OneDrive for Business に関しては、次の点に注意してください。

- OneDrive ストレージ フォルダーは、ユーザーの現在の Common Data Service 言語で作成されます。 言語が変更された場合、新しいフォルダーは新しい言語で作成されます。 古いフォルダーは前の言語のままになります。  

- OneDrive でドキュメントが共有されてから、他のユーザーが使用できるようになるまでに遅延が発生する場合があります。 
