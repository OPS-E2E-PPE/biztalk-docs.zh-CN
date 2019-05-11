---
title: 使用 BizTalk Server 中的 ESB 工具包的 SOA 管理集成 |Microsoft Docs
description: 与 BizTalk Server 中的 ESB 工具包基于 SOA 的系统和第三方的集成挑战的列表
caps.latest.revision: 3
author: MandiOhlinger
manager: anneta
ms.custom: ''
ms.date: 08/10/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccb5ac2d-cd90-414d-a6c7-045a8fe9450b
ms.author: mandia
ms.openlocfilehash: c2dcdc9f40d31a8ea037b1475cdb7a9a1380de44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268790"
---
# <a name="soa-governance-integration"></a><span data-ttu-id="b2831-103">SOA 管理集成</span><span class="sxs-lookup"><span data-stu-id="b2831-103">SOA Governance Integration</span></span>
<span data-ttu-id="b2831-104">企业级应用程序必须支持功能强大、 可靠的管理功能，以便能够符合业务要求、 政府立法、 服务级别协议 (Sla) 和客户和贸易合作伙伴的要求。</span><span class="sxs-lookup"><span data-stu-id="b2831-104">Enterprise-level applications must support robust and reliable management features to be able to comply with business requirements, government legislation, service level agreements (SLAs), and customer and trading partner expectations.</span></span> <span data-ttu-id="b2831-105">运行时管理将特别重点，要求和挑战，成功运行面向服务的体系结构 (SOA) – 基于系统满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="b2831-105">Run-time governance focuses specifically on the challenges of, and requirements for, successfully running service-oriented architecture (SOA)–based systems that meet these requirements.</span></span> <span data-ttu-id="b2831-106">由业务系统提供的质量是服务的定义其成功或失败的主要因素。</span><span class="sxs-lookup"><span data-stu-id="b2831-106">The quality of service delivered by a business system is the predominant factor that defines its success or failure.</span></span>  

## <a name="soa-challenges"></a><span data-ttu-id="b2831-107">SOA 挑战</span><span class="sxs-lookup"><span data-stu-id="b2831-107">SOA challenges</span></span>  
 <span data-ttu-id="b2831-108">基于 SOA 的系统部署到生产环境的企业面临了许多挑战，其中包括：</span><span class="sxs-lookup"><span data-stu-id="b2831-108">Businesses deploying SOA-based systems into production face a number of challenges, including the following:</span></span>  

-   <span data-ttu-id="b2831-109">降低成本的维护和升级，并允许增量更新</span><span class="sxs-lookup"><span data-stu-id="b2831-109">Minimizing the cost of maintenance and upgrades, and allowing incremental updates</span></span>  

-   <span data-ttu-id="b2831-110">允许通过业务流程管理和复合工具快速更改</span><span class="sxs-lookup"><span data-stu-id="b2831-110">Allowing rapid change through business process management and composition tools</span></span>  

-   <span data-ttu-id="b2831-111">端到端安全;这包括信任和隐私的消息发送方、 接收方和内容保护</span><span class="sxs-lookup"><span data-stu-id="b2831-111">End-to-end security; this includes trust and protection of the privacy of message senders, receivers, and content</span></span>  

-   <span data-ttu-id="b2831-112">标识、 管理和修复异常发生时</span><span class="sxs-lookup"><span data-stu-id="b2831-112">Identifying, managing, and repairing exceptions as they occur</span></span>  

-   <span data-ttu-id="b2831-113">分离的服务和使用者</span><span class="sxs-lookup"><span data-stu-id="b2831-113">Decoupling of services and consumers</span></span>  

-   <span data-ttu-id="b2831-114">测量和证明成本关注点的偏移的 SOA 应用程序的业务价值</span><span class="sxs-lookup"><span data-stu-id="b2831-114">Measuring and proving the business value of SOA applications to offset cost concerns</span></span>  

-   <span data-ttu-id="b2831-115">重复或其它不必要服务的发展壮大的控件 （管理）</span><span class="sxs-lookup"><span data-stu-id="b2831-115">Control (governance) of the proliferation of duplicate or otherwise unnecessary services</span></span>  

-   <span data-ttu-id="b2831-116">促进潜在用户需要降低初始开发成本的相应服务的标识</span><span class="sxs-lookup"><span data-stu-id="b2831-116">Facilitating the identification of the appropriate services required by potential users to reduce initial development cost</span></span>  

-   <span data-ttu-id="b2831-117">管理服务，以最大程度减少的成本和风险的不间断的维护和更改的生命周期</span><span class="sxs-lookup"><span data-stu-id="b2831-117">Managing the life cycle of services to minimize the cost and risk of ongoing maintenance and change</span></span>  

-   <span data-ttu-id="b2831-118">简化了适当的服务 （分离的位置、 传输、 策略、 标准和消息传递样式） 的实际使用量</span><span class="sxs-lookup"><span data-stu-id="b2831-118">Simplifying the actual usage of appropriate services (decoupling location, transport, policies, standards, and messaging styles)</span></span>  

-   <span data-ttu-id="b2831-119">报告功能用于识别谁在使用哪个服务位置和原因</span><span class="sxs-lookup"><span data-stu-id="b2831-119">Reporting facilities used to identify who is using which service, where, and why</span></span>  

## <a name="next-steps"></a><span data-ttu-id="b2831-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b2831-120">Next steps</span></span>
 <span data-ttu-id="b2831-121">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]支持与两个第三方运行时管理系统集成：</span><span class="sxs-lookup"><span data-stu-id="b2831-121">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] supports integration with two third-party run-time governance systems:</span></span>  

- <span data-ttu-id="b2831-122">**Sentinet SOA 冲突解决程序和 BizTalk 服务器扩展**。</span><span class="sxs-lookup"><span data-stu-id="b2831-122">**Sentinet SOA Resolver and BizTalk Server Extensions**.</span></span> <span data-ttu-id="b2831-123">有关如何 Sentinet 扩展的详细信息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]功能，请参阅[扩展使用 Sentinet BizTalk ESB 工具包功能](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md)。</span><span class="sxs-lookup"><span data-stu-id="b2831-123">For more information on how Sentinet extends [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] capabilities, see [Extending BizTalk ESB Toolkit Capabilities with Sentinet](../technical-guides/extending-biztalk-esb-toolkit-capabilities-with-sentinet.md).</span></span>

- <span data-ttu-id="b2831-124">[SOA BizTalk 管理点](../esb-toolkit/soa-biztalk-management-point.md)SOA Software，inc.</span><span class="sxs-lookup"><span data-stu-id="b2831-124">[SOA BizTalk Management Point](../esb-toolkit/soa-biztalk-management-point.md) from SOA Software, Inc.</span></span>  

- <span data-ttu-id="b2831-125">[AmberPoint BizTalk Nano 代理](../esb-toolkit/amberpoint-biztalk-nano-agent.md)AmberPoint 有限公司</span><span class="sxs-lookup"><span data-stu-id="b2831-125">[AmberPoint BizTalk Nano Agent](../esb-toolkit/amberpoint-biztalk-nano-agent.md) from AmberPoint, Inc.</span></span>
