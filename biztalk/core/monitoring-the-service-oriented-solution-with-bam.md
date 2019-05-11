---
title: 监视面向服务的解决方案使用 BAM |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring, service solutions
- service solution tutorial, monitoring
- OrchestrationEventStream object
ms.assetid: 9b251580-9371-490e-9218-0ce3f6b00fa6
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 489e1b8c19f10831e1e75115a41ac32660dfe99a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65264493"
---
# <a name="monitoring-the-service-oriented-solution-with-bam"></a>监视面向服务的解决方案使用 BAM
该解决方案监视的所有版本中的活动**CustomerService**业务流程使用业务活动监视 (BAM) API。 更具体地说，它使用新**OrchestrationEventStream**对象。  
  
## <a name="what-is-the-orchestrationeventstream-object"></a>什么是 OrchestrationEventStream 对象？  
 新**OrchestrationEventStream**对象启用跟踪和监视从业务流程。 捕获的信息是事务上与业务流程状态一致。 例如，如果在执行业务流程重新启动业务流程主机实例，该业务流程实例重启从最后一个持久点实例。 **OrchestrationEventStream**类可确保捕获的数据在事务上一致的业务流程实例的最后一个持久化点。 所有**OrchestrationEventStream**方法是静态方法，以便您的业务流程不需要创建它的一个实例。  
  
> [!NOTE]
>  若要使用**OrchestrationEventStream**对象，您需要将引用添加到**Microsoft.BizTalk.Bam.XLANGs**并**Microsoft.BizTalk.Bam.EventObservation**程序集。 尽管**OrchestrationEventStream**对象处于**Microsoft.BizTalk.Bam.EventObservation**命名空间，它在位于**Microsoft.BizTalk.Bam.XLANGs**程序集。  
  
 尽管跟踪配置文件编辑器 (TPE) 是使用 BAM 的首选的方法，但 TPE 不能捕获业务流程变量值，也可以处理自定义对象。 此解决方案使用 BAM API 来克服这些限制。  
  
 有关 BAM 的常规信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。 有关跟踪配置文件编辑器 (TPE) 的信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>包装 OrchestrationEventStream 对象  
 面向服务的解决方案包装**OrchestrationEventStream**类与**ServiceLevelTracking**类。 **ServiceLevelTracking**类提供特定于应用程序的里程碑方法，并会隐藏一些使用的详细信息**OrchestrationEventStream**。  
  
 在中作为**OrchestrationEventStream**，所有方法**ServiceLevelTracking**都是静态的。 因此，业务流程或自定义组件不需要创建它的一个实例。 开始跟踪活动，该方法**TrackingBeginRequest**，返回一个唯一的活动实例 id。 所有后续跟踪事件必须与此活动实例 ID 相关联才能捕获服务级别数据正确，因为它是唯一的实例的**CustomerService**业务流程。  
  
## <a name="see-also"></a>请参阅  
 [开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)   
 [面向服务的解决方案的实施要点](../core/implementation-highlights-of-the-service-oriented-solution.md)