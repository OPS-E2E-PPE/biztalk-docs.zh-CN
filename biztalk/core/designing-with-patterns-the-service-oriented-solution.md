---
title: 使用模式进行设计： 面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- patterns [service solutions], examples
- examples, programming patterns
- patterns [service solutions], designing
- designing, programming patterns
ms.assetid: c196cd9d-2b2d-4548-bc7d-26196f7c2878
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0663a9ec82a1e50807f676f7e46211d433086bff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351585"
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a><span data-ttu-id="918c7-102">使用模式进行设计： 面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="918c7-102">Designing with Patterns: the Service Oriented Solution</span></span>
<span data-ttu-id="918c7-103">面向服务的解决方案演示如何公开以供使用的服务的 BizTalk 应用程序由其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="918c7-103">The service-oriented solution shows how to expose a BizTalk application as a service for use by other applications.</span></span> <span data-ttu-id="918c7-104">提供程序作为服务使其他应用程序可以轻松地使用该信息以及它们提供的服务中使用它。</span><span class="sxs-lookup"><span data-stu-id="918c7-104">Presenting an application as a service enables other applications to easily consume the information and use it in the services that they provide.</span></span> <span data-ttu-id="918c7-105">详细了解服务接口都在看到"服务接口" [ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185)。</span><span class="sxs-lookup"><span data-stu-id="918c7-105">For more information about service interfaces see "Service Interface" at [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185).</span></span> <span data-ttu-id="918c7-106">有关面向服务的集成的详细信息请参阅"面向服务集成"处[ http://go.microsoft.com/fwlink/?LinkId=46186 ](http://go.microsoft.com/fwlink/?LinkId=46186)。</span><span class="sxs-lookup"><span data-stu-id="918c7-106">For more information about service-oriented integration see "Service-Oriented Integration" at [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).</span></span>  
  
 <span data-ttu-id="918c7-107">解决方法是提供作为 Web 服务响应之后聚合中其他三个应用程序的相关信息, 的信息的信用额度信息应用程序。</span><span class="sxs-lookup"><span data-stu-id="918c7-107">The solution is a credit information application that provides the information as a Web service response, after aggregating relevant information from three other applications.</span></span> <span data-ttu-id="918c7-108">应用程序将结果合并，并返回一条消息包含汇总的信用信息。</span><span class="sxs-lookup"><span data-stu-id="918c7-108">The application consolidates the results and returns a single message containing the summarized credit information.</span></span> <span data-ttu-id="918c7-109">三个后端系统是按如下所示：</span><span class="sxs-lookup"><span data-stu-id="918c7-109">The three back-end systems are as follows:</span></span>  
  
- <span data-ttu-id="918c7-110">**SAP 企业系统。**</span><span class="sxs-lookup"><span data-stu-id="918c7-110">**SAP Enterprise System.**</span></span> <span data-ttu-id="918c7-111">SAP 后端提供了客户的信用总限额。</span><span class="sxs-lookup"><span data-stu-id="918c7-111">The SAP back end provides the customer's overall credit limit.</span></span> <span data-ttu-id="918c7-112">该解决方案与使用中的 SAP 适配器此后端系统进行通信[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="918c7-112">The solution communicates with this backend system using the SAP adapter in [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
- <span data-ttu-id="918c7-113">**挂起事务系统。**</span><span class="sxs-lookup"><span data-stu-id="918c7-113">**Pending Transactions System.**</span></span> <span data-ttu-id="918c7-114">挂起事务系统报告针对帐户未完成事务的总金额。</span><span class="sxs-lookup"><span data-stu-id="918c7-114">The Pending Transactions system reports the total amount of transactions outstanding against the account.</span></span> <span data-ttu-id="918c7-115">该解决方案使用 Microsoft Host Integration Server (HIS) 与大型机从 Windows Server 进行通信。</span><span class="sxs-lookup"><span data-stu-id="918c7-115">The solution uses Microsoft Host Integration Server (HIS) to communicate with the mainframe from Windows Server.</span></span> <span data-ttu-id="918c7-116">它还使用他的事务集成器技术。</span><span class="sxs-lookup"><span data-stu-id="918c7-116">It also uses the Transaction Integrator technology of HIS.</span></span> <span data-ttu-id="918c7-117">这些筛选器可与大型机作为 Web 服务进行交互的系统。</span><span class="sxs-lookup"><span data-stu-id="918c7-117">These enable the system to interact with the mainframe as a Web service.</span></span> <span data-ttu-id="918c7-118">BizTalk 业务流程使用此 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="918c7-118">The BizTalk orchestration consumes this Web service.</span></span>  
  
- <span data-ttu-id="918c7-119">**付款跟踪系统。**</span><span class="sxs-lookup"><span data-stu-id="918c7-119">**Payment Tracking System.**</span></span> <span data-ttu-id="918c7-120">付款跟踪系统报告个人所做的最近付款。</span><span class="sxs-lookup"><span data-stu-id="918c7-120">The Payment Tracking system reports the last payment the individual made.</span></span> <span data-ttu-id="918c7-121">此系统使用 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="918c7-121">This system uses MQSeries.</span></span>  
  
  <span data-ttu-id="918c7-122">您可能还记得解决方案的概述，还可以使用通过 MQSeries 队列的非 Web 服务接口。</span><span class="sxs-lookup"><span data-stu-id="918c7-122">As you may recall from the overview of the solution, you can also use a non-Web service interface through MQSeries queues.</span></span> <span data-ttu-id="918c7-123">(有关应用程序的常规结构的详细信息，请参阅[了解面向服务的解决方案](../core/understanding-the-service-oriented-solution.md))。</span><span class="sxs-lookup"><span data-stu-id="918c7-123">(For more information about the general structure of the application, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md)).</span></span> <span data-ttu-id="918c7-124">尽管 Web 服务的最常见方式构造面向服务体系结构，但并非所有应用程序可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="918c7-124">Although Web services are the most common way to construct service oriented architectures, not all applications can use them.</span></span> <span data-ttu-id="918c7-125">与 BizTalk Server 解决方案可以提供的以及 Web 服务，旧版应用程序使用服务的备用方法。</span><span class="sxs-lookup"><span data-stu-id="918c7-125">With BizTalk Server solutions you can provide, along with Web services, alternate ways for legacy applications to use the service.</span></span>  
  
  <span data-ttu-id="918c7-126">MQSeries access 来模拟旧的交互式语音应答系统如何使用该解决方案。</span><span class="sxs-lookup"><span data-stu-id="918c7-126">The MQSeries access simulates how a legacy interactive voice response system might use the solution.</span></span> <span data-ttu-id="918c7-127">MQSeries 访问，Web 服务访问权限，以及演示如何通过旧版应用程序和新应用程序使用单个解决方案。</span><span class="sxs-lookup"><span data-stu-id="918c7-127">The MQSeries access, along with the Web service access, shows how a single solution can be used by both legacy applications and new applications.</span></span>  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a><span data-ttu-id="918c7-128">面向解决方案在服务中使用的模式</span><span class="sxs-lookup"><span data-stu-id="918c7-128">Patterns Used in the Service Oriented Solution</span></span>  
 <span data-ttu-id="918c7-129">下图显示模式的简化的版本的面向服务的解决方案中。</span><span class="sxs-lookup"><span data-stu-id="918c7-129">The following diagram shows a simplified version of the patterns in the service-oriented solution.</span></span>  
  
 <span data-ttu-id="918c7-130">![服务&#45;面向解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")</span><span class="sxs-lookup"><span data-stu-id="918c7-130">![Service&#45;Oriented Solution Patterns](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")</span></span>  
  
 <span data-ttu-id="918c7-131">该解决方案包含四个主要部分，其中每个表示一种模式： 服务接口、 基于内容的路由器、 收件人列表和聚合器。</span><span class="sxs-lookup"><span data-stu-id="918c7-131">The solution consists of four main parts, each of which represents a pattern: the service interface, a content-based router, a recipient list, and an aggregator.</span></span> <span data-ttu-id="918c7-132">服务接口表示的接口机制，使用它可以连接到解决方案。</span><span class="sxs-lookup"><span data-stu-id="918c7-132">The service interface represents the interface mechanism that makes it possible to connect to the solution.</span></span> <span data-ttu-id="918c7-133">基于内容的路由器检查消息的有效性，并发送一条错误消息是否无效。</span><span class="sxs-lookup"><span data-stu-id="918c7-133">The content-based router checks the validity of the message and sends an error message if it is invalid.</span></span> <span data-ttu-id="918c7-134">收件人列表将消息发送到三个后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="918c7-134">The recipient list sends the message to the three back-end applications.</span></span> <span data-ttu-id="918c7-135">因为后端应用程序做出响应，聚合器将响应合并到单个响应消息。</span><span class="sxs-lookup"><span data-stu-id="918c7-135">As the back-end applications respond, the aggregator combines the responses into a single response message.</span></span> <span data-ttu-id="918c7-136">响应消息到请求者通过服务接口将返回。</span><span class="sxs-lookup"><span data-stu-id="918c7-136">The response message goes back to the requester through the service interface.</span></span>  
  
 <span data-ttu-id="918c7-137">请注意，还有许多未表达不在关系图中指定：</span><span class="sxs-lookup"><span data-stu-id="918c7-137">Note that a lot is left unspecified in the diagram:</span></span>  
  
-   <span data-ttu-id="918c7-138">在关系图将忽略消息转换器，以便与外部系统进行通信所需的解决方案。</span><span class="sxs-lookup"><span data-stu-id="918c7-138">The diagram omits message translators, which are required by the solution in order to communicate with the external systems.</span></span>  
  
-   <span data-ttu-id="918c7-139">在关系图不会指定如何与后端进程进行通信。</span><span class="sxs-lookup"><span data-stu-id="918c7-139">The diagram doesn't specify how to communicate with the back-end processes.</span></span>  
  
-   <span data-ttu-id="918c7-140">在关系图也不会指定服务接口的性质。</span><span class="sxs-lookup"><span data-stu-id="918c7-140">The diagram also does not specify the nature of the service interface.</span></span>  
  
-   <span data-ttu-id="918c7-141">不会在关系图指示使用同步或异步通信。</span><span class="sxs-lookup"><span data-stu-id="918c7-141">Nor does the diagram indicate whether or not to use synchronous or asynchronous communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="918c7-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="918c7-142">See Also</span></span>  
 <span data-ttu-id="918c7-143">[开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="918c7-143">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="918c7-144">将服务的模式转换面向解决方案</span><span class="sxs-lookup"><span data-stu-id="918c7-144">Translating the Patterns of the Service Oriented Solution</span></span>](../core/translating-the-patterns-of-the-service-oriented-solution.md)