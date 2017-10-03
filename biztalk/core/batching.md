---
title: "批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batching"></a>批处理
*批处理*是一种允许与目标为数据库优化往返的一组消息的序列化的处理。 批是原子工作单元；也就是说，它或者全部成功，或者全部失败。 如果批中的某个操作成功，但另一个操作失败，则构成该批的所有操作都将失效，必须重新执行。  
  
 BizTalk Server 使用批处理执行以下操作：  
  
-   对于不同的许多消息分摊事务的成本。  
  
-   通过减少数据库内部数量的增加速度往返。  
  
-   通过使用 BizTalk Server 异步 API 更高效地使用 BizTalk Server 线程池。  
  
## <a name="applying-batching"></a>应用批处理  
 批处理在接收位置的高级属性中进行配置，并且在发送端口端自动启用。  
  
## <a name="lowering-the-batch-size"></a>减小批大小  
 在以下情况下应减小批大小：  
  
-   在处理大的消息时  
  
-   当数据库往返过程并非瓶颈所在时  
  
> [!NOTE]
>  更改时要小心**LargeMessageThreshold**设置。 乘以平均消息大小的批处理大小应该小于**LargeMessageThreshold**设置，除非批处理大小为 1。  
  
## <a name="see-also"></a>另请参阅  
 [消息传送的引擎](../core/the-messaging-engine.md)   
 [批处理消息接收处理](../core/batching-messages-for-receive-processing.md)   
 [对消息进行批处理的发送处理](../core/batching-messages-for-send-processing.md)