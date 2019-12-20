---
title: キャンバス アプリの Power Apps Component Framework | Microsoft Docs
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
ms.openlocfilehash: 2008b9d57899697b60e47d24d3acb74a72c9700e
ms.sourcegitcommit: 64d816a759c5cc6343928d56a673812c3ea066c2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2019
ms.locfileid: "2895065"
---
# <a name="power-apps-component-framework-for-canvas-apps"></a>キャンバス アプリの Power Apps Component Framework

> [!IMPORTANT]
> この機能はまだ実験的であり既定で無効になっています。 詳細については [実験的機能とプレビュー機能](../../maker/canvas-apps/working-with-experimental.md) を参照してください。

Power Apps Component Framework を使用すると、アプリ作成者はアプリ内やアプリ全体で使用するコード コンポーネントを作成できます。 詳細: [Power Apps Component Framework の概要](overview.md) 

この実験的プレビューでは、Power Apps component framework により、アプリ作成者は Power Apps CLI ツールを使用してコード コンポーネントを作成、デバッグ、インポート、キャンバス アプリに追加できます。 この実験的プレビューでは特定の API のみがサポートされています。 キャンバス アプリがサポートされているかどうか、それぞれの API を確認することをお勧めします。 

> [!WARNING]
> コード コンポーネントには Microsoft が生成していない可能性があるコードが含まれており、セキュリティ トークンやデータにアクセスする可能性があります。 コード コンポーネントをアプリに追加するときは、コード コンポーネント ソリューションが信頼できるソースのものであることを確認してください。

## <a name="prerequisites"></a>前提条件

環境で Power Apps コンポーネント機能を有効にするには、システム管理者特権が必要です。

> [!IMPORTANT]
> 既定で、Power Apps Component Framework はモデル駆動型アプリに対して有効です。

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

環境で Power Apps Component Framework 機能を有効にしたら、コード コンポーネントのロジックの実装を開始できます。 [最初のコード コンポーネントを作成する](implementing-controls-using-typescript.md) のトピックは、カスタム ロジックとマニフェスト ファイルを実装するコード コンポーネントを作成します。さらに、デバッグ プロセスを実行し、ソリューションzipファイルを作成し、ソリューションを Common Data Service へとインポートします。

> [!NOTE]
> コード コンポーネントの実装は、モデル駆動型アプリでもキャンバス アプリ (試験的プレビュー) でも同じです。 唯一の違いはコード コンポーネントの追加です。 

## <a name="add-components-to-a-canvas-app"></a>キャンバス アプリにコンポーネントを追加する

> [!NOTE]
> モデル駆動型アプリのフィールドやエンティティにコード コンポーネントを追加する方法は [モデル駆動型アプリにコード コンポーネントを追加する](add-custom-controls-to-a-field-or-entity.md) を参照してください。

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

キャンバス アプリからコード コンポーネントを削除するには、削除するコード コンポーネントを選択してから、メニューの**削除**ボタンを選択します。 コード コンポーネントがアプリケーションから削除されると、すべてのコード コンポーネント要素がアプリおよびアプリ パッケージから削除されます。 

## <a name="update-existing-code-components"></a>既存のコード コンポーネントの更新

コード コンポーネントを更新すると、マニフェスト ファイルの*バージョン*属性が指定されるため、最新の変更がランタイムで反映されます。 キャンバス アプリの場合、既存のコード コンポーネントを更新するときに *バージョン* 属性を更新する必要はありません。 設計上、キャンバス アプリは最新のコード コンポーネントを取得して実行時に表示します。 同じコンポーネントは単一バージョンのみがキャンバス アプリに存在できます。

> [!NOTE]
> 既存のコード コンポーネントは、Power Apps Studio でアプリが閉じられたか再度開かれたときにのみ更新されます。 アプリを再度開くと、コード コンポーネントを更新するように求められます。 コード コンポーネントを削除したり、コード コンポーネントをアプリに追加し直すだけでは、コンポーネントは更新されません。

## <a name="see-also"></a>関連項目

[Power Apps Component Framework の概要](overview.md)<br/>
[初めてコード コンポーネントを作成する](implementing-controls-using-typescript.md)

