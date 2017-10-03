---
title: "业务流程引擎性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dcaf7517-da4a-4ed0-a3bb-7e9b73931bff
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b3dada1e3775c918d99b1ce0269ac8b1e2a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="orchestration-engine-performance-counters"></a>业务流程引擎性能计数器
业务流程引擎维护着几个性能计数器，您可以使用性能监视器来查看这些性能计数器，以确定随着时间的推移，引擎所处理的业务流程实例和事务的数量。  
  
 若要运行性能监视器，请转到**启动**菜单上，选择**运行**，键入**perfmon**，按**Enter**。 单击**添加**按钮，然后选择**XLANG/s 业务流程**从**性能对象**下拉列表。  
  
 以下性能计数器进行访问每个主机实例下**XLANG/s 业务流程**性能对象类别：  
  
|计数器|注释|  
|-------------|--------------|  
|% used physical memory|计算机上已使用的物理内存总数所占的百分比。|  
|Active application domains|进程中已加载的业务流程应用程序域的数量。|  
|Average batch factor|自从主机实例启动以来达到的持久化点数除以底层事务数。|  
|Database transactions|自从主机实例启动以来，执行的数据库事务数。|  
|Database transactions/sec|平均每秒执行的数据库事务数。|  
|Dehydratable orchestrations|当前以主机实例为宿主的能够冻结的业务流程实例数。|  
|Dehydrating orchestrations|正在冻结的业务流程数。|  
|Dehydration cycle in progress|指示当前是否存在正在进行的冻结周期。|  
|Dehydration cycles|已完成的冻结周期数。|  
|Dehydration threshold|确定是否主动冻结业务流程的时间长度（以毫秒计）。 如果业务流程引擎预测某个实例可以冻结一段时间，而且这段时间的长度大于此阈值，则它将冻结该实例。|  
|Idle orchestrations|当前以主机实例为宿主的空闲业务流程实例的数量。 空闲业务流程实例指没有进展也不可冻结的业务流程，即业务流程在原子事务中被阻止，以等待接收、侦听或延迟处理。|  
|Megabytes allocated private memory|为主机实例分配的专用内存的字节数 (MB)。|  
|Megabytes allocated virtual memory|为主机实例的虚拟内存保留的字节数 (MB)。|  
|MessageBox database connection failures|自从主机实例启动以来，数据库连接尝试的失败次数。|  
|Online MessageBox databases|当前可用于应用程序的 MessageBox 数据库的数量。|  
|Orchestrations completed|自从主机实例启动以来，完成的业务流程实例的数量。|  
|Orchestrations completed/sec|平均每秒完成的业务流程数。|  
|Orchestrations created|自从主机实例启动以来，创建的业务流程实例的数量。|  
|Orchestrations created/sec|平均每秒创建的业务流程数。|  
|Orchestrations dehydrated|自从主机实例启动以来，冻结的业务流程实例的数量。|  
|Orchestrations dehydrated/sec|平均每秒冻结的业务流程数。|  
|Orchestrations discarded|自从主机实例启动以来，内存中被丢弃的业务流程实例的数量。 如果引擎未能持久化某个业务流程的状态，则会将其丢弃。|  
|Orchestrations discarded/sec|平均每秒丢弃的业务流程数。|  
|Orchestrations rehydrated|自从主机实例启动以来，解除冻结的业务流程实例的数量。|  
|Orchestrations rehydrated/sec|平均每秒解除冻结的业务流程数。|  
|Orchestrations resident in memory|当前以主机实例为宿主的业务流程实例的数量。|  
|Orchestrations scheduled for dehydration|冻结请求处于挂起状态的可冻结业务流程的数量。|  
|Orchestrations suspended|自从主机实例启动以来，挂起的业务流程实例的数量。|  
|Orchestrations suspended/sec|平均每秒挂起的业务流程数。|  
|Pending messages|MessageBox 已接收但尚未确认其回执的消息数。|  
|Pending work items|已安排好执行时间的代码执行块的个数。|  
|Persistence points|自从主机实例启动以来，业务流程实例向数据库持久化其状态的次数。|  
|Persistence points/sec|平均每秒持久化业务流程实例的次数。|  
|Runnable orchestrations|可以执行的业务流程实例的数量。|  
|Running orchestrations|当前正在执行的业务流程实例的数量。|  
|Transactional scopes aborted|自从主机实例启动以来，已中止的长期作用域或原子作用域的数量。|  
|Transactional scopes aborted/sec|平均每秒中止的事务作用域数。|  
|Transactional scopes committed|自从主机实例启动以来，已成功完成的长期作用域或原子作用域的数量。|  
|Transactional scopes committed/sec|平均每秒提交的事务作用域数。|  
|Transactional scopes compensated|自从应用程序启动以来，已成功完成补偿作用域的长期作用域或原子作用域的数量。|  
|Transactional scopes compensated/sec|平均每秒补偿的事务作用域数。|  
  
## <a name="see-also"></a>另请参阅  
 [引擎性能特征](../core/engine-performance-characteristics.md)   
 [方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)