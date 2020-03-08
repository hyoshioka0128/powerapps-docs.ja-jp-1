---
title: キャンバス アプリで使用されているリソースを共有する | Microsoft Docs
description: Power Apps でキャンバスアプリが使用するリソースを共有する方法を理解する
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 02/03/2020
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 77ccf02395c4d697a6d2054dd1a6dedda26d6e6e
ms.sourcegitcommit: 56c8c7cc64695ccb00e0d021c9f98cf70b69b4a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78845178"
---
# <a name="share-canvas-app-resources-in-power-apps"></a>キャンバスの共有-アプリのリソースを Power Apps で共有する

[キャンバス アプリを共有](share-app.md)する前に、依存するリソースの種類 (たとえば以下のうちの 1 つまたは複数) を考慮してください。

* Common Data Service 内のエンティティ

    このデータへのアクセス権をユーザーに付与する方法については、「[エンティティのアクセス許可を管理する](share-app.md#manage-entity-permissions)」を参照してください。
    
* データ ソースへの接続
* オンプレミス データ ゲートウェイ
* カスタム コネクタ
* Excel ブックまたはその他のサービス
* フロー

これらのリソースの中には、アプリを共有すると自動的に共有されるものがあります。 その他のリソースでは、ユーザーまたはアプリを共有している相手が、アプリが期待どおりに動作するように、追加の手順を実行する必要があります。

組織全体で接続、カスタム コネクタおよびオンプレミス データ ゲートウェイを共有することもできます。

## <a name="connections"></a>接続

他のユーザーとアプリを共有すると、一部の接続 (SQL 認証や Windows 認証の SQL Server など) がアプリと[暗黙的に共有](share-app-resources.md#implicit-sharing)されます。 その他の接続では、ユーザーは独自の接続を作成し、セキュリティ権限 (Common Data Service のセキュリティロール、OneDrive for Business、Azure AD 認証で SQL Server) を明示的に付与する必要があります。

アプリを他のユーザーと共有するときに、アプリの一部として接続を自動的に共有するかどうかを決定できます。共有のアクセス許可を更新できます。 これを行うには、make.powerapps.com に移動し、左側のナビゲーションから [**データ** -> **接続**] を選択します。 次に、必要な接続を選択します。 上部のナビゲーションに **[共有]** ボタンが表示される場合、または [*その他のコマンド*(...)] を選択したときに **[共有]** オプションが表示された場合は、選択した接続を他のユーザーと共有できます。

  ![OneDrive for Business の共有がありません](./media/share-app-resources/shared-connections-odb.png)

  ![SQL 認証接続を SQL Server に共有する](./media/share-app-resources/shared-connections-sqlauth.png)

### <a name="implicit-sharing"></a>暗黙の共有

共有可能な接続を使用するアプリを共有すると、アプリ接続はアプリと共に**暗黙的に共有**されます。 たとえば、make.powerapps.com にアクセスして **[アプリ]** を選択し、その接続を使用するアプリを選択して、[*その他のコマンド*(...)] を選択し、 **[共有]** を選択すると、次のメッセージが表示されます。

  ![暗黙のアクセス許可の警告](./media/share-app-resources/share-app-implicit-permission.png)

[選択したアプリを他のユーザーと共有する]**を選択し**た場合、アプリ接続はアプリと共にユーザーと暗黙的に共有されます。

## <a name="on-premises-data-gateways"></a>オンプレミス データ ゲートウェイ
オンプレミス ソースからのデータを含むアプリを作成して共有する場合は、[オンプレミス データ ゲートウェイ](gateway-management.md) 自体およびそのゲートウェイへの接続のうち一定の種類が自動的に共有されます。 自動的に共有されていない接続はすべて、(前のセクションに表示されているとおり) 手動で共有でき、またユーザーが独自の接続を作成するようアプリに求めさせることができます。 接続またはゲートウェイが構成されている接続を表示する方法は次の通りです。

1. [powerapps.com](https://make.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) を開き、左側のナビゲーション バーの **[管理]** をクリックまたはタップし、 **[ゲートウェイ]** をクリックまたはタップします。
2. [ゲートウェイ]をクリックまたはタップして、 **[接続]** タブをクリックまたはタップします。

> [!NOTE]
> 1 つ以上の接続を手動で共有する場合は、次の状況でもう一度共有する必要があるかもしれません。

* 既に共有しているアプリにオンプレミス データ ゲートウェイを追加します。
* オンプレミス データ ゲートウェイがあるアプリを共有したグループのセットまたはグループを変更します。

## <a name="custom-connectors"></a>カスタム コネクタ
カスタム コネクタを使用するアプリを共有するときに、アプリは自動的に共有されますが、ユーザーは独自の接続を作成する必要があります。

[powerapps.com](https://make.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) で、カスタム コネクタのアクセス許可を表示または更新できます。 左側のナビゲーション バーで、 **[管理]** をクリックまたはタップし、 **[接続]** をクリックまたはタップして、右上隅の **[新しい接続]** をクリックまたはタップします。 **[カスタム]** をクリックまたはタップします。次にカスタム コネクタをクリックまたはタップして、詳細を表示します。

## <a name="excel-workbooks"></a>Excel ブック
共有しているアプリが、(クラウド ストレージ アカウントの Excel ブックなど) すべてのユーザーにアクセスがないデータを使用している場合は、[データを共有](share-app-data.md)します。

## <a name="flows"></a>フロー
フローを含むアプリを共有する場合、アプリを実行しているユーザーは、フローが依存しているすべての接続を確認または更新するように求められます。 さらに、フローを作成したユーザーのみが、パラメーターをカスタマイズすることができます。 たとえば、指定したアドレスにメールを送信するフローを作成できますが、他のユーザーはそのアドレスの変更ができません。

