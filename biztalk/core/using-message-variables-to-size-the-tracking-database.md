---
title: 使用消息变量调整跟踪数据库的大小 |Microsoft Docs
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
ms.openlocfilehash: 8ac96e6784ed73dce415c78ff5f559d52be42395
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396827"
---
# <a name="using-message-variables-to-size-the-tracking-database"></a>使用消息变量调整跟踪数据库的大小
在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可以使用许多变量来确定如何大型 BizTalk 跟踪 (BizTalkDTADb) 数据库将处于给定的一段时间。 这些变量包括：  
  
- 使用的管道数  
  
- 所涉及的业务流程数  
  
- 生成的事件数  
  
- 跟踪消息属性的数目  
  
- 创建的其他消息数  
  
- 估计在指定时间范围内接收的消息数  
  
  尽管用于估算 BizTalk 跟踪数据库的大小的公式非常简单，必须先将它应用于使用 BizTalk Server 实现每个传入和传出消息进程。 换句话说，需要将每个不同的消息方案为此公式应用以及如何将结果以获得最终估算的数据库大小。 本文档中我们将介绍两种方案。 方案是：  
  
1. 接收一条消息，转换该消息，然后发送生成的消息  
  
2. 接收消息，运行业务流程使用的消息，并将发送生成的消息。  
  
   这两个方案可能会出现在 BizTalk Server 安装，并每个方案生成不同数量的跟踪数据。 跟踪生成的 BizTalk Server 安装的数据的总是所有方案的总和。  
  
   等式中使用的一些变量如下：  
  
|变量|Description|  
|--------------|-----------------|  
|**Nserv**|许多服务 （管道数） + 的业务流程数|  
|**事件**|生成的消息事件数|  
|**属性**|跟踪消息属性的数目|  
|**PropSize**|大小 （以字节为单位） 的升级属性 （字段）|  
|**CMsgs**|创建每个传入消息的其他消息数|  
|**消息数**|在给定的时间段内估计传入消息数|  
|**MsgSize**|消息大小|  
|**MsgNum**|为每个传入消息跟踪的消息数|  
  
 公式如下所示：  
  
```  
[((Nserv * 150 bytes) + (Events * 230 bytes) + (Properties * CMsgs*(52 bytes + PropSize))) * Msgs]/1024/1024 = Data size in MB  
```  
  
 此公式计算由消息生成的跟踪数据并不包括为业务流程调试器生成的跟踪数据。 必须将此公式应用于每个消息进程才能估算 BizTalk 跟踪数据库的大小。  
  
## <a name="see-also"></a>请参阅  
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)