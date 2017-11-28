---
title: "创建自定义路线服务使用 BizTalk 业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bd7ed38-02a3-41b1-9990-754d5539f15e
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 723c0bc93192267f404d42e7fe859bb37ea59895
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-custom-itinerary-service-using-a-biztalk-orchestration"></a><span data-ttu-id="0a2b4-102">创建自定义路线服务使用 BizTalk 业务流程</span><span class="sxs-lookup"><span data-stu-id="0a2b4-102">Creating a Custom Itinerary Service Using a BizTalk Orchestration</span></span>
<span data-ttu-id="0a2b4-103">是的一部分的路线 framework[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持使用业务流程的路线步骤执行。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-103">The itinerary framework that is part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports execution of itinerary steps using orchestrations.</span></span> <span data-ttu-id="0a2b4-104">可以按根据功能要求，其中可能包括以下 Microsoft BizTalk Server 业务流程来实现自定义的路线服务：</span><span class="sxs-lookup"><span data-stu-id="0a2b4-104">You can implement a custom itinerary service as a Microsoft BizTalk Server orchestration based on your functional requirements, which may include the following:</span></span>  
  
-   <span data-ttu-id="0a2b4-105">多个服务调用 (如所示：[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span><span class="sxs-lookup"><span data-stu-id="0a2b4-105">Multiple service invocations (as demonstrated by the [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md))</span></span>  
  
-   <span data-ttu-id="0a2b4-106">协议中介和消息关联 (例如，HTTP MQSeries)</span><span class="sxs-lookup"><span data-stu-id="0a2b4-106">Protocol mediation and message correlation (for example, HTTP-MQSeries)</span></span>  
  
-   <span data-ttu-id="0a2b4-107">复杂的路由决策基于消息扩充从外部数据源</span><span class="sxs-lookup"><span data-stu-id="0a2b4-107">Complex routing decisions based on message enrichment from external data sources</span></span>  
  
-   <span data-ttu-id="0a2b4-108">业务处理逻辑</span><span class="sxs-lookup"><span data-stu-id="0a2b4-108">Business processing logic</span></span>  
  
 <span data-ttu-id="0a2b4-109">使用 BizTalk Server 业务流程来实现的每个路线服务负责以下：</span><span class="sxs-lookup"><span data-stu-id="0a2b4-109">Every itinerary service implemented using a BizTalk Server orchestration is responsible for the following:</span></span>  
  
-   <span data-ttu-id="0a2b4-110">异常和错误处理使用 ESB 异常处理的框架或支持重新提交 （单向路线） 的可选的自定义异常处理程序</span><span class="sxs-lookup"><span data-stu-id="0a2b4-110">Exception and error handling using the ESB Exception Handling Framework or optional custom exception handlers that support resubmission (one-way itineraries)</span></span>  
  
-   <span data-ttu-id="0a2b4-111">前移路线和发布通过 BizTalk 服务器的出站消息，供执行下一步路线服务的步骤</span><span class="sxs-lookup"><span data-stu-id="0a2b4-111">Advancing the itinerary and publishing outbound messages through BizTalk Server so that the next itinerary service step can execute</span></span>  
  
#### <a name="to-create-a-custom-itinerary-service-using-a-biztalk-server-orchestration"></a><span data-ttu-id="0a2b4-112">若要创建自定义路线服务使用 BizTalk Server 业务流程</span><span class="sxs-lookup"><span data-stu-id="0a2b4-112">To create a custom itinerary service using a BizTalk Server orchestration</span></span>  
  
1.  <span data-ttu-id="0a2b4-113">创建包含新的业务流程; 新的 BizTalk Server 项目例如，MyCustomeItineraryService.odx。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-113">Create new BizTalk Server project containing a new orchestration; for example, MyCustomeItineraryService.odx.</span></span>  
  
2.  <span data-ttu-id="0a2b4-114">添加对以下程序集引用：</span><span class="sxs-lookup"><span data-stu-id="0a2b4-114">Add references to the following assemblies:</span></span>  
  
    -   <span data-ttu-id="0a2b4-115">**Microsoft.Practices.ESB.Itinerary**</span><span class="sxs-lookup"><span data-stu-id="0a2b4-115">**Microsoft.Practices.ESB.Itinerary**</span></span>  
  
    -   <span data-ttu-id="0a2b4-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span><span class="sxs-lookup"><span data-stu-id="0a2b4-116">**Microsoft.Practices.ESB.Itinerary.Schemas**</span></span>  
  
    -   <span data-ttu-id="0a2b4-117">**Microsoft.Practices.ESB.ExceptionHandling**</span><span class="sxs-lookup"><span data-stu-id="0a2b4-117">**Microsoft.Practices.ESB.ExceptionHandling**</span></span>  
  
    -   <span data-ttu-id="0a2b4-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span><span class="sxs-lookup"><span data-stu-id="0a2b4-118">**Microsoft.Practices.ESB.ExceptionHandling.Faults**</span></span>  
  
3.  <span data-ttu-id="0a2b4-119">定义逻辑的直接绑定接收端口和激活的接收形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-119">Define a logical direct-bound receive port and an activated receive shape in the orchestration.</span></span>  
  
4.  <span data-ttu-id="0a2b4-120">定义订阅筛选器来激活消息路线上下文从业务流程，以便业务流程执行**MyCustomItineraryService**步骤。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-120">Define a subscription filter to activate the orchestration from the message itinerary context so that the orchestration executes the **MyCustomItineraryService** step.</span></span> <span data-ttu-id="0a2b4-121">下面的代码演示了合适的筛选器的示例。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-121">The following code shows an example of a suitable filter.</span></span>  
  
    ```csharp  
    (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceName   
        == "MyCustomItineraryService")   
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceState == "Pending")  
    && (Microsoft.Practices.ESB.Itinerary.Schemas.ServiceType   
        == "Orchestration")  
    ```  
  
5.  <span data-ttu-id="0a2b4-122">定义类型的业务流程**Microsoft.Practices.ESB.Itinerary.ItineraryStep**。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-122">Define an orchestration of type **Microsoft.Practices.ESB.Itinerary.ItineraryStep**.</span></span> <span data-ttu-id="0a2b4-123">下面的代码中所示，请将表达式活动添加到填充此变量，业务流程。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-123">Add an expression activity to the orchestration that populates this variable, as shown in the following code.</span></span>  
  
    ```csharp  
    // Retrieve the current itinerary step.  
    itinerary = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryWrapper();  
    step = new Microsoft.Practices.ESB.Itinerary.SerializableItineraryStepWrapper();  
  
    itinerary.Itinerary = Microsoft.Practices.ESB.Itinerary.ItineraryOMFactory.Create(InboundMessage);  
    step.ItineraryStep = itinerary.Itinerary.GetItineraryStep(InboundMessage);  
  
    ```  
  
6.  <span data-ttu-id="0a2b4-124">将自定义实现添加到创建出站消息有关的下一步的路线步骤; 路线例如，OutboundMsg。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-124">Add your custom implementation to the itinerary that creates the outbound message for the next itinerary steps; for example, OutboundMsg.</span></span>  
  
7.  <span data-ttu-id="0a2b4-125">前进路线使用使用从入站消息的消息上下文的以下表达式活动。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-125">Advance the itinerary using the following expression activity that uses the message context from inbound message.</span></span>  
  
    ```csharp  
    OutboundMessage(*) = InboundMessage(*);   
    itinerary.Itinerary.Advance(OutboundMessage, itineraryStep.ItineraryStep);  
    ```  
  
8.  <span data-ttu-id="0a2b4-126">通过直接绑定发送端口来激活下一步路线服务发送更新路线的出站消息。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-126">Send the outbound message with the updated itinerary through a direct-bound send port to activate the next itinerary service.</span></span>  
  
 <span data-ttu-id="0a2b4-127">有关实现自定义路线服务使用 BizTalk Server 业务流程的详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)和[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0a2b4-127">For more information about implementing a custom itinerary service using BizTalk Server orchestrations, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md) and [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>