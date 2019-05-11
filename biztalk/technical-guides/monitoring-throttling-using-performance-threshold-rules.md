---
title: 监视带宽限制使用性能阈值规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc2c3024-a54b-4485-8110-c2ec9ec52721
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe2d443af13c8c5a3e3e5cb137bbcddd2ceefb03
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399586"
---
# <a name="monitoring-throttling-using-performance-threshold-rules"></a>监视带宽限制使用性能阈值规则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将初始化限制，以防止系统达到不可恢复的状态。 限制可以表示存在问题，并协助您找出其源。 确定基于阻止状态瓶颈的原因后，分析其他性能计数器以缩小问题来源。  
  
 例如，MessageBox 数据库上的大量争用可能是由于 CPU 使用率过高，这可能引起过度分页到磁盘，进而可能因内存不足的情况。 MessageBox 上的大量争用也可能造成高锁争用情况，这可能是由于磁盘设备趋于饱和。  
  
 监视 Message Delivery Throttling State 和 Message Publishing Throttling State 每个主机实例通常是开始进行故障排除限制时的好时机。 如果这些计数器的值不为零，则指示 BizTalk Server 系统内正发生限流，并可以进一步分析瓶颈的原因。 有关其他性能计数器的说明，请参阅[标识数据库层的瓶颈](http://go.microsoft.com/fwlink/?LinkID=154678)(<http://go.microsoft.com/fwlink/?LinkID=154678>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="biztalk-server-system-performance-counters"></a>BizTalk Server 系统性能计数器  
  
|Object|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|处理器时间百分比|资源争用|  
|Process|BTSNTSvc|虚拟字节数|内存泄漏/膨胀|  
|Process|BTSNTSvc|专用字节数|内存泄漏/膨胀|  
|Process|BTSNTSvc|句柄计数|资源争用|  
|Process|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|_Total|空闲时间百分比|资源争用|  
|物理磁盘|_Total|Current Disk Queue Length|资源争用|  
  
## <a name="biztalk-application-counters"></a>BizTalk 应用程序计数器  
  
|Object|实例|计数器|Description|  
|------------|--------------|-------------|-----------------|  
|BizTalk 消息传送|RxHost|Documents Received/Sec|传入速率|  
|BizTalk 消息传送|TxHost|处理的文档数/秒|传出速率|  
|XLANGs/业务流程|PxHost|已完成的业务流程数/秒|处理速率|  
|BizTalk:MessageBox:常规计数器|MsgBoxName|后台处理大小|所有主机队列的累积大小|  
|BizTalk:MessageBox:常规计数器|MsgBoxName|跟踪数据大小|MessageBox 上 TrackingData 表的大小|  
|BizTalk:MessageBox:主机计数器|PxHost:MsgBoxName|主机队列-长度|特定主机队列中的消息数|  
|BizTalk:MessageBox:主机计数器|TxHost:MsgBoxName|主机队列-长度|特定主机队列中的消息数|  
|BizTalk:消息代理|RxHost|数据库大小|发布 (PxHost) 队列的大小|  
|BizTalk:消息代理|PxHost|数据库大小|发布 (TxHost) 队列的大小|  
|BizTalk:消息代理|HostName|Message Delivery Throttling State|影响 XLANG 和出站传输|  
|BizTalk:消息代理|HostName|消息发布阻止状态|影响 XLANG 和入站传输|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [监视带宽限制](../technical-guides/monitoring-for-throttling.md)