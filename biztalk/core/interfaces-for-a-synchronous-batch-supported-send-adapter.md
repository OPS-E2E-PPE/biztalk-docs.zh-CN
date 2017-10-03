---
title: "批处理支持异步接口发送适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b191c41-ca4f-4d2b-bd15-a93ad87a743d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ab61fd6624468e0464cfe0c648fcc868bd20005
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-synchronous-batch-supported-send-adapter"></a>同步的支持批的发送适配器的接口
可识别批的适配器可以同步或异步发送消息，并且可以执行事务性发送操作。 若要发送消息批，发送适配器必须实现以下接口：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
 对于同步批发送，消息引擎将从适配器获取一个批，并且将要传输的消息添加到该批。 The Messaging Engine 将每条消息添加到批处理，并仅在它调用时才发送消息**完成**批次的方法。 适配器返回`True`为**bDeleteMessage**它想要以同步方式传输每条消息。 适配器应将消息数据，而不是消息指针，保存在其**TransmitMessage**实现。 这是因为消息指针将不再有效之后`True`返回，并且不应使用或缓存供以后使用。  
  
 下图显示在创建同步的支持批的发送适配器时涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter6.gif "ebiz_sdk_devadapter6")  
同步提交消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)