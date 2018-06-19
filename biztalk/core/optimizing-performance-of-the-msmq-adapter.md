---
title: 优化性能的 MSMQ 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, performance
- performance, MSMQ adapters
- configuring [MSMQ adapters], performance
ms.assetid: f8537ea8-a96e-4874-bcaf-cd1442a50bd4
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c5624eb6cf88f45d1ecad0b68fee3f5f7b8a8ba
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007334"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a>优化性能的 MSMQ 适配器
MSMQ 适配器的优化在发送端与接收端有所不同。 对于接收端，通过设置接收位置属性可控制优化。 对于发送端，则可以使用业务流程来控制优化。  
  
## <a name="receive-optimization"></a>接收优化  
 在接收端，适配器应使用单个执行线程。 适配器使用单线程还是多个线程依赖于设置**排序处理**属性接收位置，，如下所示：  
  
-   当该属性是**True**，适配器对单个线程。 这样可限制适配器一次只能处理一个消息，从而节省内存。 请注意，这将有效设置**批大小**为一 (1)，而不考虑分配给它的属性表中的值。  
  
-   当**排序处理**是**False**，适配器运行多个线程并可以处理多条消息一次，因此提高了性能。  
  
 必须设置**排序处理**到**True**如果将高级放在管理服务器资源，或如果数量或大小的消息可能会耗尽可用内存。  
  
 此外可以通过减少的值来控制内存使用**批大小**上接收位置。 较小的批大小可使内存中保持较少的消息，从而仅使用较少内存。  
  
 通过将发送端口和接收位置分别放置在单独的计算机上，也可以降低内存使用率。  
  
## <a name="send-optimization"></a>发送优化  
 在发送端，可以使用示例业务流程来实现等效的单个消息处理。 该示例将发送单个消息，然后一直等到其收到确认后才会发送下一个消息。 有关详细信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。  
  
## <a name="remote-transactional-read-operations"></a>远程事务性读取操作  
 与 BizTalk Server MSMQ 适配器是能够进行远程从事务 MSMQ 队列进行读取的操作。  这是因为 MSMQ 4.0 和更高版本支持远程事务性读取操作。  但是，事务性读取操作的速度通常较慢。 为优化性能，应在没有其他选择时使用这些操作。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)   
 [如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)   
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)