---
title: BAM 注意事项代码维护 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, code maintenance
- BAMInterceptor class
ms.assetid: e1f1d8e0-207c-47e1-b9bd-a473c86922ce
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f7cfdb75a32c23ef5c8dedec3b6a4c783bf089a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238093"
---
# <a name="considerations-for-bam-code-maintenance"></a>BAM 代码维护的注意事项
在决定如何装备您的应用程序以使用 BAM 后，您应当考虑要求将发生更改的可能性。 如果你在某个 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) 类中调用方法以写入正在被监视数据，则可以从本质上将观察模型“硬编码”到应用程序中。 如果您需要更改被监视的数据，则必须使应用程序处于脱机状态，更改其代码、重新编译应用程序，然后重新部署更新的应用程序。  
  
 或者，可以通过调用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类中的方法来检测你的应用程序。 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类是指用于确定将监视哪些事件和数据的配置文件。 通过使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类，你可以立刻检测你的代码，然后更改正被更新元数据监视的数据，而无需使应用程序处于脱机状态。  
  
## <a name="instrumenting-your-application-by-using-the-eventstream-object"></a>通过使用 EventStream 对象装备应用程序  
 在生成具有众所周知的特定监视要求的专用应用程序时，此方法更简单，适用范围更广。 在决定使用此方法之前，您需要回答以下几个问题：  
  
-   什么是 BAM 里程碑，以及它们将在代码中何处出现？  
  
-   要监视哪些数据，可在何时和代码中何处获得这些数据？  
  
 如果这其中任何一个问题的答案可能会更改，则应该考虑使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)对象来检测应用程序。  
  
 当你遵照“硬编码”方法时，你可以根据自己的需要，只在 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)、 [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx)、 **MessagingEventStream** （来自管道实现），或 **OrchestrationEventStream** （来自业务流程实现）类上调用方法。  
  
## <a name="instrumenting-your-application-by-using-the-baminterceptor-object"></a>通过使用 BAMIntercepto 对象装备应用程序  
 这种方法在以下情形中更合适：  
  
-   您需要平衡数据的可见性与应用程序的性能，并且您希望能够控制在运行时监视的数据。  
  
-   该应用程序可处理大的 XML 消息，这些消息中的任何数据都可能最终成为监视重点。  
  
-   不能通过停止应用程序然后更改代码来监视不同的数据。  
  
 在此方法中，你可以使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)类的方法以一般方式检测应用程序。 通过将不同的配置传递给该侦听器，您可以更改 BAM 监视的数据。  
  
 您可以使用跟踪配置文件编辑器 (TPE) 来更改 BAM 从 BizTalk 业务流程中收集的数据。  
  
## <a name="see-also"></a>另请参阅  
 [使用活动](../core/using-an-activity.md)   
 [BAM 侦听器是什么？](../core/what-is-the-bam-interceptor.md)   
 [BAM API （BizTalk Server 示例）](../core/bam-api-biztalk-server-sample.md)