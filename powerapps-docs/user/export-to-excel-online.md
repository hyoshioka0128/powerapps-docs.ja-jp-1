---
title: モデル駆動型アプリで Excel Online にデータをエクスポートする |MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 11/16/2018
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
- D365CE
ms.openlocfilehash: 6cb8fe650db464f41c63af87c3fcb34bb2203cf2
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2019
ms.locfileid: "61544803"
---
# <a name="export-your-data-to-excel-online"></a>Excel Online にデータをエクスポートする 

アプリから Excel Online にデータをエクスポートすることによって、アプリ内のデータのアドホック分析を迅速に実行できます。
  
Excel Online でデータを変更したら、更新された情報をアプリに保存できます。 インポート中の問題を回避するために、必ず Excel のセルの既存の形式を保持してください。 グラフ、チャート、色など、スプレッドシートに追加された情報は保存されません。  
  
## <a name="prerequisites"></a>前提条件  
  
- この機能を使用するには、Office 365 サブスクリプション、または SharePoint Online や Exchange Online などのオンライン サービスへのサブスクリプションが必要です。
  
- Microsoft アカウントが必要です。    
  
## <a name="open-app-data-in-excel-online"></a>Excel Online でアプリ データを開く  

Excel Online でデータを開くオプションは、すべてのレコードの種類で使用できるわけではありません。 オプションが表示されない場合、そのレコードでは使用できません。  
  
> [!NOTE]
> Excel Online で過去 2 分間に同じビューを開いた場合、アプリ内の更新されたデータはすぐには Excel Online に反映されません。 その時間が過ぎた後、更新されたデータが Excel Online で表示されます。
  
アプリ内のレコードの一覧を開くには、コマンド バーで **[Excel にエクスポート]** メニューを選択し、 **[Excel Online で開く]** を選択します。 

> [!div class="mx-imgBorder"] 
> ![Excel Online へのエクスポート](media/exportexcelonline.png "Excel Online へのエクスポート")  

  
## <a name="save-your-data-and-import-it-back-to-the-app"></a>データを保存してアプリにインポートし直す  
  
1. 変更が完了したら、 **[保存]** を選択します。  
  
   > [!NOTE]
   > - Excel Online での "*アドホック*" 分析のためのデータは、一時的に保存されます。 グラフ、計算、列などの追加は、Excel Online でのアドホック分析からアプリに保存し直されません。  
   > 
   > - 多数の変更を行った場合、ファイルのインポートが失敗する可能性があります。 データに大量の変更を加えてからアプリにインポートし直す必要がある場合は、代わりに Excel でワークシートをエクスポートすることをお勧めします。  
   > 
   > - 仕様により、Excel Online で **[ファイル]**  >  **[名前を付けて保存]** を行うことはできません。 これを行うと、"**ブックを保存できません**" というエラー メッセージが表示されます。   
2. **[インポート用にデータが送信されました]** ダイアログ ボックスで、 **[閉じる]** を選択します。  
  

  

 
