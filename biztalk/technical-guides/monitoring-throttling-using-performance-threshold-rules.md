---
title: 监视限制使用性能阈值规则 |Microsoft 文档
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
ms.openlocfilehash: 2aedf8040b821230b6541785426731f1cef32099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299077"
---
# <a name="monitoring-throttling-using-performance-threshold-rules"></a>监视限制使用性能阈值规则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将初始化限制，以防止系统达到不可恢复的状态。 限制可以表示存在问题，帮助您识别其源。 确定基于限制的状态的瓶颈的原因后，分析其他性能计数器，以缩小问题的根源。  
  
 例如，在 MessageBox 数据库上的大量争用可能由于 CPU 使用率过高，这可能由过度分页到磁盘，反过来可能引起内存不足的情况。 在消息框上的大量争用还可能引起高锁争用情况，这可能是因为饱和磁盘驱动器。  
  
 监视消息传递限制状态和每个主机实例将消息发布限制状态通常是开始进行故障排除限制时的好时机。 如果这些计数器的值不为零，则指示，BizTalk 服务器系统中出现了限制，并且可能要进一步分析瓶颈的原因。 有关的其他性能计数器的说明，请参阅[标识数据库层中的瓶颈](http://go.microsoft.com/fwlink/?LinkID=154678)(http://go.microsoft.com/fwlink/?LinkID=154678) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。  
  
## <a name="biztalk-server-system-performance-counters"></a>BizTalk Server 系统性能计数器  
  
|对象|实例|计数器|监视目的|  
|------------|--------------|-------------|------------------------|  
|处理器|_Total|% Processor Time|资源争用|  
|处理|BTSNTSvc|Virtual Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Private Bytes|内存泄漏/膨胀|  
|处理|BTSNTSvc|Handle Count|资源争用|  
|处理|BTSNTSvc|线程计数|资源争用|  
|物理磁盘|_Total|% Idle Time|资源争用|  
|物理磁盘|_Total|Current Disk Queue Length|资源争用|  
  
## <a name="biztalk-application-counters"></a>BizTalk 应用程序计数器  
  
|对象|实例|计数器|Description|  
|------------|--------------|-------------|-----------------|  
|BizTalk 消息传送|RxHost|Documents received/sec|传入速率|  
|BizTalk 消息传送|TxHost|Documents processed/Sec|传出速率|  
|XLANGs/业务流程|PxHost|每秒完成业务流程|处理速率|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|假脱机大小|所有主机队列的累积大小|  
|BizTalk: MessageBox： 常规计数器|MsgBoxName|Tracking Data Size|MessageBox 上 TrackingData 表的大小|  
|BizTalk: MessageBox： 承载计数器|PxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk: MessageBox： 承载计数器|TxHost:MsgBoxName|Host Queue - Length|特定主机队列中的消息数|  
|BizTalk： 消息代理|RxHost|Database Size|发布 (PxHost) 队列的大小|  
|BizTalk： 消息代理|PxHost|Database Size|发布 (TxHost) 队列的大小|  
|BizTalk： 消息代理|HostName|Message delivery throttling state|影响 XLANG 和出站传输|  
|BizTalk： 消息代理|HostName|限制状态消息发布|影响 XLANG 和入站传输|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [监视的限制](../technical-guides/monitoring-for-throttling.md)