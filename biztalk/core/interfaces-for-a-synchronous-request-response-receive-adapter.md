---
title: "接口同步请求-响应接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0c60832-52b5-4d2c-81ec-94c46c375b15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9abd84bab5da623c2dff61c6e07a5898110588af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-request-response-receive-adapter"></a>同步请求-响应接收适配器的接口
所有接收适配器都需要实现以下接口，然后才可以在请求-响应模式中工作：  
  
-   **IBTTransport**  
  
-   **IBTTransportControl** （正则仅适用于适配器）  
  
-   **IBTTransportConfig**  
  
-   **IBaseComponent**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchCallBack**  
  
-   **IBTTransmitter**  
  
 支持请求-响应协议的接收适配器（例如，HTTP 接收适配器）在提交请求消息时执行以下操作：  
  
1.  接收适配器接收传入的请求消息。 通过调用从传输代理上获取一批**GetBatch**方法**IBTTransportProxy**接口。 在此调用该适配器将中传递回调指针给其实现**IBTBatchCallBack.BatchComplete**方法。  
  
2.  适配器将请求消息添加到批处理，通过调用**SubmitRequestMessage**方法**IBTTransportBatch**接口，一次为每个请求消息。  
  
3.  当已添加的所有消息时，该适配器调用**完成**方法**IBTTransportBatch**接口，提交到通过传输代理 the Messaging Engine 批。  
  
4.  处理批后，消息引擎时，将调用适配器的**IBTBatchCallBack.BatchComplete**通过传输代理的回调方法。 提交状态作为 HRESULT 值的数组（与批处理中每个消息相对应）传递给适配器。 如果批处理在管道中或业务流程中失败，则 SOAP 错误消息将作为响应返回给适配器。  
  
5.  传入的请求消息可以有业务流程订户。 业务流程完成并处理请求消息后，消息传送引擎将发送响应消息通过传输代理到适配器通过调用适配器的**TransmitMessage**从方法**IBTTransmitter**接口。  
  
6.  适配器发送响应消息，然后从 MessageBox 数据库中删除原始消息。  
  
 下图显示在创建同步的请求-响应接收适配器时涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter3.gif "ebiz_sdk_devadapter3")  
接收适配器提交同步消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发接收适配器](../core/developing-a-receive-adapter.md)   
 [实例化和初始化接收适配器](../core/instantiating-and-initializing-a-receive-adapter.md)   
 [进程内的接口接收适配器](../core/interfaces-for-an-in-process-receive-adapter.md)   
 [一个独立的接口接收适配器](../core/interfaces-for-an-isolated-receive-adapter.md)   
 [批处理支持的接口接收适配器](../core/interfaces-for-a-batch-supported-receive-adapter.md)   
 [批处理支持为一个事务性接口接收适配器](../core/interfaces-for-a-transactional-batch-supported-receive-adapter.md)