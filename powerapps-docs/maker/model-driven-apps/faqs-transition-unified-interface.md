---
title: 'よくある質問: 統一インターフェイス への切り替え | MicrosoftDocs'
description: 従来の Web クライアント から 統一インターフェイス に ユーザー を移行する プロセス に関する FAQ。
ms.custom: ''
ms.date: 02/26/2020
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
ms.openlocfilehash: 003bc58cc0c4db717a92d75d6157b7b53eb3629c
ms.sourcegitcommit: bb1a684d4ce2d342ad092a29ebca2bb502736e6e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087797"
---
# <a name="faqs-transition-to-unified-interface"></a>よくある質問: 統一インターフェイス への切り替え

このトピックでは、従来の Webクライアント から統一インターフェイス へと ユーザー を移行する移行オプションに関して、よく寄せられる質問への回答をご案内します。

### <a name="where-can-i-go-to-see-the-transition-dates-that-have-been-suggested-for-my-environments"></a>今使用している環境に対して推奨されている移行の目安はどこで確認できますか？ 

移行ポータルを使用して、環境の移行日を管理してください: <https://runone.powerappsportals.com> 。

### <a name="how-do-i-gain-access-to-the-portal"></a>ポータルにアクセスするにはどうすればよいですか?

次の手順を実行します。
1. <https://runone.powerappsportals.com> のページはこちらです。
2. 管理するテナントの管理者資格情報でサインインします。
3. **使用中の環境** を選択し、推奨日付が適用されているすべての環境を確認してください。

### <a name="i-see-my-environment-has-a-date-suggested-for-transition-can-i-change-this-date"></a>使用中の環境に移行の提案日付が表示されています。 この日付は変更できますか?

テナントに、 **グローバル管理**、 **Dynamics 365 サービス管理**、 **Power Platform 管理** の役割がある場合は変更可能です。 

環境に関連付けられている日付は、実行するにあたって承認が必要となる推奨日付です。 提示された日付が自社組織に適用可能なある場合は承認をしてください。  

日付を変更するために、環境の横にあるドロップダウン アイコンを選択し、レコードを表示します。 テナント管理者は、移行日を前後の日付に再スケジュールできるようになります。

スケジュールを前倒しして再設定するには、既存の日付をリスト内の希望するオプションに更新します。 適切な日付がない場合は、 [手動で切り替える](transition-web-app.md) こともできます。 
 
遅い日付に再スケジュールするには、 移行日の再スケジュール ボタンを選択します。 推奨される日付はドロップ ダウンで使用可能です。 承認後、この日付がポータルで更新されます。 環境の移行をする場合は、更新された日付を承認してください。 
 
日付が 2020年10月1日 より前の場合、日付の変更が確認と許可がされます。 確認されると、日付は、ポータル内で更新されます。 

> [!NOTE]
> 既に承認されたの移行が存在し、以降予定日が48時間以内の場合は、日付の変更はできません。 同じく、2020年10月1日以降の日付を要請することはできません。従来の Web クライアント が利用できなくなるためです。

### <a name="what-will-happen-if-i-dont-opt-in-and-approve-a-suggested-transition-date-for-my-environment"></a>使用中の環境に推奨された移行日を オプトイン して、承認しなかった場合はどうなりますか？

ポータルで推奨された日付を承認していない場合は、環境に変更が適用されません。 推奨された日付が過ぎてしまった場合は、別の将来日付を推奨するべく検討します。  
 
> [!NOTE]
> 2020年10月1日以降、すべての環境は同月に予定されている一連のリリースに従って、統一インターフェイスに更新されます。

### <a name="my-transition-date-is-within-48-hours-and-i-cant-change-the-date-within-the-portal-how-can-i-stop-the-transition-from-taking-place"></a>使用している環境の移行日が 48時間以内となっており、ポータル内で日付を変更できません。 移行の実行を止めるにはどうすればよいですか？

環境の切り替え日を変更できるのは、切り替えの48時間前までです。 この期間後にプロセスを停止するには、サポート案件を上げてください。 

> [!NOTE]
> 要求がポータルで日付がロックされた後 (48 時間以内) に行われた場合、切り替えを停止できるかどうか保証できません。

### <a name="i-have-environments-without-a-scheduled-date-can-i-update-these-to-include-a-date"></a>日付が設定されていない環境があります。 これらを更新して日付を含めることはできますか?

テナントで **グローバル管理者** 、 **Dynamics 365サービス管理者** 、 **Power Platform 管理者** の役割を持っている場合、当該環境を選択し、 移行日の再スケジュール ボタンをクリックして日付を選択してください。

確認する日付でポータルを更新します。 通知電子メールが切り替え日が近づくと、グローバル テナント管理者にも送信されます。 これは、このドキュメント内の標準アラーム手順に従います。

### <a name="is-there-a-recommended-checklist-i-should-run-through-before-transition"></a>切り替え前に確認するべき推奨チェックリストはありますか?

[コミュニティ サイト](https://community.dynamics.com/365/unified-interface/) で利用可能なサポート コンテンツを確認してください。 また、 [切り替えチェックリスト](https://aka.ms/UIChecklist) して効率的な計画を立てることもできます。 統一インターフェイスへの移行に満足していること確認するため慎重に検討してください。

### <a name="my-environment-has-been-transitioned-but-i-am-finding-blocking-issues-for-my-users-and-want-to-move-back-to-the-legacy-web-client-is-this-possible"></a>環境の移行が完了したが、ユーザーがブロックされる問題が発生しており、従来の Webクライアントに戻したい。 これは可能ですか?

はい、切り替え後最大10日間、レガシ Web クライアントに切り替えることができます。 最初の10日間は [手動で切り替え](https://docs.microsoft.com/power-platform/admin/enable-unified-interface-only) を行うか、[標準サポートリクエスト](https://admin.powerplatform.microsoft.com/support?referer=mbssupport) を報告し、手動切り替えが無効になるため、問題のタイプを "レガシ Web クライアント から 統合インターフェイス への移行" に設定できます。 

> [!NOTE]
> 10日は、2020 年 10 月 1 日より前にする必要があります。その日以降、レガシー Web クライアントは利用できなくなります。

### <a name="i-want-to-transition-after-october-1-2020-is-that-possible"></a>2020 年 10 月 1 日以降に切り替えたいです。 これは可能か。

従来の Webクライアントは、2020年10月似行われる一連のリリース以降はご利用頂けません。 この期間よりも後の日付に移行日を延期することはできません。

ブロック アイテムが発生した場合は、標準サポート プロセスを使用してできるだけ早くログを記録してください。

### <a name="what-is-the-standard-reminder-procedure-throughout-this-process"></a>このプロセス全体で標準アラーム手順とは何ですか?

連絡は提示された期限の少なくとも30日前に波状的に行われますが、ポータル (<https://runone.powerappsportals.com>) にサインインすることでいつでもこの状態を確認することができます。 Microsoftは、次の通信を送信します:

-   それぞれの環境で最初に表示されるメッセージで移行の日付を推奨します。
-   日付を承認した場合は、日付がポータル内で固定される2日前に通知メッセージが表示されます。 
-   最後の通知は、移行の2日前に送信されます。 これにより、移行日が固定されていることが明示され、移行が続行されます。
-   移行の完了後は、終了メッセージが表示され、移行の成功 (あるいは問題が発生) したことを確認することができます

メッセージは、次のチャネルを使用して表示できます:
-   Microsoft 365 テナント内のメッセージ センター。 これは通常、グローバル管理者、サービス管理者、サービス メッセージ閲覧者などのロールに対して表示されるようになります。
-   電子メール広告 。  電子メールは、対象の特定の環境のシステム管理者ロール、あるいは環境管理ポータルの "通知" タブに追加されたメール アドレスにのみ送信されます。

> [!NOTE]
> ユーザー アカウントにシステム管理者ロールを持っている各環境に対して電子メールが届きます。

### <a name="i-have-requested-a-date-to-postpone-but-still-receiving-e-mails-and-message-center-posts-that-my-environment-is-set-to-transition-should-i-be-concerned"></a>日付を延期するようリクエストしましたが、まだ自分の環境が切り替えに設定されている電子メールとメッセージ センターの投稿を受信しています。 懸念する必要がありますか?

最初のレコメンデーションは、すべての環境の信頼できる単一の情報ソースであるため切り替えポータル (<https://runone.powerappsportals.com/>) をチェックすることです。 日付が更新された場合、通信一覧を更新する前に、通信システムがメッセージを送信した可能性があります。 

ポータルの日付が新しい日付に更新されていない場合は、標準的な手順に従ってサポート要求を上げてください。

管理者が承認した日付でのみ移行がされます。 

### <a name="if-i-already-have-an-environment-transitioned-to-unified-interface-will-i-still-be-able-to-switch-back-to-the-legacy-web-client-manually"></a>既に統一インターフェイスに移行した環境の場合、レガシー Web クライアントにまだ手動で切替えられますか?

環境が少なくとも 10 日間移行されている場合、レガシー Web クライアントへの手動切り替えを無効にします。 

これが無効になっており、元に戻す必要がある場合は、[標準サポートリクエスト](https://admin.powerplatform.microsoft.com/support?referer=mbssupport) を発行し、問題のタイプを "レガシ Web クライアント から 統合インターフェイス への移行" に設定します。

### <a name="is-there-a-specific-day-and-time-when-approved-transitions-will-take-place"></a>承認した移行処理を実行する具体的な日時は決まっていますか？ 

この切り替えの際にダウンタイムを予測していません。 ただし、移行を行うのは金曜日のみであり、標準ポリシーと連絡事項で説明されているのと同じメンテナンス スケジュールに従っています。 詳細: [メンテナンス タイムライン ](https://docs.microsoft.com/power-platform/admin/policies-communications#maintenance-timeline)

### <a name="are-environments-from-all-data-centers-included-within-this-transition-service"></a>この移行サービスには、全データセンターの環境が含まれていますか?

現時点では、Government Community Cloud（GCC）などの特定の データセンター の環境は ポータル には含まれません。 2020年6月までには、これら環境の推奨される移行日を提供します。 統一インターフェイスへの移行を希望するお客様は、2020 年 10 月 1 日より前であればいつでも [手動で切り替える](/power-platform/admin/enable-unified-interface-only#how-to-enable-unified-interface-only-mode) ことができます。


