---
title: Power Apps とは | Microsoft Docs
description: Power Apps の概要を説明し、エンドユーザー、アプリの開発者、管理者、および pro 開発者が Power Apps を使用する方法について説明します。
author: KumarVivek
manager: annbe
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 07/15/2019
ms.author: kvivek
ms.reviewer: kvivek
searchScope:
- GetStarted
- PowerApps
ms.openlocfilehash: 70086d5ec6e30a917f817a2d3f4012745949c99e
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "74680652"
---
# <a name="what-is-power-apps"></a>Power Apps とは

Power Apps は、アプリ、サービス、コネクタ、データプラットフォームのスイートであり、ビジネスニーズに合わせてカスタムアプリを構築するための迅速なアプリケーション開発環境を提供します。 Power Apps を使用すると、基になるデータプラットフォーム ([Common Data Service](/powerapps/maker/common-data-service/data-platform-intro))*または*さまざまなオンラインおよびオンプレミスのデータソース (SharePoint、Excel、Office 365、Dynamics 365、SQL Server など)*に格納さ*れているビジネスデータに接続するカスタムビジネスアプリをすばやく作成できます。 

Power Apps を使用して構築されたアプリは、手動のビジネスプロセスをデジタルで自動化されたプロセスに変換するための、豊富なビジネスロジックとワークフロー機能を提供します。 さらに、Power Apps を使用して構築されたアプリは応答性の高い設計になっており、ブラウザーやモバイルデバイス (携帯電話やタブレット) でシームレスに実行できます。 Power Apps は、ユーザーがコードを記述しなくても機能豊富なカスタムビジネスアプリケーションを構築できるようにすることで、カスタムビジネスアプリの構築エクスペリエンスを "も広げる" します。

また、Power Apps で提供される拡張可能なプラットフォームにより、プロの開発者は、データやメタデータをプログラムでやり取りし、ビジネス ロジックを適用し、カスタム コネクタを作成し、外部データと統合することができます。

詳細については、YouTube の[Power Apps チャネル](https://www.youtube.com/channel/UCGfWR2ekfRFckLjev6eQYLg)に関する説明を参照してください。

## <a name="power-apps-for-app-makerscreators"></a>アプリメーカー/作成者向けのパワーアプリ

Power Apps を使用すると、**キャンバス**、**モデル駆動**、**ポータル**の3種類のアプリを作成できます。 詳細については、「 [Power apps でのアプリの作成の概要」](maker/index.md)を参照してください。

アプリを作成するには、まず[make.powerapps.com](https://make.powerapps.com)を使用します。

- **Power Apps Studio**は、キャンバスアプリの作成に使用されるアプリデザイナーです。 このアプリ デザイナーでは、Microsoft PowerPoint のスライド デッキ作成に近い感覚でアプリを作成できます。 詳細情報:[データからアプリを生成する](/powerapps/maker/canvas-apps/data-platform-create-app)  

- モデル駆動型用の**アプリ デザイナー**では、サイトマップを定義し、コンポーネントを追加してモデル駆動型アプリを作成できます。 詳細情報:[アプリデザイナーを使用してモデル駆動型アプリを設計する](maker/model-driven-apps/design-custom-business-apps-using-app-designer.md)

## <a name="power-apps-for-app-users"></a>アプリユーザー向けのパワーアプリ

自分か他の誰かが作成したアプリをブラウザーやモバイル デバイス (スマートフォンやタブレット) で実行できます。 詳細:[アプリの検索と実行](user/index.md)

## <a name="power-apps-for-admins"></a>管理者向けのパワーアプリ

Power Apps の管理者は次のものを使用できます。

- **Power Apps 管理センター** ([admin.powerapps.com](https://admin.powerapps.com)) では、環境、ユーザー、ロール、およびデータ損失防止ポリシーを作成し、管理します。 

- **Power Platform 管理センター** ([admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com)) を使用して、環境を管理し、リアルタイムでセルフヘルプの推奨事項と、パワーアプリとパワー自動化のサポートを提供し、Common Data Service analytics を表示します。 

詳細情報: [Power Apps の管理](/power-platform/admin/admin-guide)

## <a name="power-apps-for-developers"></a>開発者向けのパワーアプリ

開発者は、コードを記述してさらに拡張されたビジネス アプリを作成したり、カスタマイズしたりすることができるアプリの作成者です。 開発者はコードを使用してデータやメタデータを作成したり、Azure の関数、プラグイン、ワークフロー拡張を利用してサーバー側のロジックを適用したり、JavaScript を利用してクライアント側のロジックを適用したり、仮想エンティティや Web hook を利用して外部データを統合したり、Web サイトにアプリを埋め込み、統合ソリューションを作成したりすることができます。 詳細情報:[開発者向けの Power Apps](/powerapps/#pivot=home&panel=developer)

## <a name="power-apps-and-dynamics-365"></a>Power Apps と Dynamics 365

Dynamics 365 Sales、Dynamics 365 Customer Service、Dynamics 365 Marketing などの dynamics 365 アプリケーションも、データの格納とセキュリティ保護のために Power Apps によって使用される基になるデータプラットフォーム (Common Data Service) を使用します。 これにより、Power Apps を使用してアプリを構築し、Dynamics 365 で既に使用されているコアビジネスデータに対して直接 Common Data Service して、統合する必要がなくなります。 詳細につい[ては、「Dynamics 365 と Common Data Service」を参照して](maker/common-data-service/data-platform-intro.md#dynamics-365-and-common-data-service)ください。

## <a name="try-power-apps-for-free"></a>パワーアプリを無料で試す

[30 日間の試用版](maker/signup-for-powerapps.md)または[コミュニティプラン](maker/dev-community-plan.md)にサインアップすることで、無料で Power Apps を試すことができます。

## <a name="purchase-power-apps"></a>電力アプリを購入する

Power Apps の購入を決定した場合は、こちらを参照してください。詳細については、「 [Power apps の購入](/power-platform/admin/signup-for-powerapps-admin)」をご覧ください。
