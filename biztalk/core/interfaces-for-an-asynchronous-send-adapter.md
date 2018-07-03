---
title: 发送适配器的异步接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a214716-8f39-400d-a111-ba1b92a284b4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd90aa9c5d010acc4d73a66220964ebdcb31e1f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980350"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>发送适配器的异步接口
一次发送一条消息的适配器可以同步或异步发送消息。 如果适配器在执行发送操作时不阻止传输代理线程而是使用单独的线程，则异步发送消息。 为了能够异步发送消息，适配器需要实现以下接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
  以下步骤说明了发送适配器应消息引擎的请求从服务器传输消息时执行的一系列操作：  
  
1.  消息引擎将使用传输代理要传递给发送适配器的传出消息，通过调用**TransmitMessage**方法**IBTTransmitter**接口。  
  
2.  适配器会立即返回从**TransmitMessage**后存储消息要发送到某些内部队列，并返回`False`有关**bDeleteMessage**。 这样可以通知消息引擎消息将在异步模式下传输。  
  
3.  适配器使用自己的线程池发送消息。  
  
4.  发送操作完成后，适配器从 MessageBox 数据库删除原始消息。 它从消息引擎使用获取一批**IBTTransportBatch.GetBatch**方法的传输代理，然后调用**DeleteMessage**。  
  
     下图显示了创建异步发送适配器所涉及的对象交互。  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
异步发送消息的工作流  
  
> [!NOTE]
>  我们建议适配器对当前正处理的消息进行计数。 适配器应该一直阻止**Terminate**方法，直到消息计数归零。 对于发送适配器，正处理的消息应被适当处理。 这意味着，已成功异步传送的任何消息应该从适配器的专用应用程序消息队列中删除，以防止消息被发送两次。 一般情况下后, **Terminate**调用由消息引擎它不接受发布新消息来自适配器的请求。 这种情况的一个例外是与要求-响应对相关的消息。  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [要求-响应发送适配器的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)