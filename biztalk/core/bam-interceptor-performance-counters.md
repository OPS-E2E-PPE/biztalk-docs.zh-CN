---
title: "BAM 拦截器性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 989316edff34463905c7547db815b3daaf4d4a46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-interceptor-performance-counters"></a>BAM 侦听器性能计数器
使用性能计数器可以监视 BAM 侦听器执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 下表列出了可用于 BAM 侦听器的性能计数器。 这些性能计数器的类别为“BAM 侦听器”。  
  
|计数器|Description|  
|-------------|-----------------|  
|Avg.失败的 BAM 事件/刷新 Avg|在每次将数据刷新到主导入数据库期间发生的失败 BAM 事件的平均数。|  
|Successful BAM Events/Flush|在每次将数据刷新到主导入数据库期间发生的成功 BAM 事件的平均数。 如果回滚相应事务，则这些事件可能不会保留到数据库中。|  
|Avg.提取秒/BAM 事件|提取 BAM 事件花费的时间的平均值。|  
|Avg.刷新秒/BAM 事件|刷新 BAM 事件花费的时间的平均值。|  
|Total Failed BAM Events During Flush|数据刷新期间发生的失败 BAM 事件的总数。|  
|刷新过程中成功的 BAM 事件总数|刷新到主导入数据库的成功 BAM 事件的总数。 如果回滚相应事务，则这些事件可能不会保留到数据库中。|  
  
## <a name="see-also"></a>另请参阅  
 [BAM 性能计数器](../core/bam-performance-counters.md)