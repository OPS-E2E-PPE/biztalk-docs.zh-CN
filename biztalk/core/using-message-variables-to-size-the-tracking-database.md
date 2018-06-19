---
title: 使用消息变量来调整跟踪数据库的大小 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message variables [Tracking database], CMsgs
- message variables [Tracking database], Events
- message variables [Tracking database], Properties
- Tracking database, database size
- message variables [Tracking database], Nserv
- message variables [Tracking database], Msgs
- message variables [Tracking database], PropSize
- message variables [Tracking database]
- message variables [Tracking database], MsgSize
- message variables [Tracking database], MsgNum
- Tracking database, messages
ms.assetid: 2d31ae25-3d16-4002-b5a5-dca25e764ecd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5418cdf79499302e6127db7fb66f108825a0d8c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287837"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a>使用消息变量调整跟踪数据库的大小
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，可以使用许多变量来确定 BizTalk 跟踪 (BizTalkDTADb) 数据库在给定时间段后的大小。 这些变量包括：  
  
-   使用的管道数  
  
-   涉及的业务流程数  
  
-   生成的事件数  
  
-   跟踪的消息属性数  
  
-   创建的其他消息数  
  
-   在指定时间范围内估计接收的消息数  
  
 尽管用于估算 BizTalk 跟踪数据库大小的公式简单易懂，但您必须将其应用于每个使用 BizTalk Server 实现的传入和传出消息进程。 换而言之，您需要将此公式应用于每个不同的消息方案，然后对其结果进行合计以获得最终估算的数据库大小。 在本文档中我们将介绍两个方案。 这两个方案分别是：  
  
1.  接收消息，转换该消息，然后发送生成的消息。  
  
2.  接收消息，使用该消息运行业务流程，然后发送生成的消息。  
  
 这两个方案可能出现在一个 BizTalk Server 安装中，而每个方案会生成不同数量的跟踪数据。 为该 BizTalk Server 安装生成的全部跟踪数据就是这两个方案生成的总数据量。  
  
 公式中使用的一些变量如下所示：  
  
|变量|Description|  
|--------------|-----------------|  
|**Nserv**|服务数（管道数 + 业务流程数）|  
|**事件**|生成的消息事件数|  
|**属性**|跟踪的消息属性数|  
|**PropSize**|升级属性（字段）的大小（字节）|  
|**CMsgs**|为每个传入消息创建的其他消息数|  
|**消息数**|给定时间段内估计传入的消息数|  
|**MsgSize**|消息大小|  
|**MsgNum**|为每个传入消息跟踪的消息数|  
  
 该公式如下所示：  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 此公式仅计算由消息生成的跟踪数据，不包括为业务流程调试器生成的跟踪数据。 必须将此公式应用于所有消息进程才能估算 BizTalk 跟踪数据库的大小。  
  
## <a name="see-also"></a>另请参阅  
 [大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1： 调整跟踪数据库的简单 BizTalk 消息](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3： 调整跟踪数据库的消息发送到通讯组列表](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)