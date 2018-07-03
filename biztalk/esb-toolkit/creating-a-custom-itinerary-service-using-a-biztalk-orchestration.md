---
title: 创建自定义路线服务使用 BizTalk 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa36acc84358a8e91a0b9daaa4370270fb5860b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988534"
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a><span data-ttu-id="38aa7-102">创建自定义路线服务使用 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="38aa7-102">Creating a Custom Itinerary Service Using a BizTalk Orchestration</span></span>
<span data-ttu-id="38aa7-103">是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持使用业务流程路线步骤执行。</span><span class="sxs-lookup"><span data-stu-id="38aa7-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using orchestrations.</span></span> <span data-ttu-id="38aa7-104">可以为基于应用的功能需求，其中可能包括以下 Microsoft BizTalk Server 业务流程来实现自定义路线服务：</span><span class="sxs-lookup"><span data-stu-id="38aa7-104">You can implement a custom itinerary service as a Microsoft BizTalk Server orchestration based on your functional requirements, which may include the following:</span></span>  
  
- <span data-ttu-id="38aa7-105">多个服务调用 (如所示[安装和运行分散-集中示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span><span class="sxs-lookup"><span data-stu-id="38aa7-105">Multiple service invocations (as demonstrated by the [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span></span>  
  
- <span data-ttu-id="38aa7-106">协议中介和消息相关 (例如，HTTP MQSeries)</span><span class="sxs-lookup"><span data-stu-id="38aa7-106">Protocol mediation and message correlation (for example, HTTP-MQSeries)</span></span>  
  
- <span data-ttu-id="38aa7-107">复杂的路由决策基于消息收集从外部数据源</span><span class="sxs-lookup"><span data-stu-id="38aa7-107">Complex routing decisions based on message enrichment from external data sources</span></span>  
  
- <span data-ttu-id="38aa7-108">业务处理逻辑</span><span class="sxs-lookup"><span data-stu-id="38aa7-108">Business processing logic</span></span>  
  
  <span data-ttu-id="38aa7-109">使用 BizTalk Server 业务流程实现的每个路线服务负责以下：</span><span class="sxs-lookup"><span data-stu-id="38aa7-109">Every itinerary service implemented using a BizTalk Server orchestration is responsible for the following:</span></span>  
  
- <span data-ttu-id="38aa7-110">异常和错误处理使用 ESB 异常处理框架或可选的自定义异常处理程序支持重新提交 （单向路线）</span><span class="sxs-lookup"><span data-stu-id="38aa7-110">Exception and error handling using the ESB Exception Handling Framework or optional custom exception handlers that support resubmission (one-way itineraries)</span></span>  
  
- <span data-ttu-id="38aa7-111">前移路线和发布通过 BizTalk Server 的出站消息，以便可以执行下一步的路线服务步骤</span><span class="sxs-lookup"><span data-stu-id="38aa7-111">Advancing the itinerary and publishing outbound messages through BizTalk Server so that the next itinerary service step can execute</span></span>  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a><span data-ttu-id="38aa7-112">若要创建使用 BizTalk Server 业务流程的自定义路线服务</span><span class="sxs-lookup"><span data-stu-id="38aa7-112">To create a custom itinerary service using a BizTalk Server orchestration</span></span>  
  
1. <span data-ttu-id="38aa7-113">创建包含新的业务流程; 的新 BizTalk Server 项目例如，MyCustomeItineraryService.odx。</span><span class="sxs-lookup"><span data-stu-id="38aa7-113">Create new BizTalk Server project containing a new orchestration; for example, MyCustomeItineraryService.odx.</span></span>  
  
2. <span data-ttu-id="38aa7-114">添加对以下程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="38aa7-114">Add references to the following assemblies:</span></span>  
  
   -   <span data-ttu-id="38aa7-115">**Microsoft.Practices.ESB.Itinerary**</span><span class="sxs-lookup"><span data-stu-id="38aa7-115">**Microsoft.Practices.ESB.Itinerary**</span></span>  
  
   -   <span data-ttu-id="38aa7-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span><span class="sxs-lookup"><span data-stu-id="38aa7-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span></span>  
  
   -   <span data-ttu-id="38aa7-117">**Microsoft.Practices.ESB.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="38aa7-117">**Microsoft.Practices.ESB.ExceptionHandling**</span></span>  
  
   -   <span data-ttu-id="38aa7-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span><span class="sxs-lookup"><span data-stu-id="38aa7-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span></span>  
  
3. <span data-ttu-id="38aa7-119">定义逻辑直接绑定接收端口和激活的接收形状在业务流程中。</span><span class="sxs-lookup"><span data-stu-id="38aa7-119">Define a logical direct-bound receive port and an activated receive shape in the orchestration.</span></span>  
  
4. <span data-ttu-id="38aa7-120">定义订阅筛选器，以便该业务流程执行激活业务流程从消息路线上下文**MyCustomItineraryService**步骤。</span><span class="sxs-lookup"><span data-stu-id="38aa7-120">Define a subscription filter to activate the orchestration from the message itinerary context so that the orchestration executes the **MyCustomItineraryService** step.</span></span> <span data-ttu-id="38aa7-121">下面的代码显示了合适的筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="38aa7-121">The following code shows an example of a suitable filter.</span></span>  
  
   ```csharp  
   (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
       == "MyCustomItineraryService")   
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
   && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
       == "Orchestration")  
   ```  
  
5. <span data-ttu-id="38aa7-122">定义类型的业务流程**Microsoft.Practices.ESB.Itinerary.ItineraryStep**。</span><span class="sxs-lookup"><span data-stu-id="38aa7-122">Define an orchestration of type **Microsoft.Practices.ESB.Itinerary.ItineraryStep**.</span></span> <span data-ttu-id="38aa7-123">在下面的代码所示，添加到填充此变量的业务流程的表达式活动。</span><span class="sxs-lookup"><span data-stu-id="38aa7-123">Add an expression activity to the orchestration that populates this variable, as shown in the following code.</span></span>  
  
   ```csharp  
   // Retrieve the current itinerary step.  
   itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
   step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
   itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
   step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
   ```  
  
6. <span data-ttu-id="38aa7-124">将自定义实现添加到创建的出站消息的下一步的路线步骤; 路线例如，OutboundMsg。</span><span class="sxs-lookup"><span data-stu-id="38aa7-124">Add your custom implementation to the itinerary that creates the outbound message for the next itinerary steps; for example, OutboundMsg.</span></span>  
  
7. <span data-ttu-id="38aa7-125">请继续学习路线使用下面的表达式活动，将使用从入站消息的消息上下文。</span><span class="sxs-lookup"><span data-stu-id="38aa7-125">Advance the itinerary using the following expression activity that uses the message context from inbound message.</span></span>  
  
   ```csharp  
   OutboundMessage(*) = InboundMessage(*);   
   itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
   ```  
  
8. <span data-ttu-id="38aa7-126">通过用于激活的下一步的路线服务的直接绑定发送端口发送的出站消息的已更新的路线。</span><span class="sxs-lookup"><span data-stu-id="38aa7-126">Send the outbound message with the updated itinerary through a direct-bound send port to activate the next itinerary service.</span></span>  
  
   <span data-ttu-id="38aa7-127">有关实现使用 BizTalk Server 业务流程的自定义路线服务的详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="38aa7-127">For more information about implementing a custom itinerary service using BizTalk Server orchestrations, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>