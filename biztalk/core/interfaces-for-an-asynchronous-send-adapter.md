---
title: 异步接口发送适配器 |Microsoft 文档
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
ms.openlocfilehash: db156f5a95a088ae706bb2b1c801d8dee89cdece
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257757"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>异步接口发送适配器
一次发送一条消息的适配器可以同步或异步发送消息。 如果适配器在执行发送操作时不阻止传输代理线程而是使用单独的线程，则异步发送消息。 为了能够异步发送消息，适配器需要实现以下接口：  
  
-   **IBTTransport**  
  
-   **IBaseComponent**  
  
-   **IBTTransportControl**  
  
-   **IPersistPropertyBag**  
  
-   **IBTTransmitter**  
  
 以下步骤说明了发送适配器应消息引擎的请求从服务器传输消息时执行的一系列操作：  
  
1.  The Messaging Engine 使用传输代理将传出的消息传递给发送适配器，通过调用**TransmitMessage**方法**IBTTransmitter**接口。  
  
2.  适配器将立即返回从**TransmitMessage**后存储消息发送到某些内部队列，并返回`False`为**bDeleteMessage**。 这样可以通知消息引擎消息将在异步模式下传输。  
  
3.  适配器使用自己的线程池发送消息。  
  
4.  发送操作完成后，适配器从 MessageBox 数据库删除原始消息。 从消息引擎使用，它获取一批**IBTTransportBatch.GetBatch**传输代理，然后调用的方法**DeleteMessage**。  
  
     下图显示了创建异步发送适配器所涉及的对象交互。  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
异步发送消息的工作流  
  
> [!NOTE]
>  我们建议适配器对当前正处理的消息进行计数。 适配器应阻止**终止**方法，直到消息计数已达到零。 对于发送适配器，正处理的消息应被适当处理。 这意味着，已成功异步传送的任何消息应该从适配器的专用应用程序消息队列中删除，以防止消息被发送两次。 一般情况下之后,**终止**调用由消息传送引擎它不接受请求将从适配器的新消息发布。 这种情况的一个例外是与要求-响应对相关的消息。  
  
## <a name="see-also"></a>另请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送异步接口的适配器](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [同步的批处理支持发送适配器的的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步批处理支持发送适配器的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务异步批处理支持发送适配器的的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [适配器发送的请求作出响应的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)