---
title: '開発者: Common Data Service のベスト プラクティスとガイダンス | Microsoft Docs'
description: Power Apps での Common Data Service の開発のためのベスト プラクティスとガイダンス。
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/07/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 24a873eab99dc8e453d18f5bf32f1f5c56903008
ms.sourcegitcommit: 6b27eae6dd8a53f224a8dc7d0aa00e334d6fed15
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2019
ms.locfileid: "2883541"
---
# <a name="best-practices-and-guidance-for-the-common-data-service"></a>Common Data Service に関するベスト プラクティスとガイダンス

 Common Data Service は、開発者が柔軟にカスタマイズして調整したエクスペリエンスを構築できるようにする拡張可能なフレームワークです。 Common Data Service をカスタマイズ、拡張、または統合しながら、開発者はすでに確立されたガイダンスやベスト プラクティスを認識している必要があります。 

このセクションでは、Microsoft で特定した問題とその影響について学習し、それらを解決するためのガイダンスを理解します。 ここでは、特定の手法の理由についての背景と、将来遭遇するかもしれない問題の回避について説明します。 これは、環境の使いやすさ、サポート、パフォーマンスのメリットになります。 ガイダンス ドキュメントは、管理者ガイド ページ内の既存の情報をサポートします。

## <a name="targeted-customization-types"></a>対象カスタマイズの種類
ドキュメントは、次の種類のカスタマイズを対象とします:

- ユーザー定義ワークフロー活動およびプラグイン
- Common Data Service データと作業する
- Common Data Service を拡張する統合

## <a name="sections"></a>セクション
各ガイダンス記事には、次のセクションのほとんどまたはすべてが含まれます:

- タイトル - ガイダンスの説明
- カテゴリ - ガイダンスに従わないことによって影響を受ける 1 つ以上の領域
- 影響の可能性 - ガイダンスに従わないことによって環境が影響を受けるリスク (高、中、低)
- 現象 - ガイダンスに従わなかったことで発生する可能性のある現象
- ガイダンス - レコメンデーション (例を含む場合もある)
- 問題のパターン - ガイダンスに従わない説明または例
- 追加情報 - より広範なビューに対するサポートの詳細
- 関連項目 - この記事に記載されている内容の詳細の参照先

## <a name="categories"></a>カテゴリ
各ガイダンス記事は、次のカテゴリの 1 つ以上に分類されます:

- 使用法 – 特定の API、パターン、または構成の不適切な使い方
- 設計 – カスタマイズの設計上の欠陥
- パフォーマンス – メモリ管理、CPU 使用率、ネットワーク トラフィック、ユーザー エクスペリエンスなどの領域のパフォーマンスにマイナスの影響を及ぼす可能性のあるカスタマイズやパターン
- セキュリティ – 実行時環境で悪用される可能性のある、カスタマイズの潜在的な脆弱性
- アップグレードの準備 - バージョン アップグレードの失敗のリスクが増える可能性のあるカスタマイズまたはパターン
- オンライン移行 - オンライン移行の失敗のリスクが増える可能性のあるカスタマイズまたはパターン
- 保守性 – 変更を加えるための開発者の作業量、必要な変更の頻度、リグレッションの導入の可能性を不必要に高めるカスタマイズ
- サポート - 削除された API の使用や禁止されているテクニックの実装など、公開されているサポートの範囲外に該当するカスタマイズまたはパターン
