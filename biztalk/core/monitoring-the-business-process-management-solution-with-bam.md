---
title: 监视业务流程管理解决方案使用 BAM |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, monitoring
- monitoring, process management solutions
ms.assetid: 7c5fde9d-6eef-41c9-979c-ac7e5a172812
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c46c52dad2352f0aea2d0d69af477458ed59ba5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324559"
---
# <a name="monitoring-the-business-process-management-solution-with-bam"></a>监视业务流程管理解决方案使用 BAM
该解决方案监视中使用业务活动监视 (BAM) API 的处理订单的步骤。 业务流程的设计将拆分多个阶段的活动。 通过，可以将这些活动重新组合起来以形成一个连续的过程。 BAM 还提供了聚合数据，以便您可以知道多长时间采用不同的后端，多少订单已完成，以及其他类似信息。  
  
 像面向服务的解决方案，它使用新**OrchestrationEventStream**对象。 有关的讨论**OrchestrationEventStream**对象，请参阅中的"什么是 OrchestrationEventStream 对象"[监视面向服务的解决方案使用 BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)。  
  
 有关 BAM 的常规信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。 有关跟踪配置文件编辑器 (TPE) 的信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>包装 OrchestrationEventStream 对象  
 面向服务的解决方案，如业务流程管理解决方案包装**OrchestrationEventStream**对象。 而且，如面向服务的解决方案中，所有方法是静态的以便业务流程不需要使用这些方法创建的对象的实例。 这还意味着在跟踪中使用的对象而无需进行序列化，无需保存 （不需要是可序列化） 如果引擎冻结业务流程。 业务流程管理解决方案，但是，包装**OrchestrationEventStream**全部派生自单个的多个对象，使用抽象对象。  
  
 抽象类是**BasicActivity**。 尽管它是抽象的但类不是真的作为派生类的模板。 而是通过其静态方法，它提供了一组方法无需限定即可在派生类中。 此操作，实际上，提供四种默认实现的方法。 四个静态方法是：**CreateActivityId**， **BeginActivity**， **UpdateActivity**，并且**EndActivity**。  
  
 类重载**BeginActivity**方法。 它的一个版本获取活动名称作为单个参数，创建要用作活动标识符的 GUID，然后调用其自身的版本，采用了活动名称和活动标识符，然后返回活动标识符。 此单参数版本非常有用的情况下订单可能不具有唯一标识符。  
  
 **CreateActivityId**方法采用一个字符串，例如请求标识符的唯一标识符并返回一个字符串，将它们连下划线开头。 这提供了一个唯一的活动标识符，并在派生类中广泛使用。 **BeginActivity**， **UpdateActivity**，并**EndActivity**方法将调用**BeginActiviy**， **UpdateActivity**，并**EndActivity**的方法**OrchestrationEventStream**。  
  
 该解决方案派生类从**BasicActivity** orderbroker (**CustomerOrderRequest**)，订单管理器 (**OrderManager**)，并处理阶段 (**ServiceOrderRequest**)。 每个类对应于一个活动。 每个类提供要在中使用的活动名称的字符串**CreateActivityId**创建活动标识符，以及方法专用于活动里程碑。  
  
 由于 orderbroker 发出订单并在稍后接收响应，因此包含给定顺序的请求标识符的活动标识符恢复的方法。 这样，业务流程可以继续跟踪最后处理订单的元素。  
  
> [!NOTE]
>  如果提交订单通过文件工具而不是客户服务 web 应用程序，，需要将一个唯一的标识符添加到每个请求。  
  
## <a name="see-also"></a>请参阅  
 [开发业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)