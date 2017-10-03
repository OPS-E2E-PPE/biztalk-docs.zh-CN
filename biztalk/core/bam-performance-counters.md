---
title: "BAM 性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4307f72f149405fbc04e4e6cc51efe87229c2bff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-performance-counters"></a>BAM 性能计数器
使用性能计数器可以监视 BAM 事件总线服务执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 下表列出了业务活动监视中可用的性能计数器。  
  
|计数器|Description|  
|-------------|-----------------|  
|Events being processed|BAM 事件总线服务当前处理的事件数。|  
|Batches being processed|BAM 事件总线服务当前处理的批数。|  
|Events Committed|BAM 事件总线服务在最近一秒提交给 SQL Server 的事件数。|  
|Records Committed|BAM 事件总线服务在最近一秒提交给 SQL Server 的记录数。|  
|Batches Committed|BAM 事件总线服务在最近一秒提交给 SQL Server 的批数。|  
|Total Events|BAM 事件总线服务自从启动后处理的事件数。|  
|Total Records|BAM 事件总线服务自从启动后处理的记录数。|  
|Total Batches|BAM 事件总线服务自从启动后处理的批数。|  
|Total Failed Batches|BAM 事件总线服务自从启动后处理失败的批数。|  
|Total Failed Events|BAM 事件总线服务自从启动后处理失败的事件数。|  
  
 这些性能计数器都位于 BizTalk:TDDS 性能对象下的性能监视器 (perfmon) 中。 这些性能计数器的实例名称是源服务器名称和源数据库名称的组合。 如果有两个 BAM 事件总线服务运行在同一个计算机上，但针对两个不同的源数据库，则您将看到两个 BAM 事件总线服务计数器实例。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [管理 BAM](../core/managing-bam.md)