---
title: モデル駆動型サンプル アプリ
description: モデル駆動型アプリを入手、カスタマイズ、削除する方法を説明します。
documentationcenter: na
author: mr-dang-msft
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: brdang
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 65a650b979c4196eff8c103717a63aea5309ec57
ms.sourcegitcommit: 551af7e0273862b28d9b2387671a4eeaf719eb37
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "79084602"
---
# <a name="model-driven-sample-apps"></a>モデル駆動型サンプル アプリ

[powerapps.com](https://powerapps.com) でサンプル アプリを使用して、設計の可能性を探り、独自のアプリを開発する際に適用できる概念を見つけます。 各サンプル アプリでは、架空のデータを使用して、実際のシナリオを紹介します。 

詳しくは、各サンプル アプリについてのドキュメントを確認してください。 

![Fundraiser サンプル アプリ](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>サンプル アプリを入手する

モデル駆動型アプリを実行または編集するには、最初に Common Data Service データベースでアプリをプロビジョニングする必要があります。 まず、評価環境とデータベースを作成し、 **[Depoly sample apps and data]** を選択します。

> [!div class="mx-imgBorder"] 
> Create database](media/overview-model-driven-samples/create-database1.png) ![

> [!IMPORTANT]
> このオプションをオンにすると、使用可能なすべてのサンプル アプリがデータベースにインストールされます。 サンプル アプリは学習およびデモンストレーションを目的としたものであり、運用環境のデータベースにはインストールしないことをお勧めします。 

## <a name="customize-a-sample-app"></a>サンプル アプリをカスタマイズする

1. [Powerapps.com](https://powerapps.com)にサインインします。  

2. **[作成]** ページでサンプルアプリを選択し、 **[作成]** をクリックします。

> [!div class="mx-imgBorder"] 
> ![モデルサンプルアプリ](media/overview-model-driven-samples/model-driven-create-page-sample.png)

3. アプリ デザイナーが開き、アプリをカスタマイズするための複数のオプションが表示されます。

4. その他のカスタマイズオプションについては、ポータルの左側のナビゲーションで **[詳細設定]** をクリックしてください。

## <a name="remove-sample-apps-and-data"></a>サンプル アプリとデータを削除する 
- サンプルアプリを削除するには、対応する[マネージドソリューション](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution)を削除する必要があります。 
- ソリューションを削除すると、アプリのカスタム エンティティに固有のサンプル データも削除されます。
- サンプル アプリをカスタマイズした場合は、[依存関係](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components)が存在する可能性があり、ソリューションを削除する前にそれを削除する必要があります。

### <a name="steps"></a>手順
1. [Power Apps の管理ポータル](https://admin.powerapps.com)にログインします。

2. 環境を選びます。

3. **[Dynamics 365 管理センター]** をクリックします。 

    ![Dynamics 365 管理センター](media/overview-model-driven-samples/admin-center.png)

4. 一覧からデータベースを選び、 **[開く]** をクリックします。

    ![データベースを選ぶ](media/overview-model-driven-samples/select-database.png)

5. **[設定] > [ソリューション]** に移動します。

6. 削除するアプリのソリューションを選び、 **[削除]** をクリックします。

    ![ソリューションを削除する](media/overview-model-driven-samples/delete-solution.png)

*または、メーカー ポータルで **[詳細設定]** をクリックしてソリューションの一覧に移動し、.dynamics.com/ の後にある URL 内のすべてのものを削除します*

> [!IMPORTANT]
> 影響がわかっている場合を除き、他のシステム ソリューションを削除しないでください。

## <a name="install-or-uninstall-sample-data"></a>サンプル データをインストールまたはアンインストールする
1. 前述の手順 1 ～ 4 を行います。
2. **[設定] > [データ管理] > [サンプル データ]** に移動します。
3. サンプル データがインストールされている場合は、削除するオプションを使用できます。 インストールされていない場合は、インストールするオプションを使用できます。 

    ![サンプル データを削除する](media/overview-model-driven-samples/remove-sample-data.png)




