---
title: "发送适配器的接口为异步批处理支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d38b8b87-508a-499b-86b2-846938050b44
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4af0a5c116c19c4cb1fa728cc016144594f42f13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-an-asynchronous-batch-supported-send-adapter"></a>异步的支持批的发送适配器的接口
可识别批的适配器可以同步或异步发送消息，并且可以执行事务性发送。 若要发送消息批，发送适配器必须实现以下接口：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
 对于异步批发送，消息引擎将从适配器获取一个批，并且将要传输的消息添加到该批。 仅发送消息消息引擎调用**完成**批次的方法。 适配器返回`False`它想要以异步方式传输每条消息。 然后，适配器从适配器代理获取一个批，并删除它已成功传输的那些消息。  
  
 下图显示在创建异步的支持批的发送适配器时涉及的对象交互。  
  
 ![](../core/media/ebiz-sdk-devadapter7.gif "ebiz_sdk_devadapter7")  
异步发送消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)