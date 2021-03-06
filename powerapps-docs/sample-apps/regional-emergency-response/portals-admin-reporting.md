---
title: 地域政府機関の緊急時対応答およびモニタリング ポータルを管理する | Microsoft Docs
description: 地域病院の緊急時応答ポータルを構成する方法について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 05/06/2020
ms.author: tapanm
ms.reviewer: tapanm
searchScope:
- PowerApps
ms.openlocfilehash: 2933ad47995915d60b864188c87bb6c9e6953407
ms.sourcegitcommit: c424a17b9c658f4571b5ea26ab6fc8a486051d44
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "3341889"
---
# <a name="administer-the-regional-governmentemergency-response-and-monitoring-portal"></a>地域政府機関の緊急時応答およびモニタリング ポータルを管理する

病院のスタッフは、緊急時にサプライチェーンを管理しながら、患者数の増加に対応する必要があります。 地域政府機関の緊急時応答およびモニタリング ポータルを使用することにより、管理者は、**ユーザー**、**システム**、**地域**、および**施設**に関連するデータをすばやく表示および更新できます。 関係者は、現在の医療システムの状態についてダッシュボードを通じて公開されたインサイトを表示し、アクションを実行できます。

## <a name="portal-at-a-glance"></a>ポータルの概要

**ユーザー**、**システム**、**地域**、および**設備**を追加、編集または削除するには Power Apps ポータルを参照してください。 次のセクションでは、ポータルの管理者としてアクセス、送信、または更新できる内容を手順に追って説明します。

![ポータルの概要](media/portal-at-glance.png)

地域政府機関の緊急応答およびモニタリング ポータルを使用する場合、Apple iPad を除き、最新のモバイル デバイスや Web ブラウザーを使用できます。

[!include[cc-getting-started](includes/cc-getting-started.md)]

> [!NOTE] 
> 管理者は管理およびダッシュボードの設定を表示するには、**医療機関、地域**と**設備**および**次**を選択する必要があります。 ユーザー管理やダッシュボードのレビューなどの管理操作にのみポータルを使用する場合は、任意の場所を選択できます。 ただし、**スタッフ**または**備品**のようなユーザー コンポーネントを使用する場合は、正しい場所を選択したことを確認してください。

[!include[cc-manage-user-profile](includes/cc-manage-user-profile.md)]

## <a name="administrative-tasks"></a>管理タスク

ホーム画面で**管理**選択した後、使用可能なすべての管理オプションを表示できます :

![ポータル管理](media/portal-admin-screen.png)

### <a name="administrative-tasks-and-description"></a>管理タスクおよび説明

| **オプション名** | **説明**                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------|
| [ユーザーの要請](#user-requests) | ポータル ユーザーの要請を表示、承認、または拒否します。
| [ユーザー ](#users)       | ポータル ユーザーを作成、編集、または非アクティブ化します。                                                         |
| [システム](#systems)      | システムを作成、編集、または削除します。 |
| [地域](#regions)      | 地域を作成または削除します。                              |
| [Facilities](#facilities)    | 設備を作成、編集、または削除します。                        |

### <a name="user-requests"></a>ユーザーの要請

**ユーザーの要請**管理タスク オプションを使用して、ポータル ユーザーの要請を表示、承認および拒否できます。

**ユーザーの要請**を選択すると、保留中のレビューを送信したすべての既存のポータル ユーザーの要請を参照できます:

![ポータル ユーザー要請の表示](media/view-portal-user-requests.png)

ビューを変更して、承認または拒否された要請を参照するように選択できます:

![ポータル ユーザーの要請のビューを変更](media/portal-user-requests-views.png)

#### <a name="process-pending-requests"></a>保留中の要請を処理する

保留中のポータル ユーザー要請を処理するには、**保留中のポータル ユーザーの要請**ビューから保留中の要請の**詳細の表示**を選択します:

![要請の詳細を表示](media/portal-user-requests-view-details.png)

詳細ビューから、ユーザーの取引先担当者情報、ロールを確認し、要請を承認または拒否できます。 フォームで選択されたロールは、要請されたロールです。 要請を承認または拒否する前に、チェックボックスを使用してロールを追加または削除できます:

![ユーザーの要請を承認または拒否](media/approve-reject-user-request.png)

ロールの詳細については、[ユーザー ロール](#user-roles) に移動してください。

要請を承認するには**アクセス要請を承認**、または要請を拒否するには**アクセス要請を拒否**を選択します。

要請を拒否する場合は、理由を入力する必要があります:

![理由を拒否](media/decline-request-reason.png)

#### <a name="request-approval-or-decline-emails"></a>要請の承認または電子メールを拒否

ユーザーの要請を承認するか拒否するかに応じて、要請者は要請処理結果を含む電子メールを受信します。 承認された要請の場合、電子メールには、ユーザーが初めてサインインするときに利用できる招待コードが含まれています。 拒否された要請の場合、電子メールには要請の拒否中に入力された拒否理由が含まれます。

### <a name="review-approved-requests"></a>承認された要請の確認

承認されたポータル ユーザー要請を表示するには、**承認中のポータル ユーザーの要請**ビューから保留中の要請の**詳細の表示**を選択します:

![承認された要請の表示](media/portal-user-requests-view-approved-details.png)

既存の承認済み要請を拒否するには、**アクセス要請の拒否**を選択します:

![承認された要請を拒否](media/decline-approved-request.png)

### <a name="review-declined-requests"></a>拒否された要請の確認

承認されたポータル ユーザー要請を表示するには、**承認中のポータル ユーザーの要請**ビューから保留中の要請の**詳細の表示**を選択します:

![承認された要請の表示](media/portal-user-requests-view-declined-details.png)

以前、要請が拒否されたときに提供されたコメントとして、各要請で必須の**拒否された理由**を表示することもできます。

既存の拒否された要請を承認するには、**アクセス要請の承認**を選択します:

![拒否された要請を承認](media/approve-declined-request.png)

### <a name="users"></a>ユーザー 

ポータルの管理、ダッシュボードの表示、またはポータルを医療従事者として使用する新しいユーザーを作成するには**ユーザー**に移動します:

![ユーザー ](media/portal-admin-add-user.png)

**すべてのアクティブ ユーザー**および**自分のアクティブ ユーザー**という 2 つのビューを使用できます。 **すべてのアクティブユーザー** ビューでは、選択された親組織のすべてのアクティブ ユーザーが表示されます。 **自分のアクティブユーザー** ビューでは、現在ログインしている上位組織の管理者によって作成または承認された、選択された上位組織のすべてのアクティブ ユーザーが表示されます。

**ユーザー**から、[ユーザーの詳細を表示](#view-user-details)、[ユーザー ロールを変更](#change-role-for-a-user)および[ユーザーを非アクティブ化](#deactivate-a-user) することもできます。

#### <a name="search-user-details"></a>ユーザーの詳細を検索

検索ボックスにテキストを入力して、検索されたユーザーのフィルター結果を表示します。 ワイルドカード (**\***) 検索が有効になっていて、次のフィールドを検索できます:

- 氏名

- 電子メール

- 携帯電話

- 上位組織

ワイルドカード検索および部分条件を使用して、電話番号を含む結果を表示できます。

たとえば、**デロレス バスケス**のような**氏名**でユーザーを検索したい場合、検索で次のサンプル文字列を使用できます:

- DEL\*

- \*Del

- Del\*va

**携帯電話**を検索するには、文字を数字に置き換えるワイルドカードを使用して、同様のテキストを使用できます。

#### <a name="create-user"></a>ユーザーの作成

ユーザーを作成するには、**ユーザー** フォームの時に**ユーザーを作成**ボタンを選択します。 次に、新しいユーザーの詳細をフォームに入力します:

![ユーザーの作成](media/portal-admin-create-user.png)

**名**、**姓**、**電子メール**、および**携帯電話**を入力し、ユーザーのロールを選択します。

##### <a name="user-roles"></a>ユーザー ロール

ユーザーのロールは、ポータルに表示されるコンポーネントを定義します:

![ロールのポータル](media/portal-with-roles.png)

強調表示されたコンポーネントは、次のロールが割り当てられたユーザーに表示されます:

1. [組織の医療従事者](#organizational-healthcare-worker)
2. [レポート ビューア](#report-viewer)
3. [上位組織の管理者](#parent-organization-administrator)

次のセクションでは、ロールのメンバーが実行できることの詳細の各ロールについて説明します。

##### <a name="organizational-healthcare-worker"></a>組織の医療従事者

医療従事者は、正看護師などの病院システムの従業員です。 医療従事者は 1 つ以上の設備内で勤務します。 医療従事者は、次の領域間のデータを収集します。

- ベッドのキャパシティ

- スタッフ

- 備品

- 消耗品

- COVID-19 の統計

##### <a name="report-viewer"></a>レポート ビューア

レポート ビューア― ロールは、このポータルで使用可能なダッシュボードを表示できるユーザー対象です。 レポート ビューア― ロールのメンバーは、次のダッシュボードを表示できます:

- システムの概要

- 新型コロナウイルス患者の詳細

- ベッドのキャパシティの詳細

- 備品の詳細

- 消耗品の詳細

##### <a name="parent-organization-administrator"></a>上位組織の管理者

上位組織管理者は、このポータルを使用して組織の詳細にアクセスできるユーザーを作成できます。

上位組織管理者ロールのメンバーは次のことができます:

- 新しいユーザーを作成し、それらを**組織の医療従事者、レポート ビューア―**、または**上位組織管理者**ロールに追加します。

- 組織のメタデータの変更:

    - **システム**の作成、編集、または削除

    - **地域**の作成または削除

    - **設備**の作成、編集、または削除

> [!TIP]
> 3 つのロールをすべて選択して、ユーザーがすべてのコンポーネントにアクセスできるようにします。

#### <a name="view-user-details"></a>ユーザーの詳細を表示する

ユーザーのドロップダウンを選択し、**詳細の表示**を選択してからユーザーの詳細を表示できます:

![ユーザー オプションを表示](media/portal-user-view-user-options.png)

##### <a name="change-role-for-a-user"></a>ユーザーのロールの変更

ユーザーの詳細からユーザーを追加または削除することができます:

![ユーザーの詳細を表示する](media/portal-user-view-details.png)

#### <a name="deactivate-a-user"></a>ユーザーの非アクティブ化

ユーザー ドロップダウンから**非アクティブ化**を選択し、ユーザー アカウントを非アクティブ化します:

![ユーザー オプションを表示](media/portal-user-view-user-options.png)

非アクティブ化されたユーザーは、**ユーザー** ビューのユーザー リストにもう存在しません。

### <a name="systems"></a>システム

**システム** フォームを使用して**システム**を追加、更新または削除することができます。 **システム**選択すると、すべての既存の**医療機関**を参照できます:

![システム](media/portal-add-system.png)

#### <a name="search-existing-systems"></a>既存のシステムを検索

検索ボックスにテキストを入力してシステムを検索し、フォーム上のシステムのリストをフィルターします。 ワイルドカード検索 (**\***) をテキスト文字と組み合わせて、**システム名**および**説明**フィールドを使用できます。

#### <a name="view-system-details"></a>システムの詳細を表示

システムの詳細を表示するには、システムのドロップダウン メニューを選択してから、**詳細の表示**を選択します:

![システムの表示](media/portal-view-system-details.png)

システムの詳細ページは**上位組織、システム名**、**説明**、およびシステム内の**地域**を表示します:

![システムの詳細](media/portal-system-details.png)

システムの**システム名**およびそれぞれのテキストボックスの**説明**フィールドを更新できます。

##### <a name="add-region"></a>地域を追加

**地域を追加**ボタンを使用し、現在のシステムに地域を追加します。 **地域を追加**選択すると、**地域名**および**説明**などの地域の詳細を追加できます:

![地域を追加](media/portal-admin-add-region.png)

地域を追加する前にドロップダウンで**システム**を変更できます。 ただし、地域を追加したいシステムを最初に表示して、地域をシステムに追加することをお勧めします。 これは、いったん**送信**を選択すると、選択したシステムが開いている詳細ページと異なる場合、地域セクションにリストされている地域は表示できません。

#### <a name="create-system"></a>システムの作成

システムを作成するには、**作成**、*システム名*および*説明*を入力を選択します:

![システムの作成](media/portal-admin-create-system.png)

#### <a name="delete-system"></a>システムの削除

システムを削除するには、ドロップダウン メニューを選択してから、**削除**オプションを選択します:

![システムの削除](media/portal-view-system-details.png)

システム レコードを削除するには、**削除**を選択します。 システムが削除される前に、削除の確認を求められます:

![削除の確認](media/portal-delete-system-confirm.png)

### <a name="regions"></a>地域

**地域を追加**フォームを使用して**地域**を追加、更新または削除することができます。 **地域を追加**を選択すると、すべての既存の**医療機関**を参照できます:

![地域を追加](media/portal-add-region.png)

#### <a name="search-existing-regions"></a>既存の地域を検索

検索ボックスにテキストを入力して地域を検索し、フォーム上の地域のリストをフィルターします。 ワイルドカード検索 (**\***) をテキスト文字と組み合わせて、**地域名、システム**および**説明**フィールドを使用できます。

#### <a name="create-region"></a>地域を作成

地域を作成するには、**作成**ボタンを選択し、**システム**を選択し、**地域名**および**説明**を入力します:

![地域を作成](media/portal-admin-create-region.png)

#### <a name="delete-region"></a>地域を削除

地域を削除するには、ドロップダウン メニューを選択してから、**削除**オプションを選択します:

![地域を削除](media/portal-admin-delete-region.png)

地域が削除される前に、削除の確認を求められます:

![地域の削除を確認](media/portal-admin-delete-region-confirm.png)

### <a name="facilities"></a>Facilities

**設備**フォームを使用して**設備**を追加または削除することができます。 **設備**を選択すると、すべての既存の**設備**を地域、郡、その他の詳細と共に見ることができます:

![削除の確認](media/portal-admin-add-facility.png)

#### <a name="search-existing-facilities"></a>既存の設備を検索

検索ボックスにテキストを入力してシステムを検索し、フォーム上の設備のリストをフィルターします。 ワイルドカード検索 (**\***) をテキスト文字と組み合わせて、**設備名**、**地域**、および**郡の名前**フィールドを使用できます。

#### <a name="create-facility"></a>設備を作成する

**作成**ボタンを選択して、設備を作成します:

![設備を作成する](media/portal-admin-create-facility.png)

##### <a name="options-and-description"></a>オプションおよび説明

| **オプション名**                                | **説明**                                                                                                                                                                                            |
|------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 設備名                                  | 設備名。                                                                                                                                                                                      |
| 地域                                         | この施設が関連付けられている地域を選択します。                                                                                                                                                          |
| 許可ベッドの全キャパシティ                   | 数値の表示形式に含まれる、許可ベッドのキャパシティの合計。                                                                                                                                                             |
| ICU ベッド (空気感染隔離屋) の全キャパシティ            | AIIR (空気感染隔離室) の ICU ベッドの合計数。                                                                                                                                         |
| 重症治療ベッド (空気感染隔離室) の全キャパシティ     | 数値の表示形式に含まれる重症治療ベッド (AIIR) のキャパシティの合計。                                                                                                                                                   |
| 人工呼吸器の全キャパシティ                     | 数値の表示形式に含まれる、人工呼吸器のキャパシティの合計。                                                                                                                                                               |
| 消耗品リスト | 設備で使用可能な消耗品からアイテムを選択するには、[消耗品リスト](#supplies-list-for-a-facility) を選択します。 |
| DOH 番号                                     | この設備の保健省の番号。                                                                                                                                                         |
| 飛沫防止プロトコルに従う                       | **はい**/**いいえ**を選択します。 新型コロナウイルスの場合のように、呼吸器飛沫によって伝染する病原体に感染が確定している、または疑われる患者に対する飛沫予防策に続く施設に関連します。 |
| 急増対応ベッドの全キャパシティ                      | 数値の表示形式に含まれる急増対応ベッドのキャパシティの合計。 急増対応ベッドは、患者を受け入れる必要がある場合に、許可ベッド キャパシティを超えて配備できるベッドです                                               |
| (空気感染隔離屋でない) ICU ベッドの全キャパシティ        | ICU ベッドの合計数 (空気感染隔離室以外)。                                                                                                                                                                       |
| (空気感染隔離室以外) 重症治療ベッドの全キャパシティ | 数値の表示形式に含まれる重症治療ベッド (空気感染隔離室以外) のキャパシティの合計。                                                                                                                                               |
| 合計霊安室のキャパシティ | 設備の合計霊安室のキャパシティ。 **注意** : 1 以上に設定すると、設備の**ベッド キャパシティ** フォームを使用可能にするため、*現在使用中の霊安室の数*フィールドが発生します。
| 施設の住所                               | 設備の場所の番地、市、郡、州および郵便番号。                                                                                                                                        |

##### <a name="supplies-list-for-a-facility"></a>設備の消耗品リスト

**消耗品リスト**を選択すると、個々の供給を選択し、設備で使用可能な消耗品を関連付けるリストを**保存**します:

![設備の消耗品リスト](media/portal-admin-add-facility-supplies.png)

#### <a name="delete-facility"></a>設備を削除

設備を削除するには、ドロップダウン メニューを選択してから、**削除**オプションを選択します:

![設備の削除](media/portal-admin-delete-facility.png)

設備が削除される前に、削除の確認を求められます:

![設備の削除の確認](media/portal-admin-delete-facility-confirm.png)

#### <a name="edit-facility"></a>設備の編集

設備を削除するには、ドロップダウン メニューを選択してから、**編集**オプションを選択します:

![設備の編集](media/portal-admin-delete-facility.png)

フィールドを更新し、変更を保存するのに**送信**を選択します。

## <a name="get-insights"></a>インサイトの取得

**レポート ビューア―** ロールのメンバーである場合、**ダッシュボード**表示するオプションが表示されます:

![インサイトの取得](media/portal-admin-get-insights.png)

### <a name="dashboards-overview"></a>ダッシュボードの概要

ダッシュボードは次のインサイトで利用できます:

- [システムの概要](#system-at-a-glance)

- [新型コロナウイルス患者の詳細](#covid-19-patient-details)

- [ベッドのキャパシティの詳細](#bed-capacity-details)

- [備品の詳細](#equipment-details)

- [消耗品の詳細](#equipment-details)

- [データ正常性スコアカード](#data-health-scorecard)

#### <a name="working-with-reports-in-power-bi"></a>Power BI でレポートの作業

使用可能なダッシュボードのレビューを開始する前に、全般的なレポート表示の概念およびガイドラインを理解してください :

- 要約された領域のいずれかで情報アイコン (i) を選択すると、その領域のそれぞれの詳細ページが表示されます。

- レポートに対して、データのフィルター処理と並べ替え、PDF および PowerPoint へのレポートのエクスポート、スポットライトの追加など、その他のアクションを実行することもできます。 Power BI でのレポート機能の詳細については、[Power BI のレポート](https://docs.microsoft.com/power-bi/consumer/end-user-reports) を参照してください。

- これらのレポートの一部の最新更新または最後に更新された列には、データが最後に更新された日時が表示されます。 これらの列で日付と時刻の値の色を確認することで、鮮度を簡単に特定することもできます。

- **黒:** 20 時間以内にデータが更新されました

- **灰色:** 20 - 24 時間前にデータが更新されました

- **赤:** データは 24 時間以上空けて更新されました

### <a name="system-at-a-glance"></a>システムの概要

**システムの概要**ダッシュボードを使用して、**医療機関**関連の統計全体を 1 つのビューで表示します:

![ダッシュボード​​](media/portal-admin-powerbi-reports.png)

ダッシュボードには以下の概要が表示されます:

- **新型コロナウイルス統計**: 新型コロナウイルス患者の概要を、合計患者数、検査中の患者数、陽性および挿管された患者数で表示します。

- **ベッド キャパシティ**: 概要データを表示**使用可否**およびライセンス、ICU、重症および急増カテゴリの**占有率**を表示します。

- **郡別ベッドの可用性**: すべての郡のベッドの合計数、ICU/重症/急増ベッドの可用性、およびすべてのベッドの可用性の合計数で、ベッドの可用性を表示します。

- **消耗品**: 個別に、在庫日数で消耗品情報を表示します。

- **備品**: 人工呼吸器と機器の概要番号を、可用性、使用中、および必要に応じて表示します。

### <a name="covid-19-patient-details"></a>新型コロナウイルス患者の詳細

COVID PUI、陽性、挿管の概要など、新型コロナウイルス関連の患者の詳細を表示します。 ダッシュボードの下部には、郡ごとの詳細も表示されます。

郡を地図で表示することもでき、郡は分離のために色分けされています。 ダッシュボードの右下のグラフは、新型コロナウイルス陽性および PUI を示し、最近と過去の傾向を説明するタイムラインが表示されます:

![患者の詳細](media/portal-admin-powerbi-patients.png)

#### <a name="map"></a>マップ

マップ内の郡にカーソルを合わせて、郡固有の新型コロナウイルス PUI、陽性、挿管番号を参照します:

![患者マップ](media/portal-admin-powerbi-map.png)

同様に、タイムライン チャートにカーソルを合わせると、日付間を移動するときにヒントに日付固有の番号を表示します。

### <a name="bed-capacity-details"></a>ベッドのキャパシティの詳細

ライセンスされた、重症、AIIR/AIIR 以外、急増、ICU 番号を使用したベッドの可用性など、ベッドに関連するインサイトを表示します。 下部の表形式で、郡ごとのベッド データおよび割合の詳細を表示することもできます。 マップは、数字が小さいほど明るい色で、または数字が増えるにつれて暗い色で、郡ごとに色分けされています。 右下のグラフは、傾向分析の日付に基づく占有率の違いを示しています。

![ベッドのキャパシティ](media/portal-admin-powerbi-bed-capacity.png)

#### <a name="map"></a>マップ

マップ領域にカーソルを合わせて郡をポイントすると、郡関連の情報を参照できます:

![ベッドのキャパシティ マップ](media/portal-admin-powerbi-map1.png)

同様に、タイムライン チャートにカーソルを合わせると、日付間を移動するときにヒントに日付固有の番号を表示します。

### <a name="equipment-details"></a>備品の詳細

人工呼吸器の可用性および**備品の詳細**ダッシュボードでの消費量など、郡ごとに備品の詳細を表示します:

![備品の詳細](media/portal-admin-powerbi-equipment.png)

左上で備品の可用性の合計および左下で詳細なテーブルを参照できます。 マップでは、郡固有の設備データの要件数が少ないものは薄い色および要件数が高いものは濃い色で示します。

右下のタイムライン グラフは、日付間の傾向分析の備品インサイトを示しています。

#### <a name="map"></a>マップ

マップ領域にカーソルを合わせて郡をポイントすると、郡関連の情報を参照できます:

![備品マップ](media/portal-admin-powerbi-equipment-map.png)

同様に、タイムライン チャートにカーソルを合わせると、日付間を移動するときにヒントに日付固有の番号を表示します。

### <a name="supply-details"></a>消耗品の詳細

人工呼吸器の可用性および**消耗品の詳細**ダッシュボードでの消費量など、郡ごとに消耗品の詳細を表示します:

![消耗品の詳細](media/portal-admin-powerbi-supply.png)

消耗品の詳細を左下の**医療機関**に基づいて、右側のマップおよび下部のグラフ形式の消耗品の内訳で参照できます。

#### <a name="map"></a>マップ

マップ領域にカーソルを合わせて郡をポイントすると、郡関連の情報を参照できます:

![消耗品マップ](media/portal-admin-powerbi-supply-map.png)

同様に、タイムライン チャートにカーソルを合わせると、日付間を移動するときにヒントに日付固有の番号を表示します。

### <a name="data-health-scorecard"></a>データ正常性スコアカード

**データ正常性スコアカード** ダッシュボードを使用して、選択済み設備のデータの衛生状態を表示します。 使用可能な設備リストから設備を選択し、ダッシュボードを表示するには**続行するにはこちらをクリック**を選択します:

![設備を選択](media/dashboard-data-health-facility-select.png)

ダッシュボードには、すべてのコンポーネントのデータ更新のランク付け、データ更新の割合、および日々の状態が表示されます。 日付ごとのグラフは、選択済み設備のデータ完了を、特定のデータ セットのすべての設備の平均と比較して示しています。 設備ごとデータ完全性情報は、過去 1 週間のすべての設備をリストした表形式でも使用可能です:

![データ正常性スコアカード](media/data-health-scorecard-dashboard.png)

## <a name="general-portal-options"></a>全般 ポータル オプション

[!include[cc-general-options](includes/cc-general-options.md)]

## <a name="issues-and-feedback"></a>問題とフィードバック

- 地域政府機関の緊急応答およびモニタリング ソリューションに関する問題を報告するには、<https://aka.ms/rer-issues> を参照してください。

- 地域政府機関の緊急応答およびモニタリング ソリューションに関するフィードバックについては、<https://aka.ms/rer-feedback> を参照してください。
