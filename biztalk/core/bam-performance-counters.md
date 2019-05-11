---
title: BAM 性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], performance counters
- performance, counters [BAM]
ms.assetid: e23f7038-36a5-4957-bc73-47011763d109
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad0502e27bfaefb25d03e88b6d1730d0495cc189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358461"
---
# <a name="bam-performance-counters"></a>BAM 性能计数器
性能计数器可以监视 BAM 事件总线服务执行的工作的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 下表列出了业务活动监视中可用的性能计数器。  
  
|计数器|Description|  
|-------------|-----------------|  
|正在处理的事件|BAM 事件总线服务当前正在处理的事件数|  
|正在处理的批处理|BAM 事件总线服务当前正在处理的批数|  
|已提交的事件|BAM 事件总线服务在最近一秒提交给 SQL Server 的事件数。|  
|已提交的记录|BAM 事件总线服务在最近一秒提交给 SQL Server 的记录数。|  
|已提交的批|BAM 事件总线服务在最近一秒提交给 SQL Server 的批数。|  
|Total Events|BAM 事件总线服务自从您启动以来已处理的事件数。|  
|记录总数|然后启动 BAM 事件总线服务自从已处理的记录数。|  
|总批|然后启动 BAM 事件总线服务自从已处理的批数。|  
|失败的批处理的总数|然后批处理失败 BAM 事件总线服务自从启动后处理的数。|  
|失败事件总数|然后事件失败 BAM 事件总线服务自从启动后处理的数。|  
  
 性能计数器都位于 biztalk: Tdds 性能对象下的性能监视器 (perfmon)。 性能计数器的实例名称是源服务器名称和源数据库的名称的组合。 如果两个 BAM 事件总线服务在对两个不同的源数据库在同一台计算机上运行，您将看到两个 BAM 事件总线服务计数器实例。  
  
## <a name="see-also"></a>请参阅  
 [管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md)   
 [BAM 安全建议](../core/bam-security-recommendations.md)   
 [管理 BAM](../core/managing-bam.md)