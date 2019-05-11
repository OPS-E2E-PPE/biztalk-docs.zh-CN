---
title: Microsoft BizTalk ESB 工具包 |Microsoft Docs
description: 简介、 常见的方案，以及 BizTalk Server 中的 ESB 工具包组件
caps.latest.revision: 14
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17ffaebc-7e33-4de8-8e94-109cd5d16ca0
ms.author: mandia
ms.openlocfilehash: 67c81f787d71cddee3962021f574342058edfa4a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400098"
---
# <a name="microsoft-biztalk-esb-toolkit"></a><span data-ttu-id="6d795-103">Microsoft BizTalk ESB Toolkit</span><span class="sxs-lookup"><span data-stu-id="6d795-103">Microsoft BizTalk ESB Toolkit</span></span>
<span data-ttu-id="6d795-104">![BizTalk ESB 工具包徽标](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span><span class="sxs-lookup"><span data-stu-id="6d795-104">![BizTalk ESB Toolkit Logo](../esb-toolkit/media/biztalkesbtoolkitlogo.gif "BizTalkESBToolkitLogo")</span></span>  
  
## <a name="summary"></a><span data-ttu-id="6d795-105">总结</span><span class="sxs-lookup"><span data-stu-id="6d795-105">Summary</span></span>  
 <span data-ttu-id="6d795-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]来支持松散耦合的消息传递体系结构。</span><span class="sxs-lookup"><span data-stu-id="6d795-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] uses [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] to support a loosely coupled messaging architecture.</span></span> <span data-ttu-id="6d795-107">BizTalk Server 包含的强大发布/订阅消息传送应用程序可通过创建和填充订阅机制，从而为面向服务的体系结构 (SOA) 应用程序提供高度高效、 可缩放的平台。</span><span class="sxs-lookup"><span data-stu-id="6d795-107">BizTalk Server includes a powerful publish/subscribe mechanism for messaging applications that works by creating and filling subscriptions, which provides a highly efficient and scalable platform for service-oriented architecture (SOA) applications.</span></span>  
  
 <span data-ttu-id="6d795-108">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]扩展了 BizTalk Server 能够提供各种新功能，专注于构建强大、 连接、 面向服务的整合为轻型服务基于路线的服务调用的应用程序的功能组合、 动态解析的终结点和地图，Web 服务和 WS-\* 集成、 故障管理和报告和与第三方 SOA 监管解决方案的集成。</span><span class="sxs-lookup"><span data-stu-id="6d795-108">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extends the functionality of BizTalk Server to provide a range of new capabilities focused on building robust, connected, service-oriented applications that incorporate itinerary-based service invocation for lightweight service composition, dynamic resolution of endpoints and maps, Web service and WS-\* integration, fault management and reporting, and integration with third-party SOA governance solutions.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="6d795-109">概述</span><span class="sxs-lookup"><span data-stu-id="6d795-109">Overview</span></span>  
 <span data-ttu-id="6d795-110">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供的体系结构指南、 模式和 BizTalk Server 和.NET Framework 组件以简化开发在 Microsoft 平台上的企业服务总线 (ESB) 并允许 Microsoft 客户可以扩展的集合他们自己的消息传送和集成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6d795-110">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides architectural guidance, patterns, and a collection of BizTalk Server and .NET Framework components to simplify the development of an Enterprise Service Bus (ESB) on the Microsoft platform and to allow Microsoft customers to extend their own messaging and integration solutions.</span></span>  
  
## <a name="common-scenarios"></a><span data-ttu-id="6d795-111">常见方案</span><span class="sxs-lookup"><span data-stu-id="6d795-111">Common Scenarios</span></span>  
 <span data-ttu-id="6d795-112">企业服务总线 (ESB) 广泛实现启用面向服务的体系结构 (SOA) 的基础结构的上下文中使用的术语。</span><span class="sxs-lookup"><span data-stu-id="6d795-112">The term Enterprise Service Bus (ESB) is widely used in the context of implementing an infrastructure for enabling a service-oriented architecture (SOA).</span></span> <span data-ttu-id="6d795-113">但是，部署 Soa 的实际经验表明，ESB 是进行了全面面向服务的基础结构 (SOI) 的多个构建基块之一。</span><span class="sxs-lookup"><span data-stu-id="6d795-113">However, real-world experience with the deployment of SOAs has shown that an ESB is only one of many building blocks that make up a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="6d795-114">术语的 ESB 越来越，具有相似通过多种不同的方向，并且其定义取决于各个 ESB 和集成平台供应商的解释以及特定 SOA 计划的要求。</span><span class="sxs-lookup"><span data-stu-id="6d795-114">The term ESB has morphed in a number of different directions, and its definition depends on the interpretation of individual ESB and integration platform vendors and on the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="6d795-115">基于已从许多成功的实际 SOI 实现收集了 Microsoft 的体验，您可以将 ESB 视为一系列体系结构模式基于传统的企业应用程序集成 (EAI)，面向消息的中间件，Web 服务、.NET 和 Java 互操作性、 主机系统集成和与服务注册表和资产储存库的互操作性。</span><span class="sxs-lookup"><span data-stu-id="6d795-115">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, you can think of an ESB as a collection of architectural patterns based on traditional enterprise application integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span>  
  
 <span data-ttu-id="6d795-116">图 1 显示了 ESB 体系结构可以提供间的相互连接的类型的高级视图。</span><span class="sxs-lookup"><span data-stu-id="6d795-116">Figure 1 shows a high-level view of the type of interconnectivity that an ESB architecture can provide.</span></span>  
  
 <span data-ttu-id="6d795-117">![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="6d795-117">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="6d795-118">**图 1**</span><span class="sxs-lookup"><span data-stu-id="6d795-118">**Figure 1**</span></span>  
  
 <span data-ttu-id="6d795-119">**提供的企业服务总线体系结构的连接的高级示例**</span><span class="sxs-lookup"><span data-stu-id="6d795-119">**A high-level example of the connectivity provided the Enterprise Service Bus architecture**</span></span>  
  
## <a name="audience-requirements"></a><span data-ttu-id="6d795-120">受众要求</span><span class="sxs-lookup"><span data-stu-id="6d795-120">Audience Requirements</span></span>  
 <span data-ttu-id="6d795-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]适用于开发人员创建 Microsoft BizTalk Server 解决方案或使用其他解决方案[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]组件。</span><span class="sxs-lookup"><span data-stu-id="6d795-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is intended for developers who create Microsoft BizTalk Server solutions or other solutions that use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] components.</span></span> <span data-ttu-id="6d795-122">若要充分利用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，开发人员应具备的知识和体验以下工作：</span><span class="sxs-lookup"><span data-stu-id="6d795-122">To take full advantage of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], developers should possess knowledge and experience working with the following:</span></span>  

- [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]

- [!INCLUDE[btsVStudioNoVersion_md](../includes/btsvstudionoversion-md.md)]
  
- <span data-ttu-id="6d795-123">Microsoft.NET 开发技术，包括 ASP.NET Web 服务和.NET Framework 组件的开发</span><span class="sxs-lookup"><span data-stu-id="6d795-123">Microsoft .NET development techniques, including the development of ASP.NET Web services and .NET Framework components</span></span>  
  
## <a name="design-goals"></a><span data-ttu-id="6d795-124">设计目标</span><span class="sxs-lookup"><span data-stu-id="6d795-124">Design Goals</span></span>  
 <span data-ttu-id="6d795-125">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]系列进行互操作支持和实现松散耦合的消息传送环境可简化构建基于消息的企业应用程序组件组成。</span><span class="sxs-lookup"><span data-stu-id="6d795-125">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] consists of a series of interoperating components that support and implement a loosely coupled messaging environment that makes it easier to build message-based enterprise applications.</span></span> <span data-ttu-id="6d795-126">服务和组件很自然地划分为以下七个类别：</span><span class="sxs-lookup"><span data-stu-id="6d795-126">The services and components fall naturally into the following seven categories:</span></span>  
  
- <span data-ttu-id="6d795-127">**Web 服务**:这些公开内部服务，例如路线处理，异常管理终结点和映射，BizTalk Server 操作和消息转换的解决方法。</span><span class="sxs-lookup"><span data-stu-id="6d795-127">**Web services** : These expose internal services such as itinerary processing, exception management, resolution of endpoints and maps, BizTalk Server operations, and message transformation.</span></span>  
  
- <span data-ttu-id="6d795-128">**路线服务**:其中包括用于执行基于路线的路由的基于业务流程和基于消息传送服务[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6d795-128">**Itinerary services** : These include orchestration-based and messaging-based services for performing itinerary-based routing for [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6d795-129">可以创建自定义基于路线的路由的服务。</span><span class="sxs-lookup"><span data-stu-id="6d795-129">You can create custom services for itinerary-based routing.</span></span>  
  
- <span data-ttu-id="6d795-130">**路线接入。**</span><span class="sxs-lookup"><span data-stu-id="6d795-130">**Itinerary on-ramps.**</span></span> <span data-ttu-id="6d795-131">这些接收外部消息、 附加为每个消息，适当的旅行计划和执行路线处理;它们使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。</span><span class="sxs-lookup"><span data-stu-id="6d795-131">These receive external messages, attach the appropriate itinerary for each message, and perform itinerary processing; they use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="6d795-132">**接入**:这些接收外部消息格式和传输，如 HTTP、 JMS、 WMQ、 FTP、 平面文件和 XML 的范围内。</span><span class="sxs-lookup"><span data-stu-id="6d795-132">**On-ramps** : These receive external messages in a range of formats and transports, such as HTTP, JMS, WMQ, FTP, Flat File, and XML.</span></span> <span data-ttu-id="6d795-133">它们是典型的 BizTalk Server 接收位置 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。</span><span class="sxs-lookup"><span data-stu-id="6d795-133">They are typical BizTalk Server receive locations that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="6d795-134">**接出点**:这些实现的发送端口使用的格式和传输如 SOAP、 WCF、 JMS、 WMQ、 FTP、 HTTP、 平面文件、 XML 或任何其他自定义格式的消息传递。</span><span class="sxs-lookup"><span data-stu-id="6d795-134">**Off-ramps** : These implement send ports for the delivery of messages using formats and transports such as SOAP, WCF, JMS, WMQ, FTP, HTTP, Flat File, XML, or any other custom formats.</span></span> <span data-ttu-id="6d795-135">它们是典型的 BizTalk Server 动态发送端口，是直接绑定到 Messagebox 和 （可选） 使用[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]互操作的管道组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]冲突解决程序和适配器提供程序框架，用于动态解析的终结点和元数据。</span><span class="sxs-lookup"><span data-stu-id="6d795-135">They are typical BizTalk Server dynamic send ports that are direct-bound to the Message Box and that optionally use the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] interop pipeline components and the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Resolver and Adapter Provider Framework for dynamic resolution of endpoints and metadata.</span></span>  
  
- <span data-ttu-id="6d795-136">**异常管理框架**:这包括异常 Web 服务、 异常管理 API，以及组件的丰富、 处理，并将异常详细信息传递到 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="6d795-136">**Exception Management Framework** : This includes the exception Web service, the exception management API, and components that enrich, process, and pass exception details to the ESB Management Portal.</span></span>  
  
- <span data-ttu-id="6d795-137">**ESB 管理门户**:这提供了注册表设置、 异常中介、 警报通知和分析。</span><span class="sxs-lookup"><span data-stu-id="6d795-137">**ESB Management Portal** : This provides registry provisioning, exception mediation, alert notification, and analytics.</span></span>  
  
  <span data-ttu-id="6d795-138">许多这些组件和服务的依赖功能由实现[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]，如业务流程、 转换和业务规则引擎和 Messagebox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6d795-138">Many of these components and services rely on features implemented by [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)], such as the Orchestration, Transformation, and Business Rules engines and the Message Box database.</span></span> <span data-ttu-id="6d795-139">图 2 显示了类别; 的示意图组件和服务通常发生在每个类别;使用的核心 BizTalk Server 系统组件和[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6d795-139">Figure 2 shows a schematic view of the categories; the components and services typically occurring within each category; and the core BizTalk Server system components used by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
  <span data-ttu-id="6d795-140">![ESB 体系结构](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span><span class="sxs-lookup"><span data-stu-id="6d795-140">![ESB Architecture](../esb-toolkit/media/esbarchitecture.gif "ESBArchitecture")</span></span>  
  
  <span data-ttu-id="6d795-141">**图 2**</span><span class="sxs-lookup"><span data-stu-id="6d795-141">**Figure 2**</span></span>  
  
  <span data-ttu-id="6d795-142">**体系结构和组件 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="6d795-142">**The architecture and components of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]**</span></span>  
  
## <a name="how-the-biztalk-esb-toolkit-works"></a><span data-ttu-id="6d795-143">BizTalk ESB 工具包的工作原理</span><span class="sxs-lookup"><span data-stu-id="6d795-143">How the BizTalk ESB Toolkit Works</span></span>  
 <span data-ttu-id="6d795-144">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]接受入站的消息并对其进行操作，可能是 （但不是总是） 通过执行进程，例如转换、 传送或任何其他自定义的进程。</span><span class="sxs-lookup"><span data-stu-id="6d795-144">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] accepts inbound messages and operates on them, perhaps (but not always) by performing processes such as transformation, delivery, or any other custom defined process.</span></span> <span data-ttu-id="6d795-145">若要指定的操作需要，核心处理组件要求消息包含相关联的说明或定义应用的进程的元数据以及使用消息内容来执行的任务。</span><span class="sxs-lookup"><span data-stu-id="6d795-145">To specify the operations required, the core processing components require a message to contain associated instructions or metadata that define the processes to apply and the tasks to execute with the message content.</span></span>  
  
 <span data-ttu-id="6d795-146">这种方法提供服务; 之间的松散耦合这意味着 ESB 不需要事先了解的特定处理每条消息。</span><span class="sxs-lookup"><span data-stu-id="6d795-146">This approach provides loose coupling between services; this means that the ESB does not require prior knowledge of the specific processing for each message.</span></span> <span data-ttu-id="6d795-147">它只须了解可能范围的进程以及如何将应用每个进程。</span><span class="sxs-lookup"><span data-stu-id="6d795-147">It just has to know the possible range of processes and how to apply each process.</span></span> <span data-ttu-id="6d795-148">多种选项用于指定可用进程及进程与消息中的说明进行操作之间的映射提供了用于配置和调整行为，而无需更改代码和重新部署的灵活机制组件。</span><span class="sxs-lookup"><span data-stu-id="6d795-148">The wide range of options for specifying the available processes and the mapping between the processes and the instructions within messages provides a flexible mechanism for configuring and adjusting behavior, without requiring changes to code and redeployment of components.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6d795-149">本节内容</span><span class="sxs-lookup"><span data-stu-id="6d795-149">In this section</span></span>

- [<span data-ttu-id="6d795-150">安装和配置 Microsoft BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="6d795-150">Install and configure the Microsoft BizTalk ESB Toolkit</span></span>](install-and-configure-the-microsoft-biztalk-esb-toolkit.md)

- [<span data-ttu-id="6d795-151">BizTalk ESB 工具包简介</span><span class="sxs-lookup"><span data-stu-id="6d795-151">Introduction to the BizTalk ESB Toolkit</span></span>](introduction-to-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="6d795-152">入门和了解 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="6d795-152">Getting started and understanding the BizTalk ESB Toolkit</span></span>](getting-started-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="6d795-153">关键方案和开发任务</span><span class="sxs-lookup"><span data-stu-id="6d795-153">Key scenarios and development tasks</span></span>](key-scenarios-and-development-tasks.md)

- [<span data-ttu-id="6d795-154">创建使用路线设计器的路线</span><span class="sxs-lookup"><span data-stu-id="6d795-154">Creating itineraries using itinerary designer</span></span>](creating-itineraries-using-itinerary-designer.md)

- [<span data-ttu-id="6d795-155">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="6d795-155">BizTalk ESB Toolkit sample applications</span></span>](biztalk-esb-toolkit-sample-applications.md)

- [<span data-ttu-id="6d795-156">修改和扩展 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="6d795-156">Modifying and extending the BizTalk ESB Toolkit</span></span>](modifying-and-extending-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="6d795-157">BizTalk ESB 工具包管理</span><span class="sxs-lookup"><span data-stu-id="6d795-157">Administration with the BizTalk ESB Toolkit</span></span>](administration-with-the-biztalk-esb-toolkit.md)

- [<span data-ttu-id="6d795-158">SOA 管理集成</span><span class="sxs-lookup"><span data-stu-id="6d795-158">SOA governance integration</span></span>](soa-governance-integration.md)

- [<span data-ttu-id="6d795-159">BizTalk ESB 工具包疑难解答</span><span class="sxs-lookup"><span data-stu-id="6d795-159">Troubleshooting the BizTalk ESB Toolkit</span></span>](troubleshooting-the-biztalk-esb-toolkit.md)
  
## <a name="related-topics"></a><span data-ttu-id="6d795-160">相关主题</span><span class="sxs-lookup"><span data-stu-id="6d795-160">Related topics</span></span>  
  
-   [<span data-ttu-id="6d795-161">面向解决方案的 BizTalk 服务</span><span class="sxs-lookup"><span data-stu-id="6d795-161">BizTalk Service Oriented Solutions</span></span>](../core/service-oriented-solution.md)

- [<span data-ttu-id="6d795-162">与 BizTalk Server 使用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="6d795-162">Using Web Services with BizTalk Server</span></span>](../core/using-web-services.md)  