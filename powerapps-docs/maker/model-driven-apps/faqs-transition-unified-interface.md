---
title: 'よくある質問: 統一インターフェイス への切り替え | MicrosoftDocs'
description: 従来の Web クライアント から 統一インターフェイス に ユーザー を移行する プロセス に関する FAQ。
ms.custom: ''
ms.date: 03/04/2020
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
ms.openlocfilehash: 13bf17886ab44fb14f1b510615d538a48d8090fc
ms.sourcegitcommit: 310dd3dc68ffebe6a416450836ac0ba988b84fb4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "3162124"
---
# <a name="faqs-transition-to-unified-interface"></a>よくある質問: 統一インターフェイス への切り替え

このトピックは、統一インターフェイスと、レガシ Web クライアントから統一インターフェイスへの移行に関する最も一般的な質問への回答を提供します。

## <a name="faqs-unified-interface-and-legacy-web-client"></a>よくあるご質問: 統一インターフェイスとレガシ Web クライアント

### <a name="why-should-i-move-to-unified-interface"></a>統一インターフェイスに移動すべき理由

Microsoft の生産的な職場のビジョンには、統一インターフェイスに含まれる機能と改善を含む最新のインターフェイスが必要です。これにより、より一貫したユーザー体験、パフォーマンスの向上、ユーザー効率の向上が実現します。 詳細については [統一インターフェイスのプレイブック](https://docs.microsoft.com/powerapps/maker/model-driven-apps/unified-interface-playbook) を参照してください

### <a name="are-my-isvs-compatible"></a>自分の ISV は互換性がありますか?

ISV では、統一インターフェイスへの移行に関するアクションを実行するよう通知がされています。 統一インターフェイス互換性のタイムラインについては、ISV に直接お問い合わせください。

### <a name="what-is-the-retraining-effort"></a>再トレーニングの取り組みとは何ですか?

テクノロジーの観点から見ると、ビジネス ロジックとスキーマは変更されないことから、再トレーニングは最小限に抑える必要があります。 再トレーニングでは、ナビゲーション内の最新情報と全体的なルック アンド フィールに焦点を当てる必要があります。 新しい能力や機能を最適化するために設計を変更するという業務上の決定を下した場合は、さらにトレーニングが必要になることがあります。

### <a name="will-i-need-to-re-create-my-solution-customizations"></a>ソリューションのカスタマイズを再作成する必要がありますか?

いいえ、[Common Data Service 開発者ガイド](/powerapps/developer/common-data-service/overview) に従って、変更があれば最新の状態に保たれている場合はカスタマイズを再作成する必要はありません。 ただし、カスタマイズの変更につながる可能性のある最新の投資に取り組む新しい機会があるかもしれません。

### <a name="how-long-will-it-take-to-transitionwhat-is-the-work-effort"></a>切り替えにはどのくらいの時間がかかりますか?

ここでの作業負荷は、環境の複雑さによって異なります。 テストを開始するには、パイロット/ POC モデル駆動型アプリを使い始めることをお勧めします。 そこから、企業と協力して統一インターフェイスの完全な展開を計画できます。 始めるにあたってのその他のガイダンスや当社の [ホワイトペーパー](https://download.microsoft.com/download/A/F/3/AF3D45A7-4F38-41BE-8956-1DF7A4A5AFDB/approaching-unified-interface-transition.pdf) については、[統一インターフェイス プレイブック](https://docs.microsoft.com/powerapps/maker/model-driven-apps/unified-interface-playbook) と [計画チェックリスト](https://aka.ms/UIChecklist) をご覧ください。

### <a name="where-can-i-find-public-information-about-the-unified-interface-direction"></a>統一インターフェイスの方向に関する公開情報はどこにありますか?

統一インターフェイスの戦略的方向性は、次のようなイベントを通じてすでにパブリック ドメインにあります。
- [MBAS: BRK2073 Microsoft Power Apps: 1 つの UI を実行 – Power Appsでのキャンバス、モデル駆動型、および統一インターフェイスの未来](https://powerusers.microsoft.com/t5/MBAS-Gallery/Microsoft-PowerApps-Run-one-UI-the-future-of-canvas-model-driven/td-p/301580)
- [Dynamics 365 の BRK3031 実装のベストプラクティス: 最新の統一インターフェイスへの移行](https://powerusers.microsoft.com/t5/Microsoft-Business-Applications/Implementation-Best-Practices-for-Dynamics-365-Making-the-move/m-p/299928)


### <a name="as-an-on-premises-customer-looking-to-move-to-the-cloud-what-is-the-best-approach-to-adopt-unified-interface"></a>クラウドへの移行を検討しているオンプレミス顧客として、統一インターフェイスを採用する最善の方法は何ですか?

クラウドへの移行と同時に統一インターフェイスへの移行を計画することを強くお勧めします。 統一インターフェイス内でレガシ Web クライアントのテストを開始し、移行したら、ユーザー コミュニティにリリースする前に統一インターフェイスの互換性を確認します。 これにより、トレーニングの労力が軽減され、ユーザーは統一インターフェイスが提供する必要のある新機能の一部を採用できます。 詳細については、Microsoft の担当者にお問い合わせください。

### <a name="when-will-isvs-be-notified-of-the-need-to-move-to-unified-interface"></a>ISV は統一インターフェイスに移行する必要があることをいつ通知されますか?

ISV では、統一インターフェイスへの移行に関するアクションを実行するよう通知がされています。 統一インターフェイス互換性のタイムラインについては、ISV に直接お問い合わせください。

### <a name="how-are-language-translations-handled"></a>言語翻訳はどのように処理されますか?

言語翻訳のプロセスは、サイトマップを除き主に変更されていません。 サイトマップ エリア、グループ、およびサブエリアは、サイトマップ エディター内でローカライズされています。

### <a name="i-dont-have-budget-or-resources-to-do-a-project-is-the-deadline-a-fixed-date"></a>プロジェクトを行うための予算やリソースがありません。 締め切りは固定日ですか?

2020 年 12 月 1 日までにレガシ Web クライアントから離れることが決まっています。 組織の互換性を得るためにプロジェクトの複雑性を理解するために、できるだけ早くいくつかのテストを実施することをお勧めします。 ほとんどの場合、迅速に進めてユーザーが利益を実感し始めるために、大規模な再設計は必要ありません。 サポート ケースを作成して、移行を停止させる可能性があるフィードバックを提供するには Microsoft に連絡してください。

### <a name="were-working-on-transitioning-to-unified-interface-but-have-hit-some-issues-how-can-we-report-to-microsoft"></a>統一インターフェイスへの移行に取り組んでいますが、いくつかの問題が発生しているため、Microsoft にどのように報告したらいいですか?

弊社の [リソース](https://community.dynamics.com/365/unified-interface/) をレビューして、通常の手順に従いながら、ガイダンスによる支援を受け、サポートケースを記録します。 パートナー、Microsoft の担当者、または FastTrack チームに (該当する場合) 通知することもできます。

### <a name="when-should-i-start-moving-to-unified-interface"></a>統一インターフェイスにいつ移行すべきですか?

今すぐに移動でき、すでに運用環境で統一インターフェイスに移行しているお客様が多数います。 できるだけ早くテストを開始してください。 コミュニティサイト: <https://community.dynamics.com/365/unified-interface/> の役立つコンテンツにアクセスしましょう。 Standard サポートの手順を使用して、問題をログします。

### <a name="what-are-the-risks-associated-with-moving-to-unified-interface"></a>統一インターフェイスへの移行に伴うリスクは何ですか?

弊社の投資と戦略の方向性は統一インターフェイスにあるため、レガシ Web クライアントにとどまるにはリスクがあります。 移行の計画を始めている場合は、 [コミュニティ サイト](https://community.dynamics.com/365/unified-interface/) と [クイック スタート ガイド](https://docs.microsoft.com/powerapps/maker/model-driven-apps/transition-web-app-existing) をレビューします。 これは、ギャップ (あれば) を特定し、完全なデプロイを行う前にそれらを修正する計画を立てるのに役立ちます。

### <a name="i-have-a-new-feature-idea-for-unified-interface-where-do-i-log-it"></a>統一インターフェイスの新しい機能に関してアイデアがありますが、どこにログすればいいですか?

弊社のアイデア ポータル (<https://powerusers.microsoft.com/t5/PowerApps-Ideas/idb-p/PowerAppsIdeas>) へ移動して、**アイデアを提案する** を選択して、アイテムに '統一インターフェイス' カテゴリのラベルを付けます。

### <a name="is-there-any-supporting-content-to-help-me-plan-and-execute-my-transition-to-unified-interface"></a>統一インターフェイスへの移行の計画と実行に役立つサポートコンテンツはありますか?

はい、便利なコンテンツ、インタラクティブなフォーラム、ブログを提供する、新しいコミュニティ グループ (<https://community.dynamics.com/365/unified-interface/>) と統一インターフェイスに関する最新の更新や情報をすべて確認できるブログがあります。

### <a name="how-does-this-move-impact-on-premises-customer-and-what-will-happen-when-the-web-client-is-deprecated-do-web-client-forms-become-unsupported"></a>この動きはオンプレミスの顧客にどのように影響し、Web クライアントが非推奨になるとどうなりますか (Web クライアント フォームはサポートされなくなりますか)?

この発表は今のところオンラインのお客様にのみ有効です。 弊社ではオンプレミスの展開用のレガシ Web クライアントを引き続きサポートします。

### <a name="is-the-timeline-applicable-for-customers-using-government-community-cloud-gcc-and-other-data-centers-such-as-china"></a>タイムラインは、政府機関コミュニティ クラウド (GCC) やその他のデータセンター (中国など) を使用しているお客様に適用されますか？

標準リリース プログラムの一環として、これらのデータ センターへの統一インターフェイス アップデートをリリースする予定です。

### <a name="what-action-should-i-take-as-a-unified-service-desk-customer-who-is-still-on-the-web-client"></a>まだ Web クライアント上にいる Unified Service Desk の顧客として、弊社はどのようなアクションを取る必要がありますか？

まだ Web クライアントを使用している Unified Service Desk のお客様は、自分たちの構成を Web クライアントから統一インターフェイスに移行する必要があります。 これは、[Unified Service Desk](https://docs.microsoft.com/dynamics365/unified-service-desk/download-unified-service-desk?view=dynamics-usd-4.1) (クライアント コンポーネントとサーバー コンポーネントの両方) の最新バージョンにアップグレードする必要があります。 弊社では、この取り組みをサポートするための [移行アシスタント](https://docs.microsoft.com/dynamics365/unified-service-desk/admin/migration-steps-web-client-unified-interface-configuration?view=dynamics-usd-4.1) を持っています。

### <a name="are-there-any-other-deprecations-that-i-should-plan-for"></a>その他に計画ておくべき廃止予定はありますか？

弊社の [廃止予定通知ページ](https://docs.microsoft.com/power-platform/important-changes-coming) を確認して、計画が必要な他の領域があるかどうかを特定してください。

### <a name="where-can-i-find-further-information-on-the-transition-service"></a>移行サービスの詳細情報はどこで入手できますか?

移行へのスピードを加速するために、弊社では移行サービスを介して環境をレガシ Web クライアントから統一インターフェイスに切り替えるための推奨目標日を提供しています。 お客様はアクションをおこなう前にその日付を承認する必要があり、日付が近づくと、一連の通知メッセージを受け取ります。 日付は、2020 年 12 月 1 日の期限までであればビジネスに適さない場合は日付変更ができます。 詳細については、次のセクションを参照してください。


## <a name="faqs-transitioning-to-unified-interface"></a>よくある質問: 統一インターフェイスへの移行

### <a name="where-can-i-go-to-see-the-transition-dates-that-have-been-suggested-for-my-environments"></a>今使用している環境に対して推奨されている移行の目安はどこで確認できますか？ 

移行ポータルを使用して、環境の移行日を管理してください: <https://runone.powerappsportals.com> 。

### <a name="how-do-i-gain-access-to-the-portal"></a>ポータルにアクセスするにはどうすればよいですか?

次の手順を実行します。
1. <https://runone.powerappsportals.com> のページはこちらです。
2. 管理するテナントの管理者資格情報でサインインします。
3. **使用中の環境** を選択し、推奨日付が適用されているすべての環境を確認してください。

### <a name="i-see-my-environment-has-a-date-suggested-for-transition-can-i-change-this-date"></a>使用中の環境に移行の提案日付が表示されています。 この日付は変更できますか?

テナントに、 **グローバル管理**、 **Dynamics 365 サービス管理**、 **Power Platform 管理** の役割がある場合は変更可能です。 

環境に関連付けられている日付は、実行するにあたって承認が必要となる推奨日付です。 組織にとって有効な日付かどうかを承認します。  

日付を変更するために、環境の横にあるドロップダウン アイコンを選択し、レコードを表示します。 テナント管理者は、移行日を前後の日付に再スケジュールできるようになります。

スケジュールを前倒しして再設定するには、既存の日付をリスト内の希望するオプションに更新します。 適切な日付がない場合は、 [手動で切り替える](transition-web-app.md) こともできます。 
 
遅い日付に再スケジュールするには、 移行日の再スケジュール ボタンを選択します。 推奨日はドロップ ダウンで使用可能です。 承認後、この日付がポータルで更新されます。 環境を移行したい場合は、更新された日付を受け入れてください。 
 
日付の変更は、日付が 2020 年 12 月 1 日より前の場合、レビューされて許可されます。 確認されると、日付は、ポータル内で更新されます。 

> [!NOTE]
> 承認済みの移行が存在し、以降計画された日が 48 時間以内の場合は、日付の変更はできません。 同様に、レガシ Web クライアントが利用できなくなりますので、2020 年 12 月 1 日以降の日付をリクエストすることはできません。

### <a name="what-will-happen-if-i-dont-opt-in-and-approve-a-suggested-transition-date-for-my-environment"></a>使用中の環境に推奨された移行日を オプトイン して、承認しなかった場合はどうなりますか？

ポータルで推奨された日付を承認していない場合は、環境に変更が適用されません。 推奨された日付が過ぎてしまった場合は、別の将来日付を推奨するべく検討します。  
 
> [!NOTE]
> 2020 年 12 月 1 日以降、すべての環境が統一インターフェイスに更新されます。

### <a name="my-transition-date-is-within-48-hours-and-i-cant-change-the-date-within-the-portal-how-can-i-stop-the-transition-from-taking-place"></a>自分の移行日が 48時間以内で、ポータル内で日付を変更できません。 移行の実行を止めるにはどうすればよいですか？

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
> この 10 日は、2020 年 12 月 1 日より前にする必要があり、それ以降は、レガシ Web クライアントは利用できなくなります。

### <a name="i-want-to-transition-after-december-1-2020-is-that-possible"></a>2020 年 12 月 1 日以降に移行したいです。 これは可能か。

レガシ Web クライアントは、2020 年 12 月 1 日以降は利用できなくなります。 この期間よりも後の日付に移行日を延期することはできません。

ブロック アイテムが発生した場合は、標準サポート プロセスを使用してできるだけ早くログを記録してください。

### <a name="what-is-the-standard-reminder-procedure-throughout-this-process"></a>このプロセス全体で標準アラーム手順とは何ですか?

通信は、推奨される概算時間の少なくとも 30 日前に断続的になりますが、ポータル (<https://runone.powerappsportals.com>) にサインインしていつでもステータスを表示できます。 Microsoftは、次の通信を送信します:

-    それぞれの環境で最初に表示されるメッセージで移行の日付を推奨します。
-    日付を承認する場合、日付がポータル内でロックされる 2 日前にリマインダー メッセージが届きます。 
-    移行の 2 日前に最終通知が送信されます。 これにより、移行日が固定されていることが明示され、移行が続行されます。
-    移行の完了後は、終了メッセージが表示され、移行の成功 (あるいは問題が発生) したことを確認することができます

メッセージは、次のチャネルを使用して表示できます:
-    Microsoft 365 テナント内のメッセージ センター。 これは通常、グローバル管理者、サービス管理者、サービス メッセージ閲覧者などのロールに対して表示されるようになります。
-    電子メール広告 。  電子メールは、対象の特定の環境のシステム管理者ロール、あるいは環境管理ポータルの "通知" タブに追加されたメール アドレスにのみ送信されます。

> [!NOTE]
> ユーザー アカウントにシステム管理者ロールを持っている各環境に対して電子メールが届きます。

### <a name="i-have-requested-a-date-to-postpone-but-still-receiving-e-mails-and-message-center-posts-that-my-environment-is-set-to-transition-should-i-be-concerned"></a>日付を延期するようリクエストしましたが、まだ自分の環境が切り替えに設定されている電子メールとメッセージ センターの投稿を受信しています。 懸念する必要がありますか?

弊社としてのまず最初の推奨事項は、すべての環境にとって真の単一の情報源となる、移行ポータル (<https://runone.powerappsportals.com/>) を確認することです。 日付が更新された場合、通信一覧を更新する前に、通信システムがメッセージを送信した可能性があります。 

ポータルの日付が新しい日付に更新されていない場合は、Standard 手順に従ってサポート要求を上げてください。

管理者が承認した日付でのみ移行がされます。 

### <a name="if-i-already-have-an-environment-transitioned-to-unified-interface-will-i-still-be-able-to-switch-back-to-the-legacy-web-client-manually"></a>既に統一インターフェイスに移行した環境の場合、レガシー Web クライアントにまだ手動で切替えられますか?

環境が少なくとも 10 日間移行されている場合、レガシー Web クライアントへの手動切り替えを無効にします。 

これが無効になっており、元に戻す必要がある場合は、[標準サポートリクエスト](https://admin.powerplatform.microsoft.com/support?referer=mbssupport) を発行して、問題のタイプを "レガシ Web クライアント から 統合インターフェイス への移行" に設定します。

### <a name="is-there-a-specific-day-and-time-when-approved-transitions-will-take-place"></a>承認した移行処理を実行する具体的な日時は決まっていますか？

この切り替えの際にダウンタイムを予測していません。 ただし、移行を行うのは金曜日のみであり、標準ポリシーと連絡事項で説明されているのと同じメンテナンス スケジュールに従っています。 詳細: [メンテナンス タイムライン ](https://docs.microsoft.com/power-platform/admin/policies-communications#maintenance-timeline)

### <a name="are-environments-from-all-data-centers-included-within-this-transition-service"></a>この移行サービスには、全データセンターの環境が含まれていますか?

現時点では、Government Community Cloud（GCC）などの特定の データセンター の環境は ポータル には含まれません。 弊社は 2020 年 6 月までには、これら環境の推奨移行日を提供します。 統一インターフェイスへの移行を希望するお客様は、2020 年 12 月 1 日より前であればいつでも [手動で切り替える](/power-platform/admin/enable-unified-interface-only#how-to-enable-unified-interface-only-mode) ことができます。


