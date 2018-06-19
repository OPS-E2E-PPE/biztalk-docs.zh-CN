---
title: 挂起的消息都包含在数据库限制阈值中的消息计数 |Microsoft 文档
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
ms.openlocfilehash: 7f8ea0643ccf2d6206ba86bc56b5dd54c0d51115
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278125"
---
# <a name="suspended-messages-are-included-in-the-message-count-in-database-throttling-threshold"></a>挂起消息包括在数据库中的消息数阻止阈值
默认情况下，主机**消息在数据库中的计数**限制阈值设置为值为 50000，就会触发在下列情况下的限制条件：  
  
-   主机实例发布到订阅主机的工作、状态和已挂起队列的消息总数超过 50,000。  
  
-   假脱机表或跟踪表中的消息数超过 500,000 消息。  
  
 因为挂起的消息都将纳入**消息在数据库中的计数**计算，即使 BizTalk server 遇到低，会发生发布的消息或无负载的限制。  
  
## <a name="recommendations"></a>建议  
  
-   如果你希望你可能有大量的挂起的消息，请考虑增加的默认值为**消息在数据库中的计数**考虑到包含的 SQL 服务器的空间要求的阈值BizTalk 数据库。 此外可以考虑提高**假脱机乘数**和**跟踪数据乘数**值，以允许在假脱机表中使用其他积压工作。  
  
     有关这些值的详细信息，请参阅[如何修改资源基于限制设置](../core/how-to-modify-resource-based-throttling-settings.md)。  
  
-   使用**限制状态消息发布**与关联的性能监视器计数器**BizTalk:MessageAgent**性能对象类别来测量当前限制状态。 如果此计数器返回的值为 6，请检查挂起实例，根据需要终止或恢复挂起实例。  
  
     有关主机限制性能计数器的详细信息，请参阅[主机限制性能计数器](../core/host-throttling-performance-counters.md)。  
  
## <a name="see-also"></a>另请参阅  
 [限制的设计建议](../core/throttling-design-recommendations.md)