---
title: Notify 関数 |Microsoft Docs
description: 構文と例を含む Power Apps の Notify 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 02/28/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bc3a27960a95b47115e1b7a43863572ce0c44334
ms.sourcegitcommit: ed583eb94720a9645bfd79776311792a958077b8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2020
ms.locfileid: "78204394"
---
# <a name="notify-function-in-power-apps"></a>Power Apps での通知機能
バナー メッセージをユーザーに表示します。

## <a name="description"></a>説明
**Notify** 関数を使用すると、画面の上部に現在表示されている内容の上に重ねて、バナー メッセージがユーザーに表示されます。  通知は、ユーザーがメッセージを閉じるか、別の通知を置き換えるか、タイムアウトの期限が切れるまで、既定で10秒に設定されます。

メッセージの種類に応じて適切な色とアイコンが使用されます。   種類は、関数の 2 つ目の引数で指定します。

| NotificationType 引数 | 説明 |
| --- | --- |
| **NotificationType.Error** | メッセージをエラーとして表示します。 |
| **NotificationType.Information** (既定) | メッセージを情報提供として表示します。  |
| **NotificationType.Success** | メッセージを成功として表示します。 |
| **NotificationType.Warning** | メッセージを警告として表示します。 |

アプリの作成中と、エンド ユーザーがアプリを使用しているときの両方でメッセージが表示されます。

**Notify** は、[動作の数式](../working-with-formulas-in-depth.md)内でのみ使用できます。

**Notify** は [**IfError**](function-iferror.md) 関数と組み合わせて、エラーを検出し、カスタム エラー メッセージを使って報告することができます。

Power Apps は、**通知**とはまったく異なるメカニズムを使用してプッシュ通知を送信することもできます。  詳細については[、「Power Apps で通知を送信する](../add-notifications.md)」を参照してください。

**Notify** は、常に *true* を返します。

注: この関数は、以前は **ShowError** という名前で、エラー メッセージのみを表示できました。

## <a name="syntax"></a>構文
**Notify**( *Message* [, *NotificationType* [, *Timeout* ]])

* *Message* – 必須。  ユーザーに表示するメッセージです。
* *NotificationType* – 省略可能。  前述の表の表示できるメッセージの種類。  既定は **NotificationType.Information** です。  
* *Timeout* –省略可能。  通知を自動的に終了するまでの待機時間 (ミリ秒単位)。  既定値は10秒 (1万ミリ秒) です。  *タイムアウト*が0の場合、通知は無期限に表示されます。

## <a name="examples"></a>使用例

### <a name="step-by-step"></a>操作手順

1. 画面に**ボタン** コントロールを追加します。

2. **Button** の **OnSelect** プロパティを次のように設定します。

    **Notify( "Hello, World" )**

3. ボタンをクリックするか、押します。  

    ボタンがクリックされるたびに、**Hello, World** というメッセージが情報提供としてユーザーに表示されます。  ユーザーがこのボタンを閉じるか、もう一度ボタンを押すと、自動的に10秒 (既定のタイムアウト) で破棄されます。

    ![作成環境で、Button.OnSelect により Notify が呼び出され、その結果ユーザーに対して青色のバナー メッセージで "Hello, World" のメッセージが表示されている図](media/function-showerror/hello-world.png)

4. エラーを示すようにメッセージの種類を変更します。  次の式に 2 つ目の引数を追加します。

    **Notify( "Hello, World", NotificationType.Error )**

5. ボタンをクリックするか、押します。

    これで、ボタンがクリックされるたびに、**Hello, World** というメッセージがエラーとしてユーザーに表示されます。  ユーザーがこのボタンを閉じるか、もう一度ボタンを押すと、自動的に10秒 (既定のタイムアウト) で破棄されます。

    ![作成環境で、Button.OnSelect により Notify が呼び出され、その結果ユーザーに対して赤色のバナー メッセージで "Hello, World" のメッセージが表示されている図](media/function-showerror/hello-world-error.png)

4. 警告を示すようにメッセージの種類を変更します。  次の式の 2 つ目の引数を変更します。

    **Notify ("Hello, World", NotificationType, 4000)**

5. ボタンをクリックするか、押します。

    これで、ボタンがクリックされるたびに、**Hello, World** というメッセージが警告としてユーザーに表示されます。  ユーザーがこのボタンを閉じるか、もう一度ボタンを押すと、自動的に4秒 (4000 ミリ秒) 後に破棄されます。

    ![作成環境で、Button.OnSelect により Notify が呼び出され、その結果ユーザーに対してオレンジ色のバナー メッセージで "Hello, World" のメッセージが表示されている図](media/function-showerror/hello-world-warning.png)

4. 成功を示すようにメッセージの種類を変更します。  次の式の 2 つ目の引数を変更します。

    **Notify ("Hello, World", NotificationType, 0)**

5. ボタンをクリックするか、押します。

    これで、ボタンがクリックされるたびに、**Hello, World** というメッセージが成功としてユーザーに表示されます。  タイムアウトが**0**の場合、通知はユーザーによって破棄されるか、もう一度ボタンを押して終了します。

    ![作成環境で、Button.OnSelect により Notify が呼び出され、その結果ユーザーに対して緑色のバナー メッセージで "Hello, World" のメッセージが表示されている図](media/function-showerror/hello-world-success.png)
