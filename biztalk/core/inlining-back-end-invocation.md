---
title: 内联后端调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd4d24cfc1e78a82e2ec3ddd42218390aaee289
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382164"
---
# <a name="inlining-back-end-invocation"></a>内联后端调用
完整解决方案的内联调用版本，提供最快的处理时间。 内联版本消除了持久保存到和从 MessageBox 数据库中的后端系统的请求和响应消息的开销。 在适配器版本中，消息将从发送业务流程到 MessageBox。 运行适配器的主机提取该消息，并再次将其发布到 messagebox 将消息发送到后端进程。  
  
 效率内联为代价的业务流程直接绑定到后端系统的传输协议。 中的内联版本，而不是通过逻辑端口进行通信，该业务流程调用通过三个自定义程序集的后端系统。 如果后端系统传输发生更改，则必须重新编写程序集，并将其重新编译。 下表描述程序集和其功能：  
  
|程序集名称|后端连接|  
|-------------------|--------------------------|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall|使用 MQSeries**获取**并**放置**消息函数。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall|调用对事务系统的 Web 服务。|  
|Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall|调用模拟 SAP 的 web 服务。|  
  
## <a name="see-also"></a>请参阅  
 [面向服务的实现重点推荐的解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)   
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)   
 [将服务的模式转换面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md)   
 [监视面向服务的解决方案使用 BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)