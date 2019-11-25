---
title: モデル駆動型アプリのクライアント API リファレンス | Microsoft Docs
description: このトピックでは、モデル駆動型アプリのクライアント API 参照を提供します。
ms.date: 06/27/2019
ms.service: powerapps
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
ms.assetid: ''
author: KumarVivek
ms.author: kvivek
manager: amyla
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: b4e2d49c8017011a9a7a8682843612533698990b
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2748874"
---
# <a name="client-api-reference-for-model-driven-apps"></a>モデル駆動型アプリのクライアント API リファレンス



このセクションでは、JavaScript ライブラリに使用できるクライアント API オブジェクト モデルのリファレンス ドキュメントが含まれています。

> [!IMPORTANT]
> - クライアント API オブジェクト モデルにも **Xrm.Internal** 名前空間が含まれており、この名前空間のオブジェクト/メソッドの使用はサポートされていません。 これらのオブジェクト、および HTML ドキュメント オブジェクト モデル (DOM)のいかなる部分は、将来予告なし変更される場合があります。 これらの機能やDOM に依存するスクリプトを使用しないことをお勧めします。
> - デバッグ中に、 文書化されていないメソッドおよびオブジェクトがクライアント API オブジェクト モデルに見つかることもあります。 ドキュメント化されているオブジェクトおよびメソッドのみがサポートされます。
> - このドキュメントで使用できるクライアント スクリプト API は Dynamics 365 Customer Engagement (on-premises)にも適用されます。

このセクションでのトピックは次のように分類されます。
- すべてのイベント、収集、および実行コンテキスト オブジェクトの参照を開始します。
- Customer Enagagement の**属性**および**コントロール**のメソッドに関する情報を継続的に提供します。それらは実際にはクライアント API オブジェクト モデルのさまざまなオブジェクトの下に表示されるコレクションです。
- **formContext** および **gridContext** オブジェクトのプロパティとメソッドの参照を提供します。
- 最後に **Xrm** オブジェクト モデルの名前空間の参照を提供します。 

### <a name="related-topics"></a>関連トピック

[モデル駆動型アプリでクライアント スクリプトを使用してビジネス ロジックを適用](../client-scripting.md)<br/>
[クライアント API オブジェクト モデルについて](understand-clientapi-object-model.md)<br/>
[モデル駆動型アプリの開発者向けの概要](../overview.md)
