---
title: 消息框性能计数器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eafbd7b-f5fc-4942-a975-18154e6a7ee2
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 584cad0c850b85ef7c920da1611adbdc464d7250
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972779"
---
# <a name="message-box-performance-counters"></a>消息框性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk:Message Box: General 计数器**和**BizTalk:Message 框： 主机计数器**性能对象类别:  
  
> [!NOTE]
>  若要启用引用 SQL 代理作业的计数器，必须在用于运行 BizTalk 主机/NT 服务的服务帐户中包含角色 SQLAgentUserRole。 或者，通过使用其他角色或授予显式权限，来授予读取 MSDB 数据库的权限。  
  
> [!NOTE]
>  如果已向你的 BizTalk Server 组来添加一个新的 MessageBox，下面列出的计数器将不能为新的 MessageBox 之前配置**缓存刷新**BizTalk Server 组的间隔已过去 （默认值为 60秒为单位）。  
  
|类别|计数器|Description|  
|--------------|-------------|-----------------|  
|General Counters|Instances-Total Number|跟踪每个主机的所有实例总数，这些实例存在于特定 MessageBox 内。|  
|General Counters|MsgBox Dead Processes Cleanup (Purge Jobs)|最近运行 SQL 代理作业的时间（以秒计），该作业用于释放与死 BizTalk 进程关联的数据库行。|  
|General Counters|MsgBox Msg Cleanup (Purge Jobs)|最近运行 SQL 代理作业的时间（以秒计），该作业用于清除与已删除消息关联的 MessageBox 表。|  
|General Counters|MsgBox Parts Cleanup (Purge Jobs)|最近运行 SQL 代理作业的时间（以秒计），该作业用于清除与已删除消息部分关联的 MessageBox 表。|  
|General Counters|MsgBox 清除订阅作业 （清除作业）|以秒为单位的清除订阅不再使用的 SQL 代理作业的最新运行的时间。|  
|General Counters|假脱机大小|在特定服务器上的特定消息框上跟踪假脱机的大小。|  
|General Counters|跟踪消息数副本 （清除作业）|时间 （秒） 的 SQL 代理作业的复制所跟踪的消息正文的最新运行跟踪的消息。|  
|General Counters|跟踪数据的大小|跟踪数据的大小表的特定消息框上的特定服务器的跟踪。|  
|General Counters|跟踪假脱机清理 （清除作业）|时间 （秒） 清除非活动状态的 SQL 代理作业的最新运行跟踪假脱机表。|  
|主机计数器|主机的实例状态消息 Refs 的队列长度|为该特定主机的跟踪的消息的实例状态队列中的引用的数目。|  
|主机计数器|Host Queue - Length|跟踪特定主机队列中的邮件总数。|  
|主机计数器|主机队列的实例数|跟踪此特定主机的实例数。|  
|主机计数器|主机-挂起的消息的队列长度|跟踪特定主机的挂起的消息总数。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，选择**BizTalk:Message Box: General 计数器**或**BizTalk:Message 框： 承载计数器**。 展开所选性能计数器对象，然后选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机限制的优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)