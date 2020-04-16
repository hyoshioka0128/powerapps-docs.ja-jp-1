---
title: オプション セットの作成 | Microsoft Docs
description: オプション セットを作成する方法の詳細な手順。
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 375ead78421dae021841009c5c6d1308fa4ed24b
ms.sourcegitcommit: ca7df48f819795d28ccfcd4a862639e20a7fe8fe
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2020
ms.locfileid: "3169078"
---
# <a name="create-an-option-set"></a>オプション セットの作成

オプション セットを使用して、アプリケーション内のユーザーに固定値のドロップダウン リストを含めることができ、データの一貫性を保証します。他のアプリケーションのピックリストまたは選択フィールドと呼ばれることもあります。 エンティティと同様に、標準のオプション セットと、アプリ内で使用するユーザー定義のオプション セットを作成する機能があります。

オプション セットは、ポータル内の **オプション セット** リストから、またはフィールド作成中にエンティティ内で直接の 2 つの方法で作成できます。 エンティティを作成する方法の詳細については、「[エンティティの作成](data-platform-create-entity.md)」を参照してください。

## <a name="creating-an-option-set-while-adding-a-field"></a>フィールドを追加する際にオプション セットを作成する

1. [powerapps.com](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) で**データ**セクションを展開し、左側のナビゲーション ウィンドウで**エンティティ**をクリックまたはタップします。

    ![エンティティの詳細](./media/data-platform-cds-create-entity/entitylist.png "エンティティ リスト")

2. 既存のエンティティ、または [エンティティの新規作成](data-platform-create-entity.md) をクリックまたはタップします

3. **フィールドの追加**をクリックして、新しいフィールドをエンティティに追加します。

4. 新しいフィールド パネルで、フィールドの**表示名**を入力すると、フィールドで**名前**が自動的に設定され、一意の名前として使用されます。 **表示名**はこのフィールドをユーザーに表示するときに使用され、**名前**は式や数式でアプリを構築するときに使用されます。

5. **データの種類** ドロップダウンをクリックし **オプション セット** 、または **複数選択オプション セット** をクリックします。

    > [!div class="mx-imgBorder"] 
    > ![新しいフィールド](./media/data-platform-cds-create-entity/newfieldpanel.png "新規フィールドのパネル")

6. **オプション セット**ドロップダウンをクリックし、**新しいオプション セット**を選択します。

    > [!NOTE]
    > 既存のオプション セットがエンティティに使用できる場合、新規作成するのではなく、このリストから選択できます。

    ![オプション セットのリスト](./media/data-platform-cds-newoptionset/fieldpanel-1.png "オプション セットのリスト")

7. オプション セットの作成に新しいパネルが開き、**表示名**および**名前**がフィールドの名前から既定で設定されますが、必要に応じて変更できます。 **新しい項目の追加**をクリックしてオプションの一覧を作成し始めます。 項目がすべて作成されるまで、この手順を繰り返します。

    > [!div class="mx-imgBorder"] 
    > ![新規オプション セット](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "新規オプション セット")

8. 項目を一度入力したら、オプション セットを作成するため**保存**をクリックします。

    > [!div class="mx-imgBorder"] 
    > ![新規オプション セット](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "新規オプション セット")

9. **完了** をクリックしてフィールド パネルを閉じてから、 **エンティティの保存** をクリックしてエンティティを Common Data Service に保存します。

    > [!NOTE]
    > このフィールドの**既定**として項目の 1 つを選択でき、ユーザーがエンティティで新しいレコードを作成するときには既定で選択されます。

    > [!div class="mx-imgBorder"] 
    > ![新しいフィールド](./media/data-platform-cds-newoptionset/fieldpanel-2.png "新規フィールドのパネル")

## <a name="creating-an-option-set-from-the-option-set-list"></a>オプション セット リストからオプション セットの作成

1. [powerapps.com](https://make.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) で **データ** セクションを展開し、左側のナビゲーション ウィンドウで **オプション セット** をクリックまたはタップします。

    > [!div class="mx-imgBorder"] 
    > ![オプション セット](./media/data-platform-cds-newoptionset/optionsetlist.png "オプション セットのリスト")

2. **新しいオプション セット**をクリックします

3. オプション セットを作成するため新しいパネルを開き、**表示名**および**名前**を入力します。 **新しい項目の追加**をクリックしてオプションの一覧を作成し始めます。 項目がすべて作成されるまで、この手順を繰り返します。

    > [!div class="mx-imgBorder"] 
    > ![オプション セットの作成](./media/data-platform-cds-newoptionset/optionset-create.png "オプション セットの作成")

4. 項目を一度入力したら、オプション セットを作成するため**保存**をクリックします。

    > [!div class="mx-imgBorder"] 
    > ![新規オプション セット](./media/data-platform-cds-newoptionset/optionset-create-values.png "新規オプション セット")

5. エンティティに新しいフィールドを作成して、このオプション セットを使用できるようになります。

## <a name="global-and-local-option-sets"></a>グローバルおよびローカル オプション セット

既定では、オプション セットは複数のエンティティ間で再利用されるようグローバル オプション セットとして作成されます。 新しいオプション セットを作成するときに、**詳細を表示**オプションで、オプション セットを**ローカル**に選択できます。 このオプションはフィールドを追加している間にオプション セットを作成する場合にのみ使用でき、 **オプション セット** リストを通しては使用できません。 ローカル オプション セットは作成されたエンティティおよびフィールドでのみ使用でき、他のエンティティで再利用することはできません。 この方法は、ローカル オプション セットの特定のニーズがある上級ユーザーにのみお勧めします。

> [!IMPORTANT]
> オプション セットがローカルまたはグローバルとして作成されると、これを変更することはできません。
