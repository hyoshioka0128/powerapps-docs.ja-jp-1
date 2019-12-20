---
title: Power Query のトラブルシューティング | Microsoft Docs
description: Power Query による問題を解決し Common Data Service でユーザー定義エンティティを作成します。
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9b1f0152782a31b13d6209fe3911ed10792652af
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2864261"
---
# <a name="troubleshoot-power-query"></a>Power Query のトラブルシューティング
Power Query for Excel を使用して、外部ソースからのデータを含むユーザー定義エンティティを作成すると、このエラーが表示される場合があります。

>この機能を使用できないようにするポリシーが Azure Active Directory 管理者によって設定されています。 代わりにこの機能に対するアクセス許可を付与できる管理者に連絡してください。"

このエラーは、Power Query が Power Apps または Common Data Service の自社組織のデータにアクセスできない場合に表示されます。 このような状況は、次の 2 つの状況セットで発生します。

* Azure Active Directory (Azure AD) テナント管理者は、ユーザーに代わって会社データにアクセスするアプリにユーザーが同意することを認めていません。
* アンマネージド Active Directory テナントを使用します。 アンマネージド テナントは、セルフサービス サインアップ サービスを実行するために作成された、グローバル管理者のいないディレクトリです。 このシナリオを修正するには、ユーザーはまずマネージド テナントに変換した後、この問題に対する 2 つソリューションのいずれかに従う必要があります。 解決策については、次のセクションで説明します。

この問題を解決するにあたって、 Azure Active Directory の管理者は、この記事で後述するいずれかの手順に従う必要があります。

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>ユーザーが企業データにアクセスするアプリに同意できるようにする
この方法は、次の方法より簡単ですが、幅広いアクセス許可が付与されます。

1. [Azure ポータル](https://portal.azure.com) で、 **Azure Active Directory** ウィンドウを開き、 **ユーザー設定**を選択します。
2. **ユーザーは代わりに企業データにアクセスするアプリに同意できる**の横で、**はい**を選択し、**保存**を選択します。

## <a name="allow-power-query-to-access-company-data"></a>Power Query に企業データへのアクセスを許可する
代替策として、テナント管理者はテナント全体のアクセス許可を変更せずに Power Query に同意することができます。

1. [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps) に同意します。
2. 次の PowerShell コマンドを実行します。
   * Login-AzureRmAccount (およびテナント管理者としてサインイン)
   * New-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

この方法の利点は (テナント全体のソリューションとくらべて)、このソリューションだけがターゲットとなることです。 **Power Query** サービス プリンシパルのみプロビジョニングしますが、テナントに対するそのほかアクセス許可は変更されません。

## <a name="update-personal-data"></a>個人データの更新

ユーザーは、クエリ エディターと、クエリ エディターからアクセス可能な**オプション**ダイアログ ボックスからマッシュアップや他の情報 (クエリ名やマッシュアップ データなど) を更新できます。

Power Apps では、以下の手順でクエリ エディターにアクセスします。
1. **データ**ウィンドウに移動して展開し、**エンティティ**を選択します。 
2. 省略記号 (...) を選択し、**クエリの編集**を選択します。
3. リボンで、**オプション**ボタンを選択し、**エクスポートの診断**ボタンを選択します。


## <a name="delete-personal-data"></a>個人データの削除

ほとんどのデータは、30 日以内に自動的に削除されます。 マッシュアップに関連するデータおよびメタデータの場合、ユーザーは Power Apps を使用してすべてのマッシュアップを削除する必要があります。 すべての関連データおよびメタデータは 30 日以内にすべて削除されます。

Power Apps からマッシュアップを削除するには:
1. Data Integrator プロジェクトを削除します。同じ名前のタブから削除できます。
2. 省略記号 (...) を選択し、**削除**オプションを選択します。

"データからの新しいエンティティ (テクニカル プレビュー)" 機能を使用してマッシュアップを作成した場合は、以下の手順で削除できます。
1. 省略記号 (...) を選択し、**クエリの編集**を選択します。
2. リボンで**オプション**ボタンを選択します。
3. **すべてのクエリの削除**ボタンを選択します。  
    クエリを削除することを確認すると、削除されます。

## <a name="export-personal-data"></a>個人用データのエクスポート

個人データをエクスポートするには、次のことができます。
1. クエリ エディターを開きます。
2. リボンで**オプション**ボタンを選択します。
3. **エクスポートの診断**ボタンを選択します。

Power Apps では、以下の手順でクエリ エディターにアクセスすることができます:
1. **データ**ウィンドウに移動して展開し、**エンティティ**を選択します。
2. 省略記号 (...) を選択し、**クエリの編集**を選択します。 
3. リボンで、**オプション**ボタンを選択し、**エクスポートの診断**ボタンを選択します。

ユーザー インターフェイス (UI) でのユーザー アクションについてシステムにより生成されたログには、Azure ポータルでアクセスできます。



