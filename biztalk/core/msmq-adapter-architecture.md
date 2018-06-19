---
title: MSMQ 适配器体系结构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd314b6f835568b6336121478268b84381a288ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263045"
---
# <a name="msmq-adapter-architecture"></a>MSMQ 适配器体系结构
通过 MSMQ 适配器，您可以利用其他情况下在 BizTalk Server 中无法使用的 Microsoft 消息队列（也称为 MSMQ）功能。  
  
## <a name="adapter-structure"></a>适配器结构  
 MSMQ 适配器与其他 BizTalk 适配器具有相同的结构，并使用适配器框架。 它由一个设计时组件和一个运行时组件组成。 而运行时组件又包含实现消息传输的元素。  
  
 使用设计时组件，您可以配置适配器的发送和接收属性。  
  
 运行时组件可向设计时定义的队列发送消息，或者从指定的队列接收消息。 该适配器运行时与 BizTalk Server 应用程序运行在同一进程中，而不是运行在独立主机中。  
  
 所有消息处理均依赖于本地消息队列服务，甚至对于远程队列也是如此。 对于远程队列，适配器将消息传送到本地消息队列服务。 然后，本地消息队列服务将消息发送到远程队列。  
  
 有关完整列表的发送和接收配置属性，请参阅[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)和[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)。  
  
 有关消息队列的详细信息，请参阅 Microsoft TechNet 库中提供的以下主题：  
  
-   **消息队列的设计指南**在[http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080)。  
  
-   **消息队列操作指南**在[http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079)。  
  
-   **消息队列故障排除指南**在[http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081)。  
  
-   **消息队列技术参考**在[http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082)。  
  
## <a name="see-also"></a>另请参阅  
 [什么是 MSMQ 适配器？](../core/what-is-the-msmq-adapter.md)