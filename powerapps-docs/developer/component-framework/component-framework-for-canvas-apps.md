---
title: キャンバス アプリ の コード コンポーネント| Microsoft Docs
description: キャンバス アプリのコード コンポーネントを作成する
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 11/26/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d100dc3-bd82-4b45-964c-d90eaebc0735
ms.openlocfilehash: b7d93d18ee9e176d936912235f71920f3cdeff48
ms.sourcegitcommit: 629e47c769172e312ae07cb29e66fba8b4f03efc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "3109043"
---
# <a name="code-components-for-canvas-apps"></a>キャンバス アプリのコード コンポーネント

Power Apps Component Framework を使用すると、アプリ作成者はアプリ内やアプリ全体で使用するコード コンポーネントを作成できます。 詳細: [Power Apps Component Framework の概要](overview.md) 

Power Apps  component framework を使うと、アプリの作成者は Power Apps CLI ツールを使ってコード コンポーネントを作成、デバッグ、インポートを行い、キャンバス アプリに追加することができます。 このパブリック プレビューでは、特定の API のみに対応しています。 各 API がキャンバス アプリに対応しているかどうかを確認することを推奨します。 

> [!WARNING]
> コード コンポーネントには Microsoft が生成していない可能性があるコードが含まれており、セキュリティ トークンやデータにアクセスする可能性があります。 コード コンポーネントをアプリに追加するときは、コード コンポーネント ソリューションが信頼できるソースのものであることを確認してください。

## <a name="prerequisites"></a>前提条件

1. Power Apps ライセンスの更新が必要です。 詳しくは：[Power Apps component framework のライセンス](overview.md#licensing)を参照してください
2. 環境で Power Apps コンポーネント機能を有効にするには、システム管理者特権が必要です。

## <a name="enable-power-apps-component-framework-feature"></a>Power Apps Component Framework 機能を有効にする

アプリにコード コンポーネントを追加するには、使用するそれぞれの環境で Power Apps Component Framework 機能を有効にする必要があります。 環境がアプリ内でコード コンポーネントを使用するようにする方法:

1. [Power Apps](https://powerapps.microsoft.com/) にサインインします。

2. **設定** アイコンを選択し、次に**管理センター**を選択します。
    
    ![設定と管理センター](media/select-admin-center-from-settings.png "設定と管理センター") 

3. 左ウィンドウのタブで**環境**を選択し、この機能を有効にする環境を選択します。 省略記号（**...**）を選択し、次に**設定**を選択します。

4. **製品** タブで **機能** を選択します。

   ![Power Apps Component Framework を有効にする](media/enable-pcf-feature.png "Power Apps Component Framework を有効にする")

5. 利用可能な機能のリストにて、 **Power Apps component framework の キャンバス アプリ** 配下のスイッチを **On** に設定し、 **保存**をクリックします。

6. 次に、コード コンポーネントを追加する アプリ を開き、 **ファイル** > **設定** へと移動して、 **高度な設定**を選択します。

   ![Power Apps Component Framework でコンポーネントを有効にする](media/enable-components-for-pcf.png "Power Apps Component Framework のコンポーネントを有効にする")
   
7. **実験機能**セクションで、**コンポーネント** スイッチを**オン**にします。

## <a name="implementing-code-components"></a>コード コンポーネントの実装

環境で Power Apps Component Framework 機能を有効にしたら、コード コンポーネントのロジックの実装を開始できます。

 [はじめてのコード コンポーネント作成](implementing-controls-using-typescript.md) トピックでは、コード コンポーネントを作成するにあたっての段階的なプロセスを示しています。

## <a name="add-components-to-a-canvas-app"></a>キャンバス アプリにコンポーネントを追加する

キャンバス アプリにコード コンポーネントを追加する方法:

1. Power Apps Studio に移動します。
2. キャンバスの新しいアプリケーションを作成するか、またはのコード コンポーネントを追加する既存のアプリケーションを編集します。

   > [!IMPORTANT]
   > 次の手順に進む前に、ソリューションの zip ファイルがすでに Common Data Service に[インポートされている](https://docs.microsoft.com/powerapps/maker/common-data-service/import-update-export-solutions) ことを確認します。

3. **挿入** > **カスタム** > **コンポーネントのインポート**へと移動します。 
 
    ![コンポーネントの挿入](media/insert-components-import.png "コンポーネントの挿入")

4. **コード** タブを選択し、リストからコンポーネントを追加し、 **インポート** を選択します。 

    ![サンプル コンポーネントのインポート](media/import-component-add-sample-component.png "サンプル コンポーネントのインポート")

5. 左側のウィンドウの **+** アイコン を クリックし、コード コンポーネント タブを展開して サンプル コンポーネント を追加します。

   ![サンプル コンポーネントの追加](media/add-sample-component-from-list.png "サンプル コンポーネントの追加")

## <a name="delete-a-code-component"></a>コード コンポーネントの削除 

キャンバス アプリからコード コンポーネントを削除するには、削除するコード コンポーネントを選択してから、メニューの**削除**ボタンを選択します。 コード コンポーネント が アプリ から削除されると、すべてのコード コンポーネント の要素が アプリ と アプリのパッケージから削除されます。

## <a name="update-existing-code-components"></a>既存のコード コンポーネントの更新

コード コンポーネントを更新し、実行時の変更を確認したい場合は、マニフェスト ファイルの `version` 属性を変更する必要があります。 変更を加える際は、常に コンポーネント の バージョン を更新することを推奨します。

> [!NOTE]
> 既存のコード コンポーネントは、Power Apps Studio でアプリが閉じられたか再度開かれたときにのみ更新されます。 アプリを再度開くと、コード コンポーネントを更新するように求められます。 コード コンポーネントを削除したり、コード コンポーネントをアプリに追加し直すだけでは、コンポーネントは更新されません。

## <a name="see-also"></a>関連項目

[Power Apps Component Framework の概要](overview.md)<br/>
[初めてコード コンポーネントを作成する](implementing-controls-using-typescript.md)
