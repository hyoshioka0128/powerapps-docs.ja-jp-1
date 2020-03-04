---
title: SaveData および LoadData 関数 | Microsoft Docs
description: 構文を含む、Power Apps の SaveData 関数と LoadData 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 11208b68c3ec63f3a762771844adaaf7cd35aec1
ms.sourcegitcommit: 129d004e3d33249b21e8f53e0217030b5c28b53f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2020
ms.locfileid: "78265254"
---
# <a name="savedata-and-loaddata-functions-in-power-apps"></a>Power Apps の SaveData 関数と LoadData 関数
ローカルデバイスから[コレクション](../working-with-data-sources.md#collections)を保存して再読み込みします。

## <a name="description"></a>説明
**SaveData** 関数は、後で名前から使用できるようにコレクションを格納します。  

**LoadData** 関数は、既に **SaveData** で保存されている名前でコレクションを再読み込みします。 別のソースからコレクションを読み込む場合、この関数は使用できません。  

これらの関数を使用すると、アプリの起動時のパフォーマンスを向上させることができ **[ます。](../controls/control-screen.md#additional-properties)** そのためには、最初の実行時にアプリケーションの OnStart 式にデータをキャッシュしてから、以降の実行でローカルキャッシュを再読み込みします。 これらの機能を使用して、[単純なオフライン機能](../offline-apps.md)をアプリに追加することもできます。

これらの機能は、ブラウザー内では使用できません。 Power Apps Studio でアプリを作成する場合、または web プレーヤーでアプリを実行する場合です。 アプリをテストするには、iPhone または Android デバイスの Power Apps Mobile でアプリを実行します。

これらの関数は、メモリ内コレクションで動作するため、使用可能なアプリメモリの量によって制限されます。 使用可能なメモリは、デバイスとオペレーティングシステム、パワーアプリのプレーヤーが使用するメモリ、および画面とコントロールの観点からアプリの複雑さによって異なります。 数 mb を超えるデータを格納する場合は、アプリを実行するデバイスで、想定されるシナリオでアプリをテストします。 一般に、30 ~ 70 mb の使用可能なメモリが必要です。  

これらの関数は、アプリ内の任意の数式で **[collect](function-clear-collect-clearcollect.md)** 関数または **[clearcollect](function-clear-collect-clearcollect.md)** 関数呼び出しの有無によって暗黙的に定義されているコレクションに依存します。  コレクションにデータを読み込むために**収集**または**clearcollect**を呼び出す必要はありません。これは、以前の**SaveData**の後に**LoadData**を使用する場合の一般的なケースです。  必要なのは、コレクションの構造を暗黙的に定義するために、これらの関数が数式に存在することだけです。  詳細については[、「変数の作成と削除](../working-with-variables.md#create-and-remove-variables)」を参照してください。

読み込まれたデータは、コレクションに追加されます。 空のコレクションから開始する場合は、 **LoadData**を呼び出す前に **[Clear](function-clear-collect-clearcollect.md)** 関数を使用します。

デバイスの組み込みアプリサンドボックス機能は、保存されているデータを他のアプリから分離するために使用されます。  デバイスはデータを暗号化することもできます。また、必要に応じて、 [Microsoft Intune](https://www.microsoft.com/en-us/microsoft-365/enterprise-mobility-security/microsoft-intune)などのモバイルデバイス管理ツールを使用して暗号化することもできます。

## <a name="syntax"></a>構文
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* - 必須。  格納または読み込みの対象となるコレクション。
* *Name* - 必須。  ストレージの名前。 同じデータ セットを保存し、読み込むには、同じ名前を使用する必要があります。 名前空間は、他のアプリまたはユーザーとは共有されません。
* *IgnoreNonexistentFile* - 省略可能。 ファイルがまだ存在しない場合の対処方法を示すブール値。  エラーを返す場合は*false* (既定値) を、エラーを抑制する*場合は true*を使用します。   

## <a name="examples"></a>使用例

| [数式] | 説明 | 結果 |
| --- | --- | --- |
| **SaveData (LocalCache, "MyCache")** | **Localcache**コレクションを、後で取得する**LoadData**に適した "mycache" という名前のユーザーのデバイスに保存します。 | データはローカルデバイスに保存されます。 |
| **LoadData (LocalCache, "MyCache")** | "MyCache" という名前のユーザーのデバイスから**localcache**コレクションを読み込みます。以前は**SaveData**の呼び出しで格納されていました。  | データはローカルデバイスから読み込まれます。 |   

### <a name="simple-offline-example"></a>単純なオフラインの例

この非常に単純な例では、オフライン中に毎日の項目の名前と画像をキャプチャして保存します。  この情報は、後で使用できるようにデバイスのローカルストレージに保存されるため、データを失うことなく、アプリを閉じたりデバイスを再起動したりできます。  

この例を実行するには、web ブラウザーで動作しない**LoadData**関数と**SaveData**関数が使用されているデバイスが必要です。

1. タブレットレイアウトで空のキャンバスアプリを作成します。  詳細については、「[テンプレートからアプリを作成する](../get-started-test-drive.md)」と「 **[空のアプリ]** で **[タブレットレイアウト]** を選択する」を参照してください。  

1. 次に示すように、[**テキスト入力**](../controls/control-text-input.md)コントロールと[**カメラ**](../controls/control-camera.md)コントロールを追加し、おおよその位置に配置します。
    > [!div class="mx-imgBorder"]  
    > 空の画面にテキスト入力とカメラコントロールを追加 ![](media/function-savedata-loaddata/simple-text-camera.png)

1. [**ボタン**](../controls/control-button.md)コントロールを追加します。

2. ボタンコントロールをダブルクリックして、ボタンのテキストを **[項目の追加]** に変更します (または、 **[テキスト]** プロパティを変更します)。

3. ボタンコントロールの**Onseelct**プロパティを次の数式に設定します。これにより、コレクションに項目が追加されます。
    ```powerapps-dot
    Collect( MyItems, { Item: TextInput1.Text, Picture: Camera1.Photo } )
    ```
    > [!div class="mx-imgBorder"] 
    > テキスト "Add Item" と OnSelect プロパティセットを使用して追加されたボタンコントロールを ![](media/function-savedata-loaddata/simple-additem.png)

1. **ボタン**コントロールをもう1つ追加します。

2. ボタンコントロールをダブルクリックして、ボタンのテキストを変更して**データを保存**するか、**テキスト**プロパティを変更します。

3. コレクションをローカルデバイスに保存するために、ボタンコントロールの**Onseelct**プロパティを次の数式に設定します。
    ```powerapps-dot
    SaveData( MyItems, "LocalSavedItems" )
    ```
    > [!div class="mx-imgBorder"] 
    > "Save Data" というテキストと OnSelect プロパティセットを使用して追加されたボタンコントロールを ![](media/function-savedata-loaddata/simple-savedata.png)

    ボタンをテストするのは困難ですが、試してみると、何も害はありませんが、web ブラウザーで作成しているときにのみエラーが表示されます。  この数式をテストする前に、デバイスでアプリを保存して開いておく必要があります。これを行うには、次の手順を実行します。

1. 3番目の**ボタン**コントロールを追加します。

2. ボタンコントロールをダブルクリックして、ボタンのテキストを変更して**データを読み込む**か、または**text**プロパティを変更します。

3. ローカルデバイスからコレクションを読み込むには、ボタンコントロールの**Onseelct**プロパティを次の数式に設定します。
    ```powerapps-dot
    LoadData( MyItems, "LocalSavedItems" )
    ``` 
    > [!div class="mx-imgBorder"] 
    > テキスト "Load Data" と OnSelect プロパティセットを使用して追加されたボタンコントロールを ![](media/function-savedata-loaddata/simple-loaddata.png)

1. 画像とテキスト領域を含む、縦方向のレイアウトで[**ギャラリー**](../controls/control-gallery.md)コントロールを追加します。 
    > [!div class="mx-imgBorder"] 
    > ![ギャラリーのさまざまな選択、"縦" はイメージとテキスト領域で選択されて](media/function-savedata-loaddata/simple-gallery-add.png)

1. メッセージが表示されたら、このギャラリーのデータソースとして **[Myitems]** コレクションを選択します。  これにより、**ギャラリー**コントロールの**Items**プロパティが設定されます。 
    > [!div class="mx-imgBorder"] 
    > ギャラリーテンプレート内のイメージコントロールで [データ](media/function-savedata-loaddata/simple-gallery-collection.png) ソース] を選択すると、その**イメージ**のプロパティが既定で [この項目] に設定さ**れます。画像**とラベルコントロールは、両方とも**テキスト**プロパティをこの項目に既定値に設定する必要があります。 **![。**  次の手順で項目を追加した後に、これらの数式を確認してください。ギャラリーに何も表示されません。 

1. コントロールを他のコントロールの右側に配置します。 
    > [!div class="mx-imgBorder"] 
    > ![ギャラリーを画面の右側に再配置し](media/function-savedata-loaddata/simple-gallery-placed.png)

1. アプリを保存します。  初めて保存する場合は、発行する必要はありません。それ以外の場合は、アプリも発行します。

1. スマートフォンやタブレットなどのデバイスでアプリを開きます。  **SaveData**と**LoadData**は、Studio または web ブラウザーでは使用できません。  アプリの一覧を更新するアプリがすぐに表示されない場合は、アプリがデバイスに表示されるまでに数秒かかることがあります。  アカウントにサインインして再度サインインすると、役に立ちます。
    > [!div class="mx-imgBorder"] 
    > アプリのダウンロードが完了した後](media/function-savedata-loaddata/simple-mobile.png) 項目が追加されていない状態でアプリを実行している ![、ネットワークから切断し、アプリをオフラインで実行することができます。

1. 名前を入力し、項目の画像を撮影します。

2. **[項目の追加]** ボタンを選択します。  コレクションを読み込むために複数回項目の追加を繰り返します。
    > [!div class="mx-imgBorder"] 
    > 3つの項目が追加された状態で実行中のアプリ ![](media/function-savedata-loaddata/simple-mobile-with3.png) 

1. **[データの保存]** ボタンを選択します。  これにより、コレクション内のデータがローカルデバイスに保存されます。

1. アプリを閉じます。  メモリ内のコレクションは、すべての項目名と画像を含めて失われますが、デバイスのストレージには残ります。

1. アプリをもう一度起動します。  メモリ内のコレクションは、ギャラリーに空として表示されます。
    > [!div class="mx-imgBorder"] 
    > 項目が追加されていない状態で ![アプリを再度実行する](media/function-savedata-loaddata/simple-mobile.png) 

1. **[データの読み込み]** ボタンを選択します。  コレクションは、デバイス上の格納されているデータから再作成され、項目はギャラリーに戻されます。  このボタンが**LoadData**関数を呼び出す前に、コレクションが空だったことに注意してください。ストレージからデータを読み込む前に**collect**または**clearcollect**を呼び出す必要はありませんでした。
    > [!div class="mx-imgBorder"] 
    > LoadData 関数を呼び出した後に3つの項目が復元された状態で実行中のアプリ ![](media/function-savedata-loaddata/simple-mobile-load1.png) 

1. **[データの読み込み]** ボタンをもう一度クリックします。  格納されたデータはコレクションの末尾に追加され、スクロールバーはギャラリーに表示されます。  Append ではなく置換する場合は、 **LoadData**関数を呼び出す前に**clear**関数を使用してコレクションをクリアします。
    > [!div class="mx-imgBorder"] 
    > LoadData 関数を2回呼び出した後、6つの項目を復元して実行されている ![アプリ](media/function-savedata-loaddata/simple-mobile-load2.png) 
 
### <a name="more-advanced-offline-example"></a>より高度なオフラインの例

詳細な例については、[シンプルなオフライン機能](../offline-apps.md)に関する記事を参照してください。







