---
title: キャンバス アプリを保存して発行する | Microsoft Docs
description: アプリ メーカー向けのキャンバス アプリを保存および発行するための手順
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 09/14/2017
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c8610f726c0bd65cec5681cd817d5c93ec3d3c1d
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74732719"
---
# <a name="save-and-publish-a-canvas-app-in-power-apps"></a>Power Apps でキャンバスアプリを保存して発行する
キャンバス アプリへの変更を保存するたびに、自分とアプリを編集するアクセス許可を持つ他のユーザーのみに、自動的にアプリが発行されます。 変更が完了したら、アプリを共有しているすべてのユーザーが利用できるように、明示的に発行する必要があります。

アプリを共有する方法については、「[PowerApps でのアプリの共有](share-app.md)」を参照してください。

## <a name="save-changes-to-an-app"></a>アプリへの変更を保存する
Power Apps Studio で、 **[ファイル]** メニュー (左端) の **[保存]** をクリックまたはタップして、次のいずれかの手順を実行します。

* アプリを以前に保存していない場合は、アプリの名前を指定して、 **[保存]** をクリックまたはタップします。

    ![新しいアプリを保存する](./media/save-publish-app/save-as.png)
* アプリを保存したことがある場合は、 **[保存]** をクリックまたはタップします。  

    ![更新したアプリを保存する](./media/save-publish-app/save-app.png)

Power Apps では、2分ごとにアプリを定期的に保存することもできます。 アプリを1回保存した場合は、ユーザーが [保存] 操作を押したりタップしたりしなくても、アプリのバージョンが定期的に保存されます。 作成者は **[ファイル]** メニューの **[アカウント]** タブで**自動保存**設定を有効または無効にできます。

![自動保存設定](./media/save-publish-app/autosave.png)

## <a name="publish-an-app"></a>アプリを公開します。
1. Power Apps Studio で、 **[ファイル]** メニュー (左端) の **[保存]** をクリックまたはタップし、 **[このバージョンの発行]** をクリックまたはタップします。

    ![アプリを発行する](./media/save-publish-app/publish-app.png)
2. **[発行]** ダイアログ ボックスで、 **[このバージョンの発行]** をタップまたはクリックして、アプリを共有しているすべてのユーザーにアプリを発行します。

   ![発行を確認する](./media/save-publish-app/publish-review.png)

   > [!NOTE]
   > キャンバスアプリを発行するたびに、アプリは最新バージョンの Power Apps で動作するようにアップグレードされます。つまり、最後に発行した後に追加された最新の機能とパフォーマンスのアップグレードの利点が得られます。 数か月間、更新プログラムを発行していない場合、再発行からすぐにパフォーマンス上の利点を確認できるようになることが多いです。

## <a name="identify-the-live-version"></a>ライブ バージョンを指定する
[powerapps.com](https://make.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) では、 **[ファイル]** メニュー (左端) の **[アプリ]** をクリックまたはタップし、アプリの詳細アイコンをクリックまたはタップして、 **[バージョン]** タブをクリックまたはタップします。

**ライブ** バージョンは、アプリを共有しているすべてのユーザーに発行されます。 アプリの最新バージョンは、編集のアクセス許可を持つユーザーのみが入手できます。

![ポータルから発行する](./media/save-publish-app/publish-portal.png)

最新バージョンを発行するには、 **[このバージョンの発行]** をクリックまたはタップして、 **[発行]** ダイアログ ボックスの **[このバージョンの発行]** をクリックまたはタップします。

## <a name="next-steps"></a>次の手順
* [ブラウザー](../../user/run-app-browser.md)または[電話](../../user/run-app-client.md)でアプリを検索して実行します。
* powerapps.com から[アプリの名前を変更します](set-name-tile.md)。
* アプリに複数のバージョンがある場合、[アプリを復元します](restore-an-app.md)。
