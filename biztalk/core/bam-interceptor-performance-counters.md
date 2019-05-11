---
title: BAM 侦听器性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b9b64ae1-4d94-4c3c-add1-fa020713be5c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a8d3cc2f6ab4eb0945f6f7d8563ad675e1c69de
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530574"
---
# <a name="bam-interceptor-performance-counters"></a>BAM 侦听器性能计数器
性能计数器可以监视 BAM 侦听器执行的工作的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 下表列出可用的性能计数器的 BAM 侦听器。 性能计数器的类别为"BAM 侦听器"。  
  
|计数器|Description|  
|-------------|-----------------|  
|Avg.失败的 BAM 事件/刷新 Avg|过程的数据刷新到主导入数据库中发生的失败 BAM 事件平均数。|  
|成功的 BAM 事件/刷新|过程数据刷新到主导入数据库中发生的成功 BAM 事件平均数。 如果事务回滚，这些事件可能不会保留到数据库。|  
|Avg.提取秒/BAM 事件|提取 BAM 事件所用的平均时间量。|  
|Avg.刷新秒/BAM 事件|刷新 BAM 事件所用的平均时间量。|  
|将失败 BAM 事件总数在刷新过程|数据刷新过程中发生的失败 BAM 事件总数|  
|在刷新期间的总的成功 BAM 事件|到主导入数据库刷新的成功 BAM 事件总数。 如果事务回滚，这些事件可能不会保留到数据库。|  
  
## <a name="see-also"></a>请参阅  
 [BAM 性能计数器](../core/bam-performance-counters.md)