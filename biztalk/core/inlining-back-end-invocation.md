---
title: "内联的后端调用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="inlining-back-end-invocation"></a>内联的后端调用
完整解决方案的内联调用版本提供了最快的处理速度。 该内联版本消除了将与后端系统之间的请求和响应消息保存到 MessageBox 数据库中所带来的开销。 在适配器版本中，消息从发送业务流程传到 MessageBox 中。 运行适配器的主机将提取该消息，并通过再次将其发布到 MessageBox 来向后端进程发送该消息。  
  
 内联版本具有高效率，但会将业务流程直接绑定到后端系统的传输协议。 在该内联版本中，业务流程通过三个自定义程序集调用后端系统，而不是通过逻辑端口进行通信。 如果后端系统传输发生更改，则必须重新编写并重新编译这些程序集。 下表对这些程序集及其功能进行了说明：  
  
|程序集名称|后端连接|  
|-------------------|--------------------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall|使用 MQSeries**获取**和**放**消息函数。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall|调用事务系统的 Web Services。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall|调用模拟 SAP 的 Web Services。|  
  
## <a name="see-also"></a>另请参阅  
 [服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)   
 [转换的服务的模式面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md)   
 [监视服务面向与 BAM 解决方案](../core/monitoring-the-service-oriented-solution-with-bam.md)