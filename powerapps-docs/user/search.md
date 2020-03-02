---
title: Common Data Service の検索オプション | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 1/27/2020
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 440241571f716fa1931b5c11935c70de5c85e7ee
ms.sourcegitcommit: 5bfd0448f1d5ca3d938e3bd928d1dd3d4042afff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2020
ms.locfileid: "76828594"
---
# <a name="compare-search-options-in-common-data-service"></a>Common Data Service の検索オプションの比較

Common Data Service では、次の 3 つの方法でレコードを検索できます。

-   関連性の検索   
  
-   クイック検索 (単一エンティティまたは複数エンティティ)  

-   高度な検索

> [!NOTE]
> 複数エンティティの簡易検索はカテゴリ別検索とも呼ばれています。 
  
次の表は、3 つのオプションを簡単に比較したものです。

|機能|[[関連性検索]](relevance-search.md)|[[クイック検索]](quick-find.md)|[[高度な検索]](advanced-find.md)|  
|-------------------|---------------------------|----------------|-------------------|  
|既定で有効かどうか|いいえ。 管理者が手動で有効にする必要があります。|はい|はい|  
|単一エンティティの検索範囲|エンティティ グリッドでは使用できません。 検索結果は、結果ページのエンティティでフィルター処理できます。|エンティティ グリッドで使用できます。|エンティティ グリッドで使用できます。|  
|複数エンティティの検索範囲|検索できるエンティティの数に上限はありません。 **注:** 検索できるエンティティの数に上限はありませんが、[レコードの種類] フィルターには 10 エンティティのみのデータが表示されます。|最大 10 エンティティが検索され、エンティティ別にグループ化されます。|複数エンティティ検索は使用できません。|  
|検索動作|エンティティ内のあらゆるフィールドを対象に、検索語句に含まれるいずれかの単語との一致が検索されます。|エンティティ内の 1 つのフィールドを対象に、検索語句に含まれるすべての単語との一致が検索されます。ただし、単語の一致では、フィールド内での順序が問われません。|クエリ ビルダーでは、選択したレコードの種類に対して検索基準を定義できます。 また、データを分析、集計、総計したり、ピボットテーブルを作成し、さまざまな観点からデータを表示したりするよう、Office Excel にエクスポートするデータを用意する目的で利用できます。|  
|検索可能なフィールド|1 行テキスト、複数行テキスト、参照、オプション セットなど、テキスト フィールド。 数値データ型または日付データ型のフィールドの検索はサポートされていません。|検索可能なすべてのフィールド。|検索可能なすべてのフィールド。|  
|検索結果|関連性順に並べ替え、1 つのリストで検索結果を返します。|単一エンティティの場合、エンティティ グリッドで検索結果を返します。 複数エンティティの場合、アカウント、連絡先、潜在顧客など、カテゴリ別にグループ化した上で検索結果を返します。|ユーザーが選択したレコードの種類と指定した列を対象に、設定した並べ替え順序で検索結果を返します。|
|ワイルドカード (*)|末尾にワイルドカードを付け、単語を補完できます。|先頭にワイルドカードを付けることができます。 先頭のワイルドカードは既定で追加されます。|サポートされていません。|  