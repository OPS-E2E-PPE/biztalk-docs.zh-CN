---
title: 了解面向服务的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- service solution tutorial, background information
- service solutions, about service solutions
- service solution tutorial, about service solution tutorial
- Service Oriented Architecture (SOA)
ms.assetid: 56a2ad90-74bb-489a-ab1d-900f3bea3d64
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7114ab32084abd45eb6169e1bb4e54bcf3b5f25
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292711"
---
# <a name="understanding-the-service-oriented-solution"></a><span data-ttu-id="9aa7a-102">了解面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="9aa7a-102">Understanding the Service Oriented Solution</span></span>
<span data-ttu-id="9aa7a-103">面向服务的解决方案提供的信用余额报告应用程序设计为服务。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-103">The service oriented solution presents a credit balance reporting application designed as a service.</span></span> <span data-ttu-id="9aa7a-104">应用程序，反过来，使用三个后端应用程序，作为服务公开，获取信用余额所需的信息。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-104">The application, in turn, uses three backend applications, exposed as services themselves, to get the information needed for the credit balance.</span></span>  
  
 <span data-ttu-id="9aa7a-105">面向服务体系结构 (SOA) 是一种方法，与构建分布式的系统部分重叠。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-105">A Service Oriented Architecture (SOA) is an approach that partially overlaps building distributed systems.</span></span> <span data-ttu-id="9aa7a-106">面向服务的方法有几个特性：</span><span class="sxs-lookup"><span data-stu-id="9aa7a-106">A service-oriented approach has several characteristics:</span></span>  
  
- <span data-ttu-id="9aa7a-107">松散耦合。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-107">Loosely coupled.</span></span> <span data-ttu-id="9aa7a-108">应用程序的业务逻辑是独立于处理服务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-108">The application's business logic is separate from the logic of handling the service.</span></span>  
  
- <span data-ttu-id="9aa7a-109">可发现。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-109">Discoverable.</span></span> <span data-ttu-id="9aa7a-110">应为应用程序以查找该服务的机制。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-110">There should be a mechanism for applications to find the service.</span></span>  
  
- <span data-ttu-id="9aa7a-111">合同。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-111">Contractual.</span></span> <span data-ttu-id="9aa7a-112">服务的接口实现的用户和服务之间的约定。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-112">The interface to the service implements the contract between users and the service.</span></span>  
  
  <span data-ttu-id="9aa7a-113">尽管文献资料通常将面向服务的方法视为与 web services 同义，但它们不一定是同义词。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-113">Although the literature often treats service oriented approaches as synonymous with web services, they are not necessarily synonyms.</span></span> <span data-ttu-id="9aa7a-114">Web services 提供的极具吸引力的方法来实现面向服务的解决方案，但可以使用其他技术，如.NET 远程处理，以创建服务。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-114">Web services present an attractive way to implement service oriented solutions, but you can use other technologies, such as .NET remoting, to create services.</span></span>  
  
  <span data-ttu-id="9aa7a-115">有关面向服务体系结构的详细信息，请参阅"服务接口"处[ http://go.microsoft.com/fwlink/?LinkId=46185 ](http://go.microsoft.com/fwlink/?LinkId=46185)和"面向服务的集成"， [ http://go.microsoft.com/fwlink/?LinkId=46186 ](http://go.microsoft.com/fwlink/?LinkId=46186)。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-115">For more information about service oriented architectures, see "Service Interface" at [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185) and "Service-Oriented Integration" at [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="9aa7a-116">读者指南</span><span class="sxs-lookup"><span data-stu-id="9aa7a-116">Reader Guidance</span></span>  
 <span data-ttu-id="9aa7a-117">此解决方案的文档假定您熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-117">The documentation for this solution assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="9aa7a-118">它还假定您了解有关企业应用程序集成和 web 服务的基本概念。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-118">It also assumes that you understand basic concepts about enterprise application integration and web services.</span></span>  
  
 <span data-ttu-id="9aa7a-119">此外，若要阅读并遵循开发人员文档，应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]并熟悉如何执行以下任务： 创建项目、 设置引用以及调试和测试 BizTalk解决方案。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-119">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a><span data-ttu-id="9aa7a-120">报告在 Woodgrove Bank 的信用卡</span><span class="sxs-lookup"><span data-stu-id="9aa7a-120">Credit Card Reporting at Woodgrove Bank</span></span>  
 <span data-ttu-id="9aa7a-121">面向服务的体系结构解决方案是报告服务的 Woodgrove Bank 的信用卡余额。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-121">The service oriented architecture solution is a credit card balance reporting service for Woodgrove Bank.</span></span> <span data-ttu-id="9aa7a-122">尽管银行是虚构的但方案并不是-该方案基于实际的已部署的客户应用程序。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-122">Although the bank is fictional, the scenario is not—the scenario is based on an actual, deployed, customer application.</span></span>  
  
 <span data-ttu-id="9aa7a-123">在方案中，对信用卡余额的请求来自两个方面：</span><span class="sxs-lookup"><span data-stu-id="9aa7a-123">In the scenario, requests for credit card balances come from two sources:</span></span>  
  
- <span data-ttu-id="9aa7a-124">交互式语音应答 (IVR) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-124">An Interactive Voice Response (IVR) application.</span></span>  
  
- <span data-ttu-id="9aa7a-125">Web 页面或自定义客户端应用程序之类的交互式客户端。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-125">An interactive client such as a web page or custom client application.</span></span>  
  
  <span data-ttu-id="9aa7a-126">该解决方案接收来自 IVR 应用程序通过 MQSeries 的请求。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-126">The solution receives requests from the IVR application through MQSeries.</span></span> <span data-ttu-id="9aa7a-127">它处理来自交互式客户端通过使用 HTTP 和 SOAP 的 web 服务请求。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-127">It handles requests from the interactive client through a web service using HTTP and SOAP.</span></span>  
  
  <span data-ttu-id="9aa7a-128">新的面向服务应用程序通常需要使用的旧版应用程序使用较旧技术，同时也与现代应用程序，如使用 web 服务的网站的体系结构。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-128">New service oriented architecture applications often need to work with legacy applications that use older technologies, as well as function with modern applications such as web sites that consume web services.</span></span> <span data-ttu-id="9aa7a-129">该方案进行建模这一现实世界要求-IVR 应用程序表示旧版应用程序，客户服务客户端应用程序时，是现代。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-129">The scenario models this real world requirement—the IVR application represents a legacy application, while the customer service client application, is the modern one.</span></span>  
  
  <span data-ttu-id="9aa7a-130">Woodgrove Bank 应用程序使用三个后端，从旧系统，用于对请求作出响应的数据：</span><span class="sxs-lookup"><span data-stu-id="9aa7a-130">The Woodgrove Bank application uses data from three backend, legacy systems to respond to requests:</span></span>  
  
- <span data-ttu-id="9aa7a-131">一个提供信用总限额的应用程序。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-131">An application that provides the overall credit limit.</span></span> <span data-ttu-id="9aa7a-132">这是大型机上的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-132">This is a SAP system on a mainframe computer.</span></span>  
  
- <span data-ttu-id="9aa7a-133">挂起事务系统报告事务挂起针对帐户的总金额的一个。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-133">A pending transactions system that reports the total amount for transactions pending against the account.</span></span> <span data-ttu-id="9aa7a-134">此系统为大型机或 AS / 400 系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-134">This system is a mainframe or AS/400 system.</span></span> <span data-ttu-id="9aa7a-135">该解决方案使用 web 服务和 Microsoft Host Integration Server (HIS) 与大型机或进行通信 / 400 系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-135">The solution uses a web service and Microsoft Host Integration Server (HIS) to communicate with the mainframe or AS/400 system.</span></span>  
  
- <span data-ttu-id="9aa7a-136">付款跟踪系统，用于提供对系统所做的最近付款。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-136">A payment tracking system that gives the last payment made to the system.</span></span> <span data-ttu-id="9aa7a-137">可以使用 MQSeries 达到付款跟踪系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-137">The payment tracking system can be reached using MQSeries.</span></span>  
  
  <span data-ttu-id="9aa7a-138">收集并编译了原有系统中的信息后, 解决方案将响应发送回原始应用程序，因此，给客户。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-138">After gathering and compiling the information from the legacy systems, the solution sends the response back to the originating application and, thus, to the customer.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="9aa7a-139">业务要求</span><span class="sxs-lookup"><span data-stu-id="9aa7a-139">Business Requirements</span></span>  
 <span data-ttu-id="9aa7a-140">由于信用报告应用程序实时响应客户请求，它必须具有较低的延迟，若要快速处理请求。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-140">Because the credit reporting application responds in real time to customer requests, it must have low latency in order to handle requests quickly.</span></span> <span data-ttu-id="9aa7a-141">此外，它还必须能够处理大量的并发请求数。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-141">In addition, it must also be able to handle high numbers of simultaneous requests.</span></span> <span data-ttu-id="9aa7a-142">该解决方案使用敏感信息和一个公共接口，因此安全性十分重要。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-142">The solution uses sensitive information and a public interface so that security is significant concern.</span></span> <span data-ttu-id="9aa7a-143">最后，该服务必须是可靠。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-143">Finally, the service needs to be reliable.</span></span>  
  
 <span data-ttu-id="9aa7a-144">有关解决方案如何满足这些要求的信息，请参阅[开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-144">For information about how the solution meets these requirements, see [Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md).</span></span>  
  
## <a name="performance-characteristics"></a><span data-ttu-id="9aa7a-145">性能特征</span><span class="sxs-lookup"><span data-stu-id="9aa7a-145">Performance Characteristics</span></span>  
 <span data-ttu-id="9aa7a-146">为了满足业务要求，该方案具有以下性能特征：</span><span class="sxs-lookup"><span data-stu-id="9aa7a-146">To meet the business requirements, the scenario has the following performance characteristics:</span></span>  
  
-   <span data-ttu-id="9aa7a-147">每秒 40 个传入请求的持续的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-147">Sustained throughput of 40 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="9aa7a-148">每秒 100 个传入请求的峰值吞吐量。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-148">Peak throughput of 100 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="9aa7a-149">90%的请求 （传入和传出 BizTalk Server) 在 1000 毫秒内提供服务。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-149">90 percent of the requests to be serviced (in and out of BizTalk Server) in under 1000 milliseconds.</span></span>  
  
-   <span data-ttu-id="9aa7a-150">95%的请求 （传入和传出 BizTalk Server) 在 2000 毫秒内提供服务。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-150">95 percent of the requests to be serviced (in and out of BizTalk Server) in under 2000 milliseconds.</span></span>  
  
-   <span data-ttu-id="9aa7a-151">100%的请求 （传入和传出 BizTalk Server) 在 5000 毫秒内提供服务。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-151">100 percent of the requests to be serviced (in and out of BizTalk Server) in under 5000 milliseconds.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9aa7a-152">这些时间不包括后端系统的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-152">These times do not include the latency times of the back end systems.</span></span>  
  
## <a name="three-versions-of-the-solution"></a><span data-ttu-id="9aa7a-153">三个版本的解决方案</span><span class="sxs-lookup"><span data-stu-id="9aa7a-153">Three Versions of the Solution</span></span>  
 <span data-ttu-id="9aa7a-154">有三个版本的解决方案：</span><span class="sxs-lookup"><span data-stu-id="9aa7a-154">There are three versions of the solution:</span></span>  
  
- <span data-ttu-id="9aa7a-155">存根版本将替换所有后端系统使用软件存根。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-155">The stub version replaces all of the backend systems with software stubs.</span></span> <span data-ttu-id="9aa7a-156">这些存根模拟后端系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-156">The stubs simulate the backend systems.</span></span> <span data-ttu-id="9aa7a-157">此版本提供了部署并运行该解决方案在单台计算机上的快速方法。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-157">This version provides a quick way to deploy and run the solution on a single computer.</span></span>  
  
- <span data-ttu-id="9aa7a-158">适配器版本使用 BizTalk 适配器来连接到后端系统。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-158">The adapter version uses BizTalk adapters to connect to the backend systems.</span></span> <span data-ttu-id="9aa7a-159">此版本是如何首先想象来实现此解决方案。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-159">This version is how one might first think to implement the solution.</span></span> <span data-ttu-id="9aa7a-160">但是，将消息发送到后端系统使用的适配器有明显的延迟在获取响应。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-160">However, sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="9aa7a-161">虽然适配器本身无法提供延迟非常低，BizTalk Server 的分布式的结构要求适配器与使用 messagebox 的业务流程主机实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-161">While adapters by themselves could offer very low latency, the distributed architecture of BizTalk Server requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="9aa7a-162">这给数据库带来了往返行程，从而影响延迟时间。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-162">This introduces round trips to the database and affects latency times.</span></span>  
  
- <span data-ttu-id="9aa7a-163">内联版本使用直接与后端系统进行通信的内联代码替换适配器。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-163">The inline version replaces the adapters with inline code that communicates directly with the backend systems.</span></span> <span data-ttu-id="9aa7a-164">该解决方案的内联版本具有最低的延迟和最高的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-164">The inline version of the solution has the lowest latency and the highest throughput.</span></span>  
  
  <span data-ttu-id="9aa7a-165">部署指南为构建和部署的解决方案，所有三个版本，以及提供一种方法，在每个版本中，以模拟通过 HIS 连接到挂起事务系统提供说明。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-165">The deployment guide provides directions for building and deploying all three versions of the solution, as well as providing a way, in each version, to simulate the connection through HIS to the pending transactions system.</span></span> <span data-ttu-id="9aa7a-166">有关生成和部署解决方案的信息，请参阅[部署面向服务的解决方案](../core/deploying-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="9aa7a-166">For information about building and deploying the solution, see [Deploying the Service Oriented Solution](../core/deploying-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa7a-167">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aa7a-167">See Also</span></span>  
 [<span data-ttu-id="9aa7a-168">面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="9aa7a-168">Service Oriented Solution</span></span>](../core/service-oriented-solution.md)