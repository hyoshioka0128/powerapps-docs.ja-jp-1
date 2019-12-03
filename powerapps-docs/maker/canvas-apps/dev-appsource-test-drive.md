---
title: AppSource でのお客様によるキャンバス アプリ体験版の使用 | Microsoft Docs
description: AppSource を使用してお客様とキャンバス アプリを共有し、ビジネスの潜在顧客を生成します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/08/2017
ms.author: litran
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3970c5181939f8ab6e8bd1ad4f396595d7083ff3
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74679571"
---
# <a name="let-customers-test-drive-your-canvas-app-on-appsource"></a>AppSource でのお客様によるキャンバス アプリ体験版の使用

Power Apps でキャンバスアプリを構築することに情熱を持っていますか。 キャンバス アプリをお客様と共有したいですか。 [AppSource.com](https://appsource.microsoft.com)は、お客様とアプリを共有し、ビジネスの潜在顧客を生み出する手段として、Power Apps Test Drive ソリューションをサポートしています。

## <a name="what-is-a-test-drive-solution"></a>体験版ソリューションとは

体験ソリューションを使用すると、お客様は実際のアプリを試すことができます。これには、Power Apps プランにサインアップしたり、アプリケーションをインストールしたりする必要はありません。 お客様は、Azure Active Directory (AAD) アカウントを使用して AppSource.com にサインインして、Web ブラウザーでアプリを実行するだけです。 体験版がなければ、お客様はアプリに関する説明を読んだり、ビデオを見たりするしかありません。 体験版を使用すると、ソリューションの内容やアプリの機能についてよく理解することができます。 アプリを実際に使用する経験を持つことができます。 お客様がアプリの内部の構築方法を見ることはできないため、知的財産は保護されます。 体験版アプリを起動するユーザーについて、潜在顧客の情報を収集して共有し、ビジネスの成長に役立てます。

AppSource.com で[公開されているアプリ](https://go.microsoft.com/fwlink/?linkid=848867)の例を次に示します。

![サンプル AppSource 一覧 ](./media/dev-appsource-test-drive/sample-app-source-listing.png)

上記のアプリの一覧から **[無料試用版]** リンクを選択すると、関連付けられている Power Apps Test Drive アプリがユーザーのブラウザー内で直接起動します。

![サンプル アプリ Web プレーヤー](./media/dev-appsource-test-drive/sample-app-web-player.png)

## <a name="how-do-i-build-a-test-drive-solution"></a>体験版ソリューションを構築する方法
体験ソリューション用のアプリの構築は、Power Apps でのアプリの構築と同じですが、外部データ接続ではなく埋め込みデータを使用します。 埋め込みデータを使用すると、お客様にアプリを展開するための障壁を減らすことができるため、お客様に対してお客様による問題の発生を防ぐことができます。最終的に顧客に配布する完全なソリューションには、通常、データ接続が含まれますが、埋め込みデータは体験版ソリューションに適しています。

Power Apps では、埋め込みデータを使用したアプリの構築がネイティブにサポートされているため、アプリで使用するサンプルデータのみが必要です。 このデータは Excel ファイルに 1 つ以上のテーブルとしてキャプチャする必要があります。 Power Apps では、Excel テーブルからアプリにデータを取り込み、外部接続ではなく、そこで操作します。 この後の 3 つの手順のプロセスで、アプリにデータを取得して使用する方法を説明します。

### <a name="step-1-import-data-into-the-app"></a>手順 1: アプリにデータをインポートする
2 つのテーブル **SiteInspector** と **SitePhotos** を含む Excel ファイルがあるとします。

![インポートする Excel テーブル](./media/dev-appsource-test-drive/excel-file.png)

**[静的データをアプリに追加する]** オプションを使用して、これら2つのテーブルを Power Apps にインポートします。

![[静的データをアプリに追加します]](./media/dev-appsource-test-drive/static-data.png)

これでアプリのデータ ソースとしてテーブルが追加されました。

![データ ソースとしてインポートされた Excel テーブル](./media/dev-appsource-test-drive/data-sources.png)

### <a name="step-2-handling-read-only-and-read-write-scenarios"></a>手順 2: 読み取り専用シナリオと読み取り/書き込みシナリオを扱う
インポートしたデータは、*静的*つまり読み取り専用です。 アプリが読み取り専用の場合 (ユーザーへのデータの表示のみを行うアプリなど)、アプリ内でテーブルを直接参照します。 たとえば、**SiteInspector**テーブルの **Title** フィールドにアクセスする場合、式で **SiteInspector.Title** を使用します。

アプリが読み取り/書き込みの場合は、まず各テーブルのデータを、Power Apps の表形式のデータ構造である*コレクション*にプルします。 その後、テーブルではなくコレクションを処理します。 **SiteInspector** テーブルと **SitePhotos** テーブルから **SiteInspectorCollect** コレクションと **SitePhotosCollect** コレクションにデータを取得するには、次のようにします。

```powerapps-dot
ClearCollect( SiteInspectorCollect, SiteInspector ); 
ClearCollect( SitePhotosCollect, SitePhotos )
```

この式では、両方のコレクションがクリアされてから、各テーブルのデータが対応するコレクションに収集されます。

* アプリのどこかでこの式を呼び出して、データを読み込みます。
* アプリのすべてのコレクションを表示するには、 **[ファイル]**  >  **[コレクション]** に移動します。
* 詳しくは、「[アプリのコレクションの作成と更新](../canvas-apps/create-update-collection.md)」をご覧ください。

ここで、**Title** フィールドにアクセスする場合は、式で **SiteInspectorCollect.Title** を使用します。

### <a name="step-3-add-update-and-delete-data-in-your-app"></a>手順 3: アプリのデータを追加、更新、削除する
これまで、データを直接読み取る方法とコレクションから読み取る方法を説明しました。次は、コレクションのデータの追加、更新、削除を行う方法について説明します。

**行をコレクションに追加する**には、[Collect( DataSource, Item, ... )](../canvas-apps/functions/function-clear-collect-clearcollect.md) を使用します。

```powerapps-dot
Collect( SiteInspectorCollect,
    {
        ID: Value( Max( SiteInspectorCollect, ID ) + 1 ),
        Title: TitleText.Text,
        SubTitle: SubTitleText.Text,
        Description: DescriptionText.Text
    }
)
```

**コレクションの行を更新する**には、[UpdateIf( DataSource, Condition1, ChangeRecord1 [, Condition2, ChangeRecord2, ...] )](../canvas-apps/functions/function-update-updateif.md) を使用します。

```powerapps-dot
UpdateIf( SiteInspectorCollect,
    ID = record.ID,
    {
        Title: TitleEditText.Text,
        SubTitle: SubTitleEditText.Text,
        Description: DescriptionEditText.Text
    }
)
```

**コレクションから行を削除する**には、[RemoveIf( DataSource, Condition [, ...] )](../canvas-apps/functions/function-remove-removeif.md) を使用します。

```powerapps-dot
RemoveIf( SiteInspectorCollect, ID = record.ID )
```

> [!NOTE]
> コレクションにデータが保持されるのはアプリが実行している間だけです。アプリが終了すると、すべての変更は破棄されます。

要約すると、埋め込みデータを使用するアプリのアプリのバージョンを作成できます。これを使用して、外部データに接続するアプリのエクスペリエンスをシミュレーションします。 データを埋め込んだら、そのアプリを体験版ソリューションとして AppSource.com に公開する準備が整いました。

## <a name="how-do-i-list-my-test-drive-solution-on-appsourcecom"></a>体験版ソリューションを AppSource.com に登録する方法
アプリの準備ができたので、AppSource.com に公開します。 このプロセスを開始するには、PowerApps.com の[申し込みフォーム](https://powerapps.microsoft.com/partners/get-listed/)に必要事項を入力してください。

申し込みが完了すると、AppSource.com でアプリを公開するために送信する手順が記載された電子メールが届きます。 また、エンドツーエンドのプロセスを詳しく説明している利用開始のドキュメントを[こちらから](https://go.microsoft.com/fwlink/?linkid=851031)ダウンロードできます。

