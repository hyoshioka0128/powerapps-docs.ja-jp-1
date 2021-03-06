---
title: テンプレートからキャンバス アプリを作成する | Microsoft Docs
description: Power Apps テンプレートを基にして自動的にキャンバス アプリを作成する手順について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/29/2020
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d64b1ef3f6d885093fc9f89ecf31b785c07ea6bd
ms.sourcegitcommit: 303d5aed44f2bbb406cabeb6b9c8474d738d9114
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2020
ms.locfileid: "76918725"
---
# <a name="create-a-canvas-app-from-a-template-in-power-apps"></a>Power Apps でテンプレートからキャンバス アプリを作成する

予算を追跡、休暇のスケジュール設定など、特定のシナリオ用のテンプレートに基づいて自動的にキャンバス アプリを作成し、そのアプリを実行して既定の動作を理解します。

テンプレートからアプリを作成するには、テンプレートのサンプル データを格納するクラウド ストレージ アカウント (DropBox、OneDrive、Google Drive など) が必要です。

Power Apps のライセンスを持っていない場合は、[無料でサインアップ](../signup-for-powerapps.md)できます。

## <a name="create-an-app"></a>アプリを作成する

1. [Power Apps](https://make.powerapps.com) にサインインします。

1. 左側のナビゲーションで **[アプリ]** を選択します。 **[新しいアプリ]** のドロップダウン メニューを選択し、 **[キャンバス]** を選択します。

    ![新しいキャンバス アプリ](./media/get-started-test-drive/new-canvas-app.png)

    これにより、新しいタブに [[Power Apps Studio]](https://docs.microsoft.com/powerapps/powerapps-overview#power-apps-for-app-makerscreators) が表示されます。

1. **アプリ テンプレート** タイルで、 **[携帯電話レイアウト]** または **[タブレット レイアウト]** を選択します。

    ![テンプレート タイルからアプリを作成する](./media/get-started-test-drive/template-tile.png)

1. テンプレートの一覧で、いずれかのテンプレートを選択し、右下隅にある **[Use (使用)]** を選択します。

    ![Power Apps テンプレートを開く](./media/get-started-test-drive/open-template.png)

    新しいタブで Power Apps Studio が開き、アプリが作成されます。

    > [!NOTE]
    > **[使用]** ボタンが無効になっている場合は、アプリのデータ ソースが選択されていることを確認します。 下部にある **[選択]** を選択すると、データソースを選択できます。
    >
    > ![データ ソースの選択](./media/get-started-test-drive/choose-data-source.png)

## <a name="run-the-app"></a>アプリの実行
テンプレートから作成されたアプリが既定のワークスペースに表示されます。カスタマイズに伴うほとんどの作業は、このワークスペースで行うことになります。 アプリに変更を加える前に、**プレビュー** モードでアプリの動作を詳しく見てみましょう。

1. F5 キーを押して (または、右上隅にある右矢印をクリックまたはタップして)、**プレビュー** モードでアプリを開きます。

    ![プレビュー モードを開始するためのボタン](./media/get-started-test-drive/open-preview.png)

    アプリには、アプリの機能を紹介するためのサンプル データがあらかじめ追加されています。 たとえば、Cost Estimator アプリには、予定を作成するためのデータのほか、特定の大きさの部屋に特定の床材を設置する際にかかるコストを見積もるためのサンプル データが含まれています。

4. サンプル データを作成、更新、削除して、アプリの既定の動作を探索し、クラウド ストレージ アカウント内のデータに変更が反映されていることを確認します。

    たとえば、Cost Estimator アプリで人と会う予定を作成したり、コストの見積もりを作成したりします。

5. Esc キーを押して (または、右上隅の **X** アイコンをクリックして)、既定のワークスペースに戻ります。

## <a name="next-steps"></a>次の手順
1. Ctrl + S キーを押してアプリに名前を付けたら、 **[Save (保存)]** をクリックまたはタップしてクラウドにアプリを保存します。

1. 組織内の他のユーザーと[アプリを共有](share-app.md)します。

> [!IMPORTANT]
> アプリを共有する前に、その相手となるユーザーがデータを利用できる状態になっていることを確認してください。 たとえば、クラウド ストレージ アカウント内の [Excel ファイルやその他のファイルを共有](share-app-data.md)する必要があります。
