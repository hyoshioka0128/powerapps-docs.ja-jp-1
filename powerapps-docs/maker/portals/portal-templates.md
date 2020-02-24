---
title: Power Apps で使用可能なポータル テンプレート | Microsoft Docs
description: Power Apps で使用可能なさまざまなポータル テンプレートについて説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/07/2019
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: ec678eccc0c4321db0576821035f714590b13b89
ms.sourcegitcommit: a0d069f63d2ce9496d578f81e65cd32bec2faa4d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "2981454"
---
# <a name="portal-templates"></a>ポータル テンプレート

Power Apps での指定環境に基づいて、Common Data Service スターター ポータルまたは Dynamics 365 のモデル駆動型のアプリ含む環境のポータルを作成できます。

## <a name="environment-with-common-data-service"></a>Common Data Service を使用する環境

Common Data Service を含む環境を選択して、Common Data Service スターター ポータルを作成できます。 Common Data Service スターター ポータルには、すぐ始めるためのサンプル データが付属します。 また、下記の組み込みのサンプル ページもあります:

- 既定のスタジオ テンプレート
- タイトルを含むページ
- 子リンクのあるページ

## <a name="environment-with-model-driven-apps-in-dynamics-365"></a>Dynamics 365 のモデル駆動型アプリを含む環境 

Dynamics 365 (Dynamics 365 Sales、Dynamics 365 Customer Service、Dynamics 365 Field Service、Dynamics 365 Marketing、または Dynamics 365 Project Service Automation) のモデル駆動型アプリを含む環境を選択する場合は、次のポータルを作成できます:

- **顧客セルフサービス ポータル**: 顧客セルフサービス ポータルでは、顧客がセルフサービス方式で技術情報にアクセスしたり、リソースをサポートしたり、サポート案件の進捗状況を確認したりできます。フィードバックを送信することもできます。
- **パートナー ポータル**: パートナー ポータルを使用すると、再販業者、卸売業者、納入業者、またはパートナーと取引のあるあらゆる組織が、共有した活動のすべてのステージにリアルタイムでアクセスできます。

    > [!NOTE]
    > 各オプションを有効にするにいは、Field Service と Project Service パッケージが、Dynamics 365 組織にインストールさっれている必要があります。 詳細については、[Project Service Automation の統合](https://docs.microsoft.com/dynamics365/portals/integrate-project-service-automation) および [Field Serviceの統合](https://docs.microsoft.com/dynamics365/portals/integrate-field-service) を参照してください。

- **従業員セルフサービス ポータル**: 一般的なタスクを合理化し、信頼できる技術情報ソースを提供してあらゆる従業員の能力を高めることにより、効率的で十分に情報を得た労働力を生み出します。
- **コミュニティ ポータル**: コミュニティ ポータルでは、顧客とエキスパートの間でのピアツーピアの活発なやり取りを促し、サポート情報の記事、フォーラム、ブログから入手できる技術情報を有機的に拡大しながら、コメントや評価からフィードバックを得ることができます。
- **空のポータル**: 外部および内部ユーザーとデータを共有するための Web サイトを作成します。 このテンプレートでは、迅速に開始するためのサンプル ページが取得できます。 

## <a name="portal-templates-features"></a>ポータル テンプレート機能

以下の表は、各ポータル オプションに関連する機能をまとめたものです。

| 機能 | 顧客セルフサービス ポータル | パートナー ポータル | 従業員セルフサービス ポータル | コミュニティ ポータル | 空のポータル | Common Data Service スターター ポータル|
|------------------|---------------|----------------|---------------|------------------|---------------|------|
| ワールド レディ | •  | • | • | • | • |• |
| 複数言語のサポート | •  | • | • | • | • |• |
| ポータル管理| • | • | • | • | •  |• |
| カスタマイズと拡張性  | •   | •  | •   | •  | • |• |
| テーマ化   | •   | •   | •    | •   | •   |• |
| コンテンツ管理                     | •                            |                | •                            | •                |               |
| ナレッジ マネージメント                   | •                            | •              | •                            | •                |               |
| サポート/Case Management                | •                            |                | •                            | •                |               |
| フォーラム                                 | •                            |                | •                            | •                |               |
| ファセット検索                         | •                            |                | •                            |                  |               |
| プロファイル管理                     | •                            |                | •                            |                  |               |
| フォーラム スレッドの購読              | •                            |                | •                            |                  |               |
| コメント                               | •                            |                | •                            | •                |               |
| [!INCLUDE[pn-azure-shortest](../../includes/pn-azure-shortest.md)] AD 認証                |                              |                | •                            |                  |               |
| アイデア                                  |                              |                |                              | •                |               |
| ブログ                                  |                              |                |                              | •                |               |
| Project Service Automation 統合 |                              | •              |                              |                  |               |
| Field Service 統合              |                              | •              |                              |                  |               |
| パートナーのオンボーディング                     |                              | •              |                              |                  |               |
| ポータル ベース  |  •    | •      |  •| •| •|• |
| ポータルのワークフロー|  •| •|  •| •| •|• |
| Web 通知|  •| •|  •| •| •|• |
| [!INCLUDE[cc-microsoft](../../includes/cc-microsoft.md)] ID|   •|  •|  •|   •| •|• |
| ID ワークフロー| •|  •| •|   •| •|• |
| Web フォーム|  •| •|    •| •| •|• |
| フィードバック|   •|  •|  •| •| •|• |
||
