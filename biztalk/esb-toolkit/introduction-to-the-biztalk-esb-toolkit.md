---
title: "BizTalk ESB 工具包简介 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ESBToolkitV2.introduction
ms.assetid: 98a957b8-5855-4872-b7e7-58a2e1d6b2b8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9763e55c44fc3ea45ab93127ffae8c9c742f0dc9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a><span data-ttu-id="fc9c2-102">BizTalk ESB 工具包简介</span><span class="sxs-lookup"><span data-stu-id="fc9c2-102">Introduction to the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="fc9c2-103">说明的体系结构和内容的 Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-103">Explains the architecture and contents of the Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="fc9c2-104">文档还演示了如何应用来开发企业应用程序启用灵活、 更安全的企业服务总线 (ESB) 体系结构模式和可重用的服务和快速单位的现有服务分成若干个新的端到端业务流程。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-104">The documentation also demonstrates how to apply an Enterprise Service Bus (ESB) architecture pattern to develop enterprise applications that enable flexible, secure, and reusable services and rapid organization of existing services into new end-to-end business processes.</span></span>  
  
## <a name="what-is-an-enterprise-service-bus"></a><span data-ttu-id="fc9c2-105">什么是企业服务总线？</span><span class="sxs-lookup"><span data-stu-id="fc9c2-105">What Is an Enterprise Service Bus?</span></span>  
 <span data-ttu-id="fc9c2-106">实现用于启用面向服务的体系结构 (SOA) 的基础结构的上下文中广泛使用企业服务总线的术语。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-106">The term Enterprise Service Bus is widely used in the context of implementing an infrastructure for enabling Service-Oriented Architecture (SOA).</span></span> <span data-ttu-id="fc9c2-107">但是，SOA 解决方案部署的实际经验已经演示了 ESB 是生成全面面向服务基础结构 (SOI) 所需的许多组件之一。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-107">However, real-world experience with the deployment of SOA solutions has demonstrated that an ESB is only one of many components required to build a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="fc9c2-108">术语"ESB"的发展经历了大量的方向-其定义各不相同，这是与单个 ESB 和集成平台供应商的解释和特定 SOA 方案的要求。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-108">The term "ESB" has evolved in a number of directions—its definition varies with the interpretation of individual ESB and integration platform vendors and with the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="fc9c2-109">根据从许多成功的实际 SOI 实现已收集了 Microsoft 的体验，Microsoft 认为企业服务总线体系结构模式基于上传统企业应用程序集成 (EAI) 中的集合面向消息的中间件、 Web 服务、.NET 和 Java 的互操作性、 主机系统集成和与服务注册表和资产存储库互操作性。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-109">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, Microsoft considers an Enterprise Service Bus to be a collection of architectural patterns based on traditional Enterprise Application Integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span> <span data-ttu-id="fc9c2-110">图 1 说明企业服务总线体系的结构。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-110">Figure 1 illustrates the architecture of an Enterprise Service Bus.</span></span>  
  
 <span data-ttu-id="fc9c2-111">![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="fc9c2-111">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="fc9c2-112">**图 1**</span><span class="sxs-lookup"><span data-stu-id="fc9c2-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="fc9c2-113">**高级表示形式由企业服务总线体系结构提供的连接**</span><span class="sxs-lookup"><span data-stu-id="fc9c2-113">**A high-level representation of the connectivity provided by the Enterprise Service Bus architecture**</span></span>  

<span data-ttu-id="fc9c2-114">\<！---与旧的链接的旧文本</span><span class="sxs-lookup"><span data-stu-id="fc9c2-114">\<!---  Old text with old links</span></span>
## <a name="the-industry-view-of-esb"></a><span data-ttu-id="fc9c2-115">ESB 该行业视图</span><span class="sxs-lookup"><span data-stu-id="fc9c2-115">The Industry View of ESB</span></span>  
 <span data-ttu-id="fc9c2-116">行业供应商、 系统集成商和独立的源提供了有关 ESB 设计、 体系结构、 基础结构，以及实现的信息来源。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-116">There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.</span></span>  
<span data-ttu-id="fc9c2-117">-->
\<!---</span><span class="sxs-lookup"><span data-stu-id="fc9c2-117">-->
\<!---</span></span>    
 <span data-ttu-id="fc9c2-118">IBM 作为系统定义 ESB，"...enables 企业能够对同时减少正在集成的应用程序的复杂性的集成进行全面、 灵活、 使用和一致的方法。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-118">IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated.</span></span> <span data-ttu-id="fc9c2-119">由于复杂和不同的特性的业务需求，ESB 统一面向消息的 evolutional 进展，事件驱动的和服务面向集成应用程序和服务的方法。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-119">Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service."</span></span> <span data-ttu-id="fc9c2-120">IBM 描述与好处"..分隔应用程序是逻辑和集成任务，因此数量、 大小和复杂性的集成接口，可以减少 IT 资产.greater 重用"以及的能力"...add 或更改的服务，只需极少现有 IT 环境中; 中断降低成本和风险涉及随着业务的变化和新的机会出现"。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-120">IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise."</span></span> <span data-ttu-id="fc9c2-121">有关详细信息，请参阅[WebSphere 软件](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958)) IBM Web 站点上。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-121">For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.</span></span>  
<span data-ttu-id="fc9c2-122">-->
\<！---与旧链接 Sonic 解决方案提供 ESB，全面检查讨论的原则方面和 IT 的旧文本和业务好处。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-122">-->
\<!---    Old text with old links Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits.</span></span> <span data-ttu-id="fc9c2-123">这些主题描述了 ESB 的要求:"若要将旧和新的集成，面向服务的体系结构 (SOA) 需要一种可以连接任何 IT 资源，任何基础结构其技术或部署任何位置。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-123">They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed."</span></span> <span data-ttu-id="fc9c2-124">有关详细信息，请参阅[企业服务总线 (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) Sonic 解决方案 Web 站点上。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-124">For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.</span></span>  
<span data-ttu-id="fc9c2-125">-->
\<！---与旧链接 TIBCO 软件旧文本定义为 ESB"...a 基于标准的通信层中的面向服务的体系结构 (SOA)，使服务可用于跨多个通信协议 [] 简化服务部署和管理，并将升级服务异类环境中的重复使用。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-125">-->
\<!---    Old text with old links TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment."</span></span> <span data-ttu-id="fc9c2-126">这些建议，以便提供这些功能，ESBs"...support 均是开放式标准和专有技术，包括 Web 服务和基于 UDDI 注册表，才能发现和发布服务，Java 消息服务 (JMS) 和其他广泛部署消息传递协议、 基于标准的 (XML) 转换和基本的邮件路由。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-126">They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing."</span></span> <span data-ttu-id="fc9c2-127">有关详细信息，请参阅[企业服务总线 (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) TIBCO Web 站点上。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-127">For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.</span></span>  
<span data-ttu-id="fc9c2-128">-->
\<！---与书籍，企业服务总线的说明中的旧链接的旧文本作者 David Chappell 指出"而不是符合中心辐射体系结构的传统的企业应用程序集成产品，ESB 提供高度分布式的方法集成。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-128">-->
\<!---    Old text with old links In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration."</span></span> <span data-ttu-id="fc9c2-129">他将添加"...使用唯一功能，以允许各个部门或业务单位来生成 out 增量备份，可以理解的区块，但仍然可以将连接在一起维护其自己的本地控制和自主性，其集成项目每个集成项目到更大、 更具有全局性集成构造或网格。"</span><span class="sxs-lookup"><span data-stu-id="fc9c2-129">He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid."</span></span> <span data-ttu-id="fc9c2-130">有关详细信息，请参阅 David Chappell 企业服务总线：</span><span class="sxs-lookup"><span data-stu-id="fc9c2-130">For more information, see Enterprise Service Bus by David Chappell:</span></span>  
<span data-ttu-id="fc9c2-131">-->
\<！---与旧的链接的旧文本</span><span class="sxs-lookup"><span data-stu-id="fc9c2-131">-->
\<!---    Old text with old links</span></span>
-   <span data-ttu-id="fc9c2-132">Chappell，David。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-132">Chappell, David.</span></span> <span data-ttu-id="fc9c2-133">企业服务总线。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-133">Enterprise Service Bus.</span></span> <span data-ttu-id="fc9c2-134">Sebastopol，CA: O'Reilly 媒体，inc.2004.</span><span class="sxs-lookup"><span data-stu-id="fc9c2-134">Sebastopol, CA: O'Reilly Media, Inc. 2004.</span></span>  
-->

  
## <a name="the-biztalk-esb-toolkit"></a><span data-ttu-id="fc9c2-135">BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="fc9c2-135">The BizTalk ESB Toolkit</span></span>
 <span data-ttu-id="fc9c2-136">本文档中的，作为一个整体，引入了架构师和开发人员 ESB 体系结构概念作为通过寻址[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并解释了一套广为接受 ESB 用例通过 ESB 组件的功能。</span><span class="sxs-lookup"><span data-stu-id="fc9c2-136">This documentation, as a whole, introduces architects and developers to ESB architectural concepts as addressed by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and explains the functionality of the ESB components through a set of commonly accepted ESB use cases.</span></span>  
  
 <span data-ttu-id="fc9c2-137">本部分提供的简介[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并包括以下主题：</span><span class="sxs-lookup"><span data-stu-id="fc9c2-137">This section provides an introduction to the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and includes the following topics:</span></span>  
  
-   [<span data-ttu-id="fc9c2-138">BizTalk ESB 工具包的概述</span><span class="sxs-lookup"><span data-stu-id="fc9c2-138">Overview of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="fc9c2-139">BizTalk ESB 工具包的内容</span><span class="sxs-lookup"><span data-stu-id="fc9c2-139">Contents of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 <span data-ttu-id="fc9c2-140">本文档还包括以下主题各节：</span><span class="sxs-lookup"><span data-stu-id="fc9c2-140">This documentation also includes the following topic sections:</span></span>  
  
-   [<span data-ttu-id="fc9c2-141">Getting Started with BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="fc9c2-141">Getting Started with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="fc9c2-142">重要的方案和开发任务</span><span class="sxs-lookup"><span data-stu-id="fc9c2-142">Key Scenarios and Development Tasks</span></span>](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [<span data-ttu-id="fc9c2-143">创建使用路线设计器的路线</span><span class="sxs-lookup"><span data-stu-id="fc9c2-143">Creating Itineraries Using Itinerary Designer</span></span>](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [<span data-ttu-id="fc9c2-144">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="fc9c2-144">BizTalk ESB Toolkit Sample Applications</span></span>](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [<span data-ttu-id="fc9c2-145">修改和扩展 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="fc9c2-145">Modifying and Extending the BizTalk ESB Toolkit</span></span>](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="fc9c2-146">管理 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="fc9c2-146">Administration with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="fc9c2-147">SOA 监管集成</span><span class="sxs-lookup"><span data-stu-id="fc9c2-147">SOA Governance Integration</span></span>](../esb-toolkit/soa-governance-integration.md)  
  
-   [<span data-ttu-id="fc9c2-148">故障排除</span><span class="sxs-lookup"><span data-stu-id="fc9c2-148">Troubleshooting</span></span>](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)