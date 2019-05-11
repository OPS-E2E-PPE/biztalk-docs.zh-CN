---
title: 跟踪数据库的大小调整准则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, performance
- Tracking database, size
- Tracking Analysis Server database [BAM]
- performance, Tracking database
ms.assetid: 2188bee5-c0dd-4448-bd4a-4ffb2a0c79f1
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ce436ac194c06481f80e80c4add3f70f48872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313926"
---
# <a name="tracking-database-sizing-guidelines"></a>跟踪数据库的大小调整准则
本部分介绍在 BizTalk 跟踪 (BizTalkDTADb) 数据库调整大小考虑事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 它介绍了如何使用公式和消息变量来确定如何大型 BizTalk 跟踪数据库将处于给定的一段时间，并提供如何应用这些公式的具体示例。 这提供了 BizTalk 消息、 跟踪设置和跟踪数据库之间粗略的相互关系大小。 不考虑帐户中的跟踪表; 的索引大小等其他因素的 SQL Server您可能想要考虑合理的乘数以便说明这些因素。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)  
  
-   [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)  
  
-   [方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)  
  
-   [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)  
  
-   [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)  
  
-   [方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)  
  
## <a name="see-also"></a>请参阅  
 [跟踪数据库中的记录大小](../core/record-size-in-tracking-databases.md)   
 [备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server-databases.md)