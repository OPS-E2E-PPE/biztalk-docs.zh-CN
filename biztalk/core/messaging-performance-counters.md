---
title: 消息传送性能计数器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 162d761a-fe69-45b0-a6af-c5d9f714e0ca
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8682026548e63287c85668a8b3706fb1255d3725
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324884"
---
# <a name="messaging-performance-counters"></a>消息传送性能计数器
性能计数器允许你监视的工作上的站点或系统服务执行的特定方面。 性能计数器可以帮助您确定和解决服务器性能问题。  
  
 以下性能计数器都可以访问每个主机实例下**BizTalk: Messaging**和**BizTalk: Messaging Latency**性能对象类别：  
  
|**类别**|**计数器**|**说明**|  
|------------------|-----------------|---------------------|  
|BizTalk:Messaging|活动接收位置|接收此主机实例中当前启用的位置数。|  
||活动接收线程|消息引擎当前正在处理此主机实例中运行的适配器从接收的消息中的线程数。 其中包括已由发送适配器异步处理的消息。|  
||活动发送消息|处理发送的消息引擎中当前具有的消息数。 这包括消息当前在发送管道处理的响应消息以及接收适配器。|  
||活动发送线程|消息引擎当前正在处理消息将发送到适配器中的线程数。 这包括接收适配器的响应消息。|  
||处理的文档|处理的文档。|  
||处理的文档数/秒|记录每秒处理。|  
||收到的文档|接收到的文档。|  
||每秒接收的文档|每秒接收的文档数。|  
||重新提交的文档|发送适配器通过重新提交的文档总数。|  
||提交的文档/批处理|平均每批提交的文档数。|  
||挂起的文档|挂起的文档。|  
||挂起的文档数/秒|每秒挂起的文档。|  
||传输的文档/批处理|平均每批传输的消息数。|  
||ID 进程|此主机实例进程标识符。|  
||挂起接收批处理|由消息引擎接收的尚未处理完的批数。 其中包括已由发送适配器异步处理的批。|  
||挂起传输的消息|提供的消息引擎发送适配器的尚未处理完消息数。 这包括响应消息的接收适配器。|  
||请求/响应超时|未收到响应消息由适配器指定的时间限制内的请求消息数。|  
||限制接收批处理|由于服务负载高消息引擎接收的被阻止的批数。 这些批包括要处理的新消息。|  
|BizTalk： 消息延迟|入站的延迟 （秒）|以毫秒为单位自消息引擎文档从接收适配器发布到 Messagebox 为止的平均延迟。|  
||出站适配器延迟 （秒）|以毫秒为单位从时适配器获取一个文档从消息引擎直到适配器发送的时间的平均延迟。|  
||出站延迟 （秒）|平均延迟 （毫秒） 时，消息引擎接收到文档从 Messagebox 中直到适配器发送文档的时间。|  
||请求-响应延迟 （秒）|平均延迟 （毫秒） 自消息引擎接收到请求文档从适配器响应文档传回适配器为止。|  
  
## <a name="to-access-performance-counters"></a>若要访问性能计数器  
 使用以下步骤访问性能计数器。  
  
#### <a name="if-you-are-using-windows-2008"></a>如果您使用的 Windows 2008  
  
1.  单击**启动**，依次指向**管理工具**，然后单击**性能监视器**。  
  
2.  在中**性能监视器**对话框框中，展开**监视工具**，选择**性能监视器**，然后单击**添加**。  
  
3.  在中**添加计数器**对话框中，从**可用的计数器**列表中，展开**BizTalk: Messaging**性能计数器对象，然后选择要监视的计数器  
  
4.  在中**选定对象的实例**列表中，选择要监视的所选的计数器，然后单击的特定实例**添加**。  若要选择的所有可用的计数器实例，请选择\<**所有实例**\>。  
  
5.  添加计数器之后, 单击**确定**。  
  
     所选的性能计数器随即显示在**性能监视器**屏幕。  
  
## <a name="see-also"></a>请参阅  
 [性能提示和技巧](../core/performance-tips-and-tricks.md)   
 [测量最大可承受引擎吞吐量](../core/measuring-maximum-sustainable-engine-throughput.md)   
 [测量最大可承受跟踪吞吐量](../core/measuring-maximum-sustainable-tracking-throughput.md)   
 [通过主机阻止优化资源使用情况](../core/optimizing-resource-usage-through-host-throttling.md)