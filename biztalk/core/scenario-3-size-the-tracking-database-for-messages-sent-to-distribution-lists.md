---
title: 方案 3： 调整跟踪数据库的大小的消息发送到通讯组列表扩展 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: bc6e0da0-46d1-42d6-8ec9-29a28719fbb3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb9a5992865ffbf09a493a480ecbcb61e9c0f034
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996214"
---
# <a name="scenario-3-sizing-the-tracking-database--for-messages-sent-out-to-distribution-lists"></a>方案 3：对发送到分发列表的消息调整跟踪数据库的大小
下图中的消息将通过业务流程、在业务流程内被更改，然后通过分发列表向外发送给多个不同的发送端口：  
  
 ![通过业务流程到多个端口的消息](../core/media/biztalk-server-message-orch-multiple-ports.gif "BizTalk_Server_message_orch_multiple_ports")  
  
 **通过业务流程和发送到多个不同端口的 BizTalk Server 消息**  
  
 以下为有关此方案的一些实际信息：  
  
- 消息大小为 10k。  
  
- 当前不升级任何属性。  
  
- 一年中接收的消息数为 350 万条。  
  
- 已打开对所有事件的跟踪。 此方案包含以下五个事件：  
  
  -   接收消息 M0  
  
  -   输出消息 M1 从接收端口  
  
  -   通过发送端口输出消息 M3  
  
  -   通过发送端口输出消息 M4  
  
  -   通过发送端口输出消息 M5  
  
  将这些信息应用到公式中之后结果如下：  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-a-single-promoted-property"></a>业务流程中发送给分发列表并且具有单个升级属性的消息  
 在此示例中，请按照之前方案中所执行的操作来升级大小约为 10 字节的单个属性。 公式现在如下所示：  
  
```  
[((5*150 bytes) + (10*230 bytes) + (1*5(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 260) * 3,500,000]/1024/1024 = 11048 MB ~ 10.79 GB per year  
```  
  
 如果另外升级一个大小为 20 字节的属性，则公式将如下所示：  
  
```  
[((5*150 bytes) + (10*230 bytes) + ((1*5(52 bytes + 10 bytes) + (1*5(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(750 + 2300 + 670) * 3,500,000]/1024/1024 = 12417 MB ~ 12.13 GB per year  
```  
  
## <a name="messages-in-an-orchestration-that-are-sent-out-to-a-distribution-list-with-message-body-tracking-activated"></a>业务流程中发送给分发列表并且已激活消息正文跟踪的消息  
 若要允许消息跟踪，则对于此示例，公式将如下所示：  
  
```  
[3,500,000 * 6 * 5KB]/1024 = 102539.06 MB ~ 100.14 GB per year  
  
```  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1： 调整简单 BizTalk 消息的大小跟踪数据库](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2： 业务流程中消息调整跟踪数据库](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4：为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)