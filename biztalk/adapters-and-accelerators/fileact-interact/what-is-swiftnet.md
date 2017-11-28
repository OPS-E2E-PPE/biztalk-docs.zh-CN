---
title: "什么是 SWIFTNet？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2b074385-352c-40f4-b73e-1891c627aa4e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1668c1f568a6cfb853957b3598b41f1cbdf6e33
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-swiftnet"></a><span data-ttu-id="c53d9-103">什么是 SWIFTNet？</span><span class="sxs-lookup"><span data-stu-id="c53d9-103">What Is SWIFTNet?</span></span>
<span data-ttu-id="c53d9-104">作为一般用途，金融业的行业标准解决方案 SWIFTNet 提供全局财务社区参与的所有机构中的所有连接的应用程序的应用程序无关的、 单一窗口接口。</span><span class="sxs-lookup"><span data-stu-id="c53d9-104">As a general purpose, industry-standard solution for the financial industry, SWIFTNet provides an application-independent, single window interface to all the connected applications of all the institutions participating in the global financial community.</span></span> <span data-ttu-id="c53d9-105">实际的访问控制由业务策略决策的每个服务管理员，而不是基础结构的技术限制。</span><span class="sxs-lookup"><span data-stu-id="c53d9-105">Actual access is controlled by the business policy decisions of each Service Administrator, not by the technical limitations of the infrastructure.</span></span>  
  
 <span data-ttu-id="c53d9-106">SWIFTNet 为确保业务连续性和灾难恢复任务关键型跨机构边界的财务应用程序的基础结构奠定了基础。</span><span class="sxs-lookup"><span data-stu-id="c53d9-106">SWIFTNet provides a basis for assuring business continuity and disaster recovery for the infrastructure of mission-critical financial applications that cross institutional boundaries.</span></span> <span data-ttu-id="c53d9-107">SWIFTNet 旨在满足制度社区执行关键任务的财务软件解决方案的互操作性要求。</span><span class="sxs-lookup"><span data-stu-id="c53d9-107">SWIFTNet is designed to satisfy institutional community requirements for interoperability of mission-critical financial software solutions.</span></span>  
  
 <span data-ttu-id="c53d9-108">到互连的业务应用程序，SWIFTNet 提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="c53d9-108">To interconnected business applications, SWIFTNet provides the following:</span></span>  
  
-   <span data-ttu-id="c53d9-109">基础结构可靠性保证</span><span class="sxs-lookup"><span data-stu-id="c53d9-109">Assurance of infrastructure reliability</span></span>  
  
-   <span data-ttu-id="c53d9-110">可用性</span><span class="sxs-lookup"><span data-stu-id="c53d9-110">Availability</span></span>  
  
-   <span data-ttu-id="c53d9-111">基于角色的和非基于角色的访问控制</span><span class="sxs-lookup"><span data-stu-id="c53d9-111">Role-based and non-role-based access control</span></span>  
  
-   <span data-ttu-id="c53d9-112">通信和消息身份验证</span><span class="sxs-lookup"><span data-stu-id="c53d9-112">Correspondent and message authentication</span></span>  
  
-   <span data-ttu-id="c53d9-113">消息的完整性</span><span class="sxs-lookup"><span data-stu-id="c53d9-113">Message integrity</span></span>  
  
-   <span data-ttu-id="c53d9-114">保密性</span><span class="sxs-lookup"><span data-stu-id="c53d9-114">Confidentiality</span></span>  
  
-   <span data-ttu-id="c53d9-115">不可否认性支持</span><span class="sxs-lookup"><span data-stu-id="c53d9-115">Non-repudiation support</span></span>  
  
-   <span data-ttu-id="c53d9-116">消息验证</span><span class="sxs-lookup"><span data-stu-id="c53d9-116">Message validation</span></span>  
  
-   <span data-ttu-id="c53d9-117">存储和转发</span><span class="sxs-lookup"><span data-stu-id="c53d9-117">Store and-forward</span></span>  

<span data-ttu-id="c53d9-118">SWIFTNet 使用**SWIFTNet 链接**(SNL) 作为到 SWIFTNet 服务，并使用了应用程序编程接口**SWIFTAlliance 网关**连接和可用性。</span><span class="sxs-lookup"><span data-stu-id="c53d9-118">SWIFTNet uses **SWIFTNet Link** (SNL) as the application programming interface to the SWIFTNet services, and uses the **SWIFTAlliance Gateway** for connectivity and usability.</span></span> <span data-ttu-id="c53d9-119">有关本主题中的这些资源的更多信息。</span><span class="sxs-lookup"><span data-stu-id="c53d9-119">Read more about these resources in this topic.</span></span>

## <a name="swiftnet-link-overview"></a><span data-ttu-id="c53d9-120">SWIFTNet 链接概述</span><span class="sxs-lookup"><span data-stu-id="c53d9-120">SWIFTNet Link overview</span></span>

<span data-ttu-id="c53d9-121">商业软件应用程序使用 SWIFTNet 链接 (SNL) 应用程序编程接口 (API) 访问和使用 SWIFTNet 服务。</span><span class="sxs-lookup"><span data-stu-id="c53d9-121">Business software applications use the SWIFTNet Link (SNL) application programming interface (API) to access and use SWIFTNet services.</span></span> <span data-ttu-id="c53d9-122">SNL 是 SWIFTNet 的必需的网络接口。</span><span class="sxs-lookup"><span data-stu-id="c53d9-122">The SNL is the mandatory network interface to SWIFTNet.</span></span> <span data-ttu-id="c53d9-123">SWIFTNet 所有外部接口的要求 SNL。</span><span class="sxs-lookup"><span data-stu-id="c53d9-123">SWIFTNet requires SNL for all external interfaces.</span></span> <span data-ttu-id="c53d9-124">SNL 还包括支持消息传送、 安全性和服务管理功能的后台进程。</span><span class="sxs-lookup"><span data-stu-id="c53d9-124">The SNL also includes background processes that support messaging, security, and service management functions.</span></span> <span data-ttu-id="c53d9-125">SNL 并入 SWIFTAlliance WebStation 和 SWIFTAlliance 网关 （压降）。</span><span class="sxs-lookup"><span data-stu-id="c53d9-125">The SNL is incorporated into SWIFTAlliance WebStation and SWIFTAlliance Gateway (SAG).</span></span>  
  
 <span data-ttu-id="c53d9-126">SNL 松散耦合的客户端/服务器之间建立关系业务应用程序组件。</span><span class="sxs-lookup"><span data-stu-id="c53d9-126">SNL establishes a loosely coupled client/server relationship between business application components.</span></span> <span data-ttu-id="c53d9-127">而不是直接调用方法或函数，交互是面向消息的： 客户端和服务器之间传递结构化的消息。</span><span class="sxs-lookup"><span data-stu-id="c53d9-127">Instead of directly invoking methods or functions, the interaction is message-oriented: structured messages are passed between client and server.</span></span> <span data-ttu-id="c53d9-128">业务应用程序通常用于 SWIFTNet 服务包含一组客户端和服务器。</span><span class="sxs-lookup"><span data-stu-id="c53d9-128">A business application designed for SWIFTNet services generally consists of a set of clients and servers.</span></span> <span data-ttu-id="c53d9-129">同一个客户端或相同的服务器进程可以启动多次。</span><span class="sxs-lookup"><span data-stu-id="c53d9-129">The same client or the same server process can be started multiple times.</span></span> <span data-ttu-id="c53d9-130">请注意，你无法预测到的进程将直接发送的同一个应用程序的传入消息请求的实例。</span><span class="sxs-lookup"><span data-stu-id="c53d9-130">Note that you cannot predict to which process instance of the same application an incoming message request will be delivered.</span></span> <span data-ttu-id="c53d9-131">在客户端进程内的多个线程可以调用 SwCall API 函数。</span><span class="sxs-lookup"><span data-stu-id="c53d9-131">Multiple threads within a client process can invoke the SwCall API function.</span></span> <span data-ttu-id="c53d9-132">服务器进程可以拥有多个线程也;但是，只有一个线程可以调用 SwCallback。</span><span class="sxs-lookup"><span data-stu-id="c53d9-132">A server process can have multiple threads as well; however, only one thread can invoke SwCallback.</span></span> <span data-ttu-id="c53d9-133">客户端和服务器进程不能组合相同的进程中。</span><span class="sxs-lookup"><span data-stu-id="c53d9-133">Client and server processes cannot be combined in the same process.</span></span>  
  
 <span data-ttu-id="c53d9-134">SNL 提供了一套专为高可用性和高吞吐量环境设计的传输级功能。</span><span class="sxs-lookup"><span data-stu-id="c53d9-134">SNL provides a set of transport-level features designed for high availability and high throughput environments.</span></span> <span data-ttu-id="c53d9-135">这些功能包括：</span><span class="sxs-lookup"><span data-stu-id="c53d9-135">These features include:</span></span>  
  
-   <span data-ttu-id="c53d9-136">负载平衡</span><span class="sxs-lookup"><span data-stu-id="c53d9-136">Load balancing</span></span>  
  
-   <span data-ttu-id="c53d9-137">位置透明度和路由、 屏蔽从基础传输技术的应用程序组件</span><span class="sxs-lookup"><span data-stu-id="c53d9-137">Location transparency and routing, shielding application components from the underlying transport technology</span></span>  
  
-   <span data-ttu-id="c53d9-138">传输级身份验证和保密性，打包在 SNL，以透明方式提供给应用程序</span><span class="sxs-lookup"><span data-stu-id="c53d9-138">Transport-level authentication and confidentiality, packaged within SNL and provided transparently to the application</span></span>  
  
-   <span data-ttu-id="c53d9-139">安全函数由哪些业务应用程序软件可能需要建立端到端安全性 （对用户应用程序是用户应用程序） 上，在需要时。</span><span class="sxs-lookup"><span data-stu-id="c53d9-139">Security functions by which business application software may establish end-to-end security (user application to user application), when required.</span></span>  
  
 <span data-ttu-id="c53d9-140">在源代码级使用 c + + 或 Java 进行编程，方面有只有两个函数： SwCall 和 SwCallback。</span><span class="sxs-lookup"><span data-stu-id="c53d9-140">In terms of programming at the source code level using C++ or Java, there are only two functions: SwCall and SwCallback.</span></span> <span data-ttu-id="c53d9-141">SwCall 客户端应用程序用于通过 SWIFTNet 访问服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="c53d9-141">SwCall is used by client applications to access server applications through SWIFTNet.</span></span> <span data-ttu-id="c53d9-142">服务器应用程序使用 SwCallback 以响应客户端通过 SWIFTNet。</span><span class="sxs-lookup"><span data-stu-id="c53d9-142">SwCallback is used by server applications to respond to clients through SWIFTNet.</span></span>  
  
 <span data-ttu-id="c53d9-143">SwCall 和 SwCallback 函数通过传递结构化的 XML 消息传入和传出 SWIFTNet 访问 SWIFTNet 的功能。</span><span class="sxs-lookup"><span data-stu-id="c53d9-143">The SwCall and SwCallback functions access the functionality of SWIFTNet by passing structured XML messages to and from SWIFTNet.</span></span> <span data-ttu-id="c53d9-144">在运行时 SNL 包括这两个软件库-作为业务应用程序客户端或服务器进程的同一个地址空间内执行的代码-和运行在其自己的独立进程 （守护程序或服务） 中，地址空间。</span><span class="sxs-lookup"><span data-stu-id="c53d9-144">At run-time, SNL includes both software libraries — the code of which executes within the same address space as business application client or server processes — and independent processes (daemons or services), which run in their own address spaces.</span></span> <span data-ttu-id="c53d9-145">软件库是可通过 SNL Api 访问。</span><span class="sxs-lookup"><span data-stu-id="c53d9-145">The software libraries are accessible through the SNL APIs.</span></span>  

## <a name="swiftalliance-gateway-overview"></a><span data-ttu-id="c53d9-146">SWIFTAlliance 网关概述</span><span class="sxs-lookup"><span data-stu-id="c53d9-146">SWIFTAlliance Gateway overview</span></span>
  
<span data-ttu-id="c53d9-147">SWIFTAlliance 网关 （压降） 是 SWIFTNet 接口产品。</span><span class="sxs-lookup"><span data-stu-id="c53d9-147">The SWIFTAlliance Gateway (SAG) is an interface product for SWIFTNet.</span></span> <span data-ttu-id="c53d9-148">它融合了 SWIFTNet 链接的所有功能。</span><span class="sxs-lookup"><span data-stu-id="c53d9-148">It incorporates all the functionality of the SWIFTNet Link.</span></span> <span data-ttu-id="c53d9-149">此外，它提供几个不同的连接和可用性功能用于 SWIFTNet 用户，提供集成问题的各种系统的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c53d9-149">Additionally, it provides several different connectivity and usability features for SWIFTNet users, providing solutions to a variety of system integration problems.</span></span>  
  
 <span data-ttu-id="c53d9-150">压降支持几个不同的操作模式。</span><span class="sxs-lookup"><span data-stu-id="c53d9-150">The SAG supports several different modes of operation.</span></span> <span data-ttu-id="c53d9-151">其中一种，严格 SWIFTNet 链接模式，是专门针对 for SWIFT FileAct 和交互适配器。</span><span class="sxs-lookup"><span data-stu-id="c53d9-151">One of these, the strict SWIFTNet Link Mode, is particularly relevant to the FileAct and InterAct adapters for SWIFT.</span></span> <span data-ttu-id="c53d9-152">在严格 SWIFTNet 链接模式下，压降显示功能上等效于 SWIFTNet 链接接口述在所有这些主题的消息传递接口。</span><span class="sxs-lookup"><span data-stu-id="c53d9-152">In strict SWIFTNet Link Mode, the SAG presents a messaging interface that is functionally equivalent to the SWIFTNet Link interface as it is described throughout these topics.</span></span>  
  
 <span data-ttu-id="c53d9-153">压降用作消息集中器。</span><span class="sxs-lookup"><span data-stu-id="c53d9-153">The SAG serves as a message concentrator.</span></span> <span data-ttu-id="c53d9-154">它与其他各种应用程序接收消息，并将它们传递通过 SWIFTNet。</span><span class="sxs-lookup"><span data-stu-id="c53d9-154">It receives messages from various other applications and passes them through SWIFTNet.</span></span> <span data-ttu-id="c53d9-155">它将接收这些消息通过主机适配器，包括 WebSphere MQ 主机适配器，从而使业务应用程序运行在各种不同类型的计算平台上为将通过 SWIFTNet 的消息传递。</span><span class="sxs-lookup"><span data-stu-id="c53d9-155">It receives these messages through host adapters, including a WebSphere MQ host adapter, which enables business applications running on a variety of different types of computing platforms to pass messages through SWIFTNet.</span></span>  
 
 ## <a name="next-reading"></a><span data-ttu-id="c53d9-156">下一步读取</span><span class="sxs-lookup"><span data-stu-id="c53d9-156">Next reading</span></span>
 
 [<span data-ttu-id="c53d9-157">什么是 FileAct 适配器？</span><span class="sxs-lookup"><span data-stu-id="c53d9-157">What Is the FileAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-fileact-adapter.md)  
 [<span data-ttu-id="c53d9-158">什么是交互适配器？</span><span class="sxs-lookup"><span data-stu-id="c53d9-158">What Is the InterAct Adapter?</span></span>](../../adapters-and-accelerators/fileact-interact/what-is-the-interact-adapter.md)  
 [<span data-ttu-id="c53d9-159">BizTalk FileAct 和交互适配器端到端教程</span><span class="sxs-lookup"><span data-stu-id="c53d9-159">BizTalk FileAct and InterAct Adapters End-to-End Tutorial</span></span>](../../adapters-and-accelerators/fileact-interact/biztalk-fileact-and-interact-adapters-end-to-end-tutorial.md)
 
 ## <a name="see-also"></a><span data-ttu-id="c53d9-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c53d9-160">See also</span></span>
 [<span data-ttu-id="c53d9-161">了解 FileAct 和交互适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="c53d9-161">Understanding FileAct and InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md)