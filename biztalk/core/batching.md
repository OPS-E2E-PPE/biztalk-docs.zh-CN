---
title: 批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941ded3f6b88c835c2eae819099449ed7d4e6974
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529094"
---
# <a name="batching"></a>批处理
*批处理*是一种允许将用于优化数据库往返过程的一组消息的序列化的处理。 一批是原子; 工作单元也就是说，它要么全部成功要么所有失败。 如果在批处理中的一个操作成功，但另一个操作失败，构成批的所有操作都将失效，并且必须重复。  
  
 BizTalk Server 使用批处理执行：  
  
-   在许多消息范围内分摊交易成本。  
  
-   通过减少数据库的内部数量的增加速度往返。  
  
-   使用 BizTalk Server 异步 API 发出更有效地使用 BizTalk Server 线程池。  
  
## <a name="applying-batching"></a>应用批处理  
 批处理的接收位置的高级属性中配置和发送端口端自动启用。  
  
## <a name="lowering-the-batch-size"></a>减小批大小  
 如果在以下情况下，应减小批大小：  
  
-   处理大消息时  
  
-   当数据库往返行程不是瓶颈所在  
  
> [!NOTE]
>  更改时要小心**LargeMessageThreshold**设置。 批大小乘以平均消息大小应小于**LargeMessageThreshold**设置，除非批大小为 1。  
  
## <a name="see-also"></a>请参阅  
 [消息引擎](../core/the-messaging-engine.md)   
 [批处理消息的接收处理](../core/batching-messages-for-receive-processing.md)   
 [为发送处理批处理消息](../core/batching-messages-for-send-processing.md)