---
title: 优化 MSMQ 适配器的性能 |Microsoft Docs
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
ms.openlocfilehash: ceb64bc73969015dec331d321dced5850ecb7d50
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323415"
---
# <a name="optimizing-performance-of-the-msmq-adapter"></a>优化 MSMQ 适配器的性能
优化 MSMQ 适配器不同之间发送和接收方。 通过在接收位置上设置属性控制在接收端的优化。 在发送端，可以通过使用业务流程来控制优化。  
  
## <a name="receive-optimization"></a>接收优化  
 在接收端，可以包含适配器应使用单个执行线程。 适配器使用单一线程或多个线程上的设置取决于**按序处理**属性上的接收位置，按如下所示：  
  
- 当该属性是 **，则返回 True**，适配器对单个线程。 这一次限制适配器一条消息，从而节省内存。 请注意，这会有效地设置**批大小**为一 (1)，而不考虑分配给它的属性表中的值。  
  
- 当**按序处理**是**False**，适配器在运行多个线程，并可以处理多条消息一次，从而提高性能。  
  
  必须设置**按序处理**到**True**如果管理服务器资源，以至或的数量或大小的消息可能会耗尽可用的内存。  
  
  此外可以通过减少的值控制内存使用量**批大小**接收位置上。 较小批大小在内存中保留较少的消息，并因此使用更少的内存。  
  
  将发送端口和接收位置上单独的计算机还可以减少内存使用。  
  
## <a name="send-optimization"></a>发送优化  
 在发送端，可以实现等效的单个消息使用示例业务流程来处理。 此示例发送一条消息并发送下一条消息，直到其收到确认，然后等待。 有关详细信息，请参阅[如何从代码创建 MSMQ 接收位置和发送端口](../core/how-to-create-msmq-receive-locations-and-send-ports-from-code.md)。  
  
## <a name="remote-transactional-read-operations"></a>远程事务性读取操作  
 与 BizTalk Server MSMQ 适配器是能够发出从事务性 MSMQ 队列进行远程读取的操作。  这是因为 MSMQ 4.0 和更高版本支持远程事务性读取的操作。  但是，事务性读取的操作是速度通常较慢的操作。 若要优化的性能，仅当没有其他选项时，才应使用它们。  
  
## <a name="see-also"></a>请参阅  
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)   
 [如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)   
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)