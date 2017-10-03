---
title: "异步接口发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1012b52bf5c6ab564cc219926b97445e43f60dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a>同步发送适配器的接口
执行发送操作时，如果阻止了传入消息引擎调用线程，则适配器将会同步发送消息。 为了能够同步发送消息，适配器需要实现以下接口：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
 在同步发送，该适配器将消息发送时阻止**TransmitMessage**，并返回成功传输之后`True.`  
  
 下图显示了创建同步发送适配器所涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
同步发送消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)