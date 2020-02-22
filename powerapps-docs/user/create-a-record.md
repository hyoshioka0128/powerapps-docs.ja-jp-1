---
title: レコードをすばやく作成する | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 02/03/2020
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: bf8ee15b37e9fcae5027bb91e89ceb225325dcc5
ms.sourcegitcommit: 4f2e9e8f9bd3204ca9eee9e2a46f797c957c55ec
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "77054871"
---
# <a name="create-a-new-record"></a>新しいレコードの作成

## <a name="create-a-new-record-using-the--option-on-the-command-bar"></a>コマンド バーの [+] オプションを使用して新しいレコードを作成する

**[新しいレコードの作成]** コマンドまたは **[簡易作成]** を使うと、ほぼあらゆる種類の情報を高速かつ簡単にシステムに入力できます。 このコマンドはナビゲーション バーにあるので、システムに新しい情報を入力したい場合に、いつでも利用することができます。 また、 **[簡易作成]** フォームからレコードを保存して新しいレコードを直接作成することもできます。

> [!NOTE]
> **[簡易作成]** オプションは、管理者が有効にしたレコードに対してのみ使用できます。
    
1. ナビゲーション バーで、**プラス記号** ![レコードの作成ボタン](media/create-record-button.png "レコードの作成ボタン") を選択してから、目的の項目を選択します。  

    > [!div class="mx-imgBorder"] 
    > ![レコードの作成ボタン](media/newrecord1.png "レコードの作成ボタン")
  
2.  フィールドに入力し、 **[保存して閉じる]** を選択します。 または、別のレコードを保存して作成するには、下矢印を選択し、 **[保存して新規作成]** を選択します。

     > [!div class="mx-imgBorder"] 
     > ![レコードを保存する](media/quick_create.png "レコードを保存する")
  
> [!NOTE]
> 画面上のフィールドの横のアスタリスク ![必須フィールドのボタン](media/required-field-button.png "必須フィールドのボタン") は、そのフィールドが必須であることを意味します。 必須フィールドに入力する前に、 **[保存して閉じる]** を選択すると、エラー メッセージが表示されます。また、情報を入力し **[キャンセル]** を選択した場合、警告が表示されます。
>   
> 画面上のフィールドの横のプラス記号 ![推奨フィールドのボタン](media/recommended-field-button.png "推奨フィールドのボタン") は、そのフィールドへの入力がご自分の組織で推奨されていることを意味します。  


## <a name="create-a-new-record-using-the-new-button"></a>[新規] ボタンを使用して新しいレコードを作成する 

1. 左側のナビゲーション ウィンドウで、レコードの種類を選択します。 たとえば、 **[連絡先]** を選択して、新しい連絡先レコードを作成します。
2. コマンド バーで、 **[+ 新規]** を選択します。

    > [!div class="mx-imgBorder"] 
    > ![新規作成ボタン](media/newrecord2.png "新規作成ボタン")
  
3. 新しい連絡先の適切な詳細情報を入力し、 **[保存して閉じる]** を選択します。

    > [!NOTE]
    > 保存していない変更がある場合に別のレコードまたはフォームにアクセスしようとすると、 **[未保存の変更]** ダイアログ ボックスがポップアップ表示されます。 **[保存して続行]** を選択すると、情報が保存され、アクセスしようとしていたページが開きます。 保存して続行する場合、フィールドにエラーがあると、ダイアログが閉じられるので、別のページに移動する前に、このページに残ってエラーを修正します。

    > [!div class="mx-imgBorder"] 
    > ![新規作成ボタン](media/newrecord3.png "新規作成ボタン")

 
 ## <a name="preview-use-the-save-or-save--close-option-when-editing-a-record"></a>プレビュー:レコード編集時に [保存して閉じる] オプションを使用する 
 
既存のレコードを編集するときは、コマンド バーの **[保存]** または **[保存して閉じる]** を使用します。 このリリースより前のバージョンでは、右下隅の **[保存]** オプションのみ使用できました。

> [!NOTE]
> これは先行アクセス機能です。 お使いの環境でこの機能を有効にすることを先行してオプトインでき、これらの機能をテストして環境全体に導入することができるようになります。 これらの機能を有効にする方法の詳細については、[2020 リリース ウェーブ 1 更新プログラムへのオプトイン](https://docs.microsoft.com/power-platform/admin/opt-in-early-access-updates)に関するページをご覧ください。


1. 左側のナビゲーション ウィンドウで、編集するレコードの種類を選択します。 たとえば、 **[アカウント]** を選択します。
2. 編集するアカウント レコードを開き、レコードに変更を加えます。
3. 変更を保存するには、コマンド バーで **[保存]** または **[保存して閉じる]** を選択します。 右下隅の **[保存]** オプションも使用できます。

    > [!div class="mx-imgBorder"] 
    > ![レコードの保存オプション](media/saveoptionalwaysvisible.png "レコードの保存オプション")


