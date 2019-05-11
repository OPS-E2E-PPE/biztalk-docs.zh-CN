---
title: 消息框性能计数器 |Microsoft Docs
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
ms.openlocfilehash: 43c0d914e9e45175672e3cf207ede11608e8438a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394580"
---
# <a name="message-box-performance-counters"></a>Messagebox 性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**biztalk: Message Box: General Counters**并**biztalk: Message Box: Host Counters**性能对象类别:  
  
> [!NOTE]
>  若要启用引用 SQL 代理作业的计数器，必须包括 SQLAgentUserRole 向服务帐户用于运行 BizTalk 主机/NT 服务的角色。 或者，可以授予权限使用其他角色或通过授予读取 MSDB 数据库的显式权限。  
  
> [!NOTE]
>  如果已向 BizTalk Server 组来添加一个新的 MessageBox，下面列出的计数器将不能为新的 MessageBox 之前已配置**缓存刷新**经过为 BizTalk Server 组的时间间隔 （默认值为 60秒为单位）。  
  
|Category|计数器|Description|  
|--------------|-------------|-----------------|  
|常规计数器|实例总计数|跟踪的每个主机存在特定的消息框中的所有实例的总和。|  
|常规计数器|MsgBox 死进程清理 （清除作业）|以秒为单位的 SQL 代理作业用于释放与死 BizTalk 进程关联的行的数据库的最近运行的时间。|  
|常规计数器|MsgBox Msg 清理 （清除作业）|时间 （秒） 的最新运行 SQL 代理作业用于清除与删除的消息关联的 messagebox 表。|  
|常规计数器|MsgBox 部件清理 （清除作业）|以秒为单位的最新运行 SQL 代理作业用于清除与关联的 messagebox 表已删除消息部分的时间。|  
|常规计数器|MsgBox 清除订阅作业 （清除作业）|以秒为单位的最新运行 SQL 代理作业用于清除不再使用的订阅的时间。|  
|常规计数器|后台处理大小|在特定服务器上特定 messagebox 跟踪后台缓冲区的大小。|  
|常规计数器|跟踪的消息复制 （清除作业）|时间 （秒） 的最新运行 SQL 代理作业的复制所跟踪的消息正文跟踪的消息。|  
|常规计数器|跟踪数据大小|在特定服务器上特定 messagebox 跟踪的跟踪数据大小的表。|  
|常规计数器|跟踪后台处理清除 （清除作业）|以秒为单位的最新的 SQL 代理作业用于清除非活动状态的运行时间跟踪后台处理表。|  
|主机计数器|主机队列-实例状态消息引用-长度|跟踪此特定主机的实例状态队列中消息引用的数目。|  
|主机计数器|主机队列-长度|跟踪特定主机队列中消息的总数。|  
|主机计数器|主机队列-实例数|跟踪此特定主机的实例数。|  
|主机计数器|主机队列-挂起的消息的长度|跟踪特定主机的挂起的消息总数。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中选择**biztalk: Message Box: General Counters**或**biztalk: Message 框： 主机计数器**。 展开所选的性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机阻止优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)