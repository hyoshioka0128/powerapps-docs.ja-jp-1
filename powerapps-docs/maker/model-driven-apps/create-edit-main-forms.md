---
title: Power Apps にてモデル駆動型アプリ メイン フォームを作成、編集する | MicrosoftDocs
description: メイン フォームの作成または編集の方法を学習する
ms.custom: ''
ms.date: 05/23/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: <needs new guid>
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1f2faa63b75a6842ee73f74ac1ebabd36b24d383
ms.sourcegitcommit: 551af7e0273862b28d9b2387671a4eeaf719eb37
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2020
ms.locfileid: "3116683"
---
# <a name="create-or-edit-a-model-driven-app-main-form-for-an-entity"></a>エンティティのモデル駆動型アプリのメイン フォームの作成または編集 

このトピックでは、エンティティのメイン フォームを作成または編集する方法について説明します。

エンティティのフォームを新規作成する場合、そのフォームの種類は [メイン] です。 新しいフォームを開いたとき、そのフォームは [情報] という名前のフォームと同じです。 フォームに関連するフィールド、セクション、タブ、ナビゲーション、およびプロパティを追加または編集し、そのフォームを保存できます。

各メイン フォームは、1 つ以上のタブで構成されます。 各タブは、1 つ以上のセクションを持つことができます。 各セクションは、1 つ以上のフィールドを含みます。 既存のものに基づいて新しいフォームを作成する場合は、フォームを複製できます。 

このタスクを実行するために、システム管理者またはシステム カスタマイザーのセキュリティ ロール、または同等のアクセス許可があることを確認してください。

## <a name="how-to-create-or-edit-a-main-form"></a>メイン フォームの作成または編集の方法
  
1.   [Power Apps](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) にサインインします。

2.  **データ**を展開して**エンティティ**を選択し、目的のエンティティを選択して**フォーム** タブを選択します。 

3. 新しいメイン フォームを作成するには、ツール バーで **フォームの追加** > **メイン フォーム** を選択します。  
    \-または- 既存のメイン フォームを編集するには、**メイン**の**タイプ**のフォームを選択します。
  
3.  必要に応じて、以下の方法のいずれかで、フォームの設計を変更します:
    - フォームへのタブの追加
    - セクションをフォームに追加する
    - フォームへのフィールドの追加
    - フォームでのサブグリッドの追加または編集
    - フォームのヘッダーおよびフッターの編集
    - タブ セクション フィールドの削除
    
4.  必要に応じて、フォームのパーツのプロパティを編集します。
    - フォーム プロパティの編集
    - フォームのフィールドのプロパティを編集する
    - タブのプロパティの編集
    - セクション プロパティの編集

5.    フォームの編集が終了したら、 **保存** > **名前を付けて保存** を選択し、フォームの名前を入力し、次に **OK** を選択します。

6.    カスタマイズが完了したら **公開** を選択して公開できます。
 
### <a name="next-steps"></a>次のステップ  
[モデル駆動型フォーム デザイナーの概要](form-designer-overview.md)

[フォーム エディターのユーザー インターフェイスの概要](form-editor-user-interface-legacy.md)
 
