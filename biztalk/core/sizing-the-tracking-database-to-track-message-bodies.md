---
title: 调整跟踪数据库以跟踪消息正文的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d25a93548cdf98db3a40156bcd0dd0aff4d11b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401859"
---
# <a name="sizing-the-tracking-database-to-track-message-bodies"></a>调整跟踪数据库来跟踪消息正文大小
如果您计划跟踪 BizTalk 跟踪数据库中的消息正文，然后还将需要在计算这些正文的大小。 使用以下公式：  
  
```  
[Msgs * MsgNum * (MsgSize)]/1024 = Data size in MB  
```  
  
 请考虑上面 msgsize 中添加消息上下文的平均大小，如果这一点非常重要的消息大小。  
  
 通过打开端口级别或在业务流程级别使用的消息事件和在组中心页中的服务实例跟踪的跟踪功能确定 MsgNum 变量。 必须将此公式应用于每个消息流程。  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)