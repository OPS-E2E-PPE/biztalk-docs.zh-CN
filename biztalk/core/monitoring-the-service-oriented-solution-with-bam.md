---
title: "监视服务面向解决方案与 BAM |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- monitoring, service solutions
- service solution tutorial, monitoring
- OrchestrationEventStream object
ms.assetid: 9b251580-9371-490e-9218-0ce3f6b00fa6
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1aeaec2513ebe3c6d7fe62ef542b6f044bca56
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a>监视服务面向与 BAM 解决方案
解决方案监视的所有版本中的活动**CustomerService**使用业务活动监视 (BAM) API 的业务流程。 更具体地说，它使用新**OrchestrationEventStream**对象。  
  
## <a name="what-is-the-orchestrationeventstream-object"></a>OrchestrationEventStream 对象概述  
 新**OrchestrationEventStream**对象启用跟踪和监视支持业务流程。 捕获的信息在事务性上与业务流程状态一致。 例如，如果在执行业务流程的过程中重新启动业务流程主机实例，则该业务流程实例将从其最后一个持久化点重新启动。 **OrchestrationEventStream**类，则确保捕获的数据与业务流程实例的最后一个持久点保持一致。 所有**OrchestrationEventStream**方法是静态方法，以便您的业务流程不需要创建它的实例。  
  
> [!NOTE]
>  若要使用**OrchestrationEventStream**对象，你需要将引用添加到**Microsoft.BizTalk.Bam.XLANGs**和**Microsoft.BizTalk.Bam.EventObservation**程序集。 尽管**OrchestrationEventStream**对象处于**Microsoft.BizTalk.Bam.EventObservation**命名空间，它驻留在**Microsoft.BizTalk.Bam.XLANGs**程序集。  
  
 尽管跟踪配置文件编辑器 (TPE) 是使用 BAM 的首选方式，但 TPE 不能捕获业务流程变量值，也不能处理自定义对象。 该解决方案使用 BAM API 来克服这些限制。  
  
 有关 BAM 的常规信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。 有关跟踪配置文件编辑器 （键入） 的信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>包装 OrchestrationEventStream 对象  
 面向服务的解决方案包装**OrchestrationEventStream**类，该类具有**ServiceLevelTracking**类。 **ServiceLevelTracking**类提供特定于应用程序的里程碑方法，并隐藏某些使用的详细信息**OrchestrationEventStream**。  
  
 作为 in **OrchestrationEventStream**的所有方法**ServiceLevelTracking**是静态的。 因此，业务流程或自定义组件不需要创建其实例。 将开始跟踪活动，该方法**TrackingBeginRequest**，返回一个唯一的活动实例 id。 所有后续的跟踪事件必须与此活动实例 ID 相关联才能捕获服务级数据正确，因为它是唯一的实例的**CustomerService**业务流程。  
  
## <a name="see-also"></a>另请参阅  
 [面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md)   
 [服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md)