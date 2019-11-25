---
title: Azure DevOps 構築ツールの概要| Microsoft Docs
description: PowerApps build tools は、一連の PowerApps 固有の Azure DevOps 構築タスクです。これを使用することで PowerApps の開発を管理するためにスクリプトを手動でダウンロードする必要がなくなります。
ms.custom: ''
ms.date: 07/21/2019
ms.reviewer: Dean-Haas
ms.service: powerapps
ms.topic: article
author: mikkelsen2000
ms.author: pemikkel
manager: kvivek
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: bf3e34dde090b616687e597dc7df099d9559b0ce
ms.sourcegitcommit: 8185f87dddf05ee256491feab9873e9143535e02
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "2749013"
---
# <a name="powerapps-build-tools-for-azure-devops-overview"></a>Azure DevOps の PowerApps build tools の概要


[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

PowerApps build tools を使用することで、PowerApps に関連する一般的な構築作業および導入タスクを自動化することができます。 これには、以下の処理が含まれています。 開発環境とソースコントロール間でのソリューション メタデータ (ソリューション) の同期、構築アーティファクトの生成、ダウンストリーム環境への展開、環境のプロビジョニングとデプロビジョニング、ソリューションに対する PowerApps チェッカー サービスを使用した静的解析チェック。

> [!IMPORTANT]
>
> - PowerApps build tools はプレビュー機能です。
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

  
## <a name="what-are-powerapps-build-tools"></a>PowerApps build tools とは。

PowerApps build tools は、一連の PowerApps 固有の Azure DevOps 構築タスクです。これを使用することで PowerApps のアプリケーション ライフサイクルの管理にあたって、カスタム ツールやスクリプトを手動でダウンロードする必要がなくなります。 タスクは、ダウンストリーム環境へのソリューションのインポートなどの簡単なタスクの実行に個別使用することもできますが、「構築アーティファクトの生成」や「テストの展開」、「メーカー変更の取り込み」などのパイプラインでシナリオをまとめるのことに使用することもできます。 構築タスクは大きく分けて以下の4つの種類に分類できます:

- ヘルパー 
- 品質のチェック 
- ソリューション 
- 環境の管理 

## <a name="get-the-powerapps-build-tools"></a>PowerApps build tools の入手 
PowerApps build tools は [Azure Marketplace](https://marketplace.visualstudio.com/items?itemName=microsoft-IsvExpTools.PowerApps-BuildTools) から Azure DevOps にインストールできます。 インストールが完了すると、PowerApps build tools に含まれるすべてのタスクが、新規または既存のパイプラインに追加できるようになり、**PowerApps** を検索することで容易に見つけることができます。

![構築ツールを入手する](media/build-tools-download.png)
 
## <a name="next-step"></a>次の手順

[ツール構成タスク](build-tools-tasks.md)
