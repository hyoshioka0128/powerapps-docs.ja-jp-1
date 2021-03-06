---
title: ソリューションの概要 | Microsoft Docs
description: ソリューションを使用してモデル アプリを作成する方法について説明します。
services: ''
suite: powerapps
documentationcenter: na
author: shmcarth
manager: kvivek
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.reviewer: pehecke
ms.workload: na
ms.date: 05/06/2020
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: db2dd730f172810a571d8d6289ce4ae8b25dcdbe
ms.sourcegitcommit: c6906775005aec98973b1f5c3dbe5924aff6d26e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "3341442"
---
# <a name="introduction-to-solutions"></a>ソリューションの概要

*ソリューション*とは、カスタマイザーと開発者が Common Data Service を拡張した単体ソフトウェアを作成、パッケージ化、および保守する方法です。 たとえば、Dynamics 365 for Sales、Marketing、Customer Service アプリはソリューションで構成されています。 カスタマイザーと開発者は、ソリューションによって定義されたビジネス機能を組織が Common Data Service を使用してインストールおよびアンインストールできるように、ソリューションを配布します。

Common Data Service または以前にインストールされたソリューションにおこなった各カスタマイズは、ソリューションの一部です。 適用する変更すべては追跡され、依存関係すべては計算されます。 管理ソリューションをエクスポートする場合、ソルーションに適用されている変更すべては、異なる Common Data Service 環境へインポート可能なファイルに含められます。

異なる Common Data Service 環境間のカスタマイズまたは拡張を転送する場合、また AppSource を使用してソリューションを配布する場合、ソリューション フレームワークを理解している必要があります。

> [!NOTE]
> ソリューションを効率的に使用してアプリケーション ライフサイクル管理 (ALM) の実装を成功させる方法の詳細については、[Microsoft Power Platform アプリケーション ライフサイクル管理 (ALM)](/power-platform/alm) を参照してください。

## <a name="managed-and-unmanaged-solutions"></a>管理ソリューションとアンマネージド ソリューション

ソリューションには、*マネージド*および*アンマネージド*の 2 種類があります。

**マネージド** ソリューションは、配布とインストールを目的とする完成したソリューションです。 
- 管理ソリューションのコンポーネントは編集できません。
- マネージド ソリューションはエクスポートできません。
- マネージド ソリューションのコンポーネントにはアンマネージド カスタマイズを追加できます。 これを行うには、アンマネージド カスタマイズとマネージド ソリューション間の依存関係を作成します。 依存関係が存在する場合、依存関係を削除するまでマネージド ソリューションをアンインストールすることはできません。
- マネージド ソリューションを削除 (アンインストール) すると、それに含まれるカスタマイズおよび拡張もすべて削除されます。

  > [!IMPORTANT]
  > マネージド ソリューションをアンインストールすると、マネージド ソリューションの一部となっているユーザー定義のエンティティに格納したデータや、マネージド ソリューションの一部ではない他のエンティティ上のマネージド ソリューションの一部となっているユーザー定義属性に格納したデータは失われます。

**アンマネージド** ソリューションは、まだ開発中であるか、配布を目的としないソリューションです。 
- ソリューションがアンマネージドであるとき、コンポーネントの追加および削除を続行できます。 
- アンマネージド ソリューションをエクスポートして、ある環境から他の環境へアンマネージド カスタマイズを転送することができます。
- アンマネージド ソリューションを削除すると、それに含まれるすべてのカスタマイズのソリューション コンテナのみが削除されます。 アンマネージド ソリューションはすべて効果性を保持し、既定のソリューションに属します。 
- アンマネージド ソリューションを完成して配布する場合、マネージド ソリューションとしてエクスポートします。

  > [!NOTE]
  > 元のアンマネージド ソリューションを含む同じ環境にマネージド ソリューションをインポートすることはできません。 マネージド ソリューションをテストするには、別の環境をインポートする必要があります。

## <a name="solution-publishers"></a>ソリューション発行者

各ソリューションは、ソリューション発行者にリンクされています。 ソリューション発行者は、発行者に連絡する方法とカスタマイズの接頭辞の値に関する情報を提供します。 既定値は `new` です。

スキーマの変更がソリューションの一部として含まれている場合、ソリューション発行者のカスタマイズ接頭辞は、スキーマ アイテムの名前の前に付けられます。 すべてのカスタム アクションにも、この値が追加されます。 これは、スキーマ アイテムまたはカスタム アクションを追加したソリューションを簡単に認識するのに便利です。 ソリューションのすべてのスキーマ アイテムおよびカスタム アクションが同じカスタマイズ接頭辞を使用する必要はありませんが、強くお勧めします。

> [!IMPORTANT]
> ソリューションの作成を開始する前に、ソリューション開発者レコードの作成とそれにリンクされる新しいソリューションの作成を行う必要があります。 カスタマイズ接頭辞が現実に沿った値を表していることを確認する必要があります。 

ソリューション発行者の選択は、出荷したソリューションに更新プログラムを公開する場合に重要です。 更新プログラムは、元のマネージド ソリューションと同じ発行者により、マネージド ソリューションにのみ適用されます。 

詳細については、[マネージド ソリューションの保守 > マネージド ソリューション更新の作成](/dynamics365/customer-engagement/developer/maintain-managed-solutions#create-managed-solution-updates) を参照してください。

## <a name="create-a-solution-publisher-and-solution"></a>ソリューション発行者およびソリューションの作成 

ソリューション発行者およびソリューションを作成するために、Common Data Service カスタマイズ領域に移動する必要があります。

発信元 [powerapps.com](https://make.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)

1. 左上隅の*ワッフル* アイコンの選択
2. フライアウトで、**すべてのアプリ** を選択します。
3. **Common Data Service - カスタム アプリ**を検索します。
 省略記号 (...) をクリックして、**Pin this app** を選択すると、次回は簡単に移動することができます。
4. **Common Data Service - カスタム アプリ** アプリをクリックして、選択します。
5. **設定** > **カスタマイズ** > **カスタマイズ**に移動します。

発信元 [home.dynamics.com](https://home.dynamics.com/)

1.  **Common Data Service - カスタム** タイルを検索して、クリックします。
2. **設定** > **カスタマイズ** > **カスタマイズ**に移動します。

### <a name="create-a-solution-publisher"></a>ソリューション発行者の作成

1. カスタマイズ領域から、**発行者**を選択します。
2. **新規** をクリックします。
3. 発行者フォームで、**表示名**を入力します。 表示名に基づいて**名前**の値が生成されます。 生成された値をそのまま使用するか、新しい名前を指定します。
4. **接頭辞**のフィールドで、ソリューションの開発時に追加されるすべてのカスタム スキーマ アイテムに追加されるカスタマイズの接頭辞を指定します。 既定値は `new` です。 組織を表し、ソリューションに伴うシステムにどのコンポーネントがインストールされているのかを識別するのに役立つ値を選択します。
5. **オプション値の接頭辞**の値は、カスタマイズの接頭辞に対する選択に基づいて生成されます。 これは、ソリューションの属性に追加されるオプション セット オプションのすべての値に追加される値です。 この値は、ソリューションに追加されるすべてのオプションを識別するのに役立ちます。
6. フォームの**連絡先の詳細**のセクションで、ソリューションをインストールするユーザーに対して提供する連絡先の情報すべてを追加できます。
7. 終了時は、**保存して閉じる**をクリックします。

### <a name="create-a-solution"></a>ソリューションの作成

1. カスタマイズ領域から、**ソリューション**を選択します。
2. **新規** をクリックします。
3. ソリューション フォームで、**表示名**を入力します。 表示名に基づいて**名前**の値が生成されます。 生成された値をそのまま使用するか、新しい名前を指定します。
4. **発行者**のフィールドで、[ソリューション発行者の作成](#create-a-solution-publisher) で作成した発行者を検索します。
5. **バージョン** フィールドで、1.0.0.0 のような、ソリューションに適切なバージョンを選択します。
6. 終了時には、**保存**をクリックします。

> [!IMPORTANT]
> このソリューションに含まれるソリューション コンポーネントを作成する場合は、このソリューション、または同じソリューション発行者に関連付けられている他のソリューションを使用して追加します。
> このソリューションに、異なるソリューション発行者に関連付けられているソリューションのコンテキストに作成されるソリューション コンポーネントを追加することはできますが、カスタマイズ接頭辞の値には不整合が生じます。

## <a name="solution-layering"></a>ソリューションの階層

相互に矛盾する 2 つのマネージド ソリューションをインストールすること、または一部のカスタマイズを環境に適用してマネージド ソリューションを上書きすることは可能です。 どのように使用するのですか?

Common Data Service は、インストールされた順に管理ソリューションを評価し、管理ソリューション内にないすべてのカスタマイズは最後に評価されるため、これは動作します。

次の図で、マネージド ソリューションおよびアンマネージド カスタマイズが対話し、アプリケーションのランタイムに含まれているものを制御する方法を紹介します。

![ソリューションの階層を示す図](media/solution-layering.png)

この例では、システム ソリューションで定義される既定の動作が、マネージド ソリューションによって上書きまたは追加されます。 すべてのアンマネージド カスタマイズは、アプリケーション内で表示されているカスタマイズを上書きまたは追加することができます。

詳細については、[ソリューションの概要 > アンマネージドおよびマネージド ソリューション](/dynamics365/customer-engagement/developer/introduction-solutions#managed-and-unmanaged-solutions) を参照してください。

## <a name="managed-properties"></a>マネージド プロパティ

マネージド ソリューションを配布する場合、ソリューションをインストールするユーザーはだれでも、独自のアンマネージド カスタマイズを含めることができます。 それらのアンマネージド カスタマイズは、ソリューションに依存するマネージド ソリューションとして配布されているソリューションに追加することが可能です。 ただし、ユーザーにこれを行ってほしくない場合はどうですか? マネージド ソリューションの発行者としてマネージド プロパティを使用し、マネージド ソリューションのコンポーネントに対して、特定のカスタマイズを無効にすることができます。

詳細については、[マネージド プロパティの使用](use-managed-properties.md) を参照してください。

## <a name="modular-solutions"></a>モジュール ソリューション

ソリューション フレームワークを使用して、機能セットを提供する個別のコンポーネント セットを作成することができます。 各管理ソリューションをインストール、アンインストールして、顧客の展開を元の状態に戻すことができます。 作成する各マネージド ソリューションをシステム ソリューション上で実行し、基になるソリューションの機能にアクセスすることができます。

他のソリューション上で実行するマネージド ソリューションをビルドし、異なるソリューションによって共有される機能のセットを作成することもできます。 このようにして、ソリューションとして共通のモジュールのビルドおよび保守を行い、複数のソリューションをサポートすることができます。 このため、顧客は正しいソリューションをインストールするだけでよく、各ソリューションに同じ共有機能を含める必要はありません。 複数のソリューションをサポートするソリューションに更新プログラムをプッシュする必要がある場合、共通モジュールのみ更新する必要があります。

顧客、システム実装者、および ISV はソリューション上でソリューションをビルドし、必要な特定のカスタマイズを実現することができます。

ビジネス機能のセットが複数のソリューションで構成される場合、パッケージと呼ばれます。 *Package Deployer* を使用して、複数のソリューションを単一のインストール可能なユニットにまとめることができます。

## <a name="deploy-solution-packages"></a>ソリューション パッケージの展開

*Package Deployer* を使用して、含めるパッケージに対してカスタム インストーラーを作成します。 
- 1 つ以上のソリューション ファイル。
- フラット ファイル、またはエクスポートされたコンフィギュレーション データ ファイル。 
- パッケージが展開される前、展開中、またはその後に実行できるカスタム コード。
- 展開プロセスの最初か最後に表示可能なパッケージに固有の HTML コンテンツ。 これは、パッケージに展開されるソリューションおよびファイルの説明を提供するのに便利です。

詳細: [Common Data Service Package Deployerにパッケージを作成する](package-deployer/create-packages-package-deployer.md)。

## <a name="team-development-of-solutions"></a>ソリューションのチーム開発

ソリューション ファイルは単一のバイナリ ファイルで、ソース コード コントロールやチーム展開に活用できません。 ソリューションのカスタム コンポーネントで複数の開発者が作業する方法はありません。

*SolutionPackager* ツールは、ソリューション ファイルのソース コード管理とチーム展開の問題を解決します。 ツールは、圧縮されているソリューション ファイル内の個々コンポーネントを特定して、個別のファイルに解凍されます。 ツールは、以前に解凍されたファイルをパッキングしてソリューション ファイルを再作成することもできます。 これにより、複数のユーザーが単一のソリューションで独立して作業し、共通の場所への変更を抽出できます。 ソリューション ファイルの各コンポーネントは複数のファイルに分割されるので、以前の変更を上書きしないでカスタマイズをマージすることが可能になります。 SolutionPackager ツールの二次用途は、自動化作成プロセスから起動して、 のアクティブな Common Data Service インスタンスを必要とせず、以前に解凍したコンポーネント ファイルから圧縮ソリューション ファイルを生成にできることです。

詳細については、[チーム開発のソリューション ツール](/dynamics365/customer-engagement/developer/solution-tools-team-development) を参照してください。

### <a name="see-also"></a>関連項目

[Common Data Service 開発者向けの概要](overview.md)
