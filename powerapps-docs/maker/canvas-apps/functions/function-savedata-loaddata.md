---
title: SaveData および LoadData 関数 | Microsoft Docs
description: 構文を含む、Power Apps の SaveData 関数と LoadData 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/23/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c90f0be8d1f8f62afd3fdec1701b98b434f74387
ms.sourcegitcommit: 1b29cd1fa1492037ef04188dd857a911edeb4985
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80122840"
---
# <a name="savedata-and-loaddata-functions-in-power-apps"></a>Power Apps の SaveData 関数と LoadData 関数
ローカルデバイスから[コレクション](../working-with-data-sources.md#collections)を保存して再読み込みします。

## <a name="description"></a>説明
**SaveData** 関数は、後で名前から使用できるようにコレクションを格納します。  

**LoadData**関数は、以前に**SaveData**と共に保存されたコレクションを名前で再読み込みします。 別のソースからコレクションを読み込む場合、この関数は使用できません。  

これらの関数を使用すると、次の方法でアプリ起動時のパフォーマンスを向上させることができます。

- 最初の実行時に、 **[アプリケーションの OnStart](../controls/control-screen.md#additional-properties)** 式のデータをキャッシュします。
- 次回の実行時にローカルキャッシュを再読み込みします。

これらの機能を使用して、[単純なオフライン機能](../offline-apps.md)をアプリに追加することもできます。

次の場合、ブラウザー内でこれらの関数を使用することはできません。

- Power Apps Studio でアプリを作成します。
- Web プレーヤーでアプリを実行します。 

アプリをテストするには、iPhone または Android デバイスの Power Apps Mobile でアプリを実行します。

これらの関数は、メモリ内コレクションで動作するときに利用可能なアプリメモリの量によって制限されます。 使用可能なメモリは、次のような要因によって異なります。 

- デバイスとオペレーティングシステム。
- Power Apps プレーヤーが使用するメモリ。
- 画面とコントロールを使用したアプリの複雑さ。 

大規模なデータを格納するときに、アプリが実行すると予想されるデバイスの種類に関して、予想されるシナリオでアプリをテストします。 通常は、30 MB ~ 70 MB の使用可能なメモリが必要です。

これらの関数は、 **[collect](function-clear-collect-clearcollect.md)** または **[clearcollect](function-clear-collect-clearcollect.md)** で暗黙的に定義されているコレクションに依存します。 **Collect**または**clearcollect**を呼び出して、コレクションにデータを読み込んで定義する必要はありません。 これは、前の**SaveData**の後に**LoadData**を使用する場合の一般的なケースです。  必要なのは、コレクションの構造を暗黙的に定義するために、これらの関数が数式に存在することだけです。  詳細については、「[変数の作成と削除](../working-with-variables.md#create-and-remove-variables)」を参照してください。

読み込まれたデータは、コレクションに追加されます。 空のコレクションから開始する場合は、 **LoadData**を呼び出す前に **[Clear](function-clear-collect-clearcollect.md)** 関数を使用します。

デバイスの組み込みアプリサンドボックス機能は、保存されているデータを他のアプリから分離するために使用されます。 

デバイスはデータを暗号化することもできます。または、 [Microsoft Intune](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/microsoft-intune)などのモバイルデバイス管理ツールを使用することもできます。

## <a name="syntax"></a>構文
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* - 必須。  格納または読み込みの対象となるコレクション。
* *Name* - 必須。  ストレージの名前。 同じデータセットを保存して読み込む場合は、名前が同じである必要があります。 名前空間は、他のアプリまたはユーザーとは共有されません。
* *IgnoreNonexistentFile* - 省略可能。 ファイルがまだ存在しない場合の対処方法を示すブール値。  エラーを返す場合は*false* (既定値) を、エラーを抑制する*場合は true*を使用します。   

## <a name="examples"></a>例

| [数式] | 説明 | 結果 |
| --- | --- | --- |
| **SaveData (LocalCache, "MyCache")** | **Localcache**コレクションを、後で取得する**LoadData**に適した "mycache" という名前のユーザーのデバイスに保存します。 | データはローカルデバイスに保存されます。 |
| **LoadData (LocalCache, "MyCache")** | "MyCache" という名前のユーザーのデバイスから**localcache**コレクションを読み込みます。以前は**SaveData**の呼び出しで格納されていました。  | データはローカルデバイスから読み込まれます。 |   

### <a name="simple-offline-example"></a>単純なオフラインの例

次の簡単な例では、オフライン中に毎日の項目の名前と画像をキャプチャして保存します。  この情報は、後で使用できるように、デバイスのローカルストレージに格納されます。 これにより、データを失うことなく、アプリを閉じたりデバイスを再起動したりできます。  

この例を実行するには、web ブラウザーで動作しない**LoadData**関数と**SaveData**関数が使用されているデバイスが必要です。

1. タブレットレイアウトで空のキャンバスアプリを作成します。  詳細については、「[テンプレートからアプリを作成する](../get-started-test-drive.md)」と「 **[空のアプリ]** で **[タブレットレイアウト]** を選択する」を参照してください。  

1. 次に示すように、[**テキスト入力**](../controls/control-text-input.md)コントロールと[**カメラ**](../controls/control-camera.md)コントロールを追加し、おおよその位置に配置します。
    > [!div class="mx-imgBorder"]  
    > 空の画面にテキスト入力とカメラコントロールを追加 ![](media/function-savedata-loaddata/simple-text-camera.png)

1. [**ボタン**](../controls/control-button.md)コントロールを追加します。

2. ボタンコントロールをダブルクリックして、ボタンのテキストを **[項目の追加]** に変更します (または、 **[テキスト]** プロパティを変更します)。

3. ボタンコントロールの**Onselect**プロパティを次の数式に設定して、コレクションに項目を追加します。
    ```powerapps-dot
    Collect( MyItems, { Item: TextInput1.Text, Picture: Camera1.Photo } )
    ```
    > [!div class="mx-imgBorder"] 
    > テキスト "Add Item" と OnSelect プロパティセットを使用して追加されたボタンコントロールを ![](media/function-savedata-loaddata/simple-additem.png)

1. **ボタン**コントロールをもう1つ追加します。

2. ボタンコントロールをダブルクリックして、ボタンのテキストを変更して**データを保存**するか、**テキスト**プロパティを変更します。

3. コレクションをローカルデバイスに保存するために、ボタンコントロールの**Onselect**プロパティを次の数式に設定します。
    ```powerapps-dot
    SaveData( MyItems, "LocalSavedItems" )
    ```
    > [!div class="mx-imgBorder"] 
    > "Save Data" というテキストと OnSelect プロパティセットを使用して追加されたボタンコントロールを ![](media/function-savedata-loaddata/simple-savedata.png)

    このボタンは何にも影響しないので、テストすることをお勧めします。 ただし、web ブラウザーでの作成時にのみエラーが表示されます。 最初にアプリを保存し、次の手順に従ってこの数式をテストする前に、デバイスでを開きます。

1. 3番目の**ボタン**コントロールを追加します。

2. ボタンコントロールをダブルクリックして、ボタンテキストを変更して**データを読み込む**か、**テキスト**プロパティを変更します。

3. ローカルデバイスからコレクションを読み込むには、ボタンコントロールの**Onselect**プロパティを次の数式に設定します。
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
    > ![ギャラリーが画面の右側に移動し](media/function-savedata-loaddata/simple-gallery-placed.png)

1. アプリを保存します。  初めて保存する場合は、公開する必要はありません。 初めての場合は、保存した後でアプリを発行します。

1. スマートフォンやタブレットなどのデバイスでアプリを開きます。  **SaveData**と**LoadData**は、Studio または web ブラウザーでは使用できません。  アプリの一覧を更新するアプリがすぐに表示されない場合は、アプリがデバイスに表示されるまでに数秒かかることがあります。  アカウントにサインインして再度サインインすると、役に立ちます。
    > [!div class="mx-imgBorder"] 
    > アプリのダウンロードが完了した後](media/function-savedata-loaddata/simple-mobile.png) 項目が追加されていない状態でアプリを実行している ![、ネットワークから切断し、アプリをオフラインで実行することができます。

1. 名前を入力し、項目の画像を撮影します。

2. **[項目の追加]** ボタンを選択します。  コレクションを読み込むために複数回項目の追加を繰り返します。
    > [!div class="mx-imgBorder"] 
    > 3つの項目が追加された状態で実行中のアプリ ![](media/function-savedata-loaddata/simple-mobile-with3.png) 

1. **[データの保存]** ボタンを選択します。  これにより、コレクション内のデータがローカルデバイスに保存されます。

1. アプリを閉じます。  メモリ内のコレクションは、すべての項目名と画像を含めて失われますが、デバイスのストレージに残ります。

1. アプリをもう一度起動します。  メモリ内のコレクションは、ギャラリーに空として表示されます。
    > [!div class="mx-imgBorder"] 
    > 項目が追加されていない状態で ![アプリを再度実行する](media/function-savedata-loaddata/simple-mobile.png) 

1. **[データの読み込み]** ボタンを選択します。  コレクションは、デバイス上の格納されているデータから再作成され、項目はギャラリーに戻されます。  このボタンが**LoadData**関数を呼び出す前に、コレクションが空でした。ストレージからデータを読み込む前に**collect**または**clearcollect**を呼び出す必要はありませんでした。
    > [!div class="mx-imgBorder"] 
    > LoadData 関数を呼び出した後に3つの項目が復元された状態で実行中のアプリ ![](media/function-savedata-loaddata/simple-mobile-load1.png) 

1. **[データの読み込み]** ボタンをもう一度クリックします。  格納されたデータはコレクションの末尾に追加され、スクロールバーはギャラリーに表示されます。  Append ではなく置換する場合は、 **LoadData**関数を呼び出す前に**clear**関数を使用してコレクションをクリアします。
    > [!div class="mx-imgBorder"] 
    > LoadData 関数を2回呼び出した後、6つの項目を復元して実行されている ![アプリ](media/function-savedata-loaddata/simple-mobile-load2.png) 
 
### <a name="more-advanced-offline-example"></a>より高度なオフラインの例

詳細な例については、[シンプルなオフライン機能](../offline-apps.md)に関する記事を参照してください。







