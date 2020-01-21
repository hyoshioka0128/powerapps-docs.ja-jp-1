---
title: ソリューションのインポート | MicrosoftDocs
description: Power Apps でソリューションをインポートする方法について
ms.custom: ''
ms.date: 09/30/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 56363ea3-ea76-4311-9b7a-b71675e446fb
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 0eb65eb9ac1240769ba0cc885cb9c2e30a8f83f9
ms.sourcegitcommit: 212bd841595db0d6f41002f7ff9a1c8eb33a0724
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "2909465"
---
# <a name="import-solutions"></a>ソリューションのインポート 

 次の手順に従って手動でソリューションをインポートできます。 信頼できるソースから取得したソリューションだけをインポートしてください。 カスタマイズには、外部ソースにデータを送信できるコードが含まれている場合があります。   
  
1.  左のナビゲーション ウィンドウから、**ソリューション**を選択します。  
  
2.  ソリューションの一覧メニューで、**インポート**を選択します。  

    > [!div class="mx-imgBorder"]  
    > ![ソリューションのインポート](media/solution-import.png "ソリューションのインポート") 
  
3.  **ソリューションのインポート** ダイアログの、**ソリューション パッケージの選択**のステップにおいて、**ファイルの選択**を選択し、インポートするソリューションが含まれている圧縮 (.zip または .cab) ファイルを参照します。 
  
4.  **次へ**を選択します。  
  
5.  ソリューションに関する情報を表示します。 **インポート**を選択します。  
  
6. インポートが完了するまで、数分待つ必要がある場合があります。 結果を表示し、**閉じる**を選択します。  
  
 公開が必要な変更をインポートした場合、それらを使用可能にする前に、カスタマイズを公開する必要があります。 
  
 インポートが正常に完了しない場合、キャプチャされたエラーまたは警告のレポートが表示されます。 インポートが失敗した原因に関する詳細をキャプチャするために、**ログ ファイルのダウンロード**を選択します。 インポートの失敗の最も一般的な原因は、ソリューションに必要なコンポーネントが含まれていなかったことです。  
  
 ログ ファイルをダウンロードするとき、Office Excel を使用して XML ファイルを開き、内容を表示します。  
  
> [!NOTE]
>  アクティブなルーティング規則セットを編集することはできません。 したがって、同じ ID のルールが既に存在する環境にアクティブなルーティング規則セットを組み込むソリューションをインポートする場合、インポートは失敗します。 詳細情報: [サポート案件を自動的にルーティングするルールを作成する](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

### <a name="see-also"></a>関連項目
[ソリューションの更新](update-solutions.md) <br />
[エクスポート ソリューション](export-solutions.md)

