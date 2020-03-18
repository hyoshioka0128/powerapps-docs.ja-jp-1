---
title: Teams にアプリを埋め込む |Microsoft Docs
description: Microsoft Teams で Power Apps に作成したアプリを共有することができます。
author: matthewbolanos
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/16/2020
ms.author: mabolan
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 088e817c8ef829b340032af577193888079c832a
ms.sourcegitcommit: cf492063eca27fdf73459ff2f9134f2ca04ee766
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79436830"
---
# <a name="embed-an-app-in-teams"></a>Teams にアプリを埋め込む

Microsoft Teams に直接埋め込むことで、作成したアプリを共有できます。 完了すると、ユーザーは [ **+** ] を選択して、チーム内**のチームチャネル**または会話にアプリを追加できます。 アプリは、**チームのタブ**の下にタイルとして表示されます。

管理者はアプリをアップロードして、テナント内の**すべて**のチームに対して [**すべてのタブ] セクション**に表示されるようにすることができます。 「 [Microsoft Teams でのアプリの共有」を](https://docs.microsoft.com/power-platform/admin/embed-app-teams)参照してください。

> [!NOTE]
> Team カスタムアプリポリシーは、カスタムアプリのアップロードを許可するように設定する必要があります。 アプリをチームに埋め込むことができない場合は、管理者に連絡して、[カスタムアプリ設定](https://docs.microsoft.com/MicrosoftTeams/teams-custom-app-policies-and-settings#custom-app-policy-and-settings)がセットアップされているかどうかを確認してください。

## <a name="prerequisites"></a>前提条件

- 有効な[Power Apps ライセンス](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)が必要です。
- アプリをチームに埋め込むには、 [Power Apps を使用して作成され](data-platform-create-app.md)た既存のアプリが必要です。

## <a name="download-the-app"></a>アプリのダウンロード

1. [Make.powerapps.com](https://make.powerapps.com)にサインインし、メニューの **[アプリ]** を選択します。

    ![アプリの一覧を表示する](./media/embed-teams-app/file-apps2.png "アプリの一覧を表示する")

2. チームで共有するアプリの **[その他のアクション]** (...) を選択し、 **[チームに追加]** を選択します。

    ![アプリの詳細](./media/embed-teams-app/add-to-teams.png "チームに追加")

3. チームに追加 パネルで、**ダウンロード** を選択します。 その後、アプリで既に設定したアプリの説明とロゴを使用して、Teams マニフェストファイルが生成されます。

    ![アプリの詳細](./media/embed-teams-app/download-app.png "アプリのダウンロード")

## <a name="add-the-app-as-a-personal-app"></a>アプリを個人用アプリとして追加する

1. アプリを個人用アプリとして、またはチャネルまたはメッセージ交換にタブとして追加するには、左側のナビゲーションで **[アプリ]** を選択し、 **[カスタムアプリのアップロード]** を選択します。

    > [!NOTE]
    > カスタムアプリの**アップロード**は、チームの管理者がカスタムアプリ[ポリシー](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)を作成し、 **[カスタムアプリのアップロードを許可する]** がオンになっている場合にのみ表示されます。

    ![[アプリをタブとして追加]](./media/embed-teams-app/upload-custom-app.png "カスタムアプリをアップロードする")

2. **[追加]** を選択してアプリを個人用アプリとして追加するか、 **[チームに追加]** を選択して既存のチャネルまたはメッセージ交換内のタブとしてアプリを追加します。

## <a name="publish-the-app-to-the-teams-catalog"></a>Teams カタログにアプリを発行する

管理者の場合は、Microsoft Teams カタログに[アプリを発行](https://docs.microsoft.com/microsoftteams/tenant-apps-catalog-teams)することもできます。

## <a name="use-context-from-teams"></a>チームのコンテキストを使用する

チームで緊密に統合されたアプリをビルドするには、`Param()` 関数でチームのコンテキスト変数を使用します。 たとえば、次の数式を画面の**Fill**プロパティで使用して、チーム内のユーザーのテーマに基づいてアプリの背景を変更します。

```
Switch(
        Param("theme"),
        "dark",
        RGBA(
            32,
            31,
            31,
            1
        ),
        "contrast",
        RGBA(
            0,
            0,
            0,
            1
        ),
        RGBA(
            243,
            242,
            241,
            1
        )
    )
```

アプリをテストするには、アプリを発行し、チーム内で再生します。

チームからの次のコンテキスト変数がサポートされています。

- ロケール (locale)
- channelId
- channelType
- chatId
- groupId
- hostClientType
- subEntityId
- teamId
- teamType
- テーマ
- userTeamRole

> [!NOTE]
> この機能は、2020年3月に追加されました。 この前にアプリをチーム内に埋め込んだ場合、この機能を使用するには、アプリをチームに再度追加することが必要になる場合があります。

## <a name="improve-the-performance-of-your-app"></a>アプリのパフォーマンスを向上させる

必要に応じて、アプリをチーム内に事前に読み込んで、パフォーマンスを向上させることができます。

1. [Make.powerapps.com](https://make.powerapps.com)にサインインし、メニューの **[アプリ]** を選択します。

2. チームで共有するアプリの **[その他のアクション]** (...) を選択し、 **[設定]** を選択します。

3. [設定] パネルで、[**パフォーマンスの向上のためにアプリのプリロード** **] を [はい]** に切り替えます。 アプリは、チームに埋め込まれるたびに事前に読み込まれます。

    ![アプリの詳細](./media/embed-teams-app/preload-app.png "パフォーマンスを向上させるためにアプリをプリロードする")

4. 変更を有効にするには、アプリを削除してチームに追加し直してください。

> [!NOTE]
> これにより、埋め込みシナリオで認証が実行されているときに、ユーザーがアプリファイルをダウンロードできるようになります。 ただし、ユーザーは、認証が成功した後にのみアプリを実行できます。 これにより、認証されていないユーザーはアプリデータを使用できなくなります。

### <a name="see-also"></a>参照

[Microsoft Teams へようこそ](https://docs.microsoft.com/MicrosoftTeams/teams-overview)
