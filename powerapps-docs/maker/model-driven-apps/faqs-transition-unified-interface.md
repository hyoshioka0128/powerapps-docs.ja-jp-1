---
title: 'FAQ: 統一インターフェイスへの移行 | MicrosoftDocs'
description: レガシ Web クライアントから統一インターフェイスにユーザーを移行するための自動切り替えプロセスに関するFAQです。
ms.custom: ''
ms.date: 11/04/2019
ms.reviewer: kvivek
ms.service: powerapps
ms.topic: article
author: Mattp123
ms.author: haybass
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 373201de630b46adc80b25eed10686da9112bad6
ms.sourcegitcommit: c094590862142155cbafa91c6ee0ade975c82083
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2019
ms.locfileid: "2769445"
---
# <a name="faqs-unified-interface-transition"></a>FAQ: 統一インターフェイスへの移行

このトピックは、レガシ Web クライアントから統一インターフェイスにユーザーを移行するための切り替えプロセスについて、最も多く寄せられる質問に対する回答を提供します。

### <a name="where-can-i-go-to-see-the-transition-dates-that-have-been-assigned-to-my-environments"></a>自分の環境に割り当てられた切り替え日をどこで確認できますか? 

自動切り替えポータルを使用して、環境の切り替え日: <https://runone.powerappsportals.com> を管理します。

### <a name="how-do-i-gain-access-to-the-portal"></a>ポータルにアクセスするにはどうすればよいですか?

次の手順を実行します。
1. <https://runone.powerappsportals.com> のページはこちらです。
2. 管理するテナントの管理者資格情報でサインインします。
3. **自分の環境** を選択し、割り当てられた目標の期日があるすべて環境を確認します。

### <a name="i-see-my-environment-has-a-date-for-auto-transition-can-i-change-this-date"></a>自分の環境に自動切り替えの日付があることが確認できます。 この日付は変更できますか?

はい、テナントの **グローバル管理者** または **サービス管理** ロールがある場合は可能です。 日付を変更するために、環境の横にあるドロップダウン アイコンを選択し、レコードを表示します。 テナントの管理者ロールでは、より早いまたはより遅い切り替え日の例外要求を送信できます。

- より早い切り替え日については、既存の日付をリストの推奨されるオプションに更新します。 これは、承認を必要としません。 日付が適していない場合は、手動で切り替えることもできます。

- 移行日よりも後の場合は、例外要求を送信できます。 推奨される日付はドロップ ダウンで使用可能です。 承認されると、日付はそれに応じてポータル上で更新されます。

環境ごとに合計 2 つの例外をリクエストすることができます。 例外は、選択した推奨される日付と併せて、業務上の正当な理由に基づいて許可されます。 確認されると、日付は、ポータル内で更新されます。

> [!NOTE]
> スケジュールされた切り替えが48時間以内の場合、日付は変更できません。 同様に、レガシー Web クライアントが使用できないため、2020 年 10 月1日より後の日付を要求することはできません。

### <a name="my-auto-transition-date-is-within-48-hours-and-i-cant-change-the-date-within-the-portal-how-can-i-stop-transition-taking-place"></a>自分の自動切り替え日が48時間以内で、ポータル内で日付を変更できません。 切り替えの実行を停止するにはどうすればよいですか?

環境の切り替え日を変更できるのは、切り替えの48時間前までです。 この期間後にプロセスを停止するには、サポート案件を上げてください。 

> [!NOTE]
> 要求がポータルで日付がロックされた後 (48 時間以内) に行われた場合、切り替えを停止できるかどうか保証できません。

### <a name="i-have-environments-without-a-target-auto-transition-date-can-i-update-these-to-include-a-date"></a>対象の自動切り替え日付がない環境です。 これらを更新して日付を含めることはできますか?

はい、テナントの **グローバル管理者** または **サービス管理者** である場合は、環境を選択、例外要求を送信し、対象期日一覧を使用して、選択した時間帯で更新します。 

確認する日付でポータルを更新します。 通知電子メールが切り替え日が近づくと、グローバル テナント管理者にも送信されます。 これは、このドキュメント内の標準アラーム手順に従います。

### <a name="is-there-a-recommended-checklist-i-should-run-through-before-transition"></a>切り替え前に確認するべき推奨チェックリストはありますか?

[コミュニティ サイト](https://community.dynamics.com/365/unified-interface/) で利用可能なサポート コンテンツを確認してください。 また、 [切り替えチェックリスト](https://aka.ms/UIChecklist) して効率的な計画を立てることもできます。 統一インターフェイスへの移行に満足していること確認するため慎重に検討してください。

### <a name="my-environment-has-been-transitioned-but-i-am-finding-blocking-issues-for-my-users-and-wish-to-move-back-to-the-legacy-web-client-is-this-possible"></a>自分の環境は移行されましたが、ユーザーのブロック問題を発見したため、レガシー Web クライアントに戻したいと考えています。 これは可能ですか?

はい、切り替え後最大10日間、レガシ Web クライアントに切り替えることができます。 最初の 4 日間は [手動で切り替える](https://docs.microsoft.com/power-platform/admin/enable-unified-interface-only) ことができますが、それ以降は手動切り替えが無効となるため、通常のチャネルからサポート要求を上げます。 

> [!NOTE]
> 2020 年 10 月1日以降、レガシ Web クライアントは利用できなくなるので、10日間はその日付より前で指定する必要があります。

### <a name="i-want-to-transition-after-october-1-2020-is-that-possible"></a>2020 年 10 月 1 日以降に切り替えたいです。 これは可能か。

使用可能なレガシー Web クライアントは、2020 年 10月1日以降、利用できません。 その日付後に切り替えを延期することはできません。

ブロック アイテムが発生した場合は、標準サポート プロセスを使用してできるだけ早くログを記録してください。

### <a name="what-is-the-standard-reminder-procedure-throughout-this-process"></a>このプロセス全体で標準アラーム手順とは何ですか?

Microsoftは、次の通信を送信します:

-   切り替え日が割り当てられている各環境向け最初のメッセージ
-   切り替え日がポータル内でロックされる2日前アラーム メッセージ
-   切り替え日がロックされ続行を示す最終アラーム。
-   成功を確認するクローズ メッセージ (または、問題が発生した場合)

メッセージは、次のチャネルを使用して表示できます:
-   Microsoft 365 テナント内のメッセージ センター。 これは通常、グローバル管理者、サービス管理者、サービス メッセージ閲覧者などのロールに対して表示されるようになります。
-   電子メール広告 。  電子メールは、対象の特定の環境のシステム管理者ロール、あるいは環境管理ポータルの "通知" タブに追加されたメール アドレスにのみ送信されます。

> [!NOTE]
> ユーザー アカウントにシステム管理者ロールを持っている各環境に対して電子メールが届きます。

### <a name="i-have-requested-a-date-to-postpone-but-still-receiving-e-mails-and-message-center-posts-that-my-environment-is-set-to-transition-should-i-be-concerned"></a>日付を延期するようリクエストしましたが、まだ自分の環境が切り替えに設定されている電子メールとメッセージ センターの投稿を受信しています。 懸念する必要がありますか?

最初のレコメンデーションは、すべての環境の信頼できる単一の情報ソースであるため切り替えポータル (<https://runone.powerappsportals.com/>) をチェックすることです。 日付が更新された場合、通信一覧を更新する前に、通信システムがメッセージを送信した可能性があります。 

ポータルの日付が新しい日付に更新されていない場合は、標準的な手順に従ってサポート要求を上げてください。

### <a name="if-i-already-have-an-environment-transitioned-to-unified-interface-will-i-still-be-able-to-switch-back-to-the-legacy-web-client-manually"></a>既に統一インターフェイスに移行した環境の場合、レガシー Web クライアントにまだ手動で切替えられますか?

環境が少なくとも4日間移行された場合は、レガシー Web クライアントへの手動切り替えを無効にします。 

これが無効になっていて、元に戻す必要がある場合は、評価用の通常チャネルからサポート要求を上げます。

### <a name="is-there-a-specific-day-and-time-when-automatic-transitions-will-take-place"></a>自動切り替えが実施される特定の日時はありますか? 

この切り替えの際にダウンタイムを予測していません。 ただし、自動切り替えは金曜日にのみ実施され、標準のポリシーおよび通信で規定されている同じメンテナンス タイムラインに従います。 詳細: [メンテナンス タイムライン ](https://docs.microsoft.com/power-platform/admin/policies-communications#maintenance-timeline)




