---
title: "与 BizTalk Server 中的 ESB 工具包的 SOA 监管集成 |Microsoft 文档"
description: "与 BizTalk Server 中的 ESB 工具包 SOA 基于系统和第三方的集成的挑战的列表"
caps.latest.revision: "3"
author: MandiOhlinger
manager: anneta
ms.custom: 
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccb5ac2d-cd90-414d-a6c7-045a8fe9450b
ms.author: mandia
ms.openlocfilehash: 9e1489e01a8918d1dfa7ca61a69d57f5d7316f68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="soa-governance-integration"></a><span data-ttu-id="aeece-103">SOA 监管集成</span><span class="sxs-lookup"><span data-stu-id="aeece-103">SOA Governance Integration</span></span>
<span data-ttu-id="aeece-104">企业级应用程序必须支持功能强大和可靠的管理功能，能够符合业务要求、 政府法律要求、 服务级别协议 (Sla) 和客户和贸易合作伙伴的要求。</span><span class="sxs-lookup"><span data-stu-id="aeece-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="aeece-105">运行时管理重点介绍专门要求和挑战，成功运行面向服务的体系结构 (SOA) – 基于满足这些要求的系统。</span><span class="sxs-lookup"><span data-stu-id="aeece-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="aeece-106">由业务系统提供质量影响的是服务的定义是服务的成功还是失败的主导因素。</span><span class="sxs-lookup"><span data-stu-id="aeece-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="aeece-107">SOA 挑战</span><span class="sxs-lookup"><span data-stu-id="aeece-107">SOA challenges</span></span>  
 <span data-ttu-id="aeece-108">SOA 基于系统部署到生产环境的企业面临了许多挑战，其中包括：</span><span class="sxs-lookup"><span data-stu-id="aeece-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  
  
-   <span data-ttu-id="aeece-109">降低成本的维护和升级，并允许增量更新</span><span class="sxs-lookup"><span data-stu-id="aeece-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  
  
-   <span data-ttu-id="aeece-110">允许通过业务流程管理和复合工具快速更改</span><span class="sxs-lookup"><span data-stu-id="aeece-110">Allowing rapid change through business process management and composition tools</span></span>  
  
-   <span data-ttu-id="aeece-111">端到端安全性则这包括信任和保护的消息发送方、 接收方和内容的隐私</span><span class="sxs-lookup"><span data-stu-id="aeece-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  
  
-   <span data-ttu-id="aeece-112">标识、 管理和在发生这些修复异常</span><span class="sxs-lookup"><span data-stu-id="aeece-112">Identifying, managing, and repairing exceptions as they occur</span></span>  
  
-   <span data-ttu-id="aeece-113">分离的服务和使用者</span><span class="sxs-lookup"><span data-stu-id="aeece-113">Decoupling of services and consumers</span></span>  
  
-   <span data-ttu-id="aeece-114">测量和证明的业务价值的 SOA 应用程序偏移成本问题</span><span class="sxs-lookup"><span data-stu-id="aeece-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  
  
-   <span data-ttu-id="aeece-115">控件 （管理） 的重复或否则为不必要的服务的增加</span><span class="sxs-lookup"><span data-stu-id="aeece-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  
  
-   <span data-ttu-id="aeece-116">简化了适当的服务，以减少初始开发成本潜在用户所需的标识</span><span class="sxs-lookup"><span data-stu-id="aeece-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  
  
-   <span data-ttu-id="aeece-117">服务的成本和风险日常维护的最小化和更改的生命周期管理</span><span class="sxs-lookup"><span data-stu-id="aeece-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  
  
-   <span data-ttu-id="aeece-118">简化了适当的服务 （分离位置、 传输、 策略、 标准和消息传送样式） 的实际使用情况</span><span class="sxs-lookup"><span data-stu-id="aeece-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  
  
-   <span data-ttu-id="aeece-119">报告功能用于标识使用者的服务，其中，和原因</span><span class="sxs-lookup"><span data-stu-id="aeece-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="aeece-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="aeece-120">Next steps</span></span>
 <span data-ttu-id="aeece-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持与两个第三方运行时管理系统集成：</span><span class="sxs-lookup"><span data-stu-id="aeece-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  
  
-   <span data-ttu-id="aeece-122">**Sentinet SOA 解析器和 BizTalk Server 扩展**。</span><span class="sxs-lookup"><span data-stu-id="aeece-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="aeece-123">有关详细信息如何 Sentinet 扩展[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]功能，请参阅[扩展与 Sentinet BizTalk ESB 工具包功能](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md)。</span><span class="sxs-lookup"><span data-stu-id="aeece-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>
  
-   <span data-ttu-id="aeece-124">[SOA BizTalk 管理点](../esb-toolkit/soa-biztalk-management-point.md)SOA 软件，Inc.的</span><span class="sxs-lookup"><span data-stu-id="aeece-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  
  
-   <span data-ttu-id="aeece-125">[AmberPoint BizTalk Nano 代理](../esb-toolkit/amberpoint-biztalk-nano-agent.md)AmberPoint，Inc.的</span><span class="sxs-lookup"><span data-stu-id="aeece-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>