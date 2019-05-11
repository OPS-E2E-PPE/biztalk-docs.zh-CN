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
ms.openlocfilehash: 9d8f87fe34d75f0e511568fa0e91088a1b7608a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331506"
---
# <a name="interfaces-for-an-asynchronous-send-adapter"></a>发送适配器的异步接口
一次发送一个消息的适配器可以同步或异步发送消息。 它不会阻止传输代理线程，但执行发送操作时，而是使用单独的线程时，适配器将消息异步发送。 若要能够以异步方式发送消息，适配器必须实现以下接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
  以下步骤介绍发送适配器执行传输出 server 消息引擎的请求消息的操作的序列：  
  
1.  消息引擎将使用传输代理要传递给发送适配器的传出消息，通过调用**TransmitMessage**方法**IBTTransmitter**接口。  
  
2.  适配器会立即返回从**TransmitMessage**后存储消息要发送到某些内部队列，并返回`False`有关**bDeleteMessage**。 这将告知消息引擎会将消息传输以异步方式。  
  
3.  适配器发送的消息使用其自己的线程池。  
  
4.  发送操作完成后，适配器从 MessageBox 数据库中删除原始消息。 它从消息引擎使用获取一批**IBTTransportBatch.GetBatch**方法的传输代理，然后调用**DeleteMessage**。  
  
     下图显示了对象交互涉及创建异步发送适配器。  
  
     ![](../core/media/ebiz-sdk-devadapter5.gif "ebiz_sdk_devadapter5")  
以异步方式发送一条消息的工作流  
  
> [!NOTE]
>  我们建议适配器对当前正在处理的消息的计数。 适配器应该一直阻止**Terminate**方法，直到消息计数归零。 对于发送适配器，应适当地处理正在处理的消息。 这意味着已成功异步传送的任何消息，应删除来自适配器的专用应用程序的消息队列，以防止消息被发送两次。 一般情况下后, **Terminate**调用由消息引擎它不接受发布新消息来自适配器的请求。 此规则的例外是与要求-响应对相关的响应消息。  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的同步接口](../core/interfaces-for-a-synchronous-send-adapter.md)   
 [同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [要求-响应发送适配器的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)