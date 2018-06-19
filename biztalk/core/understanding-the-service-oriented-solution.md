---
title: 了解服务面向解决方案 |Microsoft 文档
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
ms.openlocfilehash: a8be3a1e7a05c2c60f1ab16c6da4df74dddf7adb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287941"
---
# <a name="understanding-the-service-oriented-solution"></a><span data-ttu-id="c30be-102">了解服务面向解决方案</span><span class="sxs-lookup"><span data-stu-id="c30be-102">Understanding the Service Oriented Solution</span></span>
<span data-ttu-id="c30be-103">面向服务的解决方案提供了设计为服务的信用余额报告应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30be-103">The service oriented solution presents a credit balance reporting application designed as a service.</span></span> <span data-ttu-id="c30be-104">该应用程序又使用三个作为服务公开的后端应用程序来获取信用余额所需的信息。</span><span class="sxs-lookup"><span data-stu-id="c30be-104">The application, in turn, uses three backend applications, exposed as services themselves, to get the information needed for the credit balance.</span></span>  
  
 <span data-ttu-id="c30be-105">面向服务的结构 (SOA) 是一种与构建分布式系统部分重叠的方法。</span><span class="sxs-lookup"><span data-stu-id="c30be-105">A Service Oriented Architecture (SOA) is an approach that partially overlaps building distributed systems.</span></span> <span data-ttu-id="c30be-106">面向服务的方法具有以下几个特征：</span><span class="sxs-lookup"><span data-stu-id="c30be-106">A service-oriented approach has several characteristics:</span></span>  
  
-   <span data-ttu-id="c30be-107">松散连接。</span><span class="sxs-lookup"><span data-stu-id="c30be-107">Loosely coupled.</span></span> <span data-ttu-id="c30be-108">应用程序的业务逻辑独立于处理服务的逻辑。</span><span class="sxs-lookup"><span data-stu-id="c30be-108">The application's business logic is separate from the logic of handling the service.</span></span>  
  
-   <span data-ttu-id="c30be-109">可发现。</span><span class="sxs-lookup"><span data-stu-id="c30be-109">Discoverable.</span></span> <span data-ttu-id="c30be-110">应存在可供应用程序查找服务的机制。</span><span class="sxs-lookup"><span data-stu-id="c30be-110">There should be a mechanism for applications to find the service.</span></span>  
  
-   <span data-ttu-id="c30be-111">契约性。</span><span class="sxs-lookup"><span data-stu-id="c30be-111">Contractual.</span></span> <span data-ttu-id="c30be-112">指向服务的接口实现了用户与服务之间的契约。</span><span class="sxs-lookup"><span data-stu-id="c30be-112">The interface to the service implements the contract between users and the service.</span></span>  
  
 <span data-ttu-id="c30be-113">尽管在文献资料中通常将面向服务的方法视为与 Web Services 同义，但两者并不一定是同义词。</span><span class="sxs-lookup"><span data-stu-id="c30be-113">Although the literature often treats service oriented approaches as synonymous with web services, they are not necessarily synonyms.</span></span> <span data-ttu-id="c30be-114">Web Services 提供了一种实现面向服务的解决方案的有效方法，但您也可以使用 .NET 远程处理等其他技术来创建服务。</span><span class="sxs-lookup"><span data-stu-id="c30be-114">Web services present an attractive way to implement service oriented solutions, but you can use other technologies, such as .NET remoting, to create services.</span></span>  
  
 <span data-ttu-id="c30be-115">有关面向服务的体系结构的详细信息，请参阅"服务接口"网址[http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185)和在的"面向服务集成" [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186)。</span><span class="sxs-lookup"><span data-stu-id="c30be-115">For more information about service oriented architectures, see "Service Interface" at [http://go.microsoft.com/fwlink/?LinkId=46185](http://go.microsoft.com/fwlink/?LinkId=46185) and "Service-Oriented Integration" at [http://go.microsoft.com/fwlink/?LinkId=46186](http://go.microsoft.com/fwlink/?LinkId=46186).</span></span>  
  
## <a name="reader-guidance"></a><span data-ttu-id="c30be-116">读者指南</span><span class="sxs-lookup"><span data-stu-id="c30be-116">Reader Guidance</span></span>  
 <span data-ttu-id="c30be-117">此解决方案的文档假定你熟悉[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c30be-117">The documentation for this solution assumes that you are familiar with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c30be-118">并假定您了解有关企业应用程序集成和 Web Services 的基本概念。</span><span class="sxs-lookup"><span data-stu-id="c30be-118">It also assumes that you understand basic concepts about enterprise application integration and web services.</span></span>  
  
 <span data-ttu-id="c30be-119">此外，若要阅读并遵循开发人员文档，你应熟悉如何使用生成应用程序[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]和执行以下任务： 创建项目、 设置引用，调试和测试 BizTalk解决方案。</span><span class="sxs-lookup"><span data-stu-id="c30be-119">In addition, to read and follow the developer documentation, you should be familiar with how to build applications by using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and with performing the following tasks: creating projects, setting references, and debugging and testing BizTalk solutions.</span></span>  
  
## <a name="credit-card-reporting-at-woodgrove-bank"></a><span data-ttu-id="c30be-120">Woodgrove Bank 的信用卡报告</span><span class="sxs-lookup"><span data-stu-id="c30be-120">Credit Card Reporting at Woodgrove Bank</span></span>  
 <span data-ttu-id="c30be-121">面向服务的结构解决方案示例是 Woodgrove Bank 的信用卡余额报告服务。</span><span class="sxs-lookup"><span data-stu-id="c30be-121">The service oriented architecture solution is a credit card balance reporting service for Woodgrove Bank.</span></span> <span data-ttu-id="c30be-122">尽管银行都是虚构的该方案不是-方案取决于实际的已部署的客户应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30be-122">Although the bank is fictional, the scenario is not—the scenario is based on an actual, deployed, customer application.</span></span>  
  
 <span data-ttu-id="c30be-123">在该方案中，对信用卡余额的请求来自两个来源：</span><span class="sxs-lookup"><span data-stu-id="c30be-123">In the scenario, requests for credit card balances come from two sources:</span></span>  
  
-   <span data-ttu-id="c30be-124">交互式语音应答 (IVR) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30be-124">An Interactive Voice Response (IVR) application.</span></span>  
  
-   <span data-ttu-id="c30be-125">交互式客户端，例如网页或自定义客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30be-125">An interactive client such as a web page or custom client application.</span></span>  
  
 <span data-ttu-id="c30be-126">该解决方案通过 MQSeries 接收来自 IVR 应用程序的请求。</span><span class="sxs-lookup"><span data-stu-id="c30be-126">The solution receives requests from the IVR application through MQSeries.</span></span> <span data-ttu-id="c30be-127">它通过使用 HTTP 和 SOAP 的 Web Services 处理来自交互式客户端的请求。</span><span class="sxs-lookup"><span data-stu-id="c30be-127">It handles requests from the interactive client through a web service using HTTP and SOAP.</span></span>  
  
 <span data-ttu-id="c30be-128">新的面向服务的结构应用程序通常需要使用采用早期技术的旧版应用程序，同时也需要使用现代应用程序，例如使用 Web Services 的网站。</span><span class="sxs-lookup"><span data-stu-id="c30be-128">New service oriented architecture applications often need to work with legacy applications that use older technologies, as well as function with modern applications such as web sites that consume web services.</span></span> <span data-ttu-id="c30be-129">方案模型此实际要求-IVR 应用程序表示旧的应用程序，客户服务客户端应用程序时，是现代。</span><span class="sxs-lookup"><span data-stu-id="c30be-129">The scenario models this real world requirement—the IVR application represents a legacy application, while the customer service client application, is the modern one.</span></span>  
  
 <span data-ttu-id="c30be-130">Woodgrove Bank 应用程序使用三个后端原有系统中的数据来响应请求：</span><span class="sxs-lookup"><span data-stu-id="c30be-130">The Woodgrove Bank application uses data from three backend, legacy systems to respond to requests:</span></span>  
  
-   <span data-ttu-id="c30be-131">一个提供信用总限额的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c30be-131">An application that provides the overall credit limit.</span></span> <span data-ttu-id="c30be-132">此应用程序为大型机上的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-132">This is a SAP system on a mainframe computer.</span></span>  
  
-   <span data-ttu-id="c30be-133">一个用于根据帐户来报告挂起事务总数的挂起事务系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-133">A pending transactions system that reports the total amount for transactions pending against the account.</span></span> <span data-ttu-id="c30be-134">此系统为大型机或 AS/400 系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-134">This system is a mainframe or AS/400 system.</span></span> <span data-ttu-id="c30be-135">该解决方案使用 Web Services 和 Microsoft Host Integration Server (HIS) 与大型机或 AS/400 系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="c30be-135">The solution uses a web service and Microsoft Host Integration Server (HIS) to communicate with the mainframe or AS/400 system.</span></span>  
  
-   <span data-ttu-id="c30be-136">一个付款跟踪系统，用于提供对系统进行的最近一次付款。</span><span class="sxs-lookup"><span data-stu-id="c30be-136">A payment tracking system that gives the last payment made to the system.</span></span> <span data-ttu-id="c30be-137">此付款跟踪系统可以使用 MQSeries 来实现。</span><span class="sxs-lookup"><span data-stu-id="c30be-137">The payment tracking system can be reached using MQSeries.</span></span>  
  
 <span data-ttu-id="c30be-138">在收集和编译了原有系统中的信息后，该解决方案会将响应发送回源应用程序，从而也将响应发送给客户。</span><span class="sxs-lookup"><span data-stu-id="c30be-138">After gathering and compiling the information from the legacy systems, the solution sends the response back to the originating application and, thus, to the customer.</span></span>  
  
## <a name="business-requirements"></a><span data-ttu-id="c30be-139">业务需求</span><span class="sxs-lookup"><span data-stu-id="c30be-139">Business Requirements</span></span>  
 <span data-ttu-id="c30be-140">由于信用报告应用程序将实时响应客户请求，因此为了迅速处理这些请求，该应用程序必须具有低延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c30be-140">Because the credit reporting application responds in real time to customer requests, it must have low latency in order to handle requests quickly.</span></span> <span data-ttu-id="c30be-141">此外，它还必须能够同时处理大量的请求。</span><span class="sxs-lookup"><span data-stu-id="c30be-141">In addition, it must also be able to handle high numbers of simultaneous requests.</span></span> <span data-ttu-id="c30be-142">该解决方案将使用敏感信息和公共接口，因此安全性十分重要。</span><span class="sxs-lookup"><span data-stu-id="c30be-142">The solution uses sensitive information and a public interface so that security is significant concern.</span></span> <span data-ttu-id="c30be-143">最后，还需要确保服务可靠性。</span><span class="sxs-lookup"><span data-stu-id="c30be-143">Finally, the service needs to be reliable.</span></span>  
  
 <span data-ttu-id="c30be-144">有关的解决方案如何满足这些要求的信息，请参阅[开发一种服务面向解决方案](../core/developing-a-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="c30be-144">For information about how the solution meets these requirements, see [Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md).</span></span>  
  
## <a name="performance-characteristics"></a><span data-ttu-id="c30be-145">性能特征</span><span class="sxs-lookup"><span data-stu-id="c30be-145">Performance Characteristics</span></span>  
 <span data-ttu-id="c30be-146">为了满足上述业务需求，该方案具有以下性能特征：</span><span class="sxs-lookup"><span data-stu-id="c30be-146">To meet the business requirements, the scenario has the following performance characteristics:</span></span>  
  
-   <span data-ttu-id="c30be-147">每秒 40 个传入请求的持续吞吐量。</span><span class="sxs-lookup"><span data-stu-id="c30be-147">Sustained throughput of 40 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="c30be-148">每秒 100 个传入请求的峰值吞吐量。</span><span class="sxs-lookup"><span data-stu-id="c30be-148">Peak throughput of 100 incoming requests per second.</span></span>  
  
-   <span data-ttu-id="c30be-149">在 1000 毫秒内为 90% 的请求提供服务（在 BizTalk Server 内部和外部）。</span><span class="sxs-lookup"><span data-stu-id="c30be-149">90 percent of the requests to be serviced (in and out of BizTalk Server) in under 1000 milliseconds.</span></span>  
  
-   <span data-ttu-id="c30be-150">在 2000 毫秒内为 95% 的请求提供服务（在 BizTalk Server 内部和外部）。</span><span class="sxs-lookup"><span data-stu-id="c30be-150">95 percent of the requests to be serviced (in and out of BizTalk Server) in under 2000 milliseconds.</span></span>  
  
-   <span data-ttu-id="c30be-151">在 5000 毫秒内为 100% 的请求提供服务（在 BizTalk Server 内部和外部）。</span><span class="sxs-lookup"><span data-stu-id="c30be-151">100 percent of the requests to be serviced (in and out of BizTalk Server) in under 5000 milliseconds.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c30be-152">这些时间不包括后端系统的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c30be-152">These times do not include the latency times of the back end systems.</span></span>  
  
## <a name="three-versions-of-the-solution"></a><span data-ttu-id="c30be-153">解决方案的三个版本</span><span class="sxs-lookup"><span data-stu-id="c30be-153">Three Versions of the Solution</span></span>  
 <span data-ttu-id="c30be-154">该解决方案具有以下三个版本：</span><span class="sxs-lookup"><span data-stu-id="c30be-154">There are three versions of the solution:</span></span>  
  
-   <span data-ttu-id="c30be-155">存根版本使用软件存根替换所有的后端系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-155">The stub version replaces all of the backend systems with software stubs.</span></span> <span data-ttu-id="c30be-156">这些存根模拟后端系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-156">The stubs simulate the backend systems.</span></span> <span data-ttu-id="c30be-157">使用此版本，可以在单台计算机上快速部署和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="c30be-157">This version provides a quick way to deploy and run the solution on a single computer.</span></span>  
  
-   <span data-ttu-id="c30be-158">适配器版本使用 BizTalk 适配器来连接到后端系统。</span><span class="sxs-lookup"><span data-stu-id="c30be-158">The adapter version uses BizTalk adapters to connect to the backend systems.</span></span> <span data-ttu-id="c30be-159">此版本是实施解决方案时首先考虑使用的版本。</span><span class="sxs-lookup"><span data-stu-id="c30be-159">This version is how one might first think to implement the solution.</span></span> <span data-ttu-id="c30be-160">但是，如果使用适配器向后端系统发送消息，则在获取响应时会有较高的延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c30be-160">However, sending messages to the backend systems using the adapters introduces significant latency in getting back responses.</span></span> <span data-ttu-id="c30be-161">尽管适配器自身只会造成很短的延迟，但 BizTalk Server 的分布式结构要求适配器与使用 MessageBox 的业务流程主机实例进行通信。</span><span class="sxs-lookup"><span data-stu-id="c30be-161">While adapters by themselves could offer very low latency, the distributed architecture of BizTalk Server requires adapters to communicate with the orchestration host instances using the message box.</span></span> <span data-ttu-id="c30be-162">这会导致消息在适配器与该数据库之间往返，从而影响延迟时间。</span><span class="sxs-lookup"><span data-stu-id="c30be-162">This introduces round trips to the database and affects latency times.</span></span>  
  
-   <span data-ttu-id="c30be-163">内联版本使用与后端系统直接进行通信的内联代码来替换适配器。</span><span class="sxs-lookup"><span data-stu-id="c30be-163">The inline version replaces the adapters with inline code that communicates directly with the backend systems.</span></span> <span data-ttu-id="c30be-164">解决方案的内联版本具有最低的延迟时间和最高的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="c30be-164">The inline version of the solution has the lowest latency and the highest throughput.</span></span>  
  
 <span data-ttu-id="c30be-165">部署指南为生成和部署该解决方案的上述三个版本提供了指导信息，并且在每个版本中都提供了模拟通过 HIS 连接到挂起事务系统的方法。</span><span class="sxs-lookup"><span data-stu-id="c30be-165">The deployment guide provides directions for building and deploying all three versions of the solution, as well as providing a way, in each version, to simulate the connection through HIS to the pending transactions system.</span></span> <span data-ttu-id="c30be-166">有关构建和部署解决方案的信息，请参阅[部署服务面向解决方案](../core/deploying-the-service-oriented-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="c30be-166">For information about building and deploying the solution, see [Deploying the Service Oriented Solution](../core/deploying-the-service-oriented-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c30be-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c30be-167">See Also</span></span>  
 [<span data-ttu-id="c30be-168">面向服务的解决方案</span><span class="sxs-lookup"><span data-stu-id="c30be-168">Service Oriented Solution</span></span>](../core/service-oriented-solution.md)