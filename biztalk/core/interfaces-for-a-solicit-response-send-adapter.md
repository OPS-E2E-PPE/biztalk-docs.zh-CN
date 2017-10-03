---
title: "发送的请求作出响应的接口适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb8ce9b625bfea144f9a4a615a604efdbe2a3cb1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a>用于要求响应发送适配器的接口
发送适配器与接收适配器使用相同的批处理机制将响应消息提交回服务器中。  
  
> [!NOTE]
>  建议让请求-响应适配器异步处理消息。 如果适配器以同步方式处理消息，会有消息重复的风险。  
  
 发送适配器需要实现以下接口才能在请求-响应模式中工作：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
-   **IBTTransmitterBatch**和**IBTBatchTransmitter** （如果发送批处理，则需要）  
  
-   **IBTBatchCallBack**  
  
 对象交互涉及的步骤如下：  
  
1.  适配器发送要求消息后，会从目标服务器收到响应消息。 然后会从传输代理获得一个批。  
  
2.  适配器将响应消息添加到批处理，通过调用**IBTTransportProxy::SubmitResponseMessage**。  
  
3.  适配器通过调用提交批**IBTTransportProxy::Done**传递中指向的指针的其**IBTBatchComplete**从消息引擎回调的接口。  
  
4.  消息引擎调用该适配器**IBTBatchCallBack::BatchComplete**使用传输代理通知它提交操作的结果的回调方法。  
  
 下图显示了创建要求-响应发送适配器所涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
要求-响应发送适配器的交互图  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)