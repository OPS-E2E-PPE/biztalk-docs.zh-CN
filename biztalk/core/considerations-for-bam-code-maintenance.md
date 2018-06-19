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
# <a name="considerations-for-bam-code-maintenance"></a><span data-ttu-id="01ad6-102">BAM 代码维护的注意事项</span><span class="sxs-lookup"><span data-stu-id="01ad6-102">Considerations for BAM Code Maintenance</span></span>
<span data-ttu-id="01ad6-103">在决定如何装备您的应用程序以使用 BAM 后，您应当考虑要求将发生更改的可能性。</span><span class="sxs-lookup"><span data-stu-id="01ad6-103">When you decide how to instrument your application to use BAM, you should consider the likelihood that requirements will change.</span></span> <span data-ttu-id="01ad6-104">如果你在某个 [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) 类中调用方法以写入正在被监视数据，则可以从本质上将观察模型“硬编码”到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="01ad6-104">If you call methods on one of the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) classes to write the data that is being monitored, you are essentially “hard-coding” the observation model into the application.</span></span> <span data-ttu-id="01ad6-105">如果您需要更改被监视的数据，则必须使应用程序处于脱机状态，更改其代码、重新编译应用程序，然后重新部署更新的应用程序。</span><span class="sxs-lookup"><span data-stu-id="01ad6-105">If you need to change which data is being monitored, you will have to take the application offline, change the code, recompile the application, and then redeploy the updated application.</span></span>  
  
 <span data-ttu-id="01ad6-106">或者，可以通过调用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类中的方法来检测你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="01ad6-106">Alternatively, you can instrument your application by calling methods on the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class.</span></span> <span data-ttu-id="01ad6-107">[Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类是指用于确定将监视哪些事件和数据的配置文件。</span><span class="sxs-lookup"><span data-stu-id="01ad6-107">The [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class refers to a configuration file to determine which events and data to monitor.</span></span> <span data-ttu-id="01ad6-108">通过使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) 类，你可以立刻检测你的代码，然后更改正被更新元数据监视的数据，而无需使应用程序处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="01ad6-108">By using the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx) class, you can instrument your code once, and then change the data that is being monitored by updating the metadata, without having to take the application offline.</span></span>  
  
## <a name="instrumenting-your-application-by-using-the-eventstream-object"></a><span data-ttu-id="01ad6-109">通过使用 EventStream 对象装备应用程序</span><span class="sxs-lookup"><span data-stu-id="01ad6-109">Instrumenting Your Application by Using the EventStream Object</span></span>  
 <span data-ttu-id="01ad6-110">在生成具有众所周知的特定监视要求的专用应用程序时，此方法更简单，适用范围更广。</span><span class="sxs-lookup"><span data-stu-id="01ad6-110">This approach is simpler and applies when you are building a dedicated application with specific, well-known monitoring requirements.</span></span> <span data-ttu-id="01ad6-111">在决定使用此方法之前，您需要回答以下几个问题：</span><span class="sxs-lookup"><span data-stu-id="01ad6-111">Before deciding to use this approach, you need to know the answers to the following questions:</span></span>  
  
-   <span data-ttu-id="01ad6-112">什么是 BAM 里程碑，以及它们将在代码中何处出现？</span><span class="sxs-lookup"><span data-stu-id="01ad6-112">What are the BAM milestones, and where in the code do they occur?</span></span>  
  
-   <span data-ttu-id="01ad6-113">要监视哪些数据，可在何时和代码中何处获得这些数据？</span><span class="sxs-lookup"><span data-stu-id="01ad6-113">What data will be monitored, and when and where in the code is that data available?</span></span>  
  
 <span data-ttu-id="01ad6-114">如果这其中任何一个问题的答案可能会更改，则应该考虑使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)对象来检测应用程序。</span><span class="sxs-lookup"><span data-stu-id="01ad6-114">If the answer to either of these questions is likely to change, you should consider instrumenting your application by using the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)object instead.</span></span>  
  
 <span data-ttu-id="01ad6-115">当你遵照“硬编码”方法时，你可以根据自己的需要，只在 [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx)、 [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx)、 **MessagingEventStream** （来自管道实现），或 **OrchestrationEventStream** （来自业务流程实现）类上调用方法。</span><span class="sxs-lookup"><span data-stu-id="01ad6-115">When you follow this “hard-coded” approach, you simply call methods on the [Microsoft.BizTalk.Bam.EventObservation.DirectEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.directeventstream.aspx), [Microsoft.BizTalk.Bam.EventObservation.BufferedEventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.bufferedeventstream.aspx), **MessagingEventStream** (from pipeline implementations) or **OrchestrationEventStream** (from orchestration implementations) class, depending on your requirements.</span></span>  
  
## <a name="instrumenting-your-application-by-using-the-baminterceptor-object"></a><span data-ttu-id="01ad6-116">通过使用 BAMIntercepto 对象装备应用程序</span><span class="sxs-lookup"><span data-stu-id="01ad6-116">Instrumenting Your Application by Using the BAMInterceptor Object</span></span>  
 <span data-ttu-id="01ad6-117">这种方法在以下情形中更合适：</span><span class="sxs-lookup"><span data-stu-id="01ad6-117">This approach is better when:</span></span>  
  
-   <span data-ttu-id="01ad6-118">您需要平衡数据的可见性与应用程序的性能，并且您希望能够控制在运行时监视的数据。</span><span class="sxs-lookup"><span data-stu-id="01ad6-118">You need to balance visibility of data with performance of the application, and you want to be able to control the data that is monitored at run time.</span></span>  
  
-   <span data-ttu-id="01ad6-119">该应用程序可处理大的 XML 消息，这些消息中的任何数据都可能最终成为监视重点。</span><span class="sxs-lookup"><span data-stu-id="01ad6-119">The application processes large XML messages, in which any data may eventually become important for monitoring.</span></span>  
  
-   <span data-ttu-id="01ad6-120">不能通过停止应用程序然后更改代码来监视不同的数据。</span><span class="sxs-lookup"><span data-stu-id="01ad6-120">It is unacceptable to stop the application and change the code to monitor different data.</span></span>  
  
 <span data-ttu-id="01ad6-121">在此方法中，你可以使用 [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)类的方法以一般方式检测应用程序。</span><span class="sxs-lookup"><span data-stu-id="01ad6-121">In this approach, you instrument the application in a generic way by using the methods of the [Microsoft.BizTalk.Bam.EventObservation.BAMInterceptor](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.baminterceptor.aspx)class.</span></span> <span data-ttu-id="01ad6-122">通过将不同的配置传递给该侦听器，您可以更改 BAM 监视的数据。</span><span class="sxs-lookup"><span data-stu-id="01ad6-122">By passing different configurations to the interceptor, you can change the data that BAM monitors.</span></span>  
  
 <span data-ttu-id="01ad6-123">您可以使用跟踪配置文件编辑器 (TPE) 来更改 BAM 从 BizTalk 业务流程中收集的数据。</span><span class="sxs-lookup"><span data-stu-id="01ad6-123">You can use the Tracking Profile Editor (TPE) to change the data that BAM collects from a BizTalk orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01ad6-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01ad6-124">See Also</span></span>  
 <span data-ttu-id="01ad6-125">[使用活动](../core/using-an-activity.md) </span><span class="sxs-lookup"><span data-stu-id="01ad6-125">[Using an Activity](../core/using-an-activity.md) </span></span>  
 <span data-ttu-id="01ad6-126">[BAM 侦听器是什么？](../core/what-is-the-bam-interceptor.md) </span><span class="sxs-lookup"><span data-stu-id="01ad6-126">[What Is the BAM Interceptor?](../core/what-is-the-bam-interceptor.md) </span></span>  
 [<span data-ttu-id="01ad6-127">BAM API （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="01ad6-127">BAM API (BizTalk Server Sample)</span></span>](../core/bam-api-biztalk-server-sample.md)