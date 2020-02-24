---
title: Power Apps ポータルとは? | Microsoft Docs
description: Common Data Service に格納されているデータを外部ユーザーが操作できる Power Apps を使用して Web サイトを設計し、構築します 。
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 01/17/2020
ms.author: tapanm
ms.reviewer: ''
ms.openlocfilehash: 4f8617c824037d8975514e809347cfaa6c0328c4
ms.sourcegitcommit: 2fd8b682e2d4c1e6a45c851b56f37f842ef18224
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/24/2020
ms.locfileid: "2982506"
---
# <a name="what-is-power-apps-portals"></a>Power Apps ポータルとは?

Power Apps メーカーでは、新しい、強力な種類のエクスペリエンスを作成することもできます。外部に接続する Web サイトは、組織外のユーザーがさまざまな ID でサインインできるようになっており、Common Data Service でデータを作成したり閲覧したりできます。あるいは、コンテンツを匿名で参照できます。 Dynamics 365 ポータル のフル機能は、以前は、Dynamics 365 のモデル駆動型アプリケーションにアドオンする場合に限って提供されていましたが、現在では Power Apps の内部で、完全にスタンドアロンで利用できます。  

これらの能力によりエクスペリエンスが徹底的に改善され、Web サイトの作成とページ、レイアウト、コンテンツを使用したカスタマイズが迅速に実行できるようになりました。 作成者は、テンプレートを使用してページ デザインを再利用したり、フォームとビューを Common Data Service のキー データに追加したり 、ユーザーに公開したりできます。

> [!NOTE]
> - Power Apps ポータルは、[イベント ポータル](https://docs.microsoft.com/dynamics365/marketing/developer/event-management-web-application) 以外の Bootstrap 3.3.x に基づいています。 ポータル開発者は、Bootstrap 3 をその他の CSS ライブラリと置き換えるべきではありません、なぜなら Power Apps ポータルの一部のシナリオは Bootstrap 3.3.x に依存しているからです。
> - 特定の操作に既知の問題があることもあります。 これらの問題については、このドキュメントの [既知の問題](known-issues.md) セクションで後程説明します。  

## <a name="next-steps"></a>次のステップ

[スターター ポータルの作成](create-portal.md)

### <a name="see-also"></a>関連項目

#### <a name="advanced-portal-administration"></a>詳細なポータル管理

- [ポータル管理センター](admin/admin-overview.md)

#### <a name="advanced-portal-customization"></a>高度なポータル カスタマイズ

- [ポータル管理アプリ](configure/configure-portal.md)
- [ポータル サイトの設定](configure/configure-site-settings.md)
