---
title: 业务流程引擎性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dcaf7517-da4a-4ed0-a3bb-7e9b73931bff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645422d1f3ad0a24837fa216bd55c38e57413de6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323226"
---
# <a name="orchestration-engine-performance-counters"></a>业务流程引擎性能计数器
业务流程引擎维护多个性能计数器，可以检查与性能监视器来查看业务流程实例数，并且随着时间的推移引擎处理的事务。  
  
 若要运行性能监视器，请转到**启动**菜单上，选择**运行**，键入**perfmon**，然后按**Enter**。 单击**外**按钮，然后选择**XLANG/s 业务流程**从**性能对象**下拉列表。  
  
 以下性能计数器都可以访问每个主机实例下**XLANG/s 业务流程**性能对象类别：  
  
|计数器|注释|  
|-------------|--------------|  
|已用物理内存百分比|已用的计算机上的总物理内存的百分比。|  
|活动的应用程序域|进程中加载的业务流程应用程序域数。|  
|平均批身份|由于主机实例启动时，除以底层事务数达到的持久化点数量。|  
|数据库事务|自从主机实例启动以来执行的数据库事务数。|  
|每秒数据库事务|每秒执行的平均数量。|  
|Dehydratable orchestrations|当前以主机实例为宿主的能够冻结的业务流程实例数。|  
|Dehydrating orchestrations|正在冻结的业务流程数。|  
|Dehydration cycle in progress|指示当前是否存在正在进行的冻结周期。|  
|Dehydration cycles|已完成的冻结周期数。|  
|Dehydration threshold|确定是否主动冻结业务流程的时间长度（以毫秒计）。 如果业务流程引擎预测某个实例可以冻结一段时间，而且这段时间的长度大于此阈值，则它将冻结该实例。|  
|空闲业务流程|当前以主机实例为宿主的空闲业务流程实例数。 这是指没有进展也不可冻结，如业务流程被阻止时等待接收，侦听或延迟在原子事务中的业务流程。|  
|分配的专用内存兆字节为单位|主机实例分配的专用内存兆字节为单位。|  
|分配的虚拟内存兆字节为单位|保留适用于主机实例的虚拟内存兆字节。|  
|MessageBox 数据库连接失败|数据库连接尝试的失败，因为启动主机实例的数目。|  
|联机 MessageBox 数据库|当前可用的应用程序的 MessageBox 数据库数。|  
|已完成的业务流程|自从主机实例启动以来已完成的业务流程实例数。|  
|已完成的业务流程数/秒|每秒完成的平均数量。|  
|创建业务流程|自从主机实例启动以来创建的业务流程实例数。|  
|创建的业务流程数/秒|每秒创建的平均数。|  
|Orchestrations dehydrated|自从主机实例启动以来，冻结的业务流程实例的数量。|  
|Orchestrations dehydrated/sec|平均每秒冻结的业务流程数。|  
|丢弃的业务流程|自从主机实例启动以来，从内存丢弃的业务流程实例数。 如果引擎未能持久化其状态，业务流程可以被放弃。|  
|丢弃的业务流程数/秒|每秒丢弃的平均数。|  
|Orchestrations rehydrated|自从主机实例启动以来，解除冻结的业务流程实例的数量。|  
|Orchestrations rehydrated/sec|每秒解除冻结的平均数。|  
|驻留在内存中的业务流程|当前以主机实例为宿主的业务流程实例数。|  
|Orchestrations scheduled for dehydration|冻结请求处于挂起状态的可冻结业务流程的数量。|  
|挂起的业务流程|已暂停，因为主机实例启动的业务流程实例数。|  
|挂起的业务流程数/秒|每秒挂起的平均数。|  
|挂起的消息|接收为其接收但尚未确认消息框的消息数。|  
|挂起的工作项|按计划执行的代码执行块的数目。|  
|持久性点|业务流程实例已持久化到数据库其状态，自从主机实例启动以来次数。|  
|暂留点/秒|每秒持久化业务流程实例的平均数量。|  
|可运行的业务流程|准备好执行业务流程实例数。|  
|运行业务流程|当前正在执行的业务流程实例数。|  
|中止的事务作用域|自从主机实例启动以来已中止的长期或原子作用域数。|  
|中止的事务作用域数/秒|每秒中止的平均数。|  
|已提交的事务作用域|自从主机实例启动以来已成功完成的长时间运行的或原子作用域数。|  
|已提交的事务作用域数/秒|每秒提交的平均数。|  
|补偿事务作用域|已成功完成补偿作用域，因为应用程序启动的长时间运行的或原子作用域数。|  
|每秒补偿事务作用域|每秒补偿的平均数。|  
  
## <a name="see-also"></a>请参阅  
 [引擎性能特征](../core/engine-performance-characteristics.md)   
 [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)