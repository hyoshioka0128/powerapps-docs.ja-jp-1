---
title: Exit 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の Exit 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/02/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e0ed91cc66f5b42bbea769443ad086476245029c
ms.sourcegitcommit: 49b69129262a9b530e69508e84c3822b742066df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/07/2020
ms.locfileid: "80759805"
---
# <a name="exit-function-in-power-apps"></a>Power Apps の Exit 関数
現在実行中のアプリを終了し、必要に応じて現在のユーザーをサインアウトします。

## <a name="description"></a>説明
**Exit** 関数は、現在実行中のアプリを終了します。 ユーザーはアプリの一覧に返されます。 ユーザーは別のアプリを選択して開くことができます。  

**Exit**は、その他の数式の評価を停止します。 すべての関数呼び出しは、**終了**後に[セミコロン演算子](operators.md)でチェーンされます。   

オプションの*サインアウト*引数を使用して、現在のユーザーを電源アプリからサインアウトします。 *サインアウト*は、ユーザーのセキュリティを確保するためにデバイスを共有する場合に便利です。

アプリの作成中に、 **exit**を呼び出しても、ユーザーは終了しません。  ただし、数式の残りの部分の評価は停止します。

**Exit**は、[動作の数式](../working-with-formulas-in-depth.md)でのみ使用できます。

> [!NOTE]
> Web ブラウザーでのアプリの実行中は、 **Exit**関数を使用したサインアウトはサポートされていません。

## <a name="syntax"></a>構文
**終了**([*サインアウト*])

* *サインアウト*–省略可能。 *True*の場合、現在のユーザーが Power Apps からサインアウトすることを示すブール値。  既定値は*false*で、ユーザーはサインインしたままです。

## <a name="examples"></a>使用例

| [数式] | 説明 | 
| --- | --- | 
| **Exit ()** | 現在のアプリを終了し、ユーザーがサインインしたままにします。  ユーザーはアプリの一覧に返されます。  |
| **Exit (&nbsp;true&nbsp;)** | 現在のアプリを終了し、ユーザーがサインアウトします。 ユーザーは、アプリを実行する前に、資格情報でサインインする必要があります。 | 


