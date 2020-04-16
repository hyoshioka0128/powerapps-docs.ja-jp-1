---
title: Microsoft Azure Microsoft Azureソリューション用リスナー アプリケーションの記述 (Common Data Service)| Microsoft Docs
description: このトピックでは、Azure Service Bus にポストされた Common Data Service メッセージを読み取りおよび処理できる Azure ソリューション リスナー アプリケーションの記述方法について説明します。
keywords: ''
ms.date: 10/06/2019
ms.service: powerapps
ms.topic: article
ms.assetid: cf68e0a9-c240-59e7-c501-68cbfa0df455
author: JimDaly
ms.author: jdaly
manager: ryjones
ms.reviewer: pehecke
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 4988b5c3210b083658c539c53a9479abdd03d2ee
ms.sourcegitcommit: f4cf849070628cf7eeaed6b4d4f08c20dcd02e58
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154899"
---
# <a name="write-a-listener-application-for-a-azure-solution"></a>Azure ソリューション用のリスナー アプリケーションの記述

このトピックでは、Azure Service Bus にポストされた Common Data Service メッセージを読み取りおよび処理できる Azure ソリューション リスナー アプリケーションの記述方法について説明します。 Common Data Service リスナーの仕様を学習する前に、前提要件として、Azure Service Bus リスナーの記述方法を知る必要があります。 詳細については、「[Azure サービス バス ドキュメント](/azure/service-bus/)」を参照してください。
  
<a name="bkmk_writequeued"></a>

## <a name="write-a-queue-listener"></a>キュー リスナーの記述

メッセージ *キュー*は、サービス バス エンドポイントで受信されるメッセージのリポジトリです。 *キュー リスナー*は、それらのキュー メッセージを読み取って処理するアプリケーションです。 サービス バス メッセージはキューに格納されるため、リスナーはキュー内で受信されるメッセージをアクティブにリスニングする必要はありません。 キュー リスナーは、メッセージがキュー内に到達した後に開始されても、それらのメッセージを処理できます。 次のセクションで説明するその他の種類のリスナーは、アクティブにリッスンしていないとメッセージを読み取れません。 これらのメッセージは、Common Data Service またはその他のソースから送信されます。 
  
> [!IMPORTANT]
>  キュー リスナーを記述する際には、各メッセージ ヘッダー アクションをチェックして、メッセージが Common Data Service からのものであるかどうかを確認します。 これを行う方法については、「[メッセージのフィルター処理](write-listener-application-azure-solution.md#filter)」を参照してください。  
  
[ReceiveMode.ReceiveAndDelete](/dotnet/api/microsoft.servicebus.messaging.receivemode) モードの [Receive](/dotnet/api/microsoft.servicebus.messaging.queueclient.receive) を使用して破壊的メッセージ読み取りを行うと、メッセージは読み取られキューから削除されます。または、[PeekLock](/dotnet/api/microsoft.servicebus.messaging.receivemode) モードを使用して非破壊的メッセージ読み取りを行うと、メッセージは読み取られますがキューにそのまま残ります。 この SDK で提供されている永続キュー リスナーのサンプル コードは、破壊的読み取りを実行します。 キューからメッセージを読むことについての詳細は、「[キューからのメッセージの受信方法](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues#receive-messages-from-the-queue)」を参照してください。  
  
*トピック*はキューに似ていますが、公開/サブスクライブ モデルを実装します。 一つ以上リスナーがトピックをサブスクライブし、キューからメッセージを受信することができます。 詳細: [キュー、トピック、およびサブスクリプション](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions)  
  
> [!IMPORTANT]
>  これらの契約を使用するには、[Azure SDK](https://azure.microsoft.com/downloads/archive-net-downloads/) バージョン 1.7 またはそれ以降を使用して、リスナー アプリケーションを記述する必要があります。
  
マルチシステム ソフトウェアの設計でキューおよびトピックを使用すると、システムのデカップリングが生じます。 リスナー アプリケーションを使用できないようにすると、Common Data Service からメッセージは引き続きの配信され、オンラインに戻るとリスナー アプリケーションはキュー メッセージを引き続き処理することができます。 詳細: [キュー、トピック、およびサブスクリプション](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions)  
  
<a name="bkmk_writeoneway"></a>

## <a name="write-a-one-way-two-way-or-rest-listener"></a>一方向、二方向、または REST リスナーの記述

先に説明したキュー リスナーに加えて、Common Data Service でサポートされているその他 3 つのサービス バス コントラクト用のリスナーを記述できます。それらのリスナーは、一方向、二方向、および REST リスナーです。 一方向リスナーは、サービス バスにポストされたメッセージを読み取って処理できます。 二方向リスナーは、同じことをできますが、いくつかの情報の文字列を Common Data Service に返します。 REST リスナーは、REST エンドポイントを使用して機能する点を除いて二方向リスナーと同じです。 これらのリスナーは、サービス バス経由で送信されたメッセージを読み取るために、サービス エンドポイントをアクティブにリッスンする必要があります。 Common Data Service が Message をサービス バスへ投稿しようとしたときにリスナーがリッスンしていなかった場合、メッセージ は送信されません。
  
リスナーの記述は、ABC (アドレス、バインディング、コントラクト) と呼ばれる要素によって構造化されます。 

### <a name="one-way-listener"></a>一方向リスナー
  
- アドレス: サービス URI  
  
- バインディング: [WS2007HttpRelayBinding](/dotnet/api/microsoft.servicebus.ws2007httprelaybinding)  
  
- コントラクト: <xref:Microsoft.Xrm.Sdk.IServiceEndpointPlugin>  
  
リスナーがエンドポイントに登録された後、Common Data Service によってメッセージがサービス バスにポストされると、リスナーの <xref:Microsoft.Xrm.Sdk.IServiceEndpointPlugin.Execute*> メソッドが呼び出されます。 `Execute` メソッドは、メソッド呼び出しからデータを返すことはしません。 詳細については、一方向リスナーのサンプル「[サンプル: 一方向リスナー](org-service/samples/one-way-listener.md)」を参照してください。  
  
### <a name="two-way-listener"></a>二方向リスナー
  
- アドレス: サービス URI  
  
- バインディング: [WS2007HttpRelayBinding](/dotnet/api/microsoft.servicebus.ws2007httprelaybinding)  
  
- コントラクト: <xref:Microsoft.Xrm.Sdk.ITwoWayServiceEndpointPlugin>  
  
この二方向コントラクトの場合、<xref:Microsoft.Xrm.Sdk.ITwoWayServiceEndpointPlugin.Execute*> メソッドはメソッド呼び出しの結果として文字列を返します。 詳細については、二方向リスナーのサンプル「[サンプル: 二方向リスナー](org-service/samples/two-way-listener.md)」を参照してください。  
  
### <a name="rest-listener"></a>REST リスナー
  
- アドレス: サービス URI  
  
- バインディング: [WebHttpRelayBinding](/dotnet/api/microsoft.servicebus.wshttprelaybinding)
  
- コントラクト: <xref:Microsoft.Xrm.Sdk.IWebHttpServiceEndpointPlugin>  
  
REST コントラクトの場合、<xref:Microsoft.Xrm.Sdk.IWebHttpServiceEndpointPlugin.Execute*> メソッドはメソッド呼び出しの結果として文字列を返します。 詳細については、REST リスナーのサンプル、「[サンプル: REST リスナー](org-service/samples/rest-listener.md)」を参照してください。 二方向リスナーのサンプルでは <xref:System.ServiceModel.ServiceHost> がインスタンス化されますが、REST リスナーのサンプルでは、<xref:System.ServiceModel.Web.WebServiceHost> がインスタンス化されます。
  
> [!NOTE]
>  二方向または REST リスナーで標準のプラグイン (ServiceBusPlugin) を使用する場合、プラグインはリスナーから返される文字列データを使用しません。 ただし、カスタム Azure 対応のプラグインではこの情報を使用できます。  
> 
>  リスナー サンプルを実行すると、入力を求められる発行者シークレットは、Azure Service Bus 管理キーです。 WS2007 Federation HTTP バインディングでは、`token` と WS-Trust 1.3 プロトコルが使用されます。  
  
<a name="filter"></a>

## <a name="filter-messages"></a>メッセージのフィルター処理

Common Data Serviceから送信された仲介メッセージ [Properties](/dotnet/api/microsoft.servicebus.messaging.brokeredmessage#properties) プロパティごとに追加された追加情報のプロパティ バッグです。 プロパティ バッグには、キュー、中継、およびトピック コントラクト エンドポイントと共に、次の情報が含まれています。  
  
- 組織 URI
- 呼び出し元ユーザー ID
- 呼び出し元のユーザー ID
- エンティティの論理名
- 要求名前  
  
この情報は、Common Data Service で処理されサービス バス メッセージがポストされる、組織、ユーザー、エンティティ、メッセージ要求を識別します。 これらのプロパティの利用可能性はメッセージが Common Data Service から送信されたことを示します。 リスナー コードで、これらの値に基づいてメッセージを処理する方法を決定できます。  
  
<a name="bkmk_multiple-formats"></a>
 
## <a name="read-the-data-context-in-multiple-data-formats"></a>複数のデータ形式でのデータ コンテキストの読み取り

現在の Common Data Service 操作からのデータ コンテキストは、サービス バス メッセージの本文の Azure ソリューション リスナー アプリケーションに渡されます。 前のリリースでは、.NET バイナリ形式のみがサポートされました。  クロスプラットフォーム (非.NET) 相互運用性の場合、マッピングの場合、メッセージ本文: .NET Binary、JSON、または XML に、3 つのデータ形式の 1 つを指定できるようになりました。  この形式は [ServiceEndpoint エンティティ](reference/entities/serviceendpoint.md)の [MessageFormat](reference/entities/serviceendpoint.md#BKMK_MessageFormat) 属性で指定されます 。
  
メッセージが受信されると、リスナー アプリケーションは、メッセージのコンテンツ タイプに基づいてメッセージ本文のコンテキスト データを読み取ることができます。 そのようにするサンプル コードが以下に示されています。  
  
```csharp
var receivedMessage = inboundQueueClient.Receive(TimeSpan.MaxValue);  
  
if (receivedMessage.ContentType = "application/msbin1")  
{  
    RemoteExecutionContext context = receivedMessage.GetBody<RemoteExecutionContext>();  
}  
else if (receivedMessage.ContentType = "application/json")  
{  
    //string jsonBody = new StreamReader(receivedMessage.GetBody<Stream>(), Encoding.UTF8).ReadToEnd();  
    RemoteExecutionContext contextFromJSON = receivedMessage.GetBody<RemoteExecutionContext>(  
        new DataContractJsonSerializer(typeof(RemoteExecutionContext)));  
}  
else if (receivedMessage.ContentType = "application/xml")  
{  
    //string xmlBody = new StreamReader(receivedMessage.GetBody<Stream>(), Encoding.UTF8).ReadToEnd();  
    RemoteExecutionContext contextFromXML = receivedMessage.GetBody<RemoteExecutionContext>(  
        new DataContractSerializer(typeof(RemoteExecutionContext)));  
}  
```  
  
### <a name="see-also"></a>関連項目

[Azure 拡張機能](azure-integration.md)<br />
[Azure 対応のカスタム プラグインの記述](write-custom-azure-aware-plugin.md)<br />
[サンプル: 永続キュー リスナー](org-service/samples/persistent-queue-listener.md)<br />
[サンプル: 一方向リスナー](org-service/samples/one-way-listener.md)<br />
[サンプル: 二方向リスナー](org-service/samples/two-way-listener.md)<br />
[サンプル: REST リスナー](org-service/samples/rest-listener.md)<br />
[Azure ソリューションの Common Data Service データとの連携](work-data-azure-solution.md)<br />
[Azure イベント ハブ ソリューションの Common Data Service イベント データとの連携](work-event-data-azure-event-hub-solution.md)
 