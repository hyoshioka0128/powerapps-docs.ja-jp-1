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
ms.locfileid: "3302635"
---
# <a name="merge-duplicate-records"></a>重複レコードをマージする 

データを手動で入力したり、データを一括してインポートしたりすると、重複するレコードが発生することがあります。 Common Data Service は、取引先企業、取引先担当者などのアクティブなレコードのの重複データ検出を使用して、重複している可能性があるレコードの処理を補助します。 レコードをマージすると、関連するレコードまたは子レコードもマージされます。 管理者は、状態別の重複データ検出ルールを設定します。  
  
たとえば、取引先担当者レコードとして「Glynn Jim」を、携帯電話番号とともに入力するとします。  重複検出ルールにより、既に類似したレコードがあることが検出され、次のようなダイアログ ボックスが表示されます。  
  
 > [!div class="mx-imgBorder"] 
 > ![重複する連絡先レコードの検出](media/duplicates-detected.png "重複する連絡先レコードの検出")  
  
 これが新しいレコードか (たまたま既存の連絡先と同じ名前である)、重複しているか不明なので、**[無視して保存]** を選択します。  
  
 次に、**[すべての連絡先]** の一覧に移動し、同じ名前のレコードが 2 つあることを確認します。 レコードを確認した後、マージする必要がある重複であると判断します。  
 
 > [!div class="mx-imgBorder"] 
 > ![重複する連絡先レコードの検出](media/duplicates-detected_1.png "重複する連絡先レコードの検出")  
 
Common Data Service には、取引先企業および取引先担当者のための重複データ検出ルールが組み込まれています。 これらのルールは自動的に有効になるため、これらのレコードの種類に対する重複検出を設定するために、何もする必要はありません。  
  
> [!NOTE]
>  システムで使用できる場合は、連絡先とアカウントに加えて、他のレコードの種類の重複を調べることもできます。 システム管理者に確認してください。 [管理者またはサポート担当者を探す](find-admin.md)  
  
## <a name="merge-duplicate-records"></a>重複レコードをマージする  
  
1. 重複するレコードを選択し、**[マージ]** を選択します。  
  
   > [!div class="mx-imgBorder"] 
   > ![重複する連絡先レコードの検出](media/duplicates-detected_2.png "重複する連絡先レコードの検出")  
  
2. **重複レコードの統合**ダイアログ ボックスで、マスター レコード (保存するほう) を選択し、新しいレコードでマスター レコード統合するフィールドを選択します。 これらのフィールドのデータにより、マスター レコードの既存のデータがオーバーライドされる可能性があります。 **OK** を選びます。  
  
     
   > [!div class="mx-imgBorder"] 
   > ![レコードをマージするためのダイアログ ボックス](media/merge-records-dialog.png "レコードをマージするためのダイアログ ボックス")  
  
> [!NOTE]
>  次のような状況で、重複が見つかる可能性があります。  
> 
> - レコードを作成または更新するとき。  
>   - Dynamics 365 for Outlook を使用していて、オフラインからオンラインの状態に移行するとき。  
>   - データのインポート ウィザードを使用してデータをインポートしたとき。  
> 
>   レコードをマージするとき、作業を完了して保存するとき、またはレコードの状態を変更するとき (レコードのアクティブ化や再アクティブ化など) は、重複は検出されません。  
