---
title: ポータルのウェブページへのチャートを追加 | MicrosoftDocs
description: モデル駆動型のアプリで作成したチャートをポータルのウェブページに追加するための手順。
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 11/04/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 3cc2e390b988689e9a21317d80aa7d94d2ea9e6d
ms.sourcegitcommit: d9cecdd5a35279d78aa1b6c9fc642e36a4e4612c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2019
ms.locfileid: "2760641"
---
# <a name="add-a-chart-created-in-a-model-driven-app-to-a-webpage-in-portal"></a>モデル駆動型のアプリで作成したチャートをポータルの Web ページに追加する

[チャート](../liquid/portals-entity-tags.md#chart) と言う流動タグを使い、チャートをウェブページに追加します。 ウェブページの**コピー**フィールドまたは [ウェブ テンプレート](../liquid/store-content-web-templates.md) の**ソース**フィールドに、チャート流動タグを追加することができます。
 
例: {% chart id:EE3C733D-5693-DE11-97D4-00155DA3B01E %}

![グラフの例](../media/dynamics365-chart-example.png "グラフの例")

クエリをフィルターするビュー (保存されたクエリ) の ID を指定することもできます。 たとえば、次のようなものです。

<!—Leads by Source – Open Leads -->

{% chart id:"EE3C733D-5693-DE11-97D4-00155DA3B01E" viewid:"00000000-0000-0000-00AA-000010001006" %}

## <a name="get-the-id-of-a-chart"></a>チャートの ID を取得

1.  ターゲット エンティティへ移動します。例えば、**セールス** > **潜在**。
2.  **チャート**エリアを展開します。
3.  希望のチャートを選択します。
4.  **追加コマンド**を選択し、**エクスポート チャート**を選択します。

    ![グラフのエクスポート](../media/export-dynamics365-chart.png "グラフのエクスポート")

5. テキスト エディターのエクスポートされたチャートの XML ファイルを開きます。
6. \<visualizationid\> タグの値をコピーします。

    ![グラフの chartid を取得する](../media/dynamics365-chart-chartid.png "グラフのグラフ ID を取得する")

7. ID パラメーターに対して流動チャート タグ申告に、視覚化値を貼り付けます。次に例を表示します。

    {% chart id:EE3C733D-5693-DE11-97D4-00155DA3B01E %}。

## <a name="get-the-id-of-a-view"></a>ビューの ID を取得

ビュー ID を流動チャート タグで使用するには、ビュー エディターを開ける必要があります。
 
1.  ターゲット エンティティへ移動します。例えば、**セールス** > **潜在**。
2.  ドロップ ダウン ヘッダーのビューから、あなたが望むビューを選択します。
3.  ツールバーから、**ビュー**を選択します。 ビュー ウィンドウが開きます。

    ![ビュー エディタで潜在顧客を表示する](../media/dynamics365-chart-view.png "ビュー エディタで潜在顧客を表示する")

4. ビュー ウィンドウの URL から、**id** 値をコピーします。

    ![ビュー エディタからビュー ID を取得](../media/dynamics365-chart-viewid.png "ビュー エディタからビュー ID を取得する")

5. パラメーターに対して流動チャート タグ申告に、この ID を貼り付けます。次に例を表示します。

    <!—Leads by Source – Open Leads -->

    {% chart id:"EE3C733D-5693-DE11-97D4-00155DA3B01E" viewid:"00000000-0000-0000-00AA-000010001006" %}

## <a name="entity-permission-requirement"></a>エンティティ アクセス許可の要件

チャート内でクエリされているターゲット エンティティに対する読み取り権限がアサートされます。 チャートを表示できる匿名または認証されたユーザーへ向けて、適切な [エンティティ アクセス許可](assign-entity-permissions.md) のレコードが該当の [ウェブ ロール](create-web-roles.md) に作成され割り当てられることを確認する必要があります。 
 
アクセス許可が与えられない場合、ユーザーには "アクセス拒否" のメッセージが表示されます。

## <a name="unsupported-charts-and-chart-types"></a>サポートされていないチャートとチャート タイプ

次のグラフの種類は、現在ポータルでサポートされていません。
- ドーナツ
- タグ

次のテーブルは、現在ポータルでサポートされていないグラフの一覧です。

| チャート名                              | チャート ID                             | [エンティティの種類]      |
|-----------------------------------------|--------------------------------------|------------------|
| 所有者別取引先企業 - タグ グラフ           | be178262-6142-4b41-85b7-4ccedc62cfd9 | 取引先企業          |
| 所有者別活動 - タグ グラフ         | c83b331e-87c7-488c-b8e7-89a6098ea102 | activitypointer  |
| 重要度別活動 - ドーナツ グラフ | d3f6c1eb-2e4b-428b-8949-682a311ae057 | activitypointer  |
| 取引先企業別の取引先担当者                     | 2ff3ebea-6310-4dde-b3a1-e1144ea42b7b | 取引先担当者          |
| 国別取引先担当者                     | ea89e2ad-2602-4333-8724-aa5775d66b77 | 取引先担当者          |
| 優先する連絡方法別の取引先担当者    | 751b7456-308e-4568-a3a9-47135aae833a | 取引先担当者          |
| 目標の進捗 (件数)                   | a93b8f7b-9c68-df11-ae90-00155d2e3002 | goal             |
| 目標の進行状況 (金額)                   | aec6d51c-ea67-df11-ae90-00155d2e3002 | goal             |
| 本日の目標値と実績値 (件数)      | 1b697c8e-9a6f-df11-986c-00155d2e3002 | goal             |
| 本日の目標値と実績値 (金額)      | 1e697c8e-9a6f-df11-986c-00155d2e3002 | goal             |
| 取引先企業別サポート案件                        | 38872e4f-ac99-e511-80da-00155dc1b253 | incident         |
| 重要度別サポート案件                       | 0f0fb995-9d6f-453c-b26d-8f443e42e676 | incident         |
| 製品別サポート案件                        | 17c3f166-5b22-4476-819b-b05da2e8d24f | incident         |
| 今月期限切れになる所有者別の記事   | 47d696ad-7c3b-e511-80d1-00155db10d2b | ナレッジ記事 |
| 所有者別                                | 330068fd-833b-e511-80d1-00155db10d2b | ナレッジ記事 |
| 情報カテゴリ別                              | bcd3f9a5-913b-e511-80d1-00155db10d2b | ナレッジ記事 | 
| | |
