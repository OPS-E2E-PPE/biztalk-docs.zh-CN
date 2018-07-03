---
title: 挂起的消息包括在数据库限制阈值中的消息计数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9eb708bb-6d6d-4494-8b8d-67aa44800a20
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa3f26d8456836700f0e855329eaa8178f49df4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007070"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a>挂起消息包括在数据库中的消息数阻止阈值
默认情况下主机**DB 中的消息数**阻止阈值设置为 50000，会触发在下列情况下的在触发阻止条件的值：  
  
- 主机实例发布到订阅主机的工作、状态和已挂起队列的消息总数超过 50,000。  
  
- 后台处理表或跟踪表中的消息数超过 500,000 条消息。  
  
  由于挂起的消息包括在**DB 中的消息数**计算，即使 BizTalk 服务器很低，会出现发布的消息或没有负载的限制。  
  
## <a name="recommendations"></a>建议  
  
-   如果你希望你可能有大量挂起消息，请考虑增加的默认值为**DB 中的消息数**考虑到包含 SQL server 的空间要求的阈值BizTalk 数据库。 还要考虑增加**后台乘数**并**跟踪数据乘数**值，以允许后台处理表中的更多的积压。  
  
     有关这些值的详细信息，请参阅[如何修改资源基于阻止设置](../core/how-to-modify-resource-based-throttling-settings.md)。  
  
-   使用**消息发布阻止状态**与关联的性能监视器计数器**biztalk: Messageagent**性能对象类别来测量当前阻止状态。 如果此计数器返回的值为 6，请检查挂起实例，根据需要终止或恢复挂起实例。  
  
     有关主机阻止性能计数器的详细信息，请参阅[主机阻止性能计数器](../core/host-throttling-performance-counters.md)。  
  
## <a name="see-also"></a>请参阅  
 [限制设计建议](../core/throttling-design-recommendations.md)