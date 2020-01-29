---
title: キャンバス アプリをテストするためのテスト スタジオの操作 | Microsoft Docs
description: キャンバス アプリをテストするためにテスト スタジオとサンプルを使用する方法について説明します。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/18/2019
ms.author: aheaney
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: afd2427a0c24461fa79e363787a7ec6c28bb4038
ms.sourcegitcommit: 6b2961308c41867756ecdd55f55eccbebf70f7f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/23/2020
ms.locfileid: "76541614"
---
# <a name="working-with-test-studio-experimental"></a>テスト スタジオの操作 (試験段階)

このクイック スタートでは、Kudos というキャンバス アプリを対象にしたテストを作成します。 また、テストの概念を調べて理解し、独自のキャンバス アプリのテストを記述するために適用することもできます。 サンプルの Kudos アプリは、[従業員エクスペリエンス スタート キット](https://powerapps.microsoft.com/en-us/blog/powerapps-employee-experience-starter-kit)からダウンロードできる従業員エンゲージメント アプリ スイートに含まれています。

> [!NOTE]
> この機能はまだ試験段階であり、運用向け以外のアプリのテストの記述に使用することをお勧めします。 詳細については、[試験的な機能とプレビュー機能](working-with-experimental-preview.md)に関する記事を参照してください。

## <a name="open-test-studio"></a>テスト スタジオを開く

他の試験的な機能と同様に、アプリでこれを有効にする必要はありません。 既定では、すべてのキャンバス アプリでテスト スタジオを使用できます。

1. [Power Apps](https://make.powerapps.com) にサインインします。

2. [新しいアプリ](get-started-test-drive.md)を作成するか、[既存のアプリを編集](edit-app.md)します。

3. アプリを Power Apps に保存して、テスト スタジオを開きます。 
    
    > [!NOTE]
    > アプリのテストを記述する前に、アプリを保存する必要があります。

4. 左のナビゲーションにある **[高度なツール]** を選択します。

5. **[テストを開きます]** を選択して、このアプリケーション用にテスト スタジオを開きます。 新しいブラウザー タブでテスト スタジオが開かれます。

    ![テスト スタジオを開く](./media/working-with-test-studio/open-tests.png)

## <a name="create-a-test-suite"></a>テスト スイートの作成

既定では、テスト スイートとテスト ケースがテスト スタジオで自動的に作成されます。 テスト スイートは、テスト ケースを整理するために使用します。 1 つのアプリに 1 つまたは複数のテスト スイートを含めることができます。 既定のテスト スイートとテスト ケースを使用してテストの記述をすぐに開始することも、新しいテスト スイートを作成することもできます。

1. **[新しいスイート]** を選択します。
2. メイン グリッドでフィールドを選択して、**テスト スイートの名前と説明**を更新します。

    ![新しいテスト スイート](./media/working-with-test-studio/new-test-suite.png)

## <a name="create-a-test-case"></a>テスト ケースの作成

テストをどのようにまとめて整理またはグループ化したいかに応じて、1 つのテスト スイートに複数のテスト ケースを作成できます。 各ケースでは、アプリ内の特定の機能または機能のサブセットをテストできます。

1. テスト スイートを選択します。
2. 上部のメニューで **[新しいケース]** を選択して、新しいケースを作成します。
3. メイン グリッドでフィールドを選択して、**テスト ケースの名前と説明**を更新します。

 ![新しいテスト ケース](./media/working-with-test-studio/new-test-case.png)

## <a name="record-a-test-case"></a>テスト ケースの記録

テスト ケースはテスト ステップで構成され、テスト ステップにはアクションが含まれます。 テスト アクションは、タスクを実行する Power Apps 式を使用して記述します。 レコーダーを使用して、アプリを操作しながらテスト ステップを自動的に生成できます。 記録した後、テスト ケースを更新し、新しいステップを追加したり、ステップを削除したり、テスト アサーションを記述してテストの結果を検証することができます。

> [!NOTE]
> 発行済みのアプリのみが記録モードで再生されます。 テスト ケースの記録を開始する前に、アプリに最近の変更を発行します。 最近の変更を発行せずに記録すると、最後に発行されたアプリのバージョンが記録モードで再生されます。

1. 上部のメニューで **[記録]** を選択します。 これにより、発行済みのアプリが記録モードで新しいブラウザー タブに表示されます。

    > [!IMPORTANT]
    > 既存のテスト ケースの上に記録すると、既に存在する既存のテスト ステップがオーバーライドされます。

    ![テストの記録](./media/working-with-test-studio/record-tests.png)

2. アプリを操作します。 操作は、左側のペインで**記録**されます。

3. 操作が完了したら、 **[完了]** を選択します。 必要に応じて **[キャンセル]** を選択して、操作を記録せずにテスト スタジオに戻ることができます。 

    ![記録の保存](./media/working-with-test-studio/save-recording.png)

4. テスト スタジオで自動的に生成されたテスト ステップと式を表示します。
5. 必要に応じて、メイン グリッド内のステップの説明のテキストを編集します。 メイン グリッドで数式を選択して、テスト ステップのアクションを更新することもできます。

    ![テスト ケースの更新](./media/working-with-test-studio/update-test-case.png)

### <a name="add-test-steps-and-test-assertions"></a>テスト ステップとテスト アサーションの追加

すべてのテスト ケースには、予想される結果が必要です。 Kudos の例では、Kudo を送信した場合に想定される結果の 1 つは、Common Data Service データベースに新しいレコードを作成することです。 次に、テスト ケースを更新し、その他のテスト ステップを追加して、レコードが正常に作成されたことを検証します。

レコードが正常に作成されたことを確認するには、次の手順が必要です。

- テスト ケースの先頭で、データベース内の Kudo レコード カウントを表す変数を初期化します。
- テスト ケースの最後に、データベース内の Kudo レコード カウントを表す変数を初期化します。
- カウントが 1 ずつ増分されていることを検証するためのテスト アサーション式を記述します。 カウントが 1 ずつ増加していない場合、テスト アサーションは失敗し、テスト ケースが失敗します。

Kudos アプリにテスト ステップとテスト アサーションを追加するには:

1. ステップ 1 またはその上に新しいステップを挿入するステップを選択します。 

2. 上部のメニューから **[上にステップを挿入]** を選択するか、アクティブな行からこのオプションを選択します。 これで空のステップが作成されます。

    ![ステップの挿入](./media/working-with-test-studio/insert-step-above.png)

    > [!NOTE]
    > **[上にステップを挿入]** を選択すると、現在のステップの上に新しい空のステップが追加されます。 それ以外に **Assert**、**SetProperty**、**Select** または **Trace** アクションを使用することもできます。 これにより、編集可能な各アクション式がステップに追加されます。

3. ステップの説明を更新します。 たとえば、"Count Kudo in database" (データベース内の Kudo をカウントする) とします。

4. アクションの入力に、テスト実行前にデータベース内のレコードをカウントする式または数式を入力します。

    サポートされている任意の式を使用できます。 また、アプリに含まれているデータ ソース、コレクション、変数、実行フローのクエリを実行したり、テストで使用する新しいグローバル変数やコレクションを作成したりすることもできます。

    ```Set(kudosBeforeTest, CountRows(Filter(Kudos, Receiver.Email = "someone@example.com")))```

5. ステップ 2 またはその上に新しいステップを挿入するステップを選択します。

6. 上部のメニューから **[上にステップを挿入]** を選択するか、アクティブな行からこのオプションを選択します。 これで空のステップが作成されます。

7. アクションの入力に、*kudosBeforeTest* 値を[トレース](./functions/function-trace.md)してテスト結果レコードに書き込む式または数式を入力します。

    ```Trace("kudosBeforeTest : " & kudosBeforeTest);```

    ![テスト前の Kudos](./media/working-with-test-studio/kudos-before-test.png)

8. テスト ケースの下部に進み、テスト完了後にデータベース内のレコードをカウントする新しいステップを挿入します。

    ```Set(kudosAfterTest, CountRows(Filter(Kudos, Receiver.Email = "someone@example.com")))```

9. データベースのレコード カウントが 1 だけ増加したことを検証する最後のステップを追加し、次のアサーション アクションを入力して、これを確認します。

    ```Assert(kudosAfterTest = kudosBeforeTest + 1, "Kudos count incorrect. Expected : " & kudosBeforeTest + 1  & " Actual :" & kudosAfterTest)```

    ![テスト後の Kudos のアサート](./media/working-with-test-studio/kudos-after-test-assert.png)

10. テスト スタジオの右上のメニューからテスト ケースを保存します。 

## <a name="play-back-your-test"></a>テストの再生

記録されたテストを再生して、アプリの機能を検証することができます。 1 つのテスト スイートまたは 1 つのテスト ケース内の、すべてのテストを再生できます。 

最近行った変更がある記録を再生する前に、アプリを発行する必要があります。

![発行せずに再生する](./media/working-with-test-studio/publish-test-studio-changes.png)

> [!IMPORTANT]
> スキップした場合、記録の再生にテストの最新の変更は含まれません。 最後に発行されたテスト ケースまたはテスト スイートが、アプリに対して再生されます。

1. **[発行]** をクリックします。 これにより、テストが自動的に保存され、発行されます。

    ![変更の発行](./media/working-with-test-studio/publish-button.png)

2. テスト スイートまたは 1 つのテスト ケースを選択します。

3. **[再生]** をクリックします。 発行されたアプリが**再生**モードで開き、テスト ステップが自動的に再生されることを確認できます。 緑のチェック マークは、テスト ステップが正常に実行されたことを示します。 ステップが失敗した場合は、エラー メッセージと共に赤いエラー インジケーターが表示されます。

    ![再生モード](./media/working-with-test-studio/play-mode.png)

4. [完了] をクリックしてテスト スタジオに戻ります。

### <a name="failed-assertion"></a>失敗したアサーション

このセクションでは、テスト アサーションを変更して、失敗するテストを実行します。

1. 式のボックスを選択して、アサーション ステップを編集します。

2. テスト アクションの ```+ 1``` を ```+ 2``` に更新します。 これは、テストで 2 つのレコードが作成されることを想定していることを意味しますが、この想定は正しくありません。 テストが成功していれば、データベースにはレコードが 1 つだけ作成されているはずです。

    ```Assert(kudosAfterTest = kudosBeforeTest + 2, "Kudos count incorrect. Expected : " & kudosBeforeTest + 2  & " Actual :" & kudosAfterTest)```

    ![カウント更新のアサート](./media/working-with-test-studio/assert-count-update.png)

3. **[発行]** を選択します。

4. **[再生]** を選択します。

5. テストの再生を表示します。 最後のステップが失敗し、エラーと、アサーション ステップに指定したメッセージが表示されます。  

    ![再生エラー](./media/working-with-test-studio/playback-error.png)

### <a name="playing-tests-in-a-browser"></a>ブラウザーでのテストの再生

リンクをコピーして、テスト スタジオ外部の別のブラウザーでテストを再生することもできます。 こうすると、**Azure DevOps** などの継続的なビルドとリリースのパイプラインにテストを統合できます。

選択したテストの再生リンクは持続的なものです。 テスト スイートまたはテスト ケースで変更されることはありません。 ビルド プロセスやリリース プロセスを変更することなく、テストを更新できます。

ブラウザーでテストを再生するには:

1. 右側のペインでテスト スイートまたはテスト ケースを選択します。

2. **[再生リンクのコピー]** をクリックします。

    ![再生リンクのコピー](./media/working-with-test-studio/copy-play-link.png)

3. 発行されていない変更がある場合は、テストを発行するように求められます。

    ![リンクをコピーする前に発行する](./media/working-with-test-studio/publish-before-copy-link.png)

4. 発行プロセスをスキップして再生リンクをコピーすることを選択できます。 スキップした場合、テストに対する新しい変更は再生されません。

    ![再生リンクのコピー](./media/working-with-test-studio/copy-play-link-ack.png)

5. ブラウザーを開き、URL をアドレス バーに貼り付けてテストを再生します。

6. テストの再生を表示します。

## <a name="processing-test-results"></a>テスト結果の処理

ブラウザーを使用する場合、テスト スタジオでのテスト再生時に表示されるテスト パネルは表示されません。 このため、実行する特定のテスト ステップを判別することや、テストが成功または失敗したかどうかを判断することはできません。

テスト スタジオの外部でテスト結果を確認するために、テスト オブジェクトで使用可能な **OnTestCaseComplete** および **OnTestSuiteComplete** という 2 つのプロパティがあり、テストの結果を処理するために使用できます。 **Azure DevOps** のような継続的なビルドとリリースのパイプラインにテストを統合する場合は、これらのプロパティを使用して、アプリのデプロイを続行する必要があるかどうかを判断できます。

これらのプロパティに入力した式は、各ケースまたはスイートが完了するとトリガーされます。 これらのプロパティをカスタマイズしてテストの結果を処理し、次のようなさまざまなデータ ソースまたはサービスに送信することができます。

- SQL Server :
- Common Data Service
- Power Automate
- Office 365 を使用した電子メール

これらの設定は、アプリ内のすべてのテスト スイートまたはテスト ケースに適用されます。 各テスト スイートまたはテスト ケースが完了すると、テスト結果とテストに含まれるすべてのトレース メッセージが、**TestCaseResult** レコードと **TestSuiteResult** レコードで使用できるようになります。

**TestCaseResult** レコードには、次のプロパティが含まれています。

- *TestCaseName* – テスト ケースの名前。
- *TestCaseId* – テスト ケースの ID。
- *TestSuiteName* – ケースが属するテスト スイートの名前。
- *TestSuiteId* – ケースが属するテスト スイートの ID。
- *StartTime* – テストの実行開始時刻。
- *EndTime* – テストの実行終了時刻。
- *Trace* – テスト アサーションの結果と、Trace 関数からのメッセージ。
- *Success* – テスト ケースが正常に完了したかどうかを示します。
- *TestFailureMessage* – ケースが失敗した場合のエラー メッセージ。

**TestSuiteResult** レコードには、次のプロパティが含まれています。 

- *TestSuiteName* – テスト スイートの名前。
- *TestSuiteId* – テスト スイート ID。
- *StartTime* – テスト スイートの実行開始時刻。
- *EndTime* – テスト スイートの実行終了時刻。
- *TestsPassed* – スイート内の正常に完了したテスト ケースの数。
- *TestsFailed* - スイート内の失敗したテスト ケースの数。

このクイックスタートでは、Common Data Service データベースに 2 つのカスタム エンティティを作成し、**OnTestCaseComplete** および **OnTestSuiteComplete** プロパティをカスタマイズして、テスト結果を格納します。

1. 左側のペインで **[テスト]** をクリックするか、スイートのヘッダーの **[表示]** をクリックします。

    ![設定されたプロパティのテストまたは表示](./media/working-with-test-studio/test-or-view-to-set-property.png)

2. **OnTestCaseComplete** アクションを選択します。

3. テストの結果を処理するための式を入力します。 次のサンプルでは、Common Data Service のカスタム AppTestResults エンティティに各テスト ケースの結果を保存します。 必要に応じて、テスト結果を SQL、SharePoint、またはその他のデータ ソースに格納できます。 データ ソースの Trace フィールドを必要に応じて設定または増加させることが必要になる場合があります。

    > [!NOTE]
    > 次のサンプルでは、[Common Data Service 接続](https://docs.microsoft.com/connectors/commondataservice/)が必要です。 [簡単なアプリ](data-platform-create-app.md)を作成することも、Common Data Service を使用して[アプリをゼロから作成する](data-platform-create-app-scratch.md)こともできます。 また、次のサンプルで使用されているデータ ソースのレコードを変更する方法の詳細については、[Patch](./functions/function-patch.md) 関数リファレンスを参照してください。

    ```
    //Save to Common Data Service
    Patch(AppTestResults
    , Defaults(AppTestResults)
    , {
             TestPass: TestCaseResult.TestCaseName & ":" & Text(Now())
             ,TestSuiteId: TestCaseResult.TestSuiteId
             ,TestSuiteName: TestCaseResult.TestSuiteName
             ,TestCaseId: TestCaseResult.TestCaseId
             ,TestCaseName: TestCaseResult.TestCaseName
             ,StartTime: TestCaseResult.StartTime
             ,EndTime: TestCaseResult.EndTime
             ,TestSuccess: TestCaseResult.Success
             ,TestTraces: JSON(TestCaseResult.Traces)
             ,TestFailureMessage: TestCaseResult.TestFailureMessage
    }
    );
    ```
    ![OnTestCaseComplete example.png](./media/working-with-test-studio/ontestcasecomplete-example.png)

4. **OnTestSuiteComplete** アクションを選択します。

5. テストの結果を処理するための式を入力します。 次の例では、Common Data Service のカスタム AppTestSuiteResults エンティティに各テスト スイートの結果を保存します。 

    ```
    //Save to Common Data Service
    Patch(AppTestSuiteResults
        , Defaults(AppTestSuiteResults)
        , {
             TestSuiteId: TestSuiteResult.TestSuiteId
             ,TestSuiteName: TestSuiteResult.TestSuiteName
             ,StartTime: TestSuiteResult.StartTime
             ,EndTime: TestSuiteResult.EndTime
             ,TestPassCount: TestSuiteResult.TestsPassed
             ,TestFailCount: TestSuiteResult.TestsFailed
        }
    );
    ```

    ![OnTestSuiteComplete example.png](./media/working-with-test-studio/ontestsuitecomplete-example.png)

これらのプロパティで使用できるその他の式の例を次に示します。

- 結果を Power Automate のフローに送信する。

    ```MyTestResultsFlow.Run(JSON(TestCaseResult))```

- 結果を電子メールで送信する:

    ```Office365.SendMailV2(“someone@example.com”, “Test case results”, JSON(TestCaseResult, JSONFormat.IndentFour))```

- テスト結果のアプリ通知を受信する:

  たとえば、テスト スタジオ外部のブラウザーでテストを実行した場合、テスト完了後に通知を受け取ります。

    ```
    Notify(TestCaseResult.TestCaseName & " : "
            & If( TestCaseResult.Success
                , " Passed"
                , TestCaseResult.TestFailureMessage)
            ,If(  TestCaseResult.Success
                , NotificationType.Success
                , NotificationType.Error)
    )
    ```

## <a name="test-functions"></a>テスト関数

Power Apps で使用可能な[関数](formula-reference.md)に加えて、テストを作成するときに通常使用する一般的な関数を次に示します。

- [選択](./functions/function-select.md)
- [SetProperty](./functions/function-setproperty.md)
- [Filter](./functions/function-assert.md)
- [トレース](./functions/function-trace.md)
