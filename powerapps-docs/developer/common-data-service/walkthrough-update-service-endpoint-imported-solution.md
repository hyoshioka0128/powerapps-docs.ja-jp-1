---
title: 'チュートリアル: ソリューションからインポートしたサービス エンドポイントの更新 (Common Data Service) | Microsoft Docs'
description: チュートリアルは、ソリューションからインポートしたサービス エンドポイントの更新方法を示します。
keywords: ''
ms.date: 10/06/2019
ms.service: powerapps
ms.topic: article
ms.assetid: 66795838-3b15-bfb3-6f59-68cfe2fe988e
author: JimDaly
ms.author: jdaly
manager: ryjones
ms.reviewer: ''
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 969660edb15b7be94921e4d16050699ca145ec4a
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749077"
---
# <a name="tutorial-update-a-service-endpoint-imported-from-a-solution"></a>チュートリアル: ソリューションからインポートしたサービス エンドポイントの更新

1 つ以上の SAS 認証用に構成したサービス エンドポイントが含まれるソリューションを組織にインポートした後には、特別な手順が必要です。 サービス エンドポイントが含まれるソリューションをエクスポートすると、エクスポートしたソリューションには、各サービス エンドポイントに対する SAS キーは含まれません。 組織へのソリューションのインポート後、各サービス エンドポイントに SAS キーを提供するために追加の手順を実行する必要があります。  
  
ソリューションのインポート後、各サービス エンドポイントに対して SAS キーを設定するには、次の手順を実行します。  
  
## <a name="update-the-sas-key"></a>SAS キーの更新  
  
1. ダウンロードできるプラグイン登録ツールを実行します NuGet。 詳細: [ NuGet からツールをダウンロードする](download-tools-nuget.md)
  
1. プラグイン登録ツールを使用して、インポートされたソリューションを含む組織にサインインします。  
  
1. 組織のタブ ビューで対象のサービス エンドポイントを選択します。  
  
1. **更新**を選択します。 入力済のフィールドを使用して、次のフォームが表示されます。  
  
    ![サービス エンドポイントの SAS キー値の更新](media/sas-key.PNG "サービス エンドポイントの SAS キー値の更新")  
  
1. **SAS キー**フィールドに ******* の値が表示されます。  その値を正しい SAS キー値に置き換えます。 [Azure  ポータル](https://portal.azure.com) から、Azure メッセージング エンティティ (キュー、トピックなど) の SAS キーを入手できます。  
  
1. **保存**を選択します。  
  
### <a name="see-also"></a>関連項目

[Azure 統合](azure-integration.md)<br />
[Service Bus の認証および承認](/azure/service-bus-messaging/service-bus-authentication-and-authorization)<br />
[共有アクセスの署名と Service Bus のアクセス制御](/azure/service-bus-messaging/service-bus-sas)
