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
ms.openlocfilehash: 4742ad9625c91c9a8f92f8359c4e0becbb166eab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004902"
---
# <a name="understanding-the-business-process-management-solution"></a><span data-ttu-id="a5f34-102">了解业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="a5f34-102">Understanding the Business Process Management Solution</span></span>
<span data-ttu-id="a5f34-103">使用本部分中介绍的解决方案可以实现业务流程管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5f34-103">The solution described in this section presents one way to implement a business process management application.</span></span> <span data-ttu-id="a5f34-104">在理想的业务流程管理器，代表业务流程解决方案的部分中，与特定后端系统，发送响应消息进行通信的业务规则 — 分开支持过程的基础结构。</span><span class="sxs-lookup"><span data-stu-id="a5f34-104">In an ideal business process manager, the parts of the solution representing the business process—the business rules, communicating with specific backend systems, sending response messages—are separate from the infrastructure supporting the process.</span></span>  
  
 <span data-ttu-id="a5f34-105">在此解决方案（Southridge Video 的有线服务订购系统）中，业务流程分为一系列阶段。</span><span class="sxs-lookup"><span data-stu-id="a5f34-105">In this solution, a cable service ordering system for Southridge Video, the business process is broken into a series of stages.</span></span> <span data-ttu-id="a5f34-106">各个阶段的操作由一个对业务规则和后端系统的相关信息一无所知的 OrderManager 进行管理。</span><span class="sxs-lookup"><span data-stu-id="a5f34-106">An order manager, which knows nothing about the business rules and backend systems, directs the operation of the stages.</span></span> <span data-ttu-id="a5f34-107">OrderManager 接收来自 OrderBroker 的订单，后者可以将订单传至若干不同的 OrderManager。</span><span class="sxs-lookup"><span data-stu-id="a5f34-107">The order manager receives orders from an order broker, which can direct orders to several different order managers.</span></span>  
  
 <span data-ttu-id="a5f34-108">该解决方案广泛地应用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的功能，并且显示了如何使用应用程序内部消息来协调应用程序的各个部分。此外，还展示了一些其他功能。</span><span class="sxs-lookup"><span data-stu-id="a5f34-108">The solution makes extensive use of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features and shows, among other things, the use of messages internal to the application for coordinating parts of the application.</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="a5f34-109">读者指南</span><span class="sxs-lookup"><span data-stu-id="a5f34-109">Reader Guidance</span></span>  
 <span data-ttu-id="a5f34-110">本文档假定您熟悉 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a5f34-110">This document assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="a5f34-111">它还假定您了解有关企业应用程序集成和 Web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="a5f34-111">It also assumes that you understand basic concepts about enterprise application integration and Web services.</span></span>  
  
 <span data-ttu-id="a5f34-112">此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。</span><span class="sxs-lookup"><span data-stu-id="a5f34-112">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="ordering-cable-service-from-southridge-video"></a><span data-ttu-id="a5f34-113">从 Southridge Video 订购有线服务</span><span class="sxs-lookup"><span data-stu-id="a5f34-113">Ordering Cable Service from Southridge Video</span></span>  
 <span data-ttu-id="a5f34-114">该业务流程管理解决方案实现 Southridge Video 的有线服务订购系统。</span><span class="sxs-lookup"><span data-stu-id="a5f34-114">The business process management solution implements a cable service ordering system for Southridge Video.</span></span> <span data-ttu-id="a5f34-115">联系中心的客户服务代表在接到客户向联系中心拨打的电话后，会将订单信息输入到订单系统中。</span><span class="sxs-lookup"><span data-stu-id="a5f34-115">Customers phone into a call center where a customer service representative takes the order and enters it into the order system.</span></span> <span data-ttu-id="a5f34-116">下面的关系图显示了订单在该系统中的常规流程：</span><span class="sxs-lookup"><span data-stu-id="a5f34-116">The following diagram shows the general flow of an order through the system:</span></span>  
  
 <span data-ttu-id="a5f34-117">![业务流程管理解决方案工作流](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span><span class="sxs-lookup"><span data-stu-id="a5f34-117">![Business Process Management Solution Work Flow](../core/media/business-process-manager-solution-work-flow.gif "Business_Process_Manager_Solution_Work_Flow")</span></span>  
  
 <span data-ttu-id="a5f34-118">订单将传至 OrderBroker，并由后者发送至 OrderManager。</span><span class="sxs-lookup"><span data-stu-id="a5f34-118">Orders go to the order broker, which sends the order on to the order manager.</span></span> <span data-ttu-id="a5f34-119">OrderManager 会以正确的顺序运行各处理阶段来处理订单。</span><span class="sxs-lookup"><span data-stu-id="a5f34-119">The order manager runs the processing stages in the proper sequence to process the order.</span></span> <span data-ttu-id="a5f34-120">请注意，某些种类的错误会传至运营中心进行更正和重新提交，并且解决方案会在一个 SQL Server 表中记录每个订单的历史记录。</span><span class="sxs-lookup"><span data-stu-id="a5f34-120">Notice that some kinds of errors go to an operations center for correction and resubmission, and that the solution records the history of each order in a SQL Server table.</span></span>  
  
 <span data-ttu-id="a5f34-121">下面的关系图概略显示了处理订单时的步骤：</span><span class="sxs-lookup"><span data-stu-id="a5f34-121">The following diagram shows the broad outline of the steps in processing an order.</span></span>  
  
 <span data-ttu-id="a5f34-122">![业务流程管理解决方案序列](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span><span class="sxs-lookup"><span data-stu-id="a5f34-122">![Business Process Management Solution Sequence](../core/media/business-process-manager-solution-sequence.gif "Business_Process_Manager_Solution_Sequence")</span></span>  
  
 <span data-ttu-id="a5f34-123">请注意，订单可以更新，也可以取消。</span><span class="sxs-lookup"><span data-stu-id="a5f34-123">Notice that an order can be updated as well as canceled.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="a5f34-124">业务需求</span><span class="sxs-lookup"><span data-stu-id="a5f34-124">Business Requirements</span></span>  
 <span data-ttu-id="a5f34-125">此业务流程管理解决方案是 Southridge Video（一家有线服务提供商）的一个订单系统示例。</span><span class="sxs-lookup"><span data-stu-id="a5f34-125">The business process management solution is an example of an order system for Southridge Video, a cable service provider.</span></span> <span data-ttu-id="a5f34-126">它显示了一种在 Microsoft BizTalk Server 中实现流程管理器模式的方法。</span><span class="sxs-lookup"><span data-stu-id="a5f34-126">It shows one way to implement the process manager pattern in Microsoft BizTalk Server.</span></span> <span data-ttu-id="a5f34-127">该解决方案使用一个业务流程来管理两个用于实现业务程序的附属业务流程中的订单流程。</span><span class="sxs-lookup"><span data-stu-id="a5f34-127">The solution uses an orchestration to manage the flow of orders through two satellite orchestrations that implement the business process.</span></span> <span data-ttu-id="a5f34-128">此结构基于解决方案的业务需求而构建，这些需求包括：</span><span class="sxs-lookup"><span data-stu-id="a5f34-128">This structure comes out of the solution's business requirements which include the following:</span></span>  
  
- <span data-ttu-id="a5f34-129">能够对业务流程进行版本控制</span><span class="sxs-lookup"><span data-stu-id="a5f34-129">Ability to version the business process</span></span>  
  
- <span data-ttu-id="a5f34-130">处理长时间运行的订单</span><span class="sxs-lookup"><span data-stu-id="a5f34-130">Process long-running orders</span></span>  
  
- <span data-ttu-id="a5f34-131">修改或取消仍在处理的订单（补充正在处理的订单）</span><span class="sxs-lookup"><span data-stu-id="a5f34-131">Modify or cancel orders that are still being processed (supplement in-flight orders)</span></span>  
  
- <span data-ttu-id="a5f34-132">避免挂起订单</span><span class="sxs-lookup"><span data-stu-id="a5f34-132">Avoid suspended orders</span></span>  
  
- <span data-ttu-id="a5f34-133">跟踪订单的整个处理过程</span><span class="sxs-lookup"><span data-stu-id="a5f34-133">Track orders through the entire process</span></span>  
  
- <span data-ttu-id="a5f34-134">成批处理订单</span><span class="sxs-lookup"><span data-stu-id="a5f34-134">Batch order processing</span></span>  
  
- <span data-ttu-id="a5f34-135">接受来自远程数据中心的订单</span><span class="sxs-lookup"><span data-stu-id="a5f34-135">Accept orders from remote data centers</span></span>  
  
- <span data-ttu-id="a5f34-136">允许不同的组处理订单处理的各部分过程</span><span class="sxs-lookup"><span data-stu-id="a5f34-136">Allowing different groups to handle parts of the order processing</span></span>  
  
- <span data-ttu-id="a5f34-137">通过添加 BizTalk 组来扩展应用程序</span><span class="sxs-lookup"><span data-stu-id="a5f34-137">Scale the application by adding BizTalk groups</span></span>  
  
- <span data-ttu-id="a5f34-138">远程将 OrderManager 作为应用程序服务器公开</span><span class="sxs-lookup"><span data-stu-id="a5f34-138">Expose, by remoting, the order manager as an application server</span></span>  
  
  <span data-ttu-id="a5f34-139">Southridge Video 的业务要求生成三部分组成的结构： orderbroker、 流程管理器和业务流程自身。</span><span class="sxs-lookup"><span data-stu-id="a5f34-139">The business requirements of Southridge Video produce a three-part structure: an order broker, a process manager, and the business process itself.</span></span> <span data-ttu-id="a5f34-140">该应用程序涉及了 Southridge Video 的两个不同的 IT 小组。</span><span class="sxs-lookup"><span data-stu-id="a5f34-140">Southridge Videohas two separate IT groups involved in the application.</span></span> <span data-ttu-id="a5f34-141">一个是消息传送小组，负责维护公司的消息传送基础结构，并提供用于将应用程序连接到该基础结构的组件。</span><span class="sxs-lookup"><span data-stu-id="a5f34-141">A messaging group maintains the corporate messaging infrastructure and provides the components for connecting applications to that infrastructure.</span></span> <span data-ttu-id="a5f34-142">另一个小组负责编写和维护用于特定业务流程的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5f34-142">Another group writes and maintains applications for specific business processes.</span></span> <span data-ttu-id="a5f34-143">这样，OrderBroker 就独立于订单流程管理器和处理阶段，因而可以由一个单独的小组进行维护。</span><span class="sxs-lookup"><span data-stu-id="a5f34-143">Thus, the order broker is separate from the order process manager and process stages so that it can be maintained by a separate group.</span></span> <span data-ttu-id="a5f34-144">由于 OrderBroker 是一个单独的组件，因此还可以进行扩展，作为多个流程管理器的 OrderBroker。</span><span class="sxs-lookup"><span data-stu-id="a5f34-144">Because it is a separate component, the order broker can also be extended to broker orders to multiple process managers.</span></span> <span data-ttu-id="a5f34-145">可以添加流程管理器以支持新业务，例如 VIP 服务。</span><span class="sxs-lookup"><span data-stu-id="a5f34-145">A process manager might be added to support a new business line, such as VIP service.</span></span>  
  
  <span data-ttu-id="a5f34-146">Southridge Video 订单是长时间运行的进程： 有线订单可能需要一分钟一年时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="a5f34-146">Southridge Video orders are long running processes: a cable order may take anywhere from a minute to a year to complete.</span></span> <span data-ttu-id="a5f34-147">因为 BizTalk 业务流程实例必须运行到完成为止，所以这意味着业务流程实例的生存期可能长达一年。</span><span class="sxs-lookup"><span data-stu-id="a5f34-147">Because an instance of a BizTalk orchestration must run to completion, this means that an orchestration instance could have a lifetime of up to a year.</span></span>  
  
  <span data-ttu-id="a5f34-148">Southridge Video 所需的结构应支持长时间运行的流程，并允许在订单处理期间更改应用程序组件。</span><span class="sxs-lookup"><span data-stu-id="a5f34-148">Southridge Video needs an architecture for long running processes that allows for application components to change during order processing.</span></span> <span data-ttu-id="a5f34-149">这样，Southridge 可以将订单处理分为多个阶段，以便使用最新的流程组件来完成订单。</span><span class="sxs-lookup"><span data-stu-id="a5f34-149">Thus, Southridge divides order processing into multiple stages so that an order can complete using the newest process components.</span></span> <span data-ttu-id="a5f34-150">有关如何确定业务流程中的各阶段界限的信息，请参阅[业务流程管理解决方案中的某些设计原则](../core/some-design-principles-in-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="a5f34-150">For information about how to determine stage boundaries in a business process, see [Some Design Principles in the Business Process Management Solution](../core/some-design-principles-in-the-business-process-management-solution.md).</span></span>  
  
  <span data-ttu-id="a5f34-151">订单处理需要很长时间也在一定程度上决定了更改正在处理的订单的需要。</span><span class="sxs-lookup"><span data-stu-id="a5f34-151">The long processing time for an order also, in part, determines the need to change in-flight orders.</span></span> <span data-ttu-id="a5f34-152">修改订单正是该解决方案包含一系列中断的原因之一。</span><span class="sxs-lookup"><span data-stu-id="a5f34-152">Modifying orders is one of the reasons that the solution includes an extensive system of interrupts.</span></span> <span data-ttu-id="a5f34-153">这一中断系统简化了在订单完成之前进行的订购更改或取消操作。</span><span class="sxs-lookup"><span data-stu-id="a5f34-153">This interrupt system simplifies making order changes or cancellations before they are complete.</span></span> <span data-ttu-id="a5f34-154">为处理中断，解决方案使用 .NET 消息在该解决方案的各个功能部分之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="a5f34-154">The solution uses .NET messages to communicate between functional parts of the solution to handle interruptions.</span></span>  
  
  <span data-ttu-id="a5f34-155">由于系统有许多外部依存关系，因此某些操作可以在失败后重试。</span><span class="sxs-lookup"><span data-stu-id="a5f34-155">Because the system has numerous external dependencies, certain operations can be retried after failure.</span></span> <span data-ttu-id="a5f34-156">例如，如果某个后端系统不可用，而对该后端系统的某个请求超时，该解决方案将等待适当的时间间隔，然后重试该请求。</span><span class="sxs-lookup"><span data-stu-id="a5f34-156">For example, if a backend system is unavailable and a request to it times out, the solution waits an appropriate interval and retries the request.</span></span> <span data-ttu-id="a5f34-157">由于与外部系统之间的连接是通过自定义代码建立的，因此该部分的解决方案广泛地使用了 .NET 反射技术，以便重试对象方法。</span><span class="sxs-lookup"><span data-stu-id="a5f34-157">Because connections to external systems are through custom code, this portion of the solution makes extensive use of .NET reflection to allow object methods to be retried.</span></span>  
  
  <span data-ttu-id="a5f34-158">就像该解决方案所基于的真实公司一样，该解决方案假定订单处理问题可以由运营组中的人员来处理。</span><span class="sxs-lookup"><span data-stu-id="a5f34-158">The solution assumes, like the real-life company it is based on, that problems with order processing can be handled by people in an operations group.</span></span> <span data-ttu-id="a5f34-159">同样，某些种类的订单错误将返回给客户服务代表进行处理。客户服务代表可以取消订单，也可以在更正后重新提交订单。</span><span class="sxs-lookup"><span data-stu-id="a5f34-159">Similarly, some kind of order errors will be referred back to a customer service representative who may cancel or correct and re-submit the order.</span></span>  
  
## <a name="business-process-management-solution-resources"></a><span data-ttu-id="a5f34-160">业务流程管理解决方案资源</span><span class="sxs-lookup"><span data-stu-id="a5f34-160">Business Process Management Solution Resources</span></span>  
 <span data-ttu-id="a5f34-161">请阅读以下文档，以了解有关业务流程管理解决方案的其他信息。</span><span class="sxs-lookup"><span data-stu-id="a5f34-161">Read the following documents for additional information about the business process management solution.</span></span>  
  
### <a name="business-process-management-solution-resources"></a><span data-ttu-id="a5f34-162">业务流程管理解决方案资源</span><span class="sxs-lookup"><span data-stu-id="a5f34-162">Business Process Management Solution Resources</span></span>  
  
-   [<span data-ttu-id="a5f34-163">开发业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="a5f34-163">Developing a Business Process Management Solution</span></span>](../core/developing-a-business-process-management-solution.md)  
  
     <span data-ttu-id="a5f34-164">开发人员和软件设计师可以使用此指南记录生成和运行业务流程管理应用程序所需的全部代码、模式、结构和性能设计问题。</span><span class="sxs-lookup"><span data-stu-id="a5f34-164">Developers and Software Architects can use this guide to document all code, patterns, architecture, and performance design issues required to build and run the business process management application.</span></span>  
  
-   [<span data-ttu-id="a5f34-165">部署业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="a5f34-165">Deploying the Business Process Management Solution</span></span>](../core/deploying-the-business-process-management-solution.md)  
  
     <span data-ttu-id="a5f34-166">掌握 BizTalk Server 常规知识的 IT 专业人士可以使用此指南生成和运行业务流程管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5f34-166">The IT professional with a general understanding of BizTalk Server can use this guide to build and run the Business Process Management application.</span></span> <span data-ttu-id="a5f34-167">该指南假定读者掌握有关应用程序在分布式环境中的工作原理的常规知识。</span><span class="sxs-lookup"><span data-stu-id="a5f34-167">The guide assumes a general understanding of how the application works in a distributed environment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5f34-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5f34-168">See Also</span></span>  
 [<span data-ttu-id="a5f34-169">业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="a5f34-169">Business Process Management Solution</span></span>](../core/business-process-management-solution.md)