---
title: SQL を使用したデータのクエリ (Common Data Service)| Microsoft Docs
description: SQL を使用して Common Data Service エンティティ データをクエリする方法について説明します。
ms.custom: ''
ms.date: 05/05/2020
ms.reviewer: pehecke
ms.service: powerapps
ms.topic: article
author: phecke
ms.author: pehecke
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: b464b1cd4a64e9f33919567da15d10d7e50d9dd2
ms.sourcegitcommit: 0ede8e3bc795e151aa94ffcbce15cff7a949c57a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335343"
---
# <a name="use-sql-to-query-data-preview"></a>SQL を使用してデータを照会する (プレビュー)

[!INCLUDE[cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

SQL データ接続は、Common Data Service エンドポイントで使用できます。 SQL 接続は、ターゲットの Common Data Service 環境のエンティティ データへの読み取り専用アクセスを提供します。 これにより、エンティティ データ テーブルに対して SQL クエリを記述して実行できます。 テーブルの列は、エンティティの属性データを提供します。 データのカスタムビューは提供されていません。

> [!IMPORTANT]
> - これはプレビュー機能であり、すべての地域で利用できるわけではありません。
> - [!INCLUDE[cc_preview_features_definition](../../includes/cc-preview-features-definition.md)]

## <a name="applications-support"></a>アプリケーション サポート

Power Apps (https://make.powerapps.com) の **Power BI で分析**オプション (**データ** > **エンティティ** > **Power BI で分析**) を使用して、SQL 接続機能により Power BI Desktop でデータを分析できます。 詳細: [Power BI Desktop でのエンティティ データの表示](/powerapps/maker/common-data-service/view-entity-data-power-bi)

> [!NOTE]
> Power Apps 環境内に **Power BI で分析**オプションがない場合、SQL 接続機能にまだアクセスできません。

Common Data Service エンドポイントの SQL 接続で、[SQL Server Management Studio](/sql/ssms/download-sql-server-management-studio-ssms) (SSMS) バージョン 18.4 以降を使用することもできます。 SQL データ接続で SSMS を使用する例を以下に示します。

![拡張アカウント テーブル](media/ssms-table-expanded.PNG)

## <a name="security-and-authentication"></a>セキュリティおよび認証

Common Data Service エンドポイントの SQL接続は、データ アクセスに Common Data Service セキュリティモデルを使用します。 Common Data Service でユーザーがアクセスできるすべてのエンティティのデータを取得できます。

Azure Active Directory 認証のみサポートしています。 SQL 認証と Windows 認証はサポートされていません。 以下は、SSMS で SQL 接続にログオンする方法の例です。 サーバー名は、組織アドレス URL の後にコンマと 5558 のポート値が続くことに注意してください。

![接続ダイアログ](media/ssms-connect-dialog.PNG)

## <a name="example-entity-data-queries"></a>エンティティ データ クエリの例

以下は、SSMS で構成されるクエリのいくつかの例です。 最初の画像は、エイリアスと結果の順序を使用した簡単なクエリを示しています。

```tsql
select top 5 a.name as [VIP customer], a.address1_postalcode as [ZIP code] from account a order by a.address1_postalcode desc
```

![エイリアスと順序を使用した簡単なクエリ](media/ssms-simple-query.PNG)

次のクエリは、JOIN を示しています。

```tsql
select name, fullname from account a inner join contact c on a.primarycontactid = c.contactid
```

![JOIN を使用した別のクエリ](media/ssms-join-query.PNG)

## <a name="supported-operations-and-data-types"></a>サポートされている操作とデータ型

サポートされている SQL 操作のリストは次のとおりです。

- バッチ処理
- 選択
- 集計関数 (例、Count() および Max() 関数)
- UNION および JOIN
- フィルタリング

これは読み取り専用の SQL データ接続であるため、データを変更しようとする操作 (例、INSERT、UPDATE) は機能しません。 Common Data Service オプション セットは、結果セットでは \< OptionSet \> の名前と \< OptionSet \> のラベルとして表されます。

次の Common Data Service データ型は、SQL 接続ではサポートされていません。バイナリ、イメージ、ntext、sql_variant、varbinary、仮想、HierarchyId、managedproperty、ファイル、xml、partylist、タイムスタンプ。

### <a name="see-also"></a>関連項目

[FetchXML の使用によるクエリの作成](use-fetchxml-construct-query.md)
