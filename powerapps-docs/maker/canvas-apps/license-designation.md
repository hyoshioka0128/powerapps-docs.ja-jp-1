---
title: アプリのライセンスの指定 |Microsoft Docs
description: 選択したアプリのライセンスの指定を確認する方法について説明します
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/24/2020
ms.author: alaug
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 495325949776b066ed30d629fb031730e4463179
ms.sourcegitcommit: be9b8c0f5c7c7e9992e93fa0d03e961b4ac7e3ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2020
ms.locfileid: "80374994"
---
# <a name="how-to-check-license-designation-for-an-app"></a>アプリのライセンスの指定を確認する方法

2019年10月以降、いくつかのコネクタが Standard から Premium に再分類されます。

[Power Apps のライセンス](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#office-365)に関する FAQ 、コネクタの再分類の概要を示します。 再分類の前にこれらのコネクタを使用しているアプリには、premium ライセンスを持たないユーザーがこれらのアプリにアクセスすることを許可する延長期間が付与されています。

次の表は、アプリにアクセスするためにエンドユーザーが必要とする指定とライセンスの概要を示しています。

| **重大度** | **定義**
|-|-|
| 標準 | 標準コネクタのみを使用するアプリ。 エンドユーザーには、このアプリにアクセスするために、Office 365 プランの Power Apps、アプリプランごと、またはユーザーごとのプランが必要です。
| 拡張 | 2019年10月1日にプレミアムに昇格したコネクタを使用することが許可されているアプリ。 エンドユーザーは、アプリプランまたはユーザープランごとに、Office 365 プラン用の Power Apps を所有している必要があります。 [Power Apps のライセンス](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq#office-365)に関する FAQ 、2019年10月1日に premium に昇格されたコネクタの概要を示します。
| プレミアム | 少なくとも1つの premium コネクタ、カスタムコネクタ、またはオンプレミスゲートウェイを使用するアプリ。 エンドユーザーがアクセスするには、アプリごとのプランまたはユーザーごとのプランが必要です。

## <a name="check-app-license-designation-from-app-settings"></a>アプリの設定からアプリのライセンスの指定を確認する

1. [Power Apps](https://make.powerapps.com) にサインインします。

1. 左側から **[アプリ]** を選択します。

1. アプリの一覧からアプリを選択します。 **[設定]** オプションを使用して、上部またはの [その**他のコマンド**( **...** )] をクリックし、ドロップダウンメニューから**設定**を使用できます。

    ![設定オプション](media/license-designation/app-settings.png)

1. **[設定]** を選択して、ライセンスの指定情報を表示します。

    ![設定からのライセンスの指定](media/license-designation/settings-license-designation.png)

## <a name="check-app-license-designation-from-app-details"></a>アプリの詳細からアプリのライセンスの指定を確認する

1. [Power Apps](https://make.powerapps.com) にサインインします。

1. 左側から **[アプリ]** を選択します。

1. アプリの一覧からアプリを選択します。 **[詳細]** オプションを使用して、上部またはから、その**他のコマンド**( **...** ) を使用してから、ドロップダウンメニューから**詳細**を確認することができます。

    ![アプリの詳細](media/license-designation/app-details.png)

1. **詳細**の選択:

    ![アプリの指定の詳細](media/license-designation/app-details-page.png)

## <a name="pass-assignment"></a>パスの割り当て

パスの割り当ての詳細については、[アプリごとの Power Apps のプラン](https://docs.microsoft.com/power-platform/admin/about-powerapps-perapp#step-three-set-up-apps-to-use-per-app-plans)を参照してください。

## <a name="next-steps"></a>次のステップ:

- [Power Apps のライセンスに関する FAQ](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq)

### <a name="see-also"></a>参照

- [アプリを編集する](edit-app.md)
- [アプリを削除する](delete-app.md)
