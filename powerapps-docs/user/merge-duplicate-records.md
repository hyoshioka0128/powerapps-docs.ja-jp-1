---
title: 重複レコードをマージする| MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/31/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c0811645429c9f1e7570ceeaf316a5217e440ae4
ms.sourcegitcommit: bee698ca0d11524377b67813a65e1a022d08c05e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/05/2019
ms.locfileid: "73609881"
---
# <a name="merge-duplicate-records"></a>重複レコードをマージする 

データを手動で入力したり、データを一括してインポートしたりすると、重複するレコードが発生することがあります。 Common Data Service を使用すると、アカウントや連絡先などのアクティブなレコードの重複が検出され、潜在的な重複を解決できます。 レコードをマージすると、関連するレコードまたは子レコードもマージされます。 また、管理者は、他の状況に対して重複検出ルールを設定することもできます。  
  
たとえば、Jim Glynn の連絡先レコードと併せて、携帯電話番号を入力するとします。  重複検出ルールにより、既に類似したレコードがあることが検出され、次のようなダイアログ ボックスが表示されます。  
  
 > [!div class="mx-imgBorder"] 
 > ![重複する連絡先レコードの検出](media/duplicates-detected.png "重複する連絡先レコードの検出")  
  
 これが新しいレコードか (たまたま既存の連絡先と同じ名前である)、重複しているか不明なので、 **[無視して保存]** を選択します。  
  
 次に、 **[すべての連絡先]** の一覧に移動し、同じ名前のレコードが 2 つあることを確認します。 レコードを確認した後、マージする必要がある重複であると判断します。  
 
 > [!div class="mx-imgBorder"] 
 > ![重複する連絡先レコードの検出](media/duplicates-detected_1.png "重複する連絡先レコードの検出")  
 
Common Data Service には、アカウントと連絡先の重複検出ルールが含まれています。 これらのルールは自動的に有効になるため、これらのレコードの種類に対する重複検出を設定するために、何もする必要はありません。  
  
> [!NOTE]
>  システムで使用できる場合は、連絡先とアカウントに加えて、他のレコードの種類の重複を調べることもできます。 システム管理者に確認してください。 [管理者またはサポート担当者を探す](find-admin.md)  
  
## <a name="merge-duplicate-records"></a>重複レコードをマージする  
  
1. 重複するレコードを選択し、 **[マージ]** を選択します。  
  
   > [!div class="mx-imgBorder"] 
   > ![重複する連絡先レコードの検出](media/duplicates-detected_2.png "重複する連絡先レコードの検出")  
  
2. **[レコードのマージ]** ダイアログ ボックスで、マスター レコード (残すもの) を選択し、マスター レコードにマージする新しいレコードのフィールドを選択します。 これらのフィールドのデータにより、マスター レコードの既存のデータがオーバーライドされる可能性があります。 **[OK]** を選択します。  
  
     
   > [!div class="mx-imgBorder"] 
   > ![レコードをマージするためのダイアログ ボックス](media/merge-records-dialog.png "レコードをマージするためのダイアログ ボックス")  
  
> [!NOTE]
>  次のような状況で、重複が見つかる可能性があります。  
> 
> - レコードが作成または更新されたとき。  
>   - Dynamics 365 for Outlook を使用していて、オフラインからオンラインに移行したとき。  
>   - データのインポート ウィザードを使用してデータをインポートしたとき。  
> 
>   レコードをマージするとき、作業を完了して保存するとき、またはレコードの状態を変更するとき (レコードのアクティブ化や再アクティブ化など) は、重複は検出されません。  
