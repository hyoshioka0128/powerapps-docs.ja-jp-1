---
title: PowerApps でモデル駆動型アプリのサイト マップを作成 | MicrosoftDocs
description: アプリのサイト マップの作成方法を学習する
keywords: ''
ms.date: 05/29/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2461bd71-6cb4-46b7-8d1f-6a0aa3dca809
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 18
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-model-driven-app-site-map-for-an-app-using-the-site-map-designer"></a>チュートリアル: サイト マップ デザイナーを使用してアプリのモデル駆動型アプリ サイト マップを作成する

このチュートリアルでは、新しいサイト マップを作成する、領域、グループ、およびサブ領域を追加するなど、いくつかのサイト マップ タスクを実行します。

サイト マップはアプリのナビゲーションを定義します。 タイル ベースのデザイナー ベースを使用して、アプリのサイト マップを簡単に作成します。 デザイナーを使用してコンポーネントをデザイン キャンバスにドラッグし、ユーザーの作業をプレビューし、サイト マップを即時に公開します。 システム カスタマイザーまたは必要な特権を持つユーザーは、アプリのサイト マップをすばやく作成できます。  
  
サイト マップ デザイナーにより、環境でサポートされている言語で、領域、サブ領域、またはグループのタイトルを定義できます。  
  
既定のサイト マップを使用できます。 サイト マップ デザイナーを使用することによって、このサイト マップの編集または新しいアプリのサイト マップの構成が可能です。 サイト マップ デザイナーはアプリ デザイナーに統合されます。  

## <a name="prerequisites"></a>前提条件
システム管理者またはシステム カスタマイザーのセキュリティ ロール、または同等のアクセス許可があることを確認してください。  具体的には、次の特権を持つすべてのユーザーはアプリ作成することもできます:  
-   アプリのエンティティにおける作成、読み取り、および書き込み特権  
-   カスタマイズ可能なエンティティにおける読み取りおよび書き込み特権  
-   ソリューション エンティティにおける読み取り特権

これらの特権は、セキュリティ ロールの **カスタマイズ** タブで表示または設定できます。
  
## <a name="create-a-site-map-for-an-app"></a>アプリのサイト マップの作成  
  
1. アプリ デザイナー キャンバスの**サイト マップ**領域で、**サイト マップ デザイナーを開く** ![[サイト マップ デザイナーを開く] ボタン](media/dynamics365-open-designer.PNG "[サイト マップ デザイナーを開く] ボタン") を選択します。  
  
     サイト マップ デザイナーは、1 つの領域、1 つのグループ、および 1 つのサブ領域で事前設定されているキャンバスで開きます。 領域、グループ、またはサブ領域タイルを選択し、プロパティを変更します。  
  
    > [!NOTE]
    >  アプリ デザイナー キャンバスから**サイト マップ デザイナーを開く** ![[サイト マップ デザイナーを開く] ボタン](media/dynamics365-open-designer.PNG "[サイト マップ デザイナーを開く] ボタン") を選択すると、新しいサイト マップ (アプリの既存のサイト マップがない場合) が自動的に作成され、アプリ名と同じ名前およびアプリの一意の名前と同じ一意の名前が新しいサイト マップに与えられます。 

   ![サイト マップの選択](media/app-designer-sitemap-location.png "サイト マップの選択") 
  
2.  [領域をサイト マップに追加する](create-site-map-app.md#bkmk_AddArea)。  
  
3.  [サイト マップにグループを追加する](create-site-map-app.md#bkmk_AddGroup)。  
  
4.  [サイト マップのグループにサブ領域を追加する](create-site-map-app.md#bkmk_AddSubarea)。  
  
5.  **保存**を選びます。  
  
    > [!NOTE]
    >  アプリ デザイナーに戻り、**保存**を選択すると、新しいサイト マップはアプリに関連付けられます。 サイト マップが構成されるとき、**構成済み**がサイト マップ タイル上に表示されます。それ以外の場合は**未構成**がタイル上に表示されます。  アプリ デザイナーからサイト マップ デザイナーを開いて新しいサイト マップを構成しても、サイト マップをアプリに関連付ける前にブラウザーを閉じた場合は、次回にアプリ デザイナーを開いたときに、アプリの一意の名前に基づいて、サイト マップはアプリに自動的に関連付けられるようになります。  
  
6.  **発行**を選択します。  
  
## <a name="edit-the-default-site-map"></a>既定のサイト マップの編集 

 ユーザーの環境には既定のサイト マップが用意されます。  
  
1. ソリューション エクスプローラーを開きます。  
  
2. ソリューション ウィンドウの**コンポーネント**で、**クライアント拡張**を選択します。  

3. コンポーネント ツール バーで、**既存の追加** >  **サイト マップ** を選択します。

4. ソリューション コンポーネントの一覧で、**サイト マップ**という名前のサービス マップを選択し、**OK** を選択します。
  
5.  表示名**サイト マップ**および**管理済み**状態になっている、追加したサイト マップをダブルクリックして選択します。 また、サイト マップを選択してから、ツールバーで**編集**を選択することもできます。  
  
     サイト マップはサイト マップ デザイナーで開きます。  
  
6.  [領域をサイト マップに追加する](create-site-map-app.md#bkmk_AddArea)。  
  
7.  [サイト マップにグループを追加する](create-site-map-app.md#bkmk_AddGroup)。  
  
8.  [サイト マップのグループにサブ領域を追加する](create-site-map-app.md#bkmk_AddSubarea)。  
  
9. **保存**を選びます。  
  
10. **発行**を選択します。  
  
<a name="bkmk_AddArea"></a>   
## <a name="add-an-area-to-the-site-map"></a>領域をサイト マップに追加するには  
  
1.  サイト マップ デザイナー キャンバスの**追加** ![デザイナーの [追加] ボタン](media/dynamics365-designer-addbutton.PNG "デザイナーの [追加] ボタン") を選択してから、**領域**を選択します。  
  
     または  
  
     **コンポーネント**タブから、**領域**タイルをキャンバスの空のボックスにドラッグします。 キャンバスの正しい場所にタイルを移動すると、空のボックスが表示されます。  
  
2.  先ほど追加した領域を選択します。 キャンバスの右側のウィンドウにハイライトされた**プロパティ**タブが表示されます。  
  
3.  領域プロパティを追加または編集します。  
  
     **全般**の下で以下の内容を実行します。  
  
    - **タイトル**: 組織の基礎言語で領域のタイトルを入力します。  
  
    - **アイコン**: 既定のアプリケーション アイコンが選択されます。 ソリューションで使用できる Web リソースの一覧から、領域に対して異なるアイコンを選択します。  
  
    - **ID**: 一意の ID が自動的に生成されますが、必要に応じて、別の ID を入力できます。 入力した ID が一意のものでない場合、ユーザーがアプリを使用しているときにエラーが発生する可能性がある、またはこのサイト マップが含まれているソリューションをインポートするときにエラーが発生する可能性があるため、提供された ID を使用することをお勧めします。  
  
    - **グループの表示**: このチェック ボックスをオンにし、ナビゲーション ウィンドウのサブ領域のグループを表示します。  
  
     **詳細**の下で以下の内容を実行します。  
  
    - **タイトルを増やす**: 組織で複数の言語を使用する場合は、タイトルの言語 (ロケール) を選択し、タイトルを入力してから、**追加**![サイト マップ デザイナーの [追加] ボタン](media/add-icon-sitemap-designer.png "サイト マップ デザイナーの [追加] ボタン") を選択します。 組織が使用する数の言語数のタイトルを作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つのタイトルしか含めることができません。  
  
    - **説明を増やす**: 組織で複数の言語を使用する場合は、説明の言語を選択し、説明を入力してから、**追加**![サイト マップ デザイナーの [追加] ボタン](media/add-icon-sitemap-designer.png "サイト マップ デザイナーの [追加] ボタン") を選択します。 組織が使用する数の言語数で説明を作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つの説明しか含めることができません。  
  
    - **URL**: 領域を表す Dynamics 365 for Outlook フォルダーに表示する URL を入力します。  
  
<a name="bkmk_AddGroup"></a>   
## <a name="add-a-group-to-the-site-map"></a>サイト マップにグループを追加する  
  
1.  サイト マップ デザイナー キャンバスで、グループを追加する領域を選択します。  
2.  **追加** ![デザイナーの [追加] ボタン](media/dynamics365-designer-addbutton.PNG "デザイナーの [追加] ボタン") を選択してから、**グループ** を選択します。  
  
     または  
  
     **コンポーネント**タブから、**グループ**タイルをキャンバスにある**領域**の空のボックスにドラッグします。 キャンバスの正しい場所にタイルを移動すると、空のボックスが表示されます。  
  
3.  先ほど追加したグループを選択します。  
  
4.  **プロパティ**タブで、グループ プロパティを追加または編集します。  
  
     **全般**の下で以下の内容を実行します。  
  
    - **タイトル**: 組織の基礎言語でグループのタイトルを入力します。  
  
    - **ID**: 一意の ID が自動的に生成されます。 必要に応じて別の ID を入力します。 入力した ID が一意のものでない場合、このサイト マップが含まれているソリューションをインポートするときにエラーが発生する可能性があるため、自動的 ID を使用することをお勧めします。  
  
     **詳細**の下で以下の内容を実行します。  
  
    - **タイトルを増やす**: 組織で複数の言語を使用する場合は、タイトルの言語 (ロケール) を選択し、グループのタイトルを入力してから、**追加** ![サイト マップ デザイナーの [追加] ボタン](media/add-icon-sitemap-designer.png "サイト マップ デザイナーの [追加] ボタン") を選択します。 組織が使用する数の言語数のタイトルを作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つのタイトルしか含めることができません。  
  
    - **説明を増やす**: 組織で複数の言語を使用する場合は、説明の言語を選択し、グループの説明を入力してから、**追加**![サイト マップ デザイナーの [追加] ボタン](media/add-icon-sitemap-designer.png "サイト マップ デザイナーの [追加] ボタン") を選択します。 組織が使用する数の言語数で説明を作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つの説明しか含めることができません。  
  
    - **URL**: グループを表す Dynamics 365 for Outlook フォルダーに表示する URL を入力します。  
  
    - **プロファイルとして設定**: このチェック ボックスをオンにし、このグループがワークプレースに対してユーザーによる選択が可能なプロファイルを示しているどうかを示します。 ユーザーによる選択が可能なプロファイルとして設定されているグループは、個人用オプション内のオプションとして利用できるようになっています。 これは、**ワークプレース**領域内のグループに対してのみ適用されます。  
  
<a name="bkmk_AddSubarea"></a>   
## <a name="add-a-subarea-to-a-group-in-the-site-map"></a>サイト マップのグループにサブ領域を追加する  
  
1.  サイト マップ デザイナー キャンバスの**追加** ![デザイナーの [追加] ボタン](media/dynamics365-designer-addbutton.PNG "デザイナーの [追加] ボタン") を選択してから、**サブ領域**を選択します。  
  
     または  
  
     **コンポーネント**タブから、**サブエリア**タイルをキャンバスにある**グループ**セクションの下の空のボックスにドラッグします。 キャンバスの正しい場所にタイルを移動すると、空のボックスが表示されます。  
  
2.  先ほど追加したサブ領域を選択します。  
  
3.  **プロパティ**タブで、サブ領域プロパティを追加または編集します。  
  
     **全般**の下で以下の内容を実行します。  
  
    - **種類**: 追加するサブ領域が、ダッシュボード、エンティティ、Web リソース、または URL であるかどうかを選択します。  
  
    - **エンティティ**: サブ領域に対するエンティティを選択します。 サブ領域の種類が**種類**ドロップダウン リストで、**エンティティ**以外のものが選択されている場合は、このフィールドは無効です。  
  
    - **URL**: URL を指定し、アプリケーションのメイン ページで、このサブ領域が選択されているかを表示します。 ドロップダウン リストの**種類**で、**エンティティ**を選択した場合は、このフィールドは無効です。  
  
    - **既定のダッシュボード**: 既定のダッシュボードを選択し、そのサブ領域が表示されるようにします。 **種類**ドロップダウン リストで、**ダッシュボード**を選択していない場合は、このフィールドは無効です。  
  
    - **タイトル**: 組織の基礎言語でサブ領域のタイトルを入力します。  
  
    - **アイコン**: 既定のアプリケーション アイコンが選択されます。 ソリューションで使用できる Web リソースの一覧から、サブ領域における異なるアイコンを選択します。  
  
    - **ID**。 一意の ID が自動的に生成されます。 必要に応じて一意の ID を入力します。  
  
    - **パラメーター引き渡し**。 このチェック ボックスをオンにし、組織と言語コンテキストに関する情報を URL に渡します。 このチェック ボックスは、サブ領域の種類が Web リソースまたは URL ベースサブ領域である場合にのみチェックされます。  
  
     **詳細**の下で以下の内容を実行します。  
 
    - **特権**: これは、ユーザーに割り当てられているすべてのセキュリティ ロール上で使用できる特権に基づいて、サブ領域が表示されているかどうかを定義します。 特権をチェックするエンティティの名前を選択してから、チェック ボックスを選択して特権を割り当てます。 
  
    - **タイトルを増やす**: 組織が複数の言語を使用する場合、タイトルの言語を選択し、サブ領域のタイトルを入力し、**追加**を選択します。 組織が使用する数の言語数のタイトルを作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つのタイトルしか含めることができません。  
  
    - **説明を増やす**: 組織が複数の言語を使用する場合、説明の言語を選択し、サブ領域の説明を入力してから、**追加**を選択します。 組織が使用する数の言語数で説明を作成、編集、または削除を可能にします。 しかし、言語ごとに 1 つの説明しか含めることができません。  
  
    - **SKU**: このサブ領域を表示する Dynamics 365 Customer Engagement のバージョンを選択します。  
  
    - **クライアント**: このサブ領域を表示するクライアントの種類を選択します。  
  
    - **Outlook ショートカット**: Dynamics 365 for Outlook で表示するアイコンを選択します。  
  
    - **オフライン時の使用**: このチェック ボックスをオンにすると、ユーザーが Dynamics 365 for Outlook 上でオフラインである場合、このサブ領域が使用可能になります。  
  
## <a name="organize-areas-groups-and-subareas"></a>領域、グループ、およびサブ領域の編成  
 領域、グループ、およびサブ領域を新しい位置にドラッグすることによって、これらを編成することができます。 コンテナー ボックスはタイルをドロップできる位置に表示されます。 次はユーザーが実行できる事項です:  
  
-   同じ領域で同じグループまたは異なるグループの新しい位置にサブ領域を移動します。  
  
-   異なる領域のグループの新しい位置にサブ領域を移動します。  
  
-   同じ領域内の新しい位置にグループを移動します。  
  
-   異なる領域内の新しい位置にグループを移動します。  
  
-   領域を新しい位置に移動します。  
  
## <a name="clone-a-component-in-a-site-map"></a>サイト マップでのコンポーネントの複製  
 既存のコンポーネントのコピーを作成するには、コンポーネントを選択し、ツール バーで、**複製**を選択します。  複製コンポーネントのすべての詳細は、ID とタイトル以外はベース コンポーネントと同じです。 ID はランダムに生成されます。 
  
 領域を複製すると、複製された領域は、現在選択した領域の右側に追加されます。 グループを複製すると、複製されたグループは、現在選択したグループの右側に追加されます。 サブ領域を複製すると、複製されたサブ領域は、現在選択したサブ領域の下に追加されます。  
  
## <a name="delete-an-area-group-or-subarea-from-a-site-map"></a>サイト マップから領域、グループ、またはサブ領域を削除する  
 サイト マップのコンポーネントを削除するには、コンポーネント タイルを選択し、ツール バーで、**削除**を選択します。 領域を削除すると、その領域のすべてのグループとサブ領域も削除されます。 同様に、グループを削除すると、そのグループのグループおよびサブ領域も削除されます。  
  
## <a name="clients-supported"></a>サポートされているクライアント  
 次の表では、異なるサイト マップでサポートされているクライアントについて説明しています。  
 
|サイト マップ |サポートされているクライアント|  
|---------------|-----------------------|  
|新しいアプリ| 統一インターフェイスと Dynamics 365 Customer Engagement Web アプリ |  
|Dynamics 365 のサイト マップ - カスタム アプリ | Dynamics 365 Customer Engagement Web アプリと Dynamics 365 for Outlook |  
|既定のビジネス アプリ (Sales、Sales Hub、Customer Service、Customer Service Hub、Field Service、Project Service Automation)| Dynamics 365 Customer Engagement Web アプリと統一インターフェイス|  
 
  
### <a name="next-steps"></a>次のステップ  
 [アプリの作成または編集](create-edit-app.md)   
 [アプリのコンポーネントの追加または編集](add-edit-app-components.md)