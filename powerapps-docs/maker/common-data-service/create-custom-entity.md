---
title: PowerApps でコンポーネントのあるカスタム エンティティを作成するチュートリアル | Microsoft Docs
description: PowerApps アプリで使うエンティティを作成して構成する手順についてのチュートリアルです。
services: ''
suite: powerapps
documentationcenter: na
author: Mattp123
manager: bycho
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 3fd8b262849fb1f6bf2a7ff70d9d9af8b082efac
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>チュートリアル: PowerApps でコンポーネントがあるカスタム エンティティを作成する

[!INCLUDE [powerapps](../../includes/powerapps.md)] では、組織の業界、用語、固有のビジネス プロセスに合わせてアプリを調整します。 [!INCLUDE [powerapps](../../includes/powerapps.md)] アプリの開発には、標準的な既製のエンティティまたはカスタム エンティティの追加が含まれます。 エンティティでは、追跡したい情報をレコードの形式で定義し、レコードには通常、会社名、場所、製品、電子メール、電話などのプロパティが含まれます。 

このチュートリアルでは、エンティティを作成してから、フィールド、リレーションシップ、ビュー、フォームなどの主要なコンポーネントを追加またはカスタマイズします。 次の方法を説明します。

- カスタム エンティティの作成
- カスタム フィールドをエンティティに追加する
- エンティティのリレーションシップを追加する
- ビューをカスタマイズする 
- フォームをカスタマイズする

> [!IMPORTANT]
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

このチュートリアルで使う Contoso という会社は、犬や猫を対象とするペット美容室ビジネスを展開しています。 Contoso は、従業員がさまざまなデバイスで使用できる、クライアントとペットを追跡するためのアプリを必要としています。

## <a name="prerequisites"></a>前提条件

[PowerApps](https://powerapps.microsoft.com/) にサインインします。 まだ [!INCLUDE [powerapps](../../includes/powerapps.md)] アカウントを持っていない場合は、[powerapps.com](https://web.powerapps.com) で.**[GET STARTED FREE]** リンクを選びます。

## <a name="create-a-custom-entity"></a>カスタム エンティティの作成

1. 左側のナビゲーション ウィンドウの **[Common Data Service]** で **[エンティティ]** を選んでから、**[新しいエンティティ]** を選びます。
    ![新しいエンティティ](media/create-custom-entity/create-new-entity.png)
2. 右側のウィンドウで、次の値を入力してから、**[次へ]** を選びます。
  - **[表示名]**: *Pet* 
  - **[説明]**: *Custom entity to track pet services*
3. **[エンティティの保存]** を選びます。

## <a name="add-and-customize-fields"></a>フィールドを追加してカスタマイズする

1. **[フィールド]** タブで、**[プライマリ名]** フィールドを選びます。
2. 右側のウィンドウで、**[プライマリ名]** フィールドを次のように変更します。 
  - **[表示名]** を **[プライマリ名]** から「*Pet Name*」に変更します
  - **[検索可能]** をオンにします

    ![プライマリ フィールドを変更する](media/create-custom-entity/primary-field.png)
3. **[完了]** を選択します。
4. エンティティ デザイナーのツール バーで、**[追加]** フィールドを選びます。 **[フィールド プロパティ]** ウィンドウで、次の値とオプションを入力するか選びます。
  - **[表示名]**:  *Species*
  - **[データ型]**:  *オプション セット*
  - **[オプション セット]**:  *新規*
5. オプション セットを作成します

  a. **[新しいアイテムの追加]** を選びます。 
  
  b. **[新しいオプション]** を「*Dog*」に置き換えます。 
   
  c. **[新しいアイテムの追加]** を選びます。 
    
  d.  **[新しいオプション]** を「*Cat*」に置き換えます。 
    
  e. **[保存]** を選択します。 

  ![新しいオプション セット](media/create-custom-entity/optionset-add-items.png)

6. **[検索可能]** をオンにして、**[完了]** を選びます。

7. エンティティ デザイナーのツール バーで、**[追加]** フィールドを選びます。 **[フィールド プロパティ]** ウィンドウで、次の値を入力するか選んでから、**[完了]** を選びます。
  - **[表示名]**:  *Breed*
  - **[データ型]**:  *[Text (テキスト)]*
  - **[検索可能]**:  *オン*

8. エンティティ デザイナーのツール バーで、**[追加]** フィールドを選びます。 

9. **[フィールド プロパティ]** ウィンドウで、次の値を入力するか選んでから、**[完了]** を選びます。 
  - **[表示名]**:  *Appointment date*
  - **[データ型]**:  *日時*

10. **[エンティティの保存]** を選びます。

## <a name="add-a-relationship"></a>リレーションシップを追加する

1. **[リレーションシップ]** タブを選び、エンティティ デザイナーのツール バーで、**[リレーションシップの追加]** を選びます。 
2. 右ウィンドウの **[関連エンティティ]** の一覧で "**Account**" を選んで、**[完了]** を選びます。
3. **[エンティティの保存]** を選びます。

リレーションシップを追加すると、データ型が **[検索]** のフィールドが **[フィールド]** タブのフィールド一覧に自動的に追加されることに注意してください。![アカウント検索フィールド](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>ビューをカスタマイズする

1. **[ビュー]** タブを選び、"**Active Pets**" ビューを選びます。
2. ビュー デザイナーで **[列の追加]** を選び、次の列を選んで、**[OK]** を選びます。
  - アカウント
  - Appointment date 
  - Breed 
  - Species
3. **[作成日]** 列を選び、**[削除]** を選んでから **[OK]** 選び、列の削除を確認します。
4. 列を並べ替えるには、移動する列を選び、矢印ボタン <- と -> を使って次のように表示されるようにします。
    ![Active pets ビュー](media/create-custom-entity/active-pets-view.png)
5. ビュー デザイナーのツールバーで、**[保存して閉じる]** を選びます。  
6. **[エンティティの保存]** を選びます。

## <a name="model-driven-apps-only-customize-the-main-form"></a>モデル駆動型アプリのみ: メイン フォームをカスタマイズする

キャンバス アプリで Pet エンティティを使いたいだけの場合は、この手順をスキップします。 

1. [!INCLUDE [powerapps](../../includes/powerapps.md)] の左ナビゲーション ウィンドウで、**[モデル駆動型]** を選びます。
2. 左ナビゲーション ウィンドウで、**[詳細]** を選びます。
3. ソリューション ウィンドウの左ナビゲーションで、**[エンティティ]** を選び、"**Pet**" を展開して、**[フォーム]** を選びます。
4. **[メイン]** フォームの種類の **[情報]** を選び、フォーム エディターを開きます。
    ![メイン フォームを編集する](media/create-custom-entity/main-form-edit.png)
5. フォーム エディターで、フォームの表示が次のようになるまで、[フィールド エクスプローラー] ウィンドウにある **Species**、**Breed**、**Appointment date**、**Account** の各フィールドをドラッグして、フォーム キャンバスの [全般] セクションにドロップします。
    ![メイン フォームのフィールドを選ぶ](media/create-custom-entity/main-form-edit2.png) 
6. **[保存して閉じる]** を選びます。
7. ソリューション ウィンドウで、**[すべてのカスタマイズの​​公開]** を選びます。
    ![すべてのカスタマイズの​​公開](media/create-custom-entity/publish-all-customizations.png)

## <a name="add-the-custom-entity-to-an-app"></a>アプリにカスタム エンティティを追加する

これで、エンティティはキャンバス アプリまたはモデル駆動型アプリの構築に使用できるようになりました。 

## <a name="next-steps"></a>次の手順

このチュートリアルでは、役に立つアプリの作成に使用できるエンティティを作成する方法について学習しました。 キャンバス アプリを作成する方法については、「[アプリを最初から作成する](../canvas-apps/get-started-create-from-blank.md)」をご覧ください。