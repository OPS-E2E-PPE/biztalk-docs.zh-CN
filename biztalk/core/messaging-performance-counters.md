---
title: "消息传递性能计数器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 162d761a-fe69-45b0-a6af-c5d9f714e0ca
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72604822559d855f51bd24c6eacae3be3be4cbdd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="messaging-performance-counters"></a>消息传送性能计数器
使用性能计数器可以监视服务在站点或系统上执行的工作的特定方面。 性能计数器能够帮助您标识和解决有关服务器性能的问题。  
  
 以下性能计数器进行访问每个主机实例下**BizTalk： 消息传送**和**BizTalk： 消息延迟**性能对象类别：  
  
|**类别**|**计数器**|**Description**|  
|------------------|-----------------|---------------------|  
|BizTalk:Messaging|Active receive locations|此主机实例中当前启用的接收位置数。|  
||Active receive threads|消息引擎中当前正在处理特定消息的线程数，这些消息指从此主机实例上运行的适配器接收的消息。 这些消息包括发送适配器已经异步处理过的消息。|  
||Active send messages|消息引擎当前正在进行发送处理的消息数。 这包括当前正在发送管道中进行处理的消息，以及接收适配器的响应消息。|  
||Active send threads|消息引擎中当前正在处理发送给适配器的消息的线程数。 这些消息包括接收适配器的响应消息。|  
||Documents processed|已处理的文档数。|  
||处理的文档数/秒|每秒处理的文档数。|  
||Documents received|已接收的文档数。|  
||Documents received/Sec|每秒接收的文档数。|  
||Documents resubmitted|由发送适配器重新提交的文档总数。|  
||Documents submitted/Batch|平均每批提交的文档数。|  
||Documents suspended|挂起的文档数。|  
||Documents suspended/Sec|每秒挂起的文档数。|  
||Documents transmitted/Batch|平均每批传输的消息数。|  
||ID Process|此主机实例的进程标识符。|  
||Pending receive batches|消息引擎所接收的尚未处理完的批数。 这包括已经由发送适配器异步处理的批。|  
||Pending transmitted messages|由消息引擎传给发送适配器的尚未处理完的消息数。 这包括接收适配器的响应消息。|  
||Request/Response timeouts|在适配器指定的时限内尚未接收到响应消息的请求消息数。|  
||Throttled receive batches|在消息引擎接收时，由于服务负载高而被阻止的批数。 这些批包括要处理的新消息。|  
|BizTalk：消息延迟|Inbound Latency (sec)|自消息引擎从适配器接收到文档到将其发布到 MessageBox 的平均延迟时间（以毫秒计）。|  
||Outbound Adapter Latency (sec)|自适配器从消息引擎获取文档到将其发送出去的平均延迟时间（以毫秒计）。|  
||Outbound Latency (sec)|自消息引擎从 MessageBox 接收到文档到适配器将其发送出去的平均延迟时间（以毫秒计）。|  
||Request-Response Latency (sec)|自消息引擎从适配器接收到请求文档到将响应文档返回到适配器的平均延迟时间（以毫秒计）。|  
  
## <a name="to-access-performance-counters"></a>访问性能计数器  
 依照下述步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的是 Windows 2008  
  
1.  单击**启动**，指向**管理工具**，然后单击**性能监视器**。  
  
2.  在**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在**添加计数器**对话框中，从**可用计数器**列表中，展开**BizTalk： 消息传送**性能计数器对象，然后选择要监视的计数器  
  
4.  在**实例的所选对象**列表中，选择要监视的所选计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，选择\<**所有实例**\>。  
  
5.  添加计数器后, 单击**确定**。  
  
     所选的性能计数器显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>另请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量的最大可持续引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量的最大可持续跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机限制的优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)