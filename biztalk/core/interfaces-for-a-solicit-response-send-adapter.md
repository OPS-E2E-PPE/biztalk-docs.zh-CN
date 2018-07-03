---
title: 发送适配器的接口的要求响应 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c54650e8-dbfb-4c66-843b-0b82c8183dd4
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5056092886ad9d73d3db3dcc910038bc7dcd6e4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024131"
---
# <a name="interfaces-for-a-solicit-response-send-adapter"></a>用于要求响应发送适配器的接口
发送适配器与接收适配器使用相同的批处理机制将响应消息提交回服务器中。  
  
> [!NOTE]
>  建议让请求-响应适配器异步处理消息。 如果适配器以同步方式处理消息，会有消息重复的风险。  
  
 发送适配器需要实现以下接口才能在请求-响应模式中工作：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
- **IBTTransmitterBatch**并**IBTBatchTransmitter** （如果发送批处理是必需的）  
  
- **IBTBatchCallBack**  
  
  对象交互涉及的步骤如下：  
  
1. 适配器发送要求消息后，会从目标服务器收到响应消息。 然后会从传输代理获得一个批。  
  
2. 适配器通过调用将响应消息添加到批**ibttransportproxy:: Submitresponsemessage**。  
  
3. 适配器通过调用提交批处理**IBTTransportProxy::Done**传入一个指向其**IBTBatchComplete**从消息引擎回调的接口。  
  
4. 消息引擎调用适配器的**ibtbatchcallback:: Batchcomplete**使用传输代理通知它提交操作的结果的回调方法。  
  
   下图显示了创建要求-响应发送适配器所涉及的对象交互。  
  
   ![](../core/media/ebiz-sdk-devadapter13.gif "ebiz_sdk_devadapter13")  
   要求-响应发送适配器的交互图  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [支持事务性异步批处理的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)