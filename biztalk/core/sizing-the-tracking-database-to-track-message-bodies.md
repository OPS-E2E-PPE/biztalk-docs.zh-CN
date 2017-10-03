---
title: "大小调整跟踪消息正文的跟踪数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
- message variables [Tracking database], MsgNum
- HAT, ports
- Tracking database, messages
- tracking, orchestrations
- tracking, messages
- HAT, orchestrations
- tracking, ports
ms.assetid: ee75e530-f15d-4ceb-ba67-0b0b24d9df6b
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b5abc3f2a48f2baea5d158e1a0268a7eede51c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a>大小调整跟踪数据库来跟踪消息正文
如果计划在 BizTalk 跟踪数据库中跟踪消息正文，那么，在计算时还需考虑这些正文的大小。 请使用以下公式：  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 如果与消息大小相比，消息上下文非常大，请考虑增加上面 MsgSize 中的消息上下文的平均大小。  
  
 通过在端口级别和业务流程级别打开跟踪功能，使用“组中心”页中的消息事件和服务实例跟踪来确定 MsgNum 变量。 您还必须将此公式应用于每个消息流程。  
  
## <a name="see-also"></a>另请参阅  
 [使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3： 调整跟踪数据库的消息发送到通讯组列表](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)