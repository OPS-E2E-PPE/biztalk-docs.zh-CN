---
title: "Microsoft BizTalk ESB 工具包 |Microsoft 文档"
description: "简介、 常见方案和 BizTalk Server 中的 ESB 工具包的组件"
caps.latest.revision: "14"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: 1763ed4bb7f090b91565c3a5f5f480d2c081b48c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="2072a-103">Microsoft BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-103">Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="2072a-104">![BizTalk ESB 工具包徽标](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span><span class="sxs-lookup"><span data-stu-id="2072a-104">![BizTalk ESB Toolkit Logo](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="2072a-105">摘要</span><span class="sxs-lookup"><span data-stu-id="2072a-105">Summary</span></span>  
 <span data-ttu-id="2072a-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]以支持松散耦合的消息传递体系结构。</span><span class="sxs-lookup"><span data-stu-id="2072a-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="2072a-107">BizTalk Server 包含一个用于消息传送应用程序的强大发布/订阅机制，该机制通过创建和填充订阅进行运作，从而为面向服务的体系结构 (SOA) 应用程序提供一个高效的可扩展平台。</span><span class="sxs-lookup"><span data-stu-id="2072a-107">BizTalk Server includes a powerful publish/subscribe mechanism for messaging applications that works by creating and filling subscriptions, which provides a highly efficient and scalable platform for service-oriented architecture (SOA) applications.</span></span>  
  
 <span data-ttu-id="2072a-108">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展 BizTalk Server 提供一系列上构建强大、 连接、 面向服务的应用程序包含为轻型服务基于路线的服务调用的已设定焦点的新功能的功能组合、 动态解析终结点以及图、 Web 服务和 WS-* 集成、 错误管理和报告和与第三方 SOA 管理解决方案的集成。</span><span class="sxs-lookup"><span data-stu-id="2072a-108">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications that incorporate itinerary-based service invocation for lightweight service composition, dynamic resolution of endpoints and maps, Web service and WS-* integration, fault management and reporting, and integration with third-party SOA governance solutions.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="2072a-109">概述</span><span class="sxs-lookup"><span data-stu-id="2072a-109">Overview</span></span>  
 <span data-ttu-id="2072a-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供体系结构指南、 模式和 BizTalk Server 和.NET Framework 组件，以便简化的开发在 Microsoft 平台上企业服务总线 (ESB) 的并可让 Microsoft 客户扩展的集合他们自己的消息传送和集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="2072a-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns, and a collection of BizTalk Server and .NET Framework components to simplify the development of an Enterprise Service Bus (ESB) on the Microsoft platform and to allow Microsoft customers to extend their own messaging and integration solutions.</span></span>  
  
## <a name="common-scenarios"></a><span data-ttu-id="2072a-111">常见方案</span><span class="sxs-lookup"><span data-stu-id="2072a-111">Common Scenarios</span></span>  
 <span data-ttu-id="2072a-112">在实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中，Enterprise Service Bus (ESB) 这一术语被广泛使用。</span><span class="sxs-lookup"><span data-stu-id="2072a-112">The term Enterprise Service Bus (ESB) is widely used in the context of implementing an infrastructure for enabling a service-oriented architecture (SOA).</span></span> <span data-ttu-id="2072a-113">但部署 SOA 的实际经验表明，ESB 仅仅是组成全面面向服务的基础结构 (SOI) 的众多构建块中的一个。</span><span class="sxs-lookup"><span data-stu-id="2072a-113">However, real-world experience with the deployment of SOAs has shown that an ESB is only one of many building blocks that make up a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="2072a-114">ESB 术语的含义发生了一些不同方向的变化，其定义取决于各个 ESB 和集成平台供应商的解释，以及特定 SOA 计划的要求。</span><span class="sxs-lookup"><span data-stu-id="2072a-114">The term ESB has morphed in a number of different directions, and its definition depends on the interpretation of individual ESB and integration platform vendors and on the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="2072a-115">依据 Microsoft 从众多成功的实际 SOI 实现收集的经验，你可以将 ESB 看作是基于传统企业应用程序集成 (EAI)、面向消息的中间件、Web 服务、.NET 和 Java 互操作性、主机系统集成以及与服务注册表和资产储存库的互操作性的一组体系结构模型。</span><span class="sxs-lookup"><span data-stu-id="2072a-115">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, you can think of an ESB as a collection of architectural patterns based on traditional enterprise application integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span>  
  
 <span data-ttu-id="2072a-116">图 1 显示的一种 ESB 体系结构可以提供间的相互连接的高级视图。</span><span class="sxs-lookup"><span data-stu-id="2072a-116">Figure 1 shows a high-level view of the type of interconnectivity that an ESB architecture can provide.</span></span>  
  
 <span data-ttu-id="2072a-117">![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="2072a-117">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="2072a-118">**图 1**</span><span class="sxs-lookup"><span data-stu-id="2072a-118">**Figure 1**</span></span>  
  
 <span data-ttu-id="2072a-119">**提供的连接的高级示例的企业服务总线体系结构**</span><span class="sxs-lookup"><span data-stu-id="2072a-119">**A high-level example of the connectivity provided the Enterprise Service Bus architecture**</span></span>  
  
## <a name="audience-requirements"></a><span data-ttu-id="2072a-120">受众要求</span><span class="sxs-lookup"><span data-stu-id="2072a-120">Audience Requirements</span></span>  
 <span data-ttu-id="2072a-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]适用于开发人员创建 Microsoft BizTalk Server 解决方案或使用其他解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件。</span><span class="sxs-lookup"><span data-stu-id="2072a-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is intended for developers who create Microsoft BizTalk Server solutions or other solutions that use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components.</span></span> <span data-ttu-id="2072a-122">若要充分利用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，开发人员应拥有知识和体验替换为以下工作：</span><span class="sxs-lookup"><span data-stu-id="2072a-122">To take full advantage of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], developers should possess knowledge and experience working with the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
-   <span data-ttu-id="2072a-123">Microsoft .NET 开发技术，包括开发 ASP.NET Web 服务和 .NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="2072a-123">Microsoft .NET development techniques, including the development of ASP.NET Web services and .NET Framework components</span></span>  
  
## <a name="design-goals"></a><span data-ttu-id="2072a-124">设计目标</span><span class="sxs-lookup"><span data-stu-id="2072a-124">Design Goals</span></span>  
 <span data-ttu-id="2072a-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持和实现松散耦合的消息传递环境，它使更轻松地生成基于消息的企业应用程序的组件进行互操作的一系列组成。</span><span class="sxs-lookup"><span data-stu-id="2072a-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a series of interoperating components that support and implement a loosely coupled messaging environment that makes it easier to build message-based enterprise applications.</span></span> <span data-ttu-id="2072a-126">服务和组件自然地划分为以下的七种类别：</span><span class="sxs-lookup"><span data-stu-id="2072a-126">The services and components fall naturally into the following seven categories:</span></span>  
  
-   <span data-ttu-id="2072a-127">**Web 服务**： 这些公开内部服务，例如路线处理，异常管理终结点和地图、 BizTalk 服务器操作和消息转换的分辨率。</span><span class="sxs-lookup"><span data-stu-id="2072a-127">**Web services** : These expose internal services such as itinerary processing, exception management, resolution of endpoints and maps, BizTalk Server operations, and message transformation.</span></span>  
  
-   <span data-ttu-id="2072a-128">**路线服务**： 其中包括用于执行基于路线的路由的基于业务流程和基于消息的服务[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2072a-128">**Itinerary services** : These include orchestration-based and messaging-based services for performing itinerary-based routing for [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="2072a-129">你可以创建用于路线基于路由的自定义服务。</span><span class="sxs-lookup"><span data-stu-id="2072a-129">You can create custom services for itinerary-based routing.</span></span>  
  
-   <span data-ttu-id="2072a-130">**路线上的渐变。**</span><span class="sxs-lookup"><span data-stu-id="2072a-130">**Itinerary on-ramps.**</span></span> <span data-ttu-id="2072a-131">这些接收外部消息、 附加相应路线每条消息，并执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。</span><span class="sxs-lookup"><span data-stu-id="2072a-131">These receive external messages, attach the appropriate itinerary for each message, and perform itinerary processing; they use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
-   <span data-ttu-id="2072a-132">**上渐变**： 这些格式和传输协议，如 HTTP、 JMS、 WMQ、 FTP、 平面文件和 XML 的一系列中接收外部的消息。</span><span class="sxs-lookup"><span data-stu-id="2072a-132">**On-ramps** : These receive external messages in a range of formats and transports, such as HTTP, JMS, WMQ, FTP, Flat File, and XML.</span></span> <span data-ttu-id="2072a-133">它们是典型的 BizTalk Server 接收 （可选） 使用的位置[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态解析终结点以及元数据适配器提供程序框架。</span><span class="sxs-lookup"><span data-stu-id="2072a-133">They are typical BizTalk Server receive locations that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
-   <span data-ttu-id="2072a-134">**关闭渐变**： 这些实现使用的格式和传输如 SOAP、 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息的传递的发送端口。</span><span class="sxs-lookup"><span data-stu-id="2072a-134">**Off-ramps** : These implement send ports for the delivery of messages using formats and transports such as SOAP, WCF, JMS, WMQ, FTP, HTTP, Flat File, XML, or any other custom formats.</span></span> <span data-ttu-id="2072a-135">它们是典型的 BizTalk Server 动态发送端口的是直接绑定到消息框和 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]解析器和用于动态终结点解析适配器提供程序框架和元数据。</span><span class="sxs-lookup"><span data-stu-id="2072a-135">They are typical BizTalk Server dynamic send ports that are direct-bound to the Message Box and that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
-   <span data-ttu-id="2072a-136">**异常 Management Framework** ： 这包括异常 Web 服务，异常管理 API，以及丰富，组件处理，并将异常详细信息传递到 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="2072a-136">**Exception Management Framework** : This includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
-   <span data-ttu-id="2072a-137">**ESB 管理门户**： 这将提供注册表设置、 异常中介，警报通知和分析。</span><span class="sxs-lookup"><span data-stu-id="2072a-137">**ESB Management Portal** : This provides registry provisioning, exception mediation, alert notification, and analytics.</span></span>  
  
 <span data-ttu-id="2072a-138">这些组件和服务的许多依赖于由实现的功能[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，如业务流程、 转换和业务规则引擎和消息框数据库。</span><span class="sxs-lookup"><span data-stu-id="2072a-138">Many of these components and services rely on features implemented by [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], such as the Orchestration, Transformation, and Business Rules engines and the Message Box database.</span></span> <span data-ttu-id="2072a-139">图 2 显示类别; 的示意图组件和服务通常发生在每个类别;和使用的核心 BizTalk Server 系统组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2072a-139">Figure 2 shows a schematic view of the categories; the components and services typically occurring within each category; and the core BizTalk Server system components used by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
 <span data-ttu-id="2072a-140">![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span><span class="sxs-lookup"><span data-stu-id="2072a-140">![ESB Architecture](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span></span>  
  
 <span data-ttu-id="2072a-141">**图 2**</span><span class="sxs-lookup"><span data-stu-id="2072a-141">**Figure 2**</span></span>  
  
 <span data-ttu-id="2072a-142">**体系结构和组件[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="2072a-142">**The architecture and components of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span></span>  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a><span data-ttu-id="2072a-143">BizTalk ESB 工具包的工作原理</span><span class="sxs-lookup"><span data-stu-id="2072a-143">How the BizTalk ESB Toolkit Works</span></span>  
 <span data-ttu-id="2072a-144">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息，并对它们，可能 （但不是总是） 通过执行如转换、 传递或任何其他自定义定义的进程的进程。</span><span class="sxs-lookup"><span data-stu-id="2072a-144">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] accepts inbound messages and operates on them, perhaps (but not always) by performing processes such as transformation, delivery, or any other custom defined process.</span></span> <span data-ttu-id="2072a-145">为了指定所需的操作，核心处理组件要求消息包含相关说明或元数据，这些说明或元数据定义要使用消息内容应用的进程和执行的任务。</span><span class="sxs-lookup"><span data-stu-id="2072a-145">To specify the operations required, the core processing components require a message to contain associated instructions or metadata that define the processes to apply and the tasks to execute with the message content.</span></span>  
  
 <span data-ttu-id="2072a-146">此方法提供服务; 之间的松散耦合这意味着 ESB 不需要为每个消息事先了解特定的处理。</span><span class="sxs-lookup"><span data-stu-id="2072a-146">This approach provides loose coupling between services; this means that the ESB does not require prior knowledge of the specific processing for each message.</span></span> <span data-ttu-id="2072a-147">它只须了解可能的进程范围和如何应用各进程。</span><span class="sxs-lookup"><span data-stu-id="2072a-147">It just has to know the possible range of processes and how to apply each process.</span></span> <span data-ttu-id="2072a-148">用于指定可用进程及进程与消息中说明间映射的选项众多，它们提供了一个配置和调整行为的灵活机制，不需要更改代码和重新部署组件。</span><span class="sxs-lookup"><span data-stu-id="2072a-148">The wide range of options for specifying the available processes and the mapping between the processes and the instructions within messages provides a flexible mechanism for configuring and adjusting behavior, without requiring changes to code and redeployment of components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2072a-149">在本节中</span><span class="sxs-lookup"><span data-stu-id="2072a-149">In this section</span></span>

- [<span data-ttu-id="2072a-150">安装和配置 Microsoft BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-150">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [<span data-ttu-id="2072a-151">BizTalk ESB 工具包简介</span><span class="sxs-lookup"><span data-stu-id="2072a-151">Introduction to the BizTalk ESB Toolkit</span></span>](introduction-to-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="2072a-152">入门和了解 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-152">Getting started and understanding the BizTalk ESB Toolkit</span></span>](getting-started-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="2072a-153">重要的方案和开发任务</span><span class="sxs-lookup"><span data-stu-id="2072a-153">Key scenarios and development tasks</span></span>](key-scenarios-and-development-tasks.md)

- [<span data-ttu-id="2072a-154">创建使用路线设计器的路线</span><span class="sxs-lookup"><span data-stu-id="2072a-154">Creating itineraries using itinerary designer</span></span>](creating-itineraries-using-itinerary-designer.md)

- [<span data-ttu-id="2072a-155">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="2072a-155">BizTalk ESB Toolkit sample applications</span></span>](biztalk-esb-toolkit-sample-applications.md)

- [<span data-ttu-id="2072a-156">修改和扩展 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-156">Modifying and extending the BizTalk ESB Toolkit</span></span>](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="2072a-157">管理 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-157">Administration with the BizTalk ESB Toolkit</span></span>](administration-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="2072a-158">SOA 监管集成</span><span class="sxs-lookup"><span data-stu-id="2072a-158">SOA governance integration</span></span>](soa-governance-integration.md)

- [<span data-ttu-id="2072a-159">故障排除 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="2072a-159">Troubleshooting the BizTalk ESB Toolkit</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a><span data-ttu-id="2072a-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="2072a-160">Related topics</span></span>  
  
-   [<span data-ttu-id="2072a-161">面向 BizTalk 服务解决方案</span><span class="sxs-lookup"><span data-stu-id="2072a-161">BizTalk Service Oriented Solutions</span></span>](../core/service-oriented-solution.md)

- [<span data-ttu-id="2072a-162">与 BizTalk Server 中使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="2072a-162">Using Web Services with BizTalk Server</span></span>](../core/using-web-services.md)  