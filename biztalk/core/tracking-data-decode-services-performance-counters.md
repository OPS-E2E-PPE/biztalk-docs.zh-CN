---
title: "跟踪数据解码服务性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99ec03138e455c671e9ccb69aa8bc4c5588d287c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tracking-data-decode-services-performance-counters"></a>跟踪数据解码服务性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:TDDS**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:TDDS|Batches being processed|当前 SQL 事务中要处理的批次数量。|  
||Batches committed|提交给目标数据库的批次数量。|  
||Events being processed|当前 SQL 事务中要处理的事件数量。|  
||Event Committed|此秒内提交给目标数据库的事件数。|  
||Records being processed|当前 SQL 事务中要处理的记录数量。|  
||Records Committed|此秒内提交给目标数据库的记录数。|  
||Total Batches|TDDS 处理的总批数。|  
||Total Events|TDDS 处理的总事件数。|  
||Total Failed Batches|TDDS 无法运行的总批数。|  
||Total Failed Events|TDDS 无法运行的总事件数。|  
||Total Records|TDDS 处理的总记录数。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk:TDDS**性能计数器对象，然后选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机限制的优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)