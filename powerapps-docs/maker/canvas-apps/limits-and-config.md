---
title: キャンバス アプリのシステム要件、制限、構成値 | Microsoft Docs
description: Power Apps で構築されたキャンバスアプリのシステム要件、制限、および構成値
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/19/2020
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7e434de24af417b5871c762d1aecd64cc41c5c72
ms.sourcegitcommit: 1b29cd1fa1492037ef04188dd857a911edeb4985
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80122753"
---
# <a name="system-requirements-limits-and-configuration-values-for-canvas-apps"></a>キャンバス アプリのシステム要件、制限、構成値
このトピックには、デバイスプラットフォームと web ブラウザーの要件に加えて、キャンバスアプリの制限と構成値が含まれています。

## <a name="supported-platforms-for-running-canvas-apps-using-the-power-apps-mobile-app"></a>Power Apps モバイルアプリを使用してキャンバスアプリを実行するためにサポートされるプラットフォーム

| **最小構成** | **推奨** |
| --- | --- |
| iOS 12 以降 |iOS 12 以降|
| Android 7 以降 |Android 7 以降 |
| Windows 8.1 以降 (PC のみ) |Windows 10 Fall Creators Update と少なくとも 8 GB の RAM)|

> [!NOTE]
> 現在、Windows platform for [Power Apps モバイルアプリ](/powerapps/user/run-app-client)の新機能はサポートされていません。 強化された Common Data Service オプションやゲストアクセスなどの機能は、このプラットフォームでは使用できません。 すべての機能を利用するには、Windows で web プレーヤーを使用することをお勧めします。 Windows プラットフォーム用の Power Apps モバイルアプリの更新プログラムは、今後発表される予定です。

## <a name="supported-browsers-for-running-canvas-apps"></a>キャンバス アプリを実行するためにサポートされているブラウザー

| **ブラウザー** | **オペレーティング システム** |
| --- | --- |
| Google Chrome (最新バージョン)<br>(推奨) |Windows 7 SP1、8.1、および 10 <br>Android 5 以降 <br>iOS 8 以降<br>macOS |
| Microsoft Edge (最新バージョン)<br>(推奨) |Windows 10 |
| Microsoft Internet Explorer 11 (互換表示オフ) |Windows 7 SP1、8.1、および 10 |
| Mozilla Firefox (最新バージョン) |Windows 7 SP1、8.1、および 10 <br> Android 5 以降 <br>iOS 8 以降 <br>macOS |
| Apple Safari (最新バージョン) |iOS 8 以降 <br>macOS |

## <a name="supported-browsers-for-power-apps-studio"></a>Power Apps Studio でサポートされているブラウザー

| **ブラウザー** | **オペレーティング システム** |
| --- | --- |
| Google Chrome (最新バージョン)<br>(推奨) |Windows 7 SP1、8.1、および 10 <br>macOS |
| Microsoft Edge (最新バージョン)<br>(推奨) |Windows 10 |
| Microsoft Internet Explorer 11 (互換表示オフ) |Windows 7 SP1、8.1、および 10 |

## <a name="request-limits"></a>要求の制限
次の制限は、1 つの送信要求ごとに適用されます。

| Name | ［制限値］ |
| --- | --- |
| タイムアウト |180 秒 |
| 再試行回数 |4 |

> [!NOTE]
> 再試行回数が異なる場合があります。 エラーの状況によっては、再試行は無意味です。

## <a name="ip-addresses"></a>IP アドレス
パワーアプリからの要求では、アプリが存在する[環境](../../administrator/environments-overview.md)のリージョンに依存する IP アドレスを使用します。 Power Apps のシナリオで利用できる完全修飾ドメイン名は公開されません。

アプリ経由で接続される API (たとえば、SQL API や SharePoint API) から行われる呼び出しでは、このトピックの後半で説明する IP アドレスを使用します。

たとえば、Azure SQL データベース用に IP アドレスをホワイトリスト登録する必要がある場合は、これらのアドレスを使用する必要があります。

> [!IMPORTANT]
>   既存の構成がある場合は、2018年9月30日までにできるだけ早く更新してください。そのため、Power Apps アプリが存在するリージョンについて、この一覧の IP アドレスが含まれ、一致していることを確認してください。

| Region (リージョン) | 送信 IP |
| --- | --- |
| アジア | 13.75.36.64-13.75.36.79、13.67.8.240-13.67.8.255、52.175.23.169、52.187.68.19、127.0.0.1 |
| オーストラリア  | 13.70.72.192-13.70.72.207、13.72.243.10、13.77.50.240-13.77.50.255、13.70.136.174、127.0.0.1 |
| ブラジル | 191.233.203.192-191.233.203.207、104.214.19.48-104.214.19.63、13.65.86.57、104.41.59.51、127.0.0.1 |
| カナダ | 13.71.170.208-13.71.170.223、13.71.170.224-13.71.170.239、52.237.24.126、40.69.106.240、40.69.106.255、127.0.0.1|
| ヨーロッパ | 13.69.227.208-13.69.227.223、52.178.150.68、13.69.64.208-13.69.64.223、52.174.88.118、137.117.161.181、127.0.0.1|
| インド  | 104.211.81.192-104.211.81.207、52.172.211.12、40.78.194.240-40.78.194.255、13.71.125.22、104.211.146.224、104.211.146.239、127.0.0.1 |
| Japan | 13.78.108.0-13.78.108.15、13.71.153.19、40.74.100.224-40.74.100.239、104.215.61.248、127.0.0.1 |
| 南アメリカ | 191.233.203.192-191.233.203.207、104.214.19.48-104.214.19.63、13.65.86.57、104.41.59.51、127.0.0.1 |
| イギリス | 51.140.148.0-51.140.148.15、51.140.80.51、51.140.211.0-51.140.211.15、51.141.47.105、127.0.0.1 |
| 米国 | 13.89.171.80-13.89.171.95、52.173.245.164、40.71.11.80-40.71.11.95、40.71.249.205、40.70.146.208、40.70.146.223、52.232.188.154、52.162.107.160、52.162.107.175、52.162.242.161、40.112.243.160、40.112.243.175、127.0.0.1 |
| 米国 (早期アクセス)  | 13.71.195.32-13.71.195.47、52.161.102.22、13.66.140.128-13.66.140.143、52.183.78.157、127.0.0.1 |

## <a name="required-services"></a>必要なサービス
このリストは、Power Apps Studio が通信するすべてのサービスとその使用状況を識別します。 ネットワークでこれらのサービスをブロック**しないでください**。

| ドメイン | プロトコル | 用途 |
| --- | --- | --- |
| api.bap.microsoft.com<br/>api.businessappdiscovery.microsoft.com | https | 環境のアクセス許可の管理|
| management.azure.com |https |RP |
| msmanaged-na.azure-apim.net |https |コネクタ/API のランタイム |
| login.microsoft.com<br>login.windows.net<br>login.microsoftonline.com<br>secure.aadcdn.microsoftonline-p.com |https |ADAL |
| graph.microsoft.com<br>graph.windows.net |https |Azure Graph-ユーザー情報を取得する場合 (例: プロファイル写真) |
| gallery.azure.com |https |サンプルおよびテンプレート アプリ |
| \*。 azure-apim.net |https |API のハブ - ロケールごとに異なるサブドメイン |
| \*。 powerapps.com |https | create.powerapps.com、make.powerapps.com、content.powerapps.com、および make.powerapps.com |
| \*。 azureedge.net |https | create.powerapps.com、make.powerapps.com、content.powerapps.com、および make.powerapps.com |
| \*。 blob.core.windows.net |https | Blob Storage |
| \*。 flow.microsoft.com | https | create.powerapps.com、make.powerapps.com、content.powerapps.com、および make.powerapps.com |
| \*。 dynamics.com | https | Common Data Service |
| vortex.data.microsoft.com |https |製品利用統計情報 |
| localhost | https | Power Apps モバイル|


> [!NOTE]
> VPN を使用している場合は、Power Apps Mobile のトンネリングから localhost を除外するように構成する必要があります。

## <a name="size-limits"></a>サイズ制限

テキスト、ハイパーリンク、画像、メディアのサイズ制限に関する情報については、「[データ型](functions/data-types.md#text-hyperlink-image-and-media)」を参照してください。

## <a name="power-apps-per-app-plan"></a>アプリごとの電源アプリの計画

この情報は、「Power Platform 管理者ガイド」の「[アプリ別プランあたりの電源プラン](/power-platform/admin/signup-for-powerapps-admin#power-apps-per-app-plan)」セクションで利用できるようになりました。
