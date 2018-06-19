---
title: 设计用于模式： 面向服务的解决方案 |Microsoft 文档
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
ms.openlocfilehash: fcfa7f7e4f492de139ae3f5a10f6cb39abaa73be
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240189"
---
# <a name="designing-with-patterns-the-service-oriented-solution"></a><span data-ttu-id="b9aae-102">设计用于模式： 面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="b9aae-102">Designing with Patterns: the Service Oriented Solution</span></span>
<span data-ttu-id="b9aae-103">面向服务的解决方案演示如何公开 BizTalk 应用程序作为服务以使用其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9aae-103">The service-oriented solution shows how to expose a BizTalk application as a service for use by other applications.</span></span> <span data-ttu-id="b9aae-104">提供一个应用程序作为服务使其他应用程序可以轻松地使用该信息并在它们提供的服务中使用它。</span><span class="sxs-lookup"><span data-stu-id="b9aae-104">Presenting an application as a service enables other applications to easily consume the information and use it in the services that they provide.</span></span> <span data-ttu-id="b9aae-105">有关服务的详细信息接口都在看到"服务接口" [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)。</span><span class="sxs-lookup"><span data-stu-id="b9aae-105">For more information about service interfaces see "Service Interface" at [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185).</span></span> <span data-ttu-id="b9aae-106">有关面向服务的集成的详细信息请参阅"面向服务集成"网址[http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)。</span><span class="sxs-lookup"><span data-stu-id="b9aae-106">For more information about service-oriented integration see "Service-Oriented Integration" at [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).</span></span>  
  
 <span data-ttu-id="b9aae-107">解决方案是信用信息提供的应用程序作为 Web 服务响应之后聚合中三个其他应用程序的相关信息, 的信息。</span><span class="sxs-lookup"><span data-stu-id="b9aae-107">The solution is a credit information application that provides the information as a Web service response, after aggregating relevant information from three other applications.</span></span> <span data-ttu-id="b9aae-108">应用程序将合并结果，并返回单个消息包含信用额度汇总的信息。</span><span class="sxs-lookup"><span data-stu-id="b9aae-108">The application consolidates the results and returns a single message containing the summarized credit information.</span></span> <span data-ttu-id="b9aae-109">三个后端系统如下所示：</span><span class="sxs-lookup"><span data-stu-id="b9aae-109">The three back-end systems are as follows:</span></span>  
  
-   <span data-ttu-id="b9aae-110">**SAP 企业系统。**</span><span class="sxs-lookup"><span data-stu-id="b9aae-110">**SAP Enterprise System.**</span></span> <span data-ttu-id="b9aae-111">SAP 后端提供了客户的信用总限额。</span><span class="sxs-lookup"><span data-stu-id="b9aae-111">The SAP back end provides the customer's overall credit limit.</span></span> <span data-ttu-id="b9aae-112">该解决方案使用 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 中的 SAP 适配器与此后端系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="b9aae-112">The solution communicates with this backend system using the SAP adapter in [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b9aae-113">**挂起事务系统。**</span><span class="sxs-lookup"><span data-stu-id="b9aae-113">**Pending Transactions System.**</span></span> <span data-ttu-id="b9aae-114">挂起事务系统根据帐户来报告未完成事务的总数。</span><span class="sxs-lookup"><span data-stu-id="b9aae-114">The Pending Transactions system reports the total amount of transactions outstanding against the account.</span></span> <span data-ttu-id="b9aae-115">该解决方案使用 Microsoft 主机集成服务器 (HIS) 与从 Windows Server 主机进行通信。</span><span class="sxs-lookup"><span data-stu-id="b9aae-115">The solution uses Microsoft Host Integration Server (HIS) to communicate with the mainframe from Windows Server.</span></span> <span data-ttu-id="b9aae-116">它还使用他的事务系统集成商技术。</span><span class="sxs-lookup"><span data-stu-id="b9aae-116">It also uses the Transaction Integrator technology of HIS.</span></span> <span data-ttu-id="b9aae-117">这些筛选器可与作为 Web 服务主机进行交互的系统。</span><span class="sxs-lookup"><span data-stu-id="b9aae-117">These enable the system to interact with the mainframe as a Web service.</span></span> <span data-ttu-id="b9aae-118">BizTalk 业务流程使用此 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b9aae-118">The BizTalk orchestration consumes this Web service.</span></span>  
  
-   <span data-ttu-id="b9aae-119">**支付跟踪系统。**</span><span class="sxs-lookup"><span data-stu-id="b9aae-119">**Payment Tracking System.**</span></span> <span data-ttu-id="b9aae-120">付款跟踪系统报告个人所做的最近付款。</span><span class="sxs-lookup"><span data-stu-id="b9aae-120">The Payment Tracking system reports the last payment the individual made.</span></span> <span data-ttu-id="b9aae-121">此系统使用 MQSeries。</span><span class="sxs-lookup"><span data-stu-id="b9aae-121">This system uses MQSeries.</span></span>  
  
 <span data-ttu-id="b9aae-122">您可能还记得从解决方案的概述，你还可以使用通过 MQSeries 队列的非 Web 服务接口。</span><span class="sxs-lookup"><span data-stu-id="b9aae-122">As you may recall from the overview of the solution, you can also use a non-Web service interface through MQSeries queues.</span></span> <span data-ttu-id="b9aae-123">(有关应用程序的一般结构的详细信息，请参阅[了解服务面向解决方案](../core/understanding-the-service-oriented-solution.md))。</span><span class="sxs-lookup"><span data-stu-id="b9aae-123">(For more information about the general structure of the application, see [Understanding the Service Oriented Solution](../core/understanding-the-service-oriented-solution.md)).</span></span> <span data-ttu-id="b9aae-124">虽然 Web 服务的最常见的方法来构建面向服务的体系结构，但并非所有应用程序可以使用它们。</span><span class="sxs-lookup"><span data-stu-id="b9aae-124">Although Web services are the most common way to construct service oriented architectures, not all applications can use them.</span></span> <span data-ttu-id="b9aae-125">与 BizTalk Server 解决方案可以提供，以及 Web 服务，为旧版应用程序以使用服务的备用方法。</span><span class="sxs-lookup"><span data-stu-id="b9aae-125">With BizTalk Server solutions you can provide, along with Web services, alternate ways for legacy applications to use the service.</span></span>  
  
 <span data-ttu-id="b9aae-126">MQSeries 访问模拟传统的交互式语音响应系统如何使用该解决方案。</span><span class="sxs-lookup"><span data-stu-id="b9aae-126">The MQSeries access simulates how a legacy interactive voice response system might use the solution.</span></span> <span data-ttu-id="b9aae-127">MQSeries 访问，以及 Web 服务访问权限，演示如何通过旧的应用程序和新的应用程序都使用单个解决方案。</span><span class="sxs-lookup"><span data-stu-id="b9aae-127">The MQSeries access, along with the Web service access, shows how a single solution can be used by both legacy applications and new applications.</span></span>  
  
## <a name="patterns-used-in-the-service-oriented-solution"></a><span data-ttu-id="b9aae-128">服务中使用的模式面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b9aae-128">Patterns Used in the Service Oriented Solution</span></span>  
 <span data-ttu-id="b9aae-129">下图显示在面向服务的解决方案中的模式的简化的版本。</span><span class="sxs-lookup"><span data-stu-id="b9aae-129">The following diagram shows a simplified version of the patterns in the service-oriented solution.</span></span>  
  
 <span data-ttu-id="b9aae-130">![服务 &#45; 面向的解决方案模式](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")</span><span class="sxs-lookup"><span data-stu-id="b9aae-130">![Service&#45;Oriented Solution Patterns](../core/media/service-oriented-solution-patterns.gif "Service_Oriented_Solution_Patterns")</span></span>  
  
 <span data-ttu-id="b9aae-131">此解决方案由四个主要部分，其中每个表示模式组成： 服务接口、 基于内容的路由器、 收件人列表中，和聚合器。</span><span class="sxs-lookup"><span data-stu-id="b9aae-131">The solution consists of four main parts, each of which represents a pattern: the service interface, a content-based router, a recipient list, and an aggregator.</span></span> <span data-ttu-id="b9aae-132">服务接口表示使得来连接到解决方案的接口机制。</span><span class="sxs-lookup"><span data-stu-id="b9aae-132">The service interface represents the interface mechanism that makes it possible to connect to the solution.</span></span> <span data-ttu-id="b9aae-133">基于内容的路由器检查消息的有效性，并将发送一条错误消息，如果该值无效。</span><span class="sxs-lookup"><span data-stu-id="b9aae-133">The content-based router checks the validity of the message and sends an error message if it is invalid.</span></span> <span data-ttu-id="b9aae-134">收件人列表将消息发送到三个后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="b9aae-134">The recipient list sends the message to the three back-end applications.</span></span> <span data-ttu-id="b9aae-135">如后端应用程序做出响应，聚合器会将响应合并到单个响应消息。</span><span class="sxs-lookup"><span data-stu-id="b9aae-135">As the back-end applications respond, the aggregator combines the responses into a single response message.</span></span> <span data-ttu-id="b9aae-136">该响应消息将通过服务接口返回到请求方。</span><span class="sxs-lookup"><span data-stu-id="b9aae-136">The response message goes back to the requester through the service interface.</span></span>  
  
 <span data-ttu-id="b9aae-137">请注意，许多处于未指定关系图中：</span><span class="sxs-lookup"><span data-stu-id="b9aae-137">Note that a lot is left unspecified in the diagram:</span></span>  
  
-   <span data-ttu-id="b9aae-138">关系图省略消息转换器，以便与外部系统进行通信所需的解决方案。</span><span class="sxs-lookup"><span data-stu-id="b9aae-138">The diagram omits message translators, which are required by the solution in order to communicate with the external systems.</span></span>  
  
-   <span data-ttu-id="b9aae-139">关系图不指定如何与后端进程通信。</span><span class="sxs-lookup"><span data-stu-id="b9aae-139">The diagram doesn't specify how to communicate with the back-end processes.</span></span>  
  
-   <span data-ttu-id="b9aae-140">关系图也未指定服务接口的性质。</span><span class="sxs-lookup"><span data-stu-id="b9aae-140">The diagram also does not specify the nature of the service interface.</span></span>  
  
-   <span data-ttu-id="b9aae-141">也不关系图表示使用同步或异步通信。</span><span class="sxs-lookup"><span data-stu-id="b9aae-141">Nor does the diagram indicate whether or not to use synchronous or asynchronous communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9aae-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9aae-142">See Also</span></span>  
 <span data-ttu-id="b9aae-143">[面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="b9aae-143">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="b9aae-144">转换的服务的模式面向解决方案</span><span class="sxs-lookup"><span data-stu-id="b9aae-144">Translating the Patterns of the Service Oriented Solution</span></span>](../core/translating-the-patterns-of-the-service-oriented-solution.md)