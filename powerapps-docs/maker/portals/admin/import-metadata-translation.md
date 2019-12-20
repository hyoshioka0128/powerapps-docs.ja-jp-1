---
title: メタデータ翻訳のインポート | MicrosoftDocs
description: メタデータ翻訳のインポートに関する説明
author: sbmjais
manager: shujoshi
ms.service: powerapps
ms.topic: conceptual
ms.custom: ''
ms.date: 10/21/2019
ms.author: shjais
ms.reviewer: ''
ms.openlocfilehash: 6e1f577e5097aead282b6da9338acfd5d1f36364
ms.sourcegitcommit: dd2a8a0362a8e1b64a1dac7b9f98d43da8d0bd87
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/02/2019
ms.locfileid: "2862627"
---
# <a name="import-metadata-translation"></a>メタデータ翻訳のインポート

ポータルを準備する場合、ソリューションに関連するポータルが組織にインストールされます。 ソリューションのインストール中に、ソリューション メタデータ翻訳 (例: フィールド名、フォーム名、ビュー名) は現在組織でアクティブ化されている言語にのみインストールされます。 今後新しい言語をアクティブ化する場合、新たにアクティブ化した言語に対し、メタデータは自動的にインストールされません。 新しくアクティブ化された言語のメタデータ翻訳を取得するには、Power Apps ポータルの管理センターからメタデータ翻訳をインポートする必要があります。

## <a name="to-import-metadata-translation"></a>メタデータ翻訳をインポートするには

1.  [Power Apps ポータル管理センター](admin-overview.md) を開きます。

2.  **ポータル アクション** > **最新のメタデータ翻訳を取得します**へ移動します。 ポータル ソリューションを更新するかどうかを尋ねる、確認メッセージか表示されます。

3.  **更新**を選択します。 ポータル ソリューションは最新のメタデータ翻訳によって更新されます。

> [!Note]
> - ポータル パッケージの最新バージョンがある場合、更新されません。 ポータル ソリューションは同じバージョンで更新されます。 最新の使用可能なパッケージに基づいてポータル ソリューションをアップグレードするには、ソリューション管理センターにアクセスする必要があります。
> - ユーザーが Common Data Service のデータを変更しても、既存のデータは更新中は上書きされません。
> - ポータル ソリューションをインストールしている間は、ソリューションの更新をトリガーすることはできません。