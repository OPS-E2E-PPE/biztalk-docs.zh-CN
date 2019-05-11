---
title: MSMQ 适配器体系结构 |Microsoft Docs
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
ms.openlocfilehash: 1445907a98b6e86ae898015d131b0a5f892351a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263649"
---
# <a name="msmq-adapter-architecture"></a>MSMQ 适配器体系结构
MSMQ 适配器，您可以利用 Microsoft 消息队列 (也称为 MSMQ) 功能，否则将在 BizTalk Server 中不可用。  
  
## <a name="adapter-structure"></a>适配器结构  
 MSMQ 适配器具有相同的结构与其他 BizTalk 适配器，并使用适配器框架。 它是一个设计时组件和运行时组件组成。 运行时组件中，又包含实现消息传输的元素。  
  
 设计时组件允许你配置用于发送和接收适配器的属性。  
  
 运行时组件可以将消息发送到在设计时定义的队列或从指定的队列接收消息。 适配器运行时作为 BizTalk Server 应用程序在同一进程中运行，并不会运行在独立主机中。  
  
 所有消息处理都依赖于本地消息队列服务，甚至对于远程队列。 对于远程队列，适配器将消息，传送到本地消息队列服务。 它，反过来，可以将消息发送到远程队列中。  
  
 有关完整列表的发送和接收配置属性，请参阅[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)并[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)。  
  
 有关消息队列的详细信息，请参阅 Microsoft TechNet 库中提供的以下主题：  
  
-   **消息队列设计指南**处[ http://go.microsoft.com/fwlink/?LinkId=137080 ](http://go.microsoft.com/fwlink/?LinkId=137080)。  
  
-   **消息队列操作指南**处[ http://go.microsoft.com/fwlink/?LinkId=137079 ](http://go.microsoft.com/fwlink/?LinkId=137079)。  
  
-   **消息队列疑难解答指南**处[ http://go.microsoft.com/fwlink/?LinkId=137081 ](http://go.microsoft.com/fwlink/?LinkId=137081)。  
  
-   **消息队列技术参考**处[ http://go.microsoft.com/fwlink/?LinkId=137082 ](http://go.microsoft.com/fwlink/?LinkId=137082)。  
  
## <a name="see-also"></a>请参阅  
 [MSMQ 适配器概述](../core/what-is-the-msmq-adapter.md)