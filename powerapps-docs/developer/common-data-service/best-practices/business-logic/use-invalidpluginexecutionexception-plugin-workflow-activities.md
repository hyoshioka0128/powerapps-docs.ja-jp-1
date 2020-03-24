---
title: プラグインおよびワークフロー活動で InvalidPluginExecutionException を使用する | MicrosoftDocs
description: エラーをプラグインまたはワークフロー活動で上げる場合は InvalidPluginExecutionException を使用します。
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: ryjones
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/5/2020
ms.author: JimDaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 0657e9b39713f4f11d68daac1c60fa144dc6ab08
ms.sourcegitcommit: 629e47c769172e312ae07cb29e66fba8b4f03efc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "3109140"
---
# <a name="use-invalidpluginexecutionexception-in-plug-ins-and-workflow-activities"></a>プラグインおよびワークフロー活動で InvalidPluginExecutionException を使用する

**カテゴリ**: 保守性、ユーザビリティ

**影響の可能性**: 中程度

<a name='symptoms'></a>

## <a name="symptoms"></a>現象

同期プラグインがプラットフォームに <xref:Microsoft.Xrm.Sdk.InvalidPluginExecutionException> 以外の例外を返す場合、Power Apps クライアント上でエラーがスタック トレース付きの例外メッセージ <xref:System.Exception.Message>  とともに表示されます。 これは、すでに発生している可能性のある不満を感じる状況で、好ましくないユーザー エクスペリエンスを提供します。

データ検証のロジックに問題があり、操作を意図的にキャンセルするために <xref:Microsoft.Xrm.Sdk.InvalidPluginExecutionException> を使用している場合、アプリケーション ユーザーに適用可能なガイダンスを提供して、問題を修正して続行できるようにする必要があります。

エラーが予期しないものである場合、エラーをキャッチし、<xref:Microsoft.Xrm.Sdk.InvalidPluginExecutionException> に変換することをお勧めします。ユーザーや技術スタッフが問題をすばやく特定できるように、アプリケーションにガイダンス付きのわかりやすいエラーメッセージを表示できます。

<a name='guidance'></a>

## <a name="guidance"></a>ガイダンス

プラグインは、次の理由からのみ <xref:Microsoft.Xrm.Sdk.InvalidPluginExecutionException> を返します。

- ユーザーに対して役に立つメッセージを表示する
- イベント ログ / トレース ファイルの肥大化を回避する

メッセージを <xref:Microsoft.Xrm.Sdk.InvalidPluginExecutionException> に変換しないと、Power Apps クライアントからユーザーにメッセージが表示されない `IsvUnExpected` エラーが発生します。

<a name='problem'></a>

## <a name="problematic-patterns"></a>問題となるパターン

> [!WARNING]
> これらのパターンは、回避する必要があります。

エラー メッセージ テキスト内で HTML を使用しないでください。 

CDS データにアクセスする Web アプリケーションは、ユーザーに表示する前にエラー メッセージ テキストを HTML にエンコードする必要があります。 これにより、メッセージ内の HTML が意図したとおりに表示されなくなります。 HTML コードを表示するだけです。


<a name='seealso'></a>

### <a name="see-also"></a>関連項目

[操作のキャンセル](../../handle-exceptions.md#cancelling-an-operation)<br/>
[ワークフロー活動のデバッグ](../../workflow/workflow-extensions.md#debug-workflow-activities)<br/>