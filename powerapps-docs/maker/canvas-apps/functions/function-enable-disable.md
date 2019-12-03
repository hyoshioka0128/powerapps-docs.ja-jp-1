---
title: Enable および Disable 関数 | Microsoft Docs
description: 構文と例を含む Power Apps の Enable および Disable 関数の参照情報
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: af1522934bcfee13c00950a3686583393699d0ad
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "74731101"
---
# <a name="enable-and-disable-functions-in-power-apps"></a>Power Apps での関数の有効化と無効化
[シグナル](signals.md) を有効または無効に切り替えます。

## <a name="overview"></a>概要
いくつかのシグナルは頻繁に変化する場合があるため、アプリはその度に再計算を行う必要があります。  長期間にわたる頻繁な変更によって、デバイスのバッテリが消耗することがあります。 これらの関数を使用すると、手動でシグナルを有効または無効にすることができます。

シグナルは使用されていない場合、自動的に無効になります。

## <a name="description"></a>Description
**Enable** 関数と **Disable** 関数はそれぞれ、シグナルを有効および無効に切り替えます。

これらの関数は、現在、 **[Location](signals.md)** シグナルのみに有効です。

これらの関数には、戻り値がありません。 これらの関数は、[動作の数式](../working-with-formulas-in-depth.md)内でのみ使用できます。

## <a name="syntax"></a>構文
**Enable**( *Signal* )<br>**Disable**( *Signal* )

* *Signal* - 必須。  有効または無効にするシグナル。

