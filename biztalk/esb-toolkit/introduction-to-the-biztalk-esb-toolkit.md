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
ms.openlocfilehash: e44d3a100cdaefe04cf9d3aedfa8cf969811fc5e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="introduction-to-the-biztalk-esb-toolkit"></a><span data-ttu-id="7fbee-102">BizTalk ESB 工具包简介</span><span class="sxs-lookup"><span data-stu-id="7fbee-102">Introduction to the BizTalk ESB Toolkit</span></span>
<span data-ttu-id="7fbee-103">说明的体系结构和内容的 Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7fbee-103">Explains the architecture and contents of the Microsoft [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="7fbee-104">文档还演示了如何应用来开发企业应用程序启用灵活、 更安全的企业服务总线 (ESB) 体系结构模式和可重用的服务和快速单位的现有服务分成若干个新的端到端业务流程。</span><span class="sxs-lookup"><span data-stu-id="7fbee-104">The documentation also demonstrates how to apply an Enterprise Service Bus (ESB) architecture pattern to develop enterprise applications that enable flexible, secure, and reusable services and rapid organization of existing services into new end-to-end business processes.</span></span>  
  
## <a name="what-is-an-enterprise-service-bus"></a><span data-ttu-id="7fbee-105">什么是企业服务总线？</span><span class="sxs-lookup"><span data-stu-id="7fbee-105">What Is an Enterprise Service Bus?</span></span>  
 <span data-ttu-id="7fbee-106">实现用于启用面向服务的体系结构 (SOA) 的基础结构的上下文中广泛使用企业服务总线的术语。</span><span class="sxs-lookup"><span data-stu-id="7fbee-106">The term Enterprise Service Bus is widely used in the context of implementing an infrastructure for enabling Service-Oriented Architecture (SOA).</span></span> <span data-ttu-id="7fbee-107">但是，SOA 解决方案部署的实际经验已经演示了 ESB 是生成全面面向服务基础结构 (SOI) 所需的许多组件之一。</span><span class="sxs-lookup"><span data-stu-id="7fbee-107">However, real-world experience with the deployment of SOA solutions has demonstrated that an ESB is only one of many components required to build a comprehensive Service-Oriented Infrastructure (SOI).</span></span> <span data-ttu-id="7fbee-108">术语"ESB"的发展经历了大量的方向-其定义各不相同，这是与单个 ESB 和集成平台供应商的解释和特定 SOA 方案的要求。</span><span class="sxs-lookup"><span data-stu-id="7fbee-108">The term "ESB" has evolved in a number of directions—its definition varies with the interpretation of individual ESB and integration platform vendors and with the requirements of particular SOA initiatives.</span></span>  
  
 <span data-ttu-id="7fbee-109">根据从许多成功的实际 SOI 实现已收集了 Microsoft 的体验，Microsoft 认为企业服务总线体系结构模式基于上传统企业应用程序集成 (EAI) 中的集合面向消息的中间件、 Web 服务、.NET 和 Java 的互操作性、 主机系统集成和与服务注册表和资产存储库互操作性。</span><span class="sxs-lookup"><span data-stu-id="7fbee-109">Based on the experience Microsoft has gathered from many successful real-world SOI implementations, Microsoft considers an Enterprise Service Bus to be a collection of architectural patterns based on traditional Enterprise Application Integration (EAI), message-oriented middleware, Web services, .NET and Java interoperability, host system integration, and interoperability with service registries and asset repositories.</span></span> <span data-ttu-id="7fbee-110">图 1 说明企业服务总线体系的结构。</span><span class="sxs-lookup"><span data-stu-id="7fbee-110">Figure 1 illustrates the architecture of an Enterprise Service Bus.</span></span>  
  
 <span data-ttu-id="7fbee-111">![ESB 概述](../esb-toolkit/media/esboverview.gif "ESBOverview")</span><span class="sxs-lookup"><span data-stu-id="7fbee-111">![ESB Overview](../esb-toolkit/media/esboverview.gif "ESBOverview")</span></span>  
  
 <span data-ttu-id="7fbee-112">**图 1**</span><span class="sxs-lookup"><span data-stu-id="7fbee-112">**Figure 1**</span></span>  
  
 <span data-ttu-id="7fbee-113">**高级表示形式由企业服务总线体系结构提供的连接**</span><span class="sxs-lookup"><span data-stu-id="7fbee-113">**A high-level representation of the connectivity provided by the Enterprise Service Bus architecture**</span></span>  

<!---  Old text with old links
## The Industry View of ESB  
 There are many sources of information about ESB design, architecture, infrastructure, and implementation available from industry suppliers, system integrators, and independent sources.  
-->
<!---    
 IBM defines ESB as a system that "...enables a business to make use of a comprehensive, flexible, and consistent approach to integration while also reducing the complexity of the applications being integrated. Due to the complex and varying nature of business needs, ESB is an evolutional progression that unifies message oriented, event driven and service oriented approaches for integrating applications and service." IBM describes the advantages as "...greater reuse of IT assets by separating application logics and integration tasks, so you can reduce the number, size, and complexity of integration interfaces," and the ability to "...add or change services with minimal interruption to existing IT environment; reduce cost and risk involved as business changes and new opportunities arise." For more information, see [WebSphere software](http://go.microsoft.com/fwlink/p/?LinkId=185958)([http://go.microsoft.com/fwlink/p/?LinkId=185958](http://go.microsoft.com/fwlink/p/?LinkId=185958))on the IBM Web site.  
-->
<!---    Old text with old links
 Sonic Solutions provide a comprehensive examination of ESB, discussing the principle aspects, and the IT and business benefits. They describe the requirement for ESB: "To integrate old and new, service-oriented architecture (SOA) needs an infrastructure that can connect any IT resource, whatever its technology or wherever it is deployed." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185959)([http://go.microsoft.com/fwlink/p/?LinkId=185959](http://go.microsoft.com/fwlink/p/?LinkId=185959)) on the Sonic Solutions Web site.  
-->
<!---    Old text with old links
 TIBCO Software define ESB as "...a standards-based communication layer in a service- oriented architecture (SOA) that enables services to be used across multiple communication protocols [to] simplify service deployment and management, and promote service reuse in a heterogeneous environment." They suggest, in order to provide these capabilities, ESBs "...support both open standards and proprietary technologies, including Web services and UDDI-based registries to discover and publish services, Java Message Service (JMS) and other widely deployed messaging protocols, standards-based (XML) transformations, and basic message routing." For more information, see [Enterprise Service Bus (ESB)](http://go.microsoft.com/fwlink/p/?LinkId=185960)([http://go.microsoft.com/fwlink/?LinkId=185960](http://go.microsoft.com/fwlink/p/?LinkId=185960)) on the TIBCO Web site.  
-->
<!---    Old text with old links
 In the description of his book, Enterprise Service Bus, author David Chappell states that "Rather than conform to the hub-and-spoke architecture of traditional enterprise application integration products, ESB provides a highly distributed approach to integration." He adds "...with unique capabilities that allow individual departments or business units to build out their integration projects in incremental, digestible chunks, maintaining their own local control and autonomy, while still being able to connect together each integration project into a larger, more global integration fabric, or grid." For more information, see Enterprise Service Bus by David Chappell:  
-->
<!---    Old text with old links
-   Chappell, David. Enterprise Service Bus. Sebastopol, CA: O'Reilly Media, Inc. 2004.  
-->

  
## <a name="the-biztalk-esb-toolkit"></a><span data-ttu-id="7fbee-114">BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="7fbee-114">The BizTalk ESB Toolkit</span></span>
 <span data-ttu-id="7fbee-115">本文档中的，作为一个整体，引入了架构师和开发人员 ESB 体系结构概念作为通过寻址[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并解释了一套广为接受 ESB 用例通过 ESB 组件的功能。</span><span class="sxs-lookup"><span data-stu-id="7fbee-115">This documentation, as a whole, introduces architects and developers to ESB architectural concepts as addressed by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and explains the functionality of the ESB components through a set of commonly accepted ESB use cases.</span></span>  
  
 <span data-ttu-id="7fbee-116">本部分提供的简介[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，并包括以下主题：</span><span class="sxs-lookup"><span data-stu-id="7fbee-116">This section provides an introduction to the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], and includes the following topics:</span></span>  
  
-   [<span data-ttu-id="7fbee-117">BizTalk ESB 工具包概述</span><span class="sxs-lookup"><span data-stu-id="7fbee-117">Overview of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/overview-of-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="7fbee-118">BizTalk ESB 工具包内容</span><span class="sxs-lookup"><span data-stu-id="7fbee-118">Contents of the BizTalk ESB Toolkit</span></span>](../esb-toolkit/contents-of-the-biztalk-esb-toolkit.md)  
  
 <span data-ttu-id="7fbee-119">本文档还包括以下主题各节：</span><span class="sxs-lookup"><span data-stu-id="7fbee-119">This documentation also includes the following topic sections:</span></span>  
  
-   [<span data-ttu-id="7fbee-120">BizTalk ESB 工具包入门</span><span class="sxs-lookup"><span data-stu-id="7fbee-120">Getting Started with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/getting-started-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="7fbee-121">主要方案和开发任务</span><span class="sxs-lookup"><span data-stu-id="7fbee-121">Key Scenarios and Development Tasks</span></span>](../esb-toolkit/key-scenarios-and-development-tasks.md)  
  
-   [<span data-ttu-id="7fbee-122">使用路线设计器创建路线</span><span class="sxs-lookup"><span data-stu-id="7fbee-122">Creating Itineraries Using Itinerary Designer</span></span>](../esb-toolkit/creating-itineraries-using-itinerary-designer.md)  
  
-   [<span data-ttu-id="7fbee-123">BizTalk ESB 工具包示例应用程序</span><span class="sxs-lookup"><span data-stu-id="7fbee-123">BizTalk ESB Toolkit Sample Applications</span></span>](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)  
  
-   [<span data-ttu-id="7fbee-124">修改和扩展 BizTalk ESB 工具包</span><span class="sxs-lookup"><span data-stu-id="7fbee-124">Modifying and Extending the BizTalk ESB Toolkit</span></span>](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="7fbee-125">BizTalk ESB 工具包管理</span><span class="sxs-lookup"><span data-stu-id="7fbee-125">Administration with the BizTalk ESB Toolkit</span></span>](../esb-toolkit/administration-with-the-biztalk-esb-toolkit.md)  
  
-   [<span data-ttu-id="7fbee-126">SOA 管理集成</span><span class="sxs-lookup"><span data-stu-id="7fbee-126">SOA Governance Integration</span></span>](../esb-toolkit/soa-governance-integration.md)  
  
-   [<span data-ttu-id="7fbee-127">故障排除</span><span class="sxs-lookup"><span data-stu-id="7fbee-127">Troubleshooting</span></span>](../esb-toolkit/troubleshooting-the-biztalk-esb-toolkit.md)