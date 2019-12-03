---
title: SharePoint フォームの統合について |Microsoft ドキュメント
description: SharePoint でのカスタム フォームの動作について
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/11/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: fbfe1b62091ff7a4fb84b899518fc941f99d7abb
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74674854"
---
# <a name="understand-sharepoint-forms-integration"></a>SharePoint フォームの統合について
Power Apps で[SharePoint リストフォーム](customize-list-form.md)を簡単にカスタマイズできるようになりました。 この記事では、これらのフォームの動作と、フォームをさらにカスタマイズする方法を詳しく見てみましょう。

SharePoint リストのフォームをカスタマイズしたことがある方は、既定の生成されたフォームは、アイテムの作成、表示、編集などのすべての操作に対応していることをご存知でしょう。 これは、生成された数式と **SharePointIntegration** コントロールによって実現されています。

## <a name="understand-the-default-generated-form"></a>既定の生成されたフォームについて

既定の生成されたフォームは、次のコントロールと対応する既定値で構成されています。

* **FormScreen1** - これは、フォームを含む[画面](controls/control-screen.md)です。

* **SharePointForm1** - これは、リスト アイテムの作成、表示、または編集に使用される[フォーム](working-with-forms.md)です。

    * **Data Source** - フォームがカスタマイズされているリストです。

    * **Item** - リストから選択されたアイテムです。 これは、Power Apps Studio で作業するときに便利なように、一覧の First () 項目に設定されています。

        **If(IsBlank(SharePointIntegration.Selected) || IsEmpty(SharePointIntegration.Selected),First('*YourListName*'),SharePointIntegration.Selected)**

    * **OnSuccess** - アイテムが正常に作成または保存されると、フォームがリセットされ、SharePoint でこのフォームが非表示になります。

        **ResetForm(SharePointForm1); RequestHide()**

* **SharePointIntegration** - このコントロールは、SharePoint と PowerApps の間でユーザー アクションを伝達します。

    * **Data Source** - フォームがカスタマイズされているリストです。

        **'*YourListName*'**

    * **OnNew** - **SharePointForm1** を新しいモードに設定します。

        **NewForm(SharePointForm1)**

    * **OnView** - **SharePointForm1** を表示モードに設定します。

        **ViewForm(SharePointForm1)**

    * **OnEdit** - **SharePointForm1** を編集モードに設定します。

        **EditForm(SharePointForm1)**

    * **OnSave** - **SharePointForm1** の変更を送信します。 フォームの送信が成功すると、**SharePointForm1.OnSuccess** 式が実行されます。

        **SubmitForm(SharePointForm1)**

    * **OnCancel** - **SharePointForm1** の変更をリセットします。 ユーザーが SharePoint で **[キャンセル]** をクリックまたはタップすると、SharePoint では常にフォームが非表示になります。

        **ResetForm(SharePointForm1)**

これらの既定値を使用すると、SharePoint 内で実行されるときにフォームが動作するようになります。ユーザーが sharepoint で Power Apps フォームモードを操作すると、その変更が SharePoint に送信されるようになります。

## <a name="understand-the-sharepointintegration-control"></a>SharePointIntegration コントロールについて
**SharePointIntegration** コントロールは、SharePoint と PowerApps の間でユーザー アクションを伝達します。

![](./media/sharepoint-form-integration/sharepointintegration-object.png)

>[!NOTE]
>**Sharepointintegration**コントロールのプロパティにアクセスできるのは、フォームが SharePoint で実行されている場合のみです。 Power Apps Studio でフォームをカスタマイズしている場合は対象になりません。 これらのプロパティは、**OnStart** または **OnVisible** では使用できないことがあります。 

**SharePointIntegration** コントロールには、次のプロパティがあります。

**Selected** - SharePoint リストから選択されたアイテムです。

**OnNew** - ユーザーが SharePoint で **[新規]** ボタンをクリックまたはタップしたとき、または**アイテム作成**フォームを開いたときのアプリの応答です。

**OnView** - ユーザーが SharePoint で **[アイテム]** ボタンをクリックまたはタップしたとき、または**アイテム詳細**フォームを開いたときのアプリの応答です。

**OnEdit** - ユーザーが SharePoint で **[すべて編集]** ボタンをクリックまたはタップしたとき、または**アイテム編集**フォームを開いたときのアプリの応答です。

**OnSave** - ユーザーが SharePoint で **[保存]** ボタンをクリックまたはタップしたときのアプリの応答です。

**OnCancel** - ユーザーが SharePoint で **[キャンセル]** ボタンをクリックまたはタップしたときのアプリの応答です。

**SelectedListItemID** - SharePoint リストで選択されたアイテムのアイテム ID です。

**Data Source** – フォームが表示、編集、または作成するレコードが含まれるリストです。 このプロパティを変更すると、**Selected** プロパティと **SelectedItemID** プロパティが無効になる可能性があることに注意してください。

## <a name="customize-the-default-form"></a>既定のフォームをカスタマイズする
既定の生成されたフォームと **SharePointIntegration** コントロールを理解したら、数式を変更して、フォームをさらにカスタマイズすることができます。 フォームをカスタマイズするときの注意事項をいくつか次に示します。

* アイテムを作成、表示、または編集するための個別のカスタム エクスペリエンスを作成するには、**SharePointIntegration** コントロールの **OnNew**、**OnView**、または **OnEdit** 式を、変数を設定するか別の画面に移動するように設定します。

* ユーザーが SharePoint で **[保存]** をクリックまたはタップしたときの動作をカスタマイズするには、**SharePointIntegration** コントロールの **OnSave** 式を使用します。 複数のフォームがある場合は、現在使用しているフォームに対する変更だけを送信してください。

  > [!TIP]
  >    **OnNew**、**OnView**、および **OnEdit** 式の変数には異なる値を設定します。 **OnSave** 式でこの変数を使用すると、使用されているフォームを指定できます。

* すべてのフォームの **OnSuccess** 式に必ず **RequestHide()** を含めてください。 これを忘れると、SharePoint はフォームを非表示にするタイミングを認識できません。

* SharePoint でユーザーが **[キャンセル]** をクリックまたはタップしたときのフォームの非表示は制御できないので、**SharePointIntegration** コントロールの **OnCancel** 式でかならずフォームをリセットしてください。

* **SharePointIntegration** コントロールのプロパティは **OnStart** または **OnVisible** では使用できないことがあり、それらのイベントはリストの読み込み中に 1 回だけ実行します。 **OnNew**、**OnView**、または **OnEdit** 式を使って、フォームが毎回ユーザーに表示される前にロジックを実行できます。 
