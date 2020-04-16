---
title: コンポーネント実装ライブラリ | Microsoft Docs
description: JavaScript や TypeScript を使用してコード コンポーネントを作成する
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d100dc3-bd82-4b45-964c-d90eaebc0735
ms.openlocfilehash: febda5c1c52b482db449b370d114c771cb2984eb
ms.sourcegitcommit: 310dd3dc68ffebe6a416450836ac0ba988b84fb4
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "3162172"
---
# <a name="component-implementation-library"></a>コンポーネント実装ライブラリ

Power Apps component framework を使用してコード コンポーネントを開発する場合、コンポーネント ライブラリの実装は重要なステップのひとつです。 開発者は TypeScript を使用してコンポーネント ライブラリを実装できます。

各コード コンポーネントは、コード コンポーネント インタフェースに記述されたメソッドを実装したオブジェクトを返すことができる、関数の定義を含むライブラリが必要となります。 

オブジェクトは次のメソッドを実装します:

- [init](reference/control/init.md) (必須)
- [updateView](reference/control/updateview.md) (必須)
- [getOutputs](reference/control/getoutputs.md) (オプション)
- [destroy](reference/control/destroy.md) (必須)

これらのメソッドはコード コンポーネントのライフサイクルを制御します。

