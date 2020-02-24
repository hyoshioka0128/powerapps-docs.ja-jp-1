---
title: 発信呼を行うプラグインの証明書の依存関係を確認する | MicrosoftDocs
description: コードが発信呼に依存する証明書には、有効な証明書チェーンがあることを確認してください。
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: ryjones
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/08/2020
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: ee8dd188c1b88aea4aedb8330e4a0251216b0bb5
ms.sourcegitcommit: 5e23beed96cc14efae9ff264405956d59fae1e7c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945032"
---
# <a name="verify-certification-dependencies-for-plug-ins-making-outbound-calls"></a>発信呼を行うプラグインの証明書の依存関係を確認する

**カテゴリ**: 保守性、サポート

**影響の可能性**: 高い

<a name='symptoms'></a>

## <a name="symptoms"></a>現象

プラグインが外部リソースに対して https 呼び出しを行うと、このエラーが発生する場合があります。

`WebException: The underlying connection was closed: Could not establish trust relationship for the SSL/TLS secure channel.`


<a name='guidance'></a>

## <a name="guidance"></a>ガイダンス

接続するサイトに有効な証明書チェーンがあることを確認する必要があります。 [Qualys SSL Labs SSL サーバー テスト](https://www.ssllabs.com/ssltest/analyze.html)などのオンライン テスト ツールのいずれかを使用し、サイトが証明書の有効なチェーンを提供していることを確認します。


<a name='additional'></a>

## <a name="additional-information"></a>追加情報

これは、新しいエンドポイントに初めて接続するとき、または証明書に関する何かが変更されたときに発生する可能性があります。

サンドボックスで実行されているプラグインのコードが https を使用して外部エンドポイントに接続しようとすると、CDS サンドボックスは SSL/TLS ネゴシエーションを開始します。 エンドポイントは、暗号化に使用する証明書を提示します。 証明書に 1 つ以上の中間証明書がある場合、チェーン全体を提示して SSL/TLS ネゴシエーションを正常に完了する必要があります。 完全なチェーンが提示されない場合、SSL/TLS 通信を確立できません。 




<a name='seealso'></a>

### <a name="see-also"></a>関連項目

[プラグインを記述する](../../write-plug-in.md) <br /> 
[プラグインで外部ホストを操作するときは、キープアライブを false に設定する](set-keepalive-false-interacting-external-hosts-plugin.md)<br /> 
[プラグインで外部呼び出しをする場合のタイムアウトを設定する](set-timeout-for-external-calls-from-plug-ins.md)