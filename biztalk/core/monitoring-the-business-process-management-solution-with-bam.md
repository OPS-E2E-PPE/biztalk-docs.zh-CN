---
title: 监视业务流程管理解决方案与 BAM |Microsoft 文档
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
ms.openlocfilehash: 26a8b795b90b75518f6c1ec21a6ca6d8f0f0d6a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264365"
---
# <a name="monitoring-the-business-process-management-solution-with-bam"></a>使用 BAM 监视业务流程管理解决方案
该解决方案使用业务活动监视 (BAM) API 来监视订单处理步骤。 业务流程在设计上将活动拆分为多个阶段。 但是，可以将这些活动重新组合起来以形成连续的流程。 BAM 还提供聚合数据，以便您能够了解不同后端系统所花费的时间、已完成的订单数以及其他类似信息。  
  
 如面向服务的解决方案，它使用新**OrchestrationEventStream**对象。 有关的讨论**OrchestrationEventStream**对象，请参阅中的"什么是 OrchestrationEventStream Object"[监视服务面向解决方案与 BAM](../core/monitoring-the-service-oriented-solution-with-bam.md)。  
  
 有关 BAM 的常规信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。 有关跟踪配置文件编辑器 （键入） 的信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a>包装 OrchestrationEventStream 对象  
 面向服务的解决方案，如业务流程管理解决方案包装**OrchestrationEventStream**对象。 并且，与面向服务的解决方案一样，所有方法都是静态方法，这样业务流程不需要创建对象实例也可以使用这些方法。 这也意味着如果引擎冻结某个业务流程，则不一定非要对跟踪中使用的对象进行序列化，并且也不需要保存这些对象（不必为可序列化对象）。 业务流程管理解决方案，但是，包装**OrchestrationEventStream**与多个对象从一个所有派生，抽象对象。  
  
 抽象类是**BasicActivity**。 尽管该类为抽象类，但它并不是真的作为派生类的模板。 而是通过其静态方法提供一组没有派生类中的限定条件的可用方法。 这实际上为您提供了四种默认的方法实现方式。 四个静态方法为： **CreateActivityId**， **BeginActivity**， **UpdateActivity**，和**EndActivity**。  
  
 类重载**BeginActivity**方法。 该类的一个版本获取活动名称作为单个参数，并创建一个 GUID 用作活动标识符，接着调用该类获取活动名称和活动标识符的版本，然后返回活动标识符。 在订单可能不具有唯一标识符的情况下，此单参数版本非常有用。  
  
 **CreateActivityId**方法采用一个字符串，如请求标识符的唯一标识符，并返回将它们连接起来下划线开头的字符串。 这提供了一个唯一的活动标识符，在派生类中广泛使用。 **BeginActivity**， **UpdateActivity**，和**EndActivity**方法调用**BeginActiviy**， **UpdateActivity**，和**EndActivity**方法**OrchestrationEventStream**。  
  
 解决方案派生的类**BasicActivity**顺序 broker (**CustomerOrderRequest**)，顺序管理器 (**OrderManager**)，和处理阶段 (**ServiceOrderRequest**)。 每个类都对应于一个活动。 每个类提供了要在中使用的活动名称的字符串**CreateActivityId**创建活动标识符以及方法专用于活动里程碑。  
  
 由于 OrderBroker 发出订单，并在稍后接收响应，因此它包含一个用于将给定的活动标识符恢复为订单的请求标识符的方法。 这使得业务流程可以继续跟踪最后处理订单的元素。  
  
> [!NOTE]
>  如果通过文件工具而非客户服务 Web 应用程序来提交订单，则需要为每个请求添加一个唯一的标识符。  
  
## <a name="see-also"></a>另请参阅  
 [开发一个业务流程管理解决方案](../core/developing-a-business-process-management-solution.md)