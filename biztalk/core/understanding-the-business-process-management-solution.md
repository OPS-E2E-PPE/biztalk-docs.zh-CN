---
title: 了解业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solutions, resources
- process management solutions, applications
- process management solution tutorial, background information
- process management solutions, about process management solutions
- applications, process management solutions
ms.assetid: fa6ad8d2-08d7-4770-9394-835f99bfd146
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f866df79f46f941604bc72a189a080f56aea170
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292672"
---
# <a name="understanding-the-business-process-management-solution"></a><span data-ttu-id="87d10-102">了解业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="87d10-102">Understanding the Business Process Management Solution</span></span>
<span data-ttu-id="87d10-103">在本部分中所述的解决方案提供了一种可实现业务流程管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d10-103">The solution described in this section presents one way to implement a business process management application.</span></span> <span data-ttu-id="87d10-104">在理想的业务流程管理器，代表业务流程解决方案的部分中，与特定后端系统，发送响应消息进行通信的业务规则 — 分开支持过程的基础结构。</span><span class="sxs-lookup"><span data-stu-id="87d10-104">In an ideal business process manager, the parts of the solution representing the business process—the business rules, communicating with specific backend systems, sending response messages—are separate from the infrastructure supporting the process.</span></span>  
  
 <span data-ttu-id="87d10-105">此解决方案中的有线服务订购系统 Southridge video 的业务流程将划分成一系列阶段。</span><span class="sxs-lookup"><span data-stu-id="87d10-105">In this solution, a cable service ordering system for Southridge Video, the business process is broken into a series of stages.</span></span> <span data-ttu-id="87d10-106">相关信息一无所知的业务规则和后端系统，订单管理器指示阶段的操作。</span><span class="sxs-lookup"><span data-stu-id="87d10-106">An order manager, which knows nothing about the business rules and backend systems, directs the operation of the stages.</span></span> <span data-ttu-id="87d10-107">订单管理器接收来自 orderbroker，后者可以将多个不同的 ordermanager 的订单的订单。</span><span class="sxs-lookup"><span data-stu-id="87d10-107">The order manager receives orders from an order broker, which can direct orders to several different order managers.</span></span>  
  
 <span data-ttu-id="87d10-108">该解决方案可广泛使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能，并演示如何在等来协调应用程序的各个部分的消息应用程序内部使用。</span><span class="sxs-lookup"><span data-stu-id="87d10-108">The solution makes extensive use of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and shows, among other things, the use of messages internal to the application for coordinating parts of the application.</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="87d10-109">读者指南</span><span class="sxs-lookup"><span data-stu-id="87d10-109">Reader Guidance</span></span>  
 <span data-ttu-id="87d10-110">本文档假定你熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="87d10-110">This document assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="87d10-111">它还假定您了解有关企业应用程序集成和 Web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="87d10-111">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span>  
  
 <span data-ttu-id="87d10-112">此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。</span><span class="sxs-lookup"><span data-stu-id="87d10-112">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="ordering-cable-service-from-southridge-video"></a><span data-ttu-id="87d10-113">从 Southridge Video 订购有线服务</span><span class="sxs-lookup"><span data-stu-id="87d10-113">Ordering Cable Service from Southridge Video</span></span>  
 <span data-ttu-id="87d10-114">业务流程管理解决方案实现 Southridge Video 订购系统的有线服务。</span><span class="sxs-lookup"><span data-stu-id="87d10-114">The business process management solution implements a cable service ordering system for Southridge Video.</span></span> <span data-ttu-id="87d10-115">为呼叫中心的客户服务代表客户电话会将订单并将它输入到订单系统。</span><span class="sxs-lookup"><span data-stu-id="87d10-115">Customers phone into a call center where a customer service representative takes the order and enters it into the order system.</span></span> <span data-ttu-id="87d10-116">下图显示了订单在系统的常规流程：</span><span class="sxs-lookup"><span data-stu-id="87d10-116">The following diagram shows the general flow of an order through the system:</span></span>  
  
 <span data-ttu-id="87d10-117">![业务流程管理解决方案工作流](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span><span class="sxs-lookup"><span data-stu-id="87d10-117">![Business Process Management Solution Work Flow](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span></span>  
  
 <span data-ttu-id="87d10-118">订单都进入顺序 broker，它将发送到订单管理器的顺序。</span><span class="sxs-lookup"><span data-stu-id="87d10-118">Orders go to the order broker, which sends the order on to the order manager.</span></span> <span data-ttu-id="87d10-119">订单管理器运行以正确的顺序来处理订单处理阶段。</span><span class="sxs-lookup"><span data-stu-id="87d10-119">The order manager runs the processing stages in the proper sequence to process the order.</span></span> <span data-ttu-id="87d10-120">请注意某些种类的错误可转到运营中心进行更正和重新提交，并且解决方案中的 SQL Server 表中记录的每个订单的历史记录。</span><span class="sxs-lookup"><span data-stu-id="87d10-120">Notice that some kinds of errors go to an operations center for correction and resubmission, and that the solution records the history of each order in a SQL Server table.</span></span>  
  
 <span data-ttu-id="87d10-121">下图显示了处理订单的广泛概括了这些步骤。</span><span class="sxs-lookup"><span data-stu-id="87d10-121">The following diagram shows the broad outline of the steps in processing an order.</span></span>  
  
 <span data-ttu-id="87d10-122">![业务流程管理解决方案序列](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span><span class="sxs-lookup"><span data-stu-id="87d10-122">![Business Process Management Solution Sequence](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span></span>  
  
 <span data-ttu-id="87d10-123">请注意，订单可以进行更新，以及已取消。</span><span class="sxs-lookup"><span data-stu-id="87d10-123">Notice that an order can be updated as well as canceled.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="87d10-124">业务要求</span><span class="sxs-lookup"><span data-stu-id="87d10-124">Business Requirements</span></span>  
 <span data-ttu-id="87d10-125">业务流程管理解决方案是 Southridge Video，有线电视服务提供商的订单系统的示例。</span><span class="sxs-lookup"><span data-stu-id="87d10-125">The business process management solution is an example of an order system for Southridge Video, a cable service provider.</span></span> <span data-ttu-id="87d10-126">它显示在 Microsoft BizTalk Server 中实现流程管理器模式的一种方法。</span><span class="sxs-lookup"><span data-stu-id="87d10-126">It shows one way to implement the process manager pattern in Microsoft BizTalk Server.</span></span> <span data-ttu-id="87d10-127">该解决方案使用业务流程管理中的订单通过实现业务流程的两个附属业务流程。</span><span class="sxs-lookup"><span data-stu-id="87d10-127">The solution uses an orchestration to manage the flow of orders through two satellite orchestrations that implement the business process.</span></span> <span data-ttu-id="87d10-128">此结构不再是解决方案的业务要求，其中包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="87d10-128">This structure comes out of the solution's business requirements which include the following:</span></span>  
  
- <span data-ttu-id="87d10-129">版本的业务流程的能力</span><span class="sxs-lookup"><span data-stu-id="87d10-129">Ability to version the business process</span></span>  
  
- <span data-ttu-id="87d10-130">进程长时间运行的订单</span><span class="sxs-lookup"><span data-stu-id="87d10-130">Process long-running orders</span></span>  
  
- <span data-ttu-id="87d10-131">修改或取消仍在处理的订单 （补充正在处理的订单）</span><span class="sxs-lookup"><span data-stu-id="87d10-131">Modify or cancel orders that are still being processed (supplement in-flight orders)</span></span>  
  
- <span data-ttu-id="87d10-132">避免挂起的订单</span><span class="sxs-lookup"><span data-stu-id="87d10-132">Avoid suspended orders</span></span>  
  
- <span data-ttu-id="87d10-133">跟踪订单的整个过程</span><span class="sxs-lookup"><span data-stu-id="87d10-133">Track orders through the entire process</span></span>  
  
- <span data-ttu-id="87d10-134">成批处理订单</span><span class="sxs-lookup"><span data-stu-id="87d10-134">Batch order processing</span></span>  
  
- <span data-ttu-id="87d10-135">接受来自远程数据中心的订单</span><span class="sxs-lookup"><span data-stu-id="87d10-135">Accept orders from remote data centers</span></span>  
  
- <span data-ttu-id="87d10-136">允许不同的组来处理部分的订单处理</span><span class="sxs-lookup"><span data-stu-id="87d10-136">Allowing different groups to handle parts of the order processing</span></span>  
  
- <span data-ttu-id="87d10-137">通过添加 BizTalk 组中缩放应用程序</span><span class="sxs-lookup"><span data-stu-id="87d10-137">Scale the application by adding BizTalk groups</span></span>  
  
- <span data-ttu-id="87d10-138">公开，通过远程处理，作为应用程序服务器的订单管理器</span><span class="sxs-lookup"><span data-stu-id="87d10-138">Expose, by remoting, the order manager as an application server</span></span>  
  
  <span data-ttu-id="87d10-139">Southridge Video 的业务要求生成三部分组成的结构： orderbroker、 流程管理器和业务流程自身。</span><span class="sxs-lookup"><span data-stu-id="87d10-139">The business requirements of Southridge Video produce a three-part structure: an order broker, a process manager, and the business process itself.</span></span> <span data-ttu-id="87d10-140">了 Southridge Video 的两个不同的 IT 小组所涉及的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="87d10-140">Southridge Videohas two separate IT groups involved in the application.</span></span> <span data-ttu-id="87d10-141">消息组维护公司的消息传送基础结构，并连接到该基础结构的应用程序提供的组件。</span><span class="sxs-lookup"><span data-stu-id="87d10-141">A messaging group maintains the corporate messaging infrastructure and provides the components for connecting applications to that infrastructure.</span></span> <span data-ttu-id="87d10-142">另一个小组负责编写和维护用于特定业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d10-142">Another group writes and maintains applications for specific business processes.</span></span> <span data-ttu-id="87d10-143">因此，orderbroker 就独立于订单流程管理器和处理阶段，以便它可以通过单独的组进行维护。</span><span class="sxs-lookup"><span data-stu-id="87d10-143">Thus, the order broker is separate from the order process manager and process stages so that it can be maintained by a separate group.</span></span> <span data-ttu-id="87d10-144">因为它是一个单独的组件，还可以扩展 orderbroker 代理向多个进程管理器的订单。</span><span class="sxs-lookup"><span data-stu-id="87d10-144">Because it is a separate component, the order broker can also be extended to broker orders to multiple process managers.</span></span> <span data-ttu-id="87d10-145">可能会添加流程管理器，以支持新业务，例如 VIP 服务。</span><span class="sxs-lookup"><span data-stu-id="87d10-145">A process manager might be added to support a new business line, such as VIP service.</span></span>  
  
  <span data-ttu-id="87d10-146">Southridge Video 订单是长时间运行的进程： 有线订单可能需要一分钟一年时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="87d10-146">Southridge Video orders are long running processes: a cable order may take anywhere from a minute to a year to complete.</span></span> <span data-ttu-id="87d10-147">因为 BizTalk 业务流程的实例必须运行完毕，这意味着业务流程实例可能有长达一年的生存期。</span><span class="sxs-lookup"><span data-stu-id="87d10-147">Because an instance of a BizTalk orchestration must run to completion, this means that an orchestration instance could have a lifetime of up to a year.</span></span>  
  
  <span data-ttu-id="87d10-148">Southridge Video 需长时间运行的进程，允许在订单处理过程中更改应用程序组件的结构。</span><span class="sxs-lookup"><span data-stu-id="87d10-148">Southridge Video needs an architecture for long running processes that allows for application components to change during order processing.</span></span> <span data-ttu-id="87d10-149">因此，Southridge 可以将订单处理划分为多个阶段，以便使用最新的流程组件来完成订单。</span><span class="sxs-lookup"><span data-stu-id="87d10-149">Thus, Southridge divides order processing into multiple stages so that an order can complete using the newest process components.</span></span> <span data-ttu-id="87d10-150">有关如何确定业务流程中的各阶段界限的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="87d10-150">For information about how to determine stage boundaries in a business process, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
  <span data-ttu-id="87d10-151">较长的处理时间为订单，此外，部分，确定需要更改正在处理的订单。</span><span class="sxs-lookup"><span data-stu-id="87d10-151">The long processing time for an order also, in part, determines the need to change in-flight orders.</span></span> <span data-ttu-id="87d10-152">修改订单是该解决方案包含大量系统的中断的原因之一。</span><span class="sxs-lookup"><span data-stu-id="87d10-152">Modifying orders is one of the reasons that the solution includes an extensive system of interrupts.</span></span> <span data-ttu-id="87d10-153">这一中断系统简化了使顺序更改或取消操作完成前。</span><span class="sxs-lookup"><span data-stu-id="87d10-153">This interrupt system simplifies making order changes or cancellations before they are complete.</span></span> <span data-ttu-id="87d10-154">该解决方案使用.NET 消息来处理中断的解决方案的各个功能部分之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="87d10-154">The solution uses .NET messages to communicate between functional parts of the solution to handle interruptions.</span></span>  
  
  <span data-ttu-id="87d10-155">由于系统有许多外部依存关系，因此可以发生故障后重试某些操作。</span><span class="sxs-lookup"><span data-stu-id="87d10-155">Because the system has numerous external dependencies, certain operations can be retried after failure.</span></span> <span data-ttu-id="87d10-156">例如，如果后端系统，并且向其请求超时时，解决方案将等待适当的时间间隔，然后重试请求。</span><span class="sxs-lookup"><span data-stu-id="87d10-156">For example, if a backend system is unavailable and a request to it times out, the solution waits an appropriate interval and retries the request.</span></span> <span data-ttu-id="87d10-157">由于与外部系统的连接是通过自定义代码，此部分的解决方案，可广泛使用.NET 反射技术，以便对象方法将重试。</span><span class="sxs-lookup"><span data-stu-id="87d10-157">Because connections to external systems are through custom code, this portion of the solution makes extensive use of .NET reflection to allow object methods to be retried.</span></span>  
  
  <span data-ttu-id="87d10-158">该解决方案，基于真实公司一样假定订单处理问题可以由运营组中的人。</span><span class="sxs-lookup"><span data-stu-id="87d10-158">The solution assumes, like the real-life company it is based on, that problems with order processing can be handled by people in an operations group.</span></span> <span data-ttu-id="87d10-159">同样，某些种类的订单错误将返回引用与客户服务代表他们可能会取消或更正并重新提交订单。</span><span class="sxs-lookup"><span data-stu-id="87d10-159">Similarly, some kind of order errors will be referred back to a customer service representative who may cancel or correct and re-submit the order.</span></span>  
  
## <a name="business-process-management-solution-resources"></a><span data-ttu-id="87d10-160">业务流程管理解决方案资源</span><span class="sxs-lookup"><span data-stu-id="87d10-160">Business Process Management Solution Resources</span></span>  
 <span data-ttu-id="87d10-161">请阅读以下文档有关业务流程管理解决方案的其他信息。</span><span class="sxs-lookup"><span data-stu-id="87d10-161">Read the following documents for additional information about the business process management solution.</span></span>  
  
### <a name="business-process-management-solution-resources"></a><span data-ttu-id="87d10-162">业务流程管理解决方案资源</span><span class="sxs-lookup"><span data-stu-id="87d10-162">Business Process Management Solution Resources</span></span>  
  
-   [<span data-ttu-id="87d10-163">开发业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="87d10-163">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
     <span data-ttu-id="87d10-164">开发人员和软件架构师可以使用本指南记录所有代码、 模式、 体系结构，以及性能设计问题所需生成并运行业务流程管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d10-164">Developers and Software Architects can use this guide to document all code, patterns, architecture, and performance design issues required to build and run the business process management application.</span></span>  
  
-   [<span data-ttu-id="87d10-165">部署业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="87d10-165">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)  
  
     <span data-ttu-id="87d10-166">IT 专业人士的 BizTalk Server 有一个大致了解可以使用本指南生成并运行业务流程管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="87d10-166">The IT professional with a general understanding of BizTalk Server can use this guide to build and run the Business Process Management application.</span></span> <span data-ttu-id="87d10-167">本指南假定大致了解应用程序在分布式环境中工作原理。</span><span class="sxs-lookup"><span data-stu-id="87d10-167">The guide assumes a general understanding of how the application works in a distributed environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87d10-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="87d10-168">See Also</span></span>  
 [<span data-ttu-id="87d10-169">业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="87d10-169">Business Process Management Solution</span></span>](../core/business-process-management-solution.md)