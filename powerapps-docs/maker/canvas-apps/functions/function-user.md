---
title: User 関数 | Microsoft Docs
description: 構文を含む PowerApps の User 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f95a6f7769cde01e99bc4c18fab0ae60ae6b8c96
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74680146"
---
# <a name="user-function-in-powerapps"></a>PowerApps の User 関数
現在のユーザーに関する情報を返します。

## <a name="description"></a>Description
**User** 関数は現在のユーザーに関する情報の[レコード](../working-with-tables.md#records)を返します。

| プロパティ | Description |
| --- | --- |
| **User().Email** |現在のユーザーの電子メール アドレス。 |
| **User().FullName** |姓名を含む、現在のユーザーのフル ネーム。 |
| **User().Image** |現在のユーザーの画像。 これは、フォーム "blob:*identifier*" の画像の URL になります。 **[画像](../controls/control-image.md)** コントロールの **[Image](../controls/properties-visual.md)** プロパティをこの値に設定し、アプリで画像を表示します。 |

> [!NOTE]
> 返される情報は、現在の Power Apps ユーザー用です。  これは、作成されたアプリの外部にある、Power Apps のプレーヤーと studio に表示される "アカウント" 情報と一致します。  これは、Office 365 または他のサービスの現在のユーザーの情報とは一致しない場合があります。

## <a name="syntax"></a>構文
**User**()

## <a name="examples"></a>例
現在の Power Apps ユーザーには、次の情報が含まれています。

* フル ネーム: **"John Doe"**
* メール アドレス: **"john.doe@contoso.com"**
* 画像: ![](media/function-user/john-doe-picture.png) 

|       数式       |                                                                    Description                                                                    |                                                 結果                                                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|     **User()**      |                                             現在の Power Apps ユーザーのすべての情報の記録。                                             |    { FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678" }    |
|  **User().Email**   |                                                 現在の Power Apps ユーザーの電子メールアドレス。                                                  |                                         "john.doe@contoso.com"                                          |
| **User().FullName** |                                                   現在の Power Apps ユーザーの完全な名前。                                                    |                                               "John Doe"                                                |
|  **User().Image**   | 現在の Power Apps ユーザーのイメージの URL。  **画像**コントロールの **Image** プロパティをこの値に設定し、アプリで画像を表示します。 | "blob: 1234... 5678"<br><br>**ImageControl.Image** を使用:<br>![](media/function-user/john-doe-picture.png) |

