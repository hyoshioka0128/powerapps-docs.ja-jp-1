---
title: ソリューション発行者の概要 | MicrosoftDocs
ms.custom: ''
ms.date: 02/03/2020
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: ece684h8-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: b54afabbed9e7dfcc53fe887f600593e77a02a7f
ms.sourcegitcommit: cb533c30252240dc298594e74e3189d7290a4bd7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "3017575"
---
# <a name="solution-publisher-overview"></a>ソリューション発行者の概要

作成したアプリや加えたカスタマイズもソリューションの一部です。 すべてのソリューションには発行者がいます。 ソリューションを作成する際に発行元を指定します。 

> [!div class="mx-imgBorder"] 
> <img src="media/solution-publisher-select.png" alt="Select solution publisher" height="731" width="416">

ソリューションの発行者は、アプリの開発者を指定します。 接頭辞を確認することで、どのソリューションが項目を追加したかを簡単に知ることができます。 これらの理由から、ソリューション発行者を作成し、分かりやすい接頭辞を指定する必要があるのです。 これは、読み込んだソリューションに含まれるメタ データ項目を表示する場合に特に重要となります。 たとえば、資金調達のサンプル アプリを含むソリューションでは、発行者の接頭辞として *サンプル* を使用します。 

> [!div class="mx-imgBorder"] 
> ![資金調達ソリューション発行者の接頭辞](media/fundraiser-sample-app-prefix.png)

> [!NOTE]
> ソリューション発行者の接頭辞を変更する場合は、新しいアプリ、またはメタデータ項目を作成する前に変更をしておく必要があります。 メタデータ項目の名前を変更することはできません。 

## <a name="common-data-services-default-solution"></a>Common Data Service の既定のソリューション
Power Apps の既定のソリューションは Common Data Service の既定のソリューションでもあり、これは Common Data Service の既定のパブリッシャーと関連付けられています。 この発行元には、既定の発行元の接頭辞がランダムに割り当てられます。たとえば、接頭辞として *cr8a3* などが割り当てられます。 つまり、既定のソリューションで作成されるメタデータの新たな項目の名前の先頭には、そのアイテムを一意に識別するために使用される名前が付加されます。 たとえば、 *動物* という名前の新しいエンティティを作成する場合、Common Data Service が使用する一意の名称は *cr8a3_animal*となります。 これは、新しいフィールド (属性)、関連付け、オプション セットのオプションについても同様です。 既定のソリューションをカスタマイズする場合は、発行元の接頭辞を変更することを検討してください。 

## <a name="create-a-solution-publisher"></a>ソリューション発行者の作成
1.  Power Apps ポータルで **設定** (歯車)を選択し、 続いて **高度な設定** を選択します。 
2.  **設定** > **カスタマイズ** > **発行元**を選択します。 
3.  **発行元のメイン ビュー**コマンドバーで、 **新規**を選択します。 
4.  必須となるの情報を入力します: 
   - **表示名**: 発行元の表示名称を入力します。 
   - **名前**. 発行元の一意の名称を入力します。 
   - **接頭辞**:  お好みの発行元の接頭辞を入力します。 
   -    **オプション値の接頭辞**。 このフィールドは、発行元の接頭辞に基づいた番号を生成します。 この番号は、オプション セットにオプションを追加する際に使用し、オプションを追加するのに使用したソリューションを識別する助けとなります。 
   - **取引先担当者の詳細**。 オプションで、連絡先と住所の情報を追加できます。
5. **保存して閉じる**を選択します。

## <a name="change-a-solution-publisher"></a>ソリューションの発行元を変更する
管理されていないソリューションの発行者を変更するには、次の手順に従ってください:
1.  Power Appsポータルで、 **ソリューション** を選択し、 **…** を選択します 変更するソリューションの **設定** を選択します。 
2.  **ソリューション設定** ウィンドウで、 **発行元の編集** を選択します。 
3.  **表示名称** と **接頭辞** フィールドの値を変更します。 **オプション値の接頭辞** フィールドは、発行元の接頭辞に基づいた番号を生成します。 この番号は、オプション セットにオプションを追加する際に使用し、オプションを追加するのに使用したソリューションを識別する助けとなります。 
4.  接頭辞に加えて、 **連絡先** セクションのソリューション発行者の表示名称、連絡先情報、アドレスを変更することもできます。 
5.  **保存して閉じる**を選択します。

### <a name="see-also"></a>関連項目
[ソリューションの作成](create-solution.md)