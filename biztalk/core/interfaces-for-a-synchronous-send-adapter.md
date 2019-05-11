---
title: 发送适配器的同步接口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e1b397a-3a35-4447-8522-d8a5f39a42d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c2398840eb44fcaf8dd42259704d860d7466ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331595"
---
# <a name="interfaces-for-a-synchronous-send-adapter"></a>发送适配器的同步接口
阻止传入消息引擎在执行发送操作时调用线程时，适配器将消息以同步方式发送。 若要能够同步发送消息，适配器必须实现以下接口：  
  
- **IBTTransport**  
  
- **IBaseComponent**  
  
- **IBTTransportControl**  
  
- **IPersistPropertyBag**  
  
- **IBTTransmitter**  
  
  在同步发送中，适配器将消息发送时阻塞**TransmitMessage**，和传输成功返回后 `True.`  
  
  下图显示了对象交互涉及创建同步发送适配器。  
  
  ![](../core/media/ebiz-sdk-devadapter4.gif "ebiz_sdk_devadapter4")  
  以同步方式发送一条消息的工作流  
  
## <a name="see-also"></a>请参阅  
 [适配器变量](../core/adapter-variables.md)   
 [开发发送适配器](../core/developing-a-send-adapter.md)   
 [实例化和初始化发送适配器](../core/instantiating-and-initializing-a-send-adapter.md)   
 [发送适配器的异步接口](../core/interfaces-for-an-asynchronous-send-adapter.md)   
 [同步的支持批的发送适配器的接口](../core/interfaces-for-a-synchronous-batch-supported-send-adapter.md)   
 [异步的支持批的发送适配器的的接口](../core/interfaces-for-an-asynchronous-batch-supported-send-adapter.md)   
 [事务性异步的支持批的发送适配器的接口](../core/interfaces-for-a-transactional-asynchronous-batch-supported-send-adapter.md)   
 [要求-响应发送适配器的接口](../core/interfaces-for-a-solicit-response-send-adapter.md)