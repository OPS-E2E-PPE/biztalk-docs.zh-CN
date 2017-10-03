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
# <a name="monitoring-the-service-oriented-solution-with-bam"></a><span data-ttu-id="358d4-102">监视服务面向与 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="358d4-102">Monitoring the Service Oriented Solution with BAM</span></span>
<span data-ttu-id="358d4-103">解决方案监视的所有版本中的活动**CustomerService**使用业务活动监视 (BAM) API 的业务流程。</span><span class="sxs-lookup"><span data-stu-id="358d4-103">The solution monitors activity in all versions of the **CustomerService** orchestration using the Business Activity Monitoring (BAM) API.</span></span> <span data-ttu-id="358d4-104">更具体地说，它使用新**OrchestrationEventStream**对象。</span><span class="sxs-lookup"><span data-stu-id="358d4-104">More specifically, it uses the new **OrchestrationEventStream** object.</span></span>  
  
## <a name="what-is-the-orchestrationeventstream-object"></a><span data-ttu-id="358d4-105">OrchestrationEventStream 对象概述</span><span class="sxs-lookup"><span data-stu-id="358d4-105">What is the OrchestrationEventStream Object?</span></span>  
 <span data-ttu-id="358d4-106">新**OrchestrationEventStream**对象启用跟踪和监视支持业务流程。</span><span class="sxs-lookup"><span data-stu-id="358d4-106">The new **OrchestrationEventStream** object enables tracking and monitoring from orchestrations.</span></span> <span data-ttu-id="358d4-107">捕获的信息在事务性上与业务流程状态一致。</span><span class="sxs-lookup"><span data-stu-id="358d4-107">The information captured is transactionally consistent with the orchestration state.</span></span> <span data-ttu-id="358d4-108">例如，如果在执行业务流程的过程中重新启动业务流程主机实例，则该业务流程实例将从其最后一个持久化点重新启动。</span><span class="sxs-lookup"><span data-stu-id="358d4-108">For example, if the orchestration host instance restarts in the middle of executing the orchestration, the orchestration instance restarts from the last persistence point of the instance.</span></span> <span data-ttu-id="358d4-109">**OrchestrationEventStream**类，则确保捕获的数据与业务流程实例的最后一个持久点保持一致。</span><span class="sxs-lookup"><span data-stu-id="358d4-109">The **OrchestrationEventStream** class ensures that the captured data is transactionally consistent with the orchestration instance's last persistence point.</span></span> <span data-ttu-id="358d4-110">所有**OrchestrationEventStream**方法是静态方法，以便您的业务流程不需要创建它的实例。</span><span class="sxs-lookup"><span data-stu-id="358d4-110">All of the **OrchestrationEventStream** methods are static so that your orchestration does not need to create an instance of it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="358d4-111">若要使用**OrchestrationEventStream**对象，你需要将引用添加到**Microsoft.BizTalk.Bam.XLANGs**和**Microsoft.BizTalk.Bam.EventObservation**程序集。</span><span class="sxs-lookup"><span data-stu-id="358d4-111">To use the **OrchestrationEventStream** object, you need to add references to the **Microsoft.BizTalk.Bam.XLANGs** and **Microsoft.BizTalk.Bam.EventObservation** assemblies.</span></span> <span data-ttu-id="358d4-112">尽管**OrchestrationEventStream**对象处于**Microsoft.BizTalk.Bam.EventObservation**命名空间，它驻留在**Microsoft.BizTalk.Bam.XLANGs**程序集。</span><span class="sxs-lookup"><span data-stu-id="358d4-112">Although the **OrchestrationEventStream** object is in the **Microsoft.BizTalk.Bam.EventObservation** namespace, it resides in the **Microsoft.BizTalk.Bam.XLANGs** assembly.</span></span>  
  
 <span data-ttu-id="358d4-113">尽管跟踪配置文件编辑器 (TPE) 是使用 BAM 的首选方式，但 TPE 不能捕获业务流程变量值，也不能处理自定义对象。</span><span class="sxs-lookup"><span data-stu-id="358d4-113">Although the Tracking Profile Editor (TPE) is the preferred way of using BAM, TPE cannot capture the orchestration variable values, nor can it handle custom objects.</span></span> <span data-ttu-id="358d4-114">该解决方案使用 BAM API 来克服这些限制。</span><span class="sxs-lookup"><span data-stu-id="358d4-114">The solution uses the BAM API to overcome these limitations.</span></span>  
  
 <span data-ttu-id="358d4-115">有关 BAM 的常规信息，请参阅[使用业务活动监视](../core/using-business-activity-monitoring.md)。</span><span class="sxs-lookup"><span data-stu-id="358d4-115">For general information about BAM, see [Using Business Activity Monitoring](../core/using-business-activity-monitoring.md).</span></span> <span data-ttu-id="358d4-116">有关跟踪配置文件编辑器 （键入） 的信息，请参阅[跟踪配置文件编辑器](../core/tracking-profile-editor.md)。</span><span class="sxs-lookup"><span data-stu-id="358d4-116">For information about the Tracking Profile Editor (TPE), see [Tracking Profile Editor](../core/tracking-profile-editor.md).</span></span>  
  
## <a name="wrapping-the-orchestrationeventstream-object"></a><span data-ttu-id="358d4-117">包装 OrchestrationEventStream 对象</span><span class="sxs-lookup"><span data-stu-id="358d4-117">Wrapping the OrchestrationEventStream Object</span></span>  
 <span data-ttu-id="358d4-118">面向服务的解决方案包装**OrchestrationEventStream**类，该类具有**ServiceLevelTracking**类。</span><span class="sxs-lookup"><span data-stu-id="358d4-118">The service oriented solution wraps the **OrchestrationEventStream** class with the **ServiceLevelTracking** class.</span></span> <span data-ttu-id="358d4-119">**ServiceLevelTracking**类提供特定于应用程序的里程碑方法，并隐藏某些使用的详细信息**OrchestrationEventStream**。</span><span class="sxs-lookup"><span data-stu-id="358d4-119">The **ServiceLevelTracking** class provides application-specific milestone methods and hides some of the details of using **OrchestrationEventStream**.</span></span>  
  
 <span data-ttu-id="358d4-120">作为 in **OrchestrationEventStream**的所有方法**ServiceLevelTracking**是静态的。</span><span class="sxs-lookup"><span data-stu-id="358d4-120">As in **OrchestrationEventStream**, all the methods of **ServiceLevelTracking** are static.</span></span> <span data-ttu-id="358d4-121">因此，业务流程或自定义组件不需要创建其实例。</span><span class="sxs-lookup"><span data-stu-id="358d4-121">Thus, the orchestration or custom component does not need to create an instance of it.</span></span> <span data-ttu-id="358d4-122">将开始跟踪活动，该方法**TrackingBeginRequest**，返回一个唯一的活动实例 id。</span><span class="sxs-lookup"><span data-stu-id="358d4-122">The method that begins tracking an activity, **TrackingBeginRequest**, returns a unique activity instance ID.</span></span> <span data-ttu-id="358d4-123">所有后续的跟踪事件必须与此活动实例 ID 相关联才能捕获服务级数据正确，因为它是唯一的实例的**CustomerService**业务流程。</span><span class="sxs-lookup"><span data-stu-id="358d4-123">All subsequent tracking events must be associated with this activity instance ID in order to capture the service level data correctly, because it is unique to the instance of the **CustomerService** orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="358d4-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="358d4-124">See Also</span></span>  
 <span data-ttu-id="358d4-125">[面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="358d4-125">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="358d4-126">服务实现重点介绍面向解决方案</span><span class="sxs-lookup"><span data-stu-id="358d4-126">Implementation Highlights of the Service Oriented Solution</span></span>](../core/implementation-highlights-of-the-service-oriented-solution.md)