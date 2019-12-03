---
title: キャンバス アプリの現在のユーザーに関する詳細の表示 | Microsoft Docs
description: Power Apps で、サインインしているユーザーの名前と電子メールアドレスを canvas アプリに表示する
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/16/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f77ec80cfaf579c836277f0e29d3b84b325a0462
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74674612"
---
# <a name="show-information-about-a-power-apps-user-in-a-canvas-app"></a>Power Apps ユーザーに関する情報を canvas アプリに表示する

Power Apps で、フルネーム、電子メールアドレス、および canvas アプリにサインインしたユーザーに関連付けられている画像を表示します。 この情報を使用すると、たとえば、自動的にフォームへの入力を行うことができます。

たとえば、この機能を使うと次のことができます。

* ユーザー用のサインアップ "シート" を作成する (トレーニング、イベントのボランティア、券売機での発券など)。
* 人事管理アプリでフル ネームを表示する。
* ヘルプデスクへの問い合わせ時に電子メール アドレスを自動的に入力する。

基本的にこの機能は、フォームやラベルの自動入力を活かすことができる部分であれば、どこにでも利用できます。

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="show-user-details"></a>ユーザー情報を表示する

1. **[挿入]** タブの **[メディア]** をクリックまたはタップし、 **[画像]** をクリックまたはタップします。
   
   ![][2]
2. **[Image](controls/properties-visual.md)** プロパティを次の数式に設定します。
   <br>**User().Image**
   
    ![][3]
3. **[挿入]** タブの **[テキスト]** をクリックまたはタップし、 **[ラベル]** をクリックまたはタップします。  
   
    ![][4]
4. **[Text](controls/properties-core.md)** プロパティを次の数式に設定します。
   <br>**User().FullName**
   
   ![][6]
   
   これを実行すると、ラベルにフル ネームが自動的に設定されます。 次のように、ラベルをイメージ コントロールの下に移動します。
   
   ![][5]
5. 別のラベルを追加し、その **[Text](controls/properties-core.md)** プロパティを次の数式に設定します。
   <br>**User().Email**  
   
    ![][8]
   
    これを実行すると、ラベルに電子メール アドレスが自動的に設定されます。 このラベルを、次のように 1 つ目のラベルの下に移動します。  
   
    ![][7]

[2]: ./media/show-current-user/add-image.png
[3]: ./media/show-current-user/imageproperty.png
[4]: ./media/show-current-user/insertlabel.png
[5]: ./media/show-current-user/label.png
[6]: ./media/show-current-user/textproperty.png
[7]: ./media/show-current-user/secondlabel.png
[8]: ./media/show-current-user/email.png
[9]: ./media/show-current-user/preview.png
