---
title: "为事务异步批处理支持发送适配器接口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 948000883c092c8e247b1d4f41fb2bc7e2280e40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a>事务异步批处理支持发送适配器的的接口
在必须以事务方式传输消息时，发送适配器可以创建和控制事务。 为了支持事务性发送，适配器需要实现以下接口：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTBatchTransmitter**  
  
-   **IBTTransmitterBatch**  
  
-   **IBTBatchCallBack**  
  
 适配器创建的 MSDTC 事务并对该对象的调用中返回的指针**BeginBatch**方法**IBTTransmitterBatch**接口。 消息引擎调用此方法来获得一个批，并通过此批将传出消息发送到发送适配器。 当适配器完成发送操作和提交或回滚事务时，它将通知消息的事务结果引擎使用**DTCCommitConfirm**方法**IBTDTCCommitConfirm**接口。  
  
 下图显示了执行事务性发送操作时，传输代理和发送适配器之间的交互过程。  
  
 ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
异步发送事务性消息的工作流  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [异步接口发送适配器](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)