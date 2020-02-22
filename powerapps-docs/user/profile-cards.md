---
title: 連絡先またはユーザーのプロファイル カードを表示する | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 276c7d3cbf95947306fab768da8af3c4c66b33e0
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "73543370"
---
# <a name="view-the-profile-card-for-a-contact-or-user"></a>連絡先またはユーザーのプロファイル カードを表示する

プロファイル カードを使用して、連絡先またはユーザーに関する簡単な情報を取得します。 Dynamics 365 Sales や Dynamics 365 Customer Service など、Dynamics 365 のモデル駆動型アプリで連絡先またはユーザー フィールドを選択すると、それらに関連する情報がプロファイル カードに表示されます。 プロファイル カードの詳細については、[Office 365 のプロファイル カード](https://support.office.com/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501)に関するページを参照してください。

> [!NOTE]
>  - プロファイル カードは、**連絡先**と**ユーザー** エンティティに対して使用できます。 詳細については、[プロファイル カードを有効にする (管理者の場合)](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-profile-card) に関するページを参照してください。
>  - Azure Active Directory で Office Delve サービスに対して多要素認証が有効になっている場合、Common Data Service のプロファイル カードは表示されません。

## <a name="view-a-contacts-profile"></a>連絡先のプロファイルを表示する

1.  **[アクティビティ]** に移動します。
2.  既存のアクティビティを選択するか、新しいアクティビティを作成します。
3.  連絡先レコードがある場合は、 **[通話先]** フィールドの上にマウス ポインターを置きます。 

連絡先の画像、名前、タイトル、およびアカウントが含まれる連絡先の詳細をインラインで表示できます。

4. さらに詳細を表示するには、 **[詳細表示]** を選択して、連絡先のプロファイルを展開します。
 
    > [!div class="mx-imgBorder"] 
    > ![連絡先プロファイル カードの詳細を展開する](media/profile1.png "連絡先プロファイル カードの詳細を展開する")
   
 ## <a name="view-a-users-profile"></a>ユーザーのプロファイルの表示
 
1.  **[アカウント]** にアクセスします。
2.  アカウント レコードを選択します。
3.  ユーザー レコードがある場合は、[所有者] フィールドの上にマウス ポインターを置きます。 ユーザーの詳細をインラインで表示できます。
4.  電子メールやそのユーザーとの共有ファイルなどの詳細を表示するには、 **[詳細表示]** を選択して、連絡先のプロファイルを展開します。
 
    > [!div class="mx-imgBorder"] 
    > ![ユーザー プロファイル カードの詳細を展開する](media/profile2.png "ユーザー プロファイル カードの詳細を展開する")


 ## <a name="faqs"></a>FAQ
 
### <a name="where-can-i-see-profile-cards-in-dynamics-365"></a>Dynamics 365 のプロファイル カードはどこで確認できますか。
プロファイル カードは、連絡先レコードとユーザー レコードで確認できます。 参照されている場合にのみ表示できます。

### <a name="where-is-information-shown-in-the-profile-card-coming-from"></a>プロファイル カードに表示される情報はどこにありますか。
連絡先プロファイル カードに表示される情報は、(Microsoft Exchange ではなく) Common Data Service から取り込まれます。 これは、連絡先の詳細が Dynamics 365 にあることを意味します。

ユーザー プロファイル カードに表示される情報は、Office 365 (Azure Active Directory) から取り込まれます。 詳細については、[Office 365 のプロファイル カード (管理者セクション)](https://support.office.com/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501) に関するページを参照してください。

### <a name="how-can-i-customize-the-fields-shown-on-the-profile-card"></a>プロファイル カードに表示されるフィールドをカスタマイズする方法はありますか。
現時点では、プロファイル カードに表示されるフィールドの一覧のカスタマイズはできません。

### <a name="why-is-the-start-chat-option-on-the-profile-card-disabled-greyed-out"></a>プロファイル カードの **[チャットを開始]** オプションが無効 (グレー表示) になっているのはなぜですか。
プロファイル カードの **[チャットを開始]** と **[電子メールの送信]** オプションを選択すると、既定のインスタント メッセージと電子メール アプリが開きます。 **[チャットの開始]** オプションは、連絡しようとしている相手が、同じ Azure Active Directory 環境内にいる、またはフェデレーションからの連絡先である場合に有効になります。


  
