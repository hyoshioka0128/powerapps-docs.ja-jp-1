---
title: Azure DevOps 構築ツールの概要| Microsoft Docs
description: Power Apps build tools は、一連の Power Apps 固有の Azure DevOps 構築タスクです。これを使用することで Power Apps の開発を管理するためにスクリプトを手動でダウンロードする必要がなくなります。
ms.custom: ''
ms.date: 07/21/2019
ms.reviewer: pehecke
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
ms.openlocfilehash: 111169c35463ba082a734082ea5eca1f4bab5c21
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3156419"
---
# <a name="power-apps-build-tools-for-azure-devops-overview"></a>Azure DevOps の Power Apps build tools の概要


[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Power Apps build tools を使用することで、Power Apps に関連する一般的な構築作業および導入タスクを自動化することができます。 これには、以下の処理が含まれています。 開発環境とソースコントロール間でのソリューション メタデータ (ソリューション) の同期、構築アーティファクトの生成、ダウンストリーム環境への展開、環境のプロビジョニングとデプロビジョニング、ソリューションに対する Power Apps チェッカー サービスを使用した静的解析チェック。

> [!IMPORTANT]
>
> - Power Apps build tools はプレビュー機能です。
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]

  
## <a name="what-are-power-apps-build-tools"></a>Power Apps build tools とは。

Power Apps build tools は、一連の Power Apps 固有の Azure DevOps 構築タスクです。これを使用することで Power Apps のアプリケーション ライフサイクルの管理にあたって、カスタム ツールやスクリプトを手動でダウンロードする必要がなくなります。 タスクは、ダウンストリーム環境へのソリューションのインポートなどの簡単なタスクの実行に個別使用することもできますが、「構築アーティファクトの生成」や「テストの展開」、「メーカー変更の取り込み」などのパイプラインでシナリオをまとめるのことに使用することもできます。 構築タスクは大きく分けて以下の4つの種類に分類できます:

- ヘルパー 
- 品質のチェック 
- ソリューション 
- 環境の管理 

## <a name="get-the-power-apps-build-tools"></a>Power Apps build tools の入手 
Power Apps build tools は [Azure Marketplace](https://marketplace.visualstudio.com/items?itemName=microsoft-IsvExpTools.PowerApps-BuildTools) から Azure DevOps にインストールできます。 インストールが完了すると、Power Apps build tools に含まれるすべてのタスクが、新規または既存のパイプラインに追加できるようになり、**PowerApps** を検索することで容易に見つけることができます。

![構築ツールを入手する](media/build-tools-download.png)
 
## <a name="next-step"></a>次の手順

[ツール構成タスク](build-tools-tasks.md)
