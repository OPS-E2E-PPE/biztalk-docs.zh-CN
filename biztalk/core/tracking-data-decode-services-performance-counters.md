---
title: 跟踪数据解码服务性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 733450b1-71b5-48a4-9ac3-cd880324440c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 944baf51a1ca10edc157f2062a6883d77ddffeb0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313899"
---
# <a name="tracking-data-decode-services-performance-counters"></a>跟踪数据解码服务性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Tdds**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|BizTalk:TDDS|正在处理的批处理|当前 SQL 事务中要处理的批数。|  
||已提交的批|提交到目标数据库的批数。|  
||正在处理的事件|当前 SQL 事务中要处理的事件数。|  
||已提交的事件|这一秒内提交到目标数据库的事件数。|  
||正在处理的记录|当前 SQL 事务中要处理的记录数。|  
||已提交的记录|这一秒内提交到目标数据库的记录数。|  
||总批|TDDS 处理的总批。|  
||Total Events|TDDS 处理的事件总数。|  
||失败的批处理的总数|总批运行失败的 TDDS。|  
||失败事件总数|无法运行的 TDDS 事件总数。|  
||记录总数|TDDS 处理的总记录。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**biztalk: Tdds**性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机阻止优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)