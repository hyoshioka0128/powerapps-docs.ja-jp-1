---
title: PowerApps アプリ デザイナーでのモデル駆動型アプリ プロパティの管理 | MicrosoftDocs
description: アプリのプロパティの管理方法を説明します。
keywords: ''
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: e773e60f-0211-4c4b-a1af-663be4997629
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 14
topic-status: Drafting
---

# <a name="manage-model-driven-app-properties-in-the-app-designer"></a>アプリ デザイナーでのモデル駆動型アプリ プロパティの管理

アプリ プロパティは、タイトルまたは URL などのアプリケーションに関する重要な詳細を定義します。 アプリを作成するとき、そのアプリ プロパティを定義します。 それらのプロパティを後で変更する場合は、アプリ デザイナーで行うことができます。  
  
1.  アプリ デザイナーの右側で、**プロパティ**タブを選択します。  

    > [!div class="mx-imgBorder"] 
    > ![アプリ デザイナーの [プロパティ] ウィンドウ](media/app-designer-properties-tab.png "アプリ デザイナーの [プロパティ] ウィンドウ")  
  
2.  必要に応じて、情報を変更:  

    |プロパティ|内容|  
    |--------------|-----------------|
    |**名前**|アプリケーションに一意および内容を示す名前を入力します。|  
    |**説明**|どのアプリであるかに関する短い説明を入力します。|  
    |**アイコン**|既定では、**既定のアプリの使用**チェック ボックスはオンになっています。 アプリケーションのアイコンとして、異なる Web リソースを選択するには、チェック ボックスをオフにし、次に、ドロップダウン リストからアイコンを選択します。 このアイコンはアプリのプレビュー タイルに表示されます。|
    |**一意の名前**| 一意の名前は変更できません。 一意の名前を使用してテーブルをクエリし、データベースからデータを取得できます。| 
    |**クライアント**|アプリが使用されるクライアントの種類を定義します。<br/>-  **Web:** これは従来の Dynamics 365 Customer Engagement Web ブラウザー クライアントです。<br/>-  **統一インターフェイス:** これは、PC とモバイル デバイス全体で同様のインターフェイスを持つ新しい Web ブラウザー クライアントです。|
    |**アプリの URL の接頭辞**| アプリの作成中に選択した URL は、既定でここに表示されます。 **アプリの管理**ダイアログ ボックスでアプリの URL を変更できます。 この時点では、ソリューションによってアプリ URL サフィックスをエクスポート、またはインポートすることはできない点に注目してください。|
    |**アプリの [ようこそ] ページを選択**|このオプションを使用すると、環境で利用できる Web リソースの中から選択することができます。 作成した [ようこそ] ページには、ビデオへのリンク、アップグレードの手順、開始方法に関する情報など、有用な情報を含めることができます。 [ようこそ] ページとして使用できる HTML ファイルなどの Web リソースの作成方法の詳細については、「[Web リソースを作成および編集して Web アプリケーションを拡張](create-edit-web-resources.md)」を参照してください。|
    |**Mobile Offline の有効化**|このオプションにより、**Mobile Offline プロファイル**ドロップ ダウン リストを使用して選択されたプロファイルを、モバイル上のアプリがオフラインで使用できます。|
  
3.  アプリを保存します。  
  
## <a name="next-steps"></a>次のステップ  
 [アプリの作成または編集](create-edit-app.md)