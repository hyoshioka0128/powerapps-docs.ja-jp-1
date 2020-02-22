---
title: 相互にレコードをリンクするためのつながりロールを追加する | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 8/01/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4552c874ca6be72d37465abd2492a64979aba865
ms.sourcegitcommit: 5ec4cab1dd934446ec57c320a375e577560ac88a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/10/2019
ms.locfileid: "72239572"
---
# <a name="add-a-connection-role-to-link-records-to-each-other"></a>相互にレコードをリンクするためのつながりロールを追加する

つながりにより、ユーザー、連絡先、見積もり、販売注文などの多数のエンティティ レコードを簡単に相互関連付けすることができます。 関連付け内のレコードには、関係の目的を定義するのに役立つ特定のロールを割り当てることができます。

これにより、特定のレコードに対して複数のつながりとロールを簡単に作成できます。 たとえば、連絡先に、他の連絡先、アカウント、または契約との多数の関係があるとしましょう。 連絡先は、関係ごとに異なるロールを果たすことができます。

つながりロールはつながりに直接関連付けられます。 つながりロールを使用するには、まず、つながりをレコードに追加する必要があります。

つながりロールは、追加する前に、管理者によって有効にされている必要があります。詳細については、「[つながりロールの構成](https://docs.microsoft.com/powerapps/maker/common-data-service/configure-connection-roles)」を参照してください。

1. つながりを追加または管理するには、営業案件など、管理するレコードを選択します。  
2. **[関連]** タブを選択し、 **[つながり]** を選択します。 これにより、つながりグリッドが開いて、レコードのつながりの一覧が表示されます。

    > [!div class="mx-imgBorder"]
    > ![新しいつながりロールを追加する](media/connection1.png "新しいつながりロールを追加する") 

3. **[つながり]** を選択し、 **[他へ]** または **[自分に関連付け]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![つながりの種類を選択する](media/connection2.png "つながりの種類を選択する") 
  
4. **[名前]** フィールドで、つながりのレコードの名前を入力するか、検索します。

5. **[このロールとして]** フィールドでルックアップ アイコンを選択し、 **[新しいつながりロール]** を選択します。 または、検索を使用して、つながりに関連付ける既存のロールを検索し、 **[保存]** を選択します。

    > [!div class="mx-imgBorder"]
    > ![新しいつながりロールを選択する](media/connection3.png "新しいつながりロールを選択する")  

    > [!NOTE]
    > 新しいつながりロールを作成する前に情報を入力すると、警告ダイアログが表示され、キャンセルしてつながりを続行するか、入力している現在のレコードをそのままにして先に進むかを質問されます。

6. 新しいつながりロールを作成するには、 **[新しいつながりロール]** 画面で、名前を入力して、 **[つながりロール カテゴリ]** を選択します。

    > [!div class="mx-imgBorder"]
    >  ![つながりロール カテゴリを追加する](media/connection4.png "つながりロール カテゴリを追加する") 

7. 完了したら、 **[保存して閉じる]** を選択します。

  
## <a name="manage-connection-roles"></a>つながりロールの管理

つながりロールを管理するには、つながりエンティティからつながりロールを選択します。 これにより、つながりロール エンティティ レコードが開きます。  名前を編集して、つながりロール カテゴリを選択し、説明を追加することができます。


   > [!div class="mx-imgBorder"]
   > ![つながりロールを編集する](media/connection7.png "つながりロールを編集する") 
  
また、つながりロールに関連付けるつながりロールの種類を管理することもできます。

1. つながりロールを開いて、コマンドの **[レコードの種類の管理]** を選択します。 

    > [!div class="mx-imgBorder"]
    > ![つながりロールを編集する](media/connection5.png "つながりロールを編集する") 
  

2. これにより、このつながりロールに対して追加または削除できるつながりロールの種類の一覧が開きます。

    > [!div class="mx-imgBorder"]
    > ![レコードの種類の管理](media/connection6.png "レコードの種類の管理") 


