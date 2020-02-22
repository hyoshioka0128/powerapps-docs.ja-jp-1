---
title: データがレポートに表示されない問題のトラブルシューティング | Microsoft Docs
description: データがレポートに表示されない問題のトラブルシューティング
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 06/27/2019
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1156aa8fb5fbc3ae51c21b8aa41606df6dbc2e86
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420768"
---
# <a name="troubleshoot-problems-with-data-not-displaying-in-a-report"></a>データがレポートに表示されない問題のトラブルシューティング

レポートに含まれるはずのデータが表示されない場合、次のような理由が考えられます。  
  
- **セキュリティのアクセス許可が不十分**: レコードを表示するためのアクセス許可が Common Data Service にない場合、レコードはレポートに表示されません。  
  
- **データが入力されていない**: データを入力するユーザーが、フィールドを空のままにしている可能性があります。  
  
- **データがレポートの基準と一致しない**: 多くのレポートには、アクティブなレコードのみを表示する規定のフィルターが含まれています。または、一致するレコードがない条件を選択した可能性があります。 レポート フィルターを変更してみてください。 詳細については、「[レポートの既定のフィルターの編集](edit-report-filter.md)」を参照してください。  
  
- **レポートのキャッシュ コピーを表示している**: 既定では、Common Data Service レポートのデータは、レポートを実行するたびにデータベースから取得されます。 しかし、システム管理者がキャッシュから実行するようにレポートを変更している場合もあります。 最近入力したデータがレポートに含まれない場合は、キャッシュの古いバージョンのレポートを使用している可能性があります。 レポートを更新するには、[レポート] ツールバーで、 **[更新]** ボタンを選択します。  
  
- **サブレポート内のレコードを読み取るためのアクセス許可がない**: サブレポートに含まれるレコードの種類を読み取るためのアクセス許可ない場合、サブレポートを表示できないというエラー メッセージが表示されます。  
  
- **Microsoft Internet Explorer のプライバシー設定により、必要な Cookie がブロックされている**: グラフ レポートで、グラフを表示する代わりに赤色の文字 X が表示される場合、プライバシー設定によって、グラフ コントロールに必要な Cookie がブロックされている可能性があります。 この問題を解決するには、ブラウザーで、Reporting Services を実行しているサーバーに対して Cookie を有効にします。  
  

### <a name="see-also"></a>参照
[レポートを操作する](work-with-reports.md) 

[レポート ウィザードを使用してレポートを作成する](create-report-with-wizard.md)

[既存のレポートを追加する](add-existing-report.md)

[レポートの既定のフィルターの編集](edit-report-filter.md)

