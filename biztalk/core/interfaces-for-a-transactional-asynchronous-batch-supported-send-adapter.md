---
title: 事务性异步的支持批的发送适配器的接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5b2dbdf-e6ba-4b58-a0a5-fc78feaf5c35
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e911445cd0f92bbe863f10b8335aee0bf64630bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381859"
---
# <a name="interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter"></a>事务性异步的支持批的发送适配器的接口
发送适配器可以创建和需要事务方式传输消息时控制事务。 若要支持事务性发送，适配器需要实现以下接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTBatchTransmitter**  
  
- **IBTTransmitterBatch**  
  
- **IBTBatchCallBack**  
  
  适配器创建 MSDTC 事务，并对该对象对的调用中返回的指针**BeginBatch**方法**IBTTransmitterBatch**接口。 消息引擎调用此方法以获取到发送适配器用于将传出消息批。 当适配器完成发送操作和提交或回滚事务时，它通知事务结果的消息引擎通过使用**DTCCommitConfirm**方法的**IBTDTCCommitConfirm**接口。  
  
  执行事务性发送操作时下, 图显示了传输代理和发送适配器之间的交互。  
  
  ![](../core/media/ebiz-sdk-devadapter8.gif "ebiz_sdk_devadapter8")  
  以异步方式发送事务性消息的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [要求-响应发送适配器的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)