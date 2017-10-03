---
title: "为性能规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 267a8bc6-a0ab-4335-bc04-c22d5a56792f
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fac21f0b483ac3cbaec64c48b524a17422cb146
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-performance"></a><span data-ttu-id="b983e-102">规划性能</span><span class="sxs-lookup"><span data-stu-id="b983e-102">Planning for Performance</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b983e-103">是一个应用程序平台。</span><span class="sxs-lookup"><span data-stu-id="b983e-103"> is an application platform.</span></span> <span data-ttu-id="b983e-104">它不是只是一种服务器产品或只是开发人员产品。</span><span class="sxs-lookup"><span data-stu-id="b983e-104">It is not just a server product or just a developer product.</span></span> <span data-ttu-id="b983e-105">它是一个用于构建业务流程管理系统，将企业应用程序，以自动执行工作流，集成的应用程序平台和启用服务的面向体系结构。</span><span class="sxs-lookup"><span data-stu-id="b983e-105">It is an application platform that is used to build business process management systems, to integrate enterprise applications, to automate workflows, and to enable service oriented architectures.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="b983e-106">是依赖于许多其他软件组件。</span><span class="sxs-lookup"><span data-stu-id="b983e-106"> is dependent on many other software components.</span></span> <span data-ttu-id="b983e-107">BizTalk 应用程序平台通常提供多个以下的软件组件： Windows Server 操作系统的 SQL Server， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS （可选），外部系统的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与，进行交互，以及非 Microsoft 适配器和组件。</span><span class="sxs-lookup"><span data-stu-id="b983e-107">The BizTalk application platform typically includes several of the following software components: the Windows Server operating system, SQL Server, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], IIS (optional), external systems that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is interacting with, as well as non-Microsoft adapters and components.</span></span>  
  
 <span data-ttu-id="b983e-108">本质上是复杂的性质，因此[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，有许多注意事项为性能规划时进行。</span><span class="sxs-lookup"><span data-stu-id="b983e-108">Because of the inherently complex nature of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, there are many considerations to be made when planning for performance.</span></span> <span data-ttu-id="b983e-109">有几种默认设置适用于所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境和一些其他注意事项和有关优化方法特定的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构。</span><span class="sxs-lookup"><span data-stu-id="b983e-109">There are several default settings that are applicable to all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments and there are additional considerations and methodologies for optimizing specific [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] architectures.</span></span>  
  
 <span data-ttu-id="b983e-110">本主题提供的默认设置优化的所有性能时应该应用概述[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="b983e-110">This topic provides an overview of the default settings that you should apply when optimizing performance for all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments.</span></span> <span data-ttu-id="b983e-111">它还提供用于测试和优化建议[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]旨在用于特定方案的环境。</span><span class="sxs-lookup"><span data-stu-id="b983e-111">It also provides recommendations for testing and optimizing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environments that are designed for specific scenarios.</span></span>  
  
## <a name="settings-that-you-should-apply-to-all-biztalk-server-environments"></a><span data-ttu-id="b983e-112">应适用于所有的 BizTalk Server 环境的设置</span><span class="sxs-lookup"><span data-stu-id="b983e-112">Settings That You Should Apply to All BizTalk Server Environments</span></span>  
 <span data-ttu-id="b983e-113">[操作的准备情况清单](../technical-guides/operational-readiness-checklists.md)部分本指南包含使用任何 BizTalk 解决方案前应查看的项的列表。</span><span class="sxs-lookup"><span data-stu-id="b983e-113">The [Operational Readiness Checklists](../technical-guides/operational-readiness-checklists.md) section of this guide contains a list of items that you should review before employing any BizTalk solution.</span></span> <span data-ttu-id="b983e-114">此清单包含会对性能有显著的影响的操作项你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]而不考虑特定性质的 BizTalk 解决方案采用的环境。</span><span class="sxs-lookup"><span data-stu-id="b983e-114">This checklist contains action items that can have a significant impact on the performance of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment regardless of the specific nature of the BizTalk solution that is employed.</span></span>  
  
## <a name="considerations-for-testing-and-optimizing-a-biztalk-solution"></a><span data-ttu-id="b983e-115">测试和优化 BizTalk 解决方案注意事项</span><span class="sxs-lookup"><span data-stu-id="b983e-115">Considerations for Testing and Optimizing a BizTalk Solution</span></span>  
 <span data-ttu-id="b983e-116">不同的 BizTalk 解决方案可能有差别很大的性能条件。</span><span class="sxs-lookup"><span data-stu-id="b983e-116">Different BizTalk solutions may have drastically different performance criteria.</span></span> <span data-ttu-id="b983e-117">例如，围绕运行业务流程构建一个 BizTalk 解决方案将具有比侧重于接收、 转换和映射平面文件文档 BizTalk 解决方案的不同的性能配置文件。</span><span class="sxs-lookup"><span data-stu-id="b983e-117">For example, a BizTalk solution that is built around running orchestrations will have a different performance profile than a BizTalk solution that is focused on receiving, converting, and mapping flat file documents.</span></span> <span data-ttu-id="b983e-118">业务流程已设定焦点的解决方案可能是 CPU 密集型，也可以调用受益优化，而平面文件转换和映射已设定焦点的解决方案可能更占用大量内存的自定义组件。</span><span class="sxs-lookup"><span data-stu-id="b983e-118">An orchestration-focused solution may be CPU intensive or may call custom components that benefit from optimization, while a flat file conversion and mapping-focused solution may be more memory-intensive.</span></span>  
  
 <span data-ttu-id="b983e-119">适配器和用于接收和发送中和扩展的文档的管道[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]也可能对 BizTalk 解决方案的性能产生深远的影响。</span><span class="sxs-lookup"><span data-stu-id="b983e-119">The adapters and pipelines used to receive and send documents in and out of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] can also have a profound impact on the performance of the BizTalk solution.</span></span> <span data-ttu-id="b983e-120">解决方案所需的文档跟踪的级别将也会显著影响性能。</span><span class="sxs-lookup"><span data-stu-id="b983e-120">The level of document tracking required by the solution will also greatly impact performance.</span></span> <span data-ttu-id="b983e-121">由于的多个同名的不同性能配置文件在不同的 BizTalk 解决方案可能会出现，它是非常关键，测试 BizTalk 解决方案以度量最大可持续的性能和最大可持续跟踪性能。</span><span class="sxs-lookup"><span data-stu-id="b983e-121">Because of the many divergent performance profiles that are possible in different BizTalk solutions, it is absolutely critical that that you test the BizTalk solution to measure maximum sustainable performance and maximum sustainable tracking performance.</span></span>  
  
 <span data-ttu-id="b983e-122">确定后的最大可持续的性能和最大可持续跟踪性能 BizTalk 解决方案，有一些可以用于瓶颈移除 BizTalk 解决方案中的特定步骤。</span><span class="sxs-lookup"><span data-stu-id="b983e-122">After determining the maximum sustainable performance and maximum sustainable tracking performance of the BizTalk solution, there are specific steps that you can employ to remove bottlenecks in the BizTalk solution.</span></span> <span data-ttu-id="b983e-123">有关详细信息，请参阅[BizTalk Server 2009 性能指南](http://go.microsoft.com/fwlink/?LinkID=150492)(http://go.microsoft.com/fwlink/?LinkID=150492)。</span><span class="sxs-lookup"><span data-stu-id="b983e-123">For more information, see the [BizTalk Server 2009 Performance Guide](http://go.microsoft.com/fwlink/?LinkID=150492) (http://go.microsoft.com/fwlink/?LinkID=150492).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b983e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b983e-124">See Also</span></span>  
 [<span data-ttu-id="b983e-125">规划 BizTalk 服务器层</span><span class="sxs-lookup"><span data-stu-id="b983e-125">Planning the BizTalk Server Tier</span></span>](../technical-guides/planning-the-biztalk-server-tier.md)