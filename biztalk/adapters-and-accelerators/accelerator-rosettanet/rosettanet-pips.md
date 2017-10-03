---
title: "RosettaNet Pip |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1980f7c5e22259dc6c09d4f2d8dba31f3ac04d61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="rosettanet-pips"></a><span data-ttu-id="59fc8-102">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="59fc8-102">RosettaNet PIPs</span></span>
<span data-ttu-id="59fc8-103">RosettaNet 组织创建并维护合作伙伴接口流程 (PIP)，以便为所有 RosettaNet 消息交换提供通用的业务流程定义。</span><span class="sxs-lookup"><span data-stu-id="59fc8-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="59fc8-104">每个 PIP 规范都提供了文档类型定义 (DTD) 文件和消息指南文档。</span><span class="sxs-lookup"><span data-stu-id="59fc8-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="59fc8-105">DTD 文件定义了服务内容消息的结构。</span><span class="sxs-lookup"><span data-stu-id="59fc8-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="59fc8-106">消息指南文档作为可读的 HTML 文件，指定了元素级的约束，</span><span class="sxs-lookup"><span data-stu-id="59fc8-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="59fc8-107">同时，还提供了业务流程的完整定义。</span><span class="sxs-lookup"><span data-stu-id="59fc8-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="59fc8-108">PIP 规范的相关的详细信息，请参阅位于的 RosettaNet 网站[http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859)。</span><span class="sxs-lookup"><span data-stu-id="59fc8-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="59fc8-109">PIP 内容</span><span class="sxs-lookup"><span data-stu-id="59fc8-109">PIP Contents</span></span>  
 <span data-ttu-id="59fc8-110">PIP 规范的作用如下：</span><span class="sxs-lookup"><span data-stu-id="59fc8-110">A PIP specification does the following:</span></span>  
  
-   <span data-ttu-id="59fc8-111">说明实施哪种公用流程模式</span><span class="sxs-lookup"><span data-stu-id="59fc8-111">Describes which public process pattern it implements</span></span>  
  
-   <span data-ttu-id="59fc8-112">说明如何配置公用流程</span><span class="sxs-lookup"><span data-stu-id="59fc8-112">Describes how to configure the public process</span></span>  
  
-   <span data-ttu-id="59fc8-113">提供对 PIP 内进行交换的文档的引用</span><span class="sxs-lookup"><span data-stu-id="59fc8-113">Provides references to the documents to exchange within the PIP</span></span>  
  
 <span data-ttu-id="59fc8-114">PIP 规范包括三个主要部分： 业务操作视图 (BOV)、 功能服务视图 (FSV) 和实现 Framework 视图 (IFV)。</span><span class="sxs-lookup"><span data-stu-id="59fc8-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="59fc8-115">每个视图都指定了元素级的约束：</span><span class="sxs-lookup"><span data-stu-id="59fc8-115">Each of these views specifies element-level constraints:</span></span>  
  
-   <span data-ttu-id="59fc8-116">BOV 指定了业务数据实体和业务流程的语义；</span><span class="sxs-lookup"><span data-stu-id="59fc8-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="59fc8-117">说明了开始状态、结束状态、合作伙伴角色，</span><span class="sxs-lookup"><span data-stu-id="59fc8-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="59fc8-118">还说明了角色之间的交互，并详细介绍了安全、审核和流程控制；</span><span class="sxs-lookup"><span data-stu-id="59fc8-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="59fc8-119">此外，还指定了业务文档和业务数据实体。</span><span class="sxs-lookup"><span data-stu-id="59fc8-119">It specifies the business documents and business data entities.</span></span>  
  
-   <span data-ttu-id="59fc8-120">FSV 指定了网络组件服务、代理和交互；</span><span class="sxs-lookup"><span data-stu-id="59fc8-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="59fc8-121">提供了运行 PIP 所需的网络组件设计，并说明了可能的网络组件交互。</span><span class="sxs-lookup"><span data-stu-id="59fc8-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
-   <span data-ttu-id="59fc8-122">IFV 指定了运行 PIP 所需的网络协议消息格式和通信要求。</span><span class="sxs-lookup"><span data-stu-id="59fc8-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="59fc8-123">群集和段</span><span class="sxs-lookup"><span data-stu-id="59fc8-123">Clusters and Segments</span></span>  
 <span data-ttu-id="59fc8-124">按高级业务功能（群集）和子功能（段）对 PIP 进行分类。</span><span class="sxs-lookup"><span data-stu-id="59fc8-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="59fc8-125">群集和段将业务消息组织成可识别的类别。</span><span class="sxs-lookup"><span data-stu-id="59fc8-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="59fc8-126">下表列出了这些群集和段。</span><span class="sxs-lookup"><span data-stu-id="59fc8-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="59fc8-127">Clusters</span><span class="sxs-lookup"><span data-stu-id="59fc8-127">Clusters</span></span>|<span data-ttu-id="59fc8-128">段</span><span class="sxs-lookup"><span data-stu-id="59fc8-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="59fc8-129">0: RosettaNet 支持</span><span class="sxs-lookup"><span data-stu-id="59fc8-129">0: RosettaNet Support</span></span>|<span data-ttu-id="59fc8-130">0A： 管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="59fc8-131">0 C： 测试</span><span class="sxs-lookup"><span data-stu-id="59fc8-131">0C: Testing</span></span>|  
|<span data-ttu-id="59fc8-132">1： 合作伙伴的产品和服务复查</span><span class="sxs-lookup"><span data-stu-id="59fc8-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="59fc8-133">1A： 合作伙伴评审</span><span class="sxs-lookup"><span data-stu-id="59fc8-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="59fc8-134">1B： 产品和服务复查</span><span class="sxs-lookup"><span data-stu-id="59fc8-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="59fc8-135">2： 产品信息</span><span class="sxs-lookup"><span data-stu-id="59fc8-135">2: Product Information</span></span>|<span data-ttu-id="59fc8-136">2A： 准备分发</span><span class="sxs-lookup"><span data-stu-id="59fc8-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="59fc8-137">2B： 产品更改通知</span><span class="sxs-lookup"><span data-stu-id="59fc8-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="59fc8-138">2c： 产品设计信息</span><span class="sxs-lookup"><span data-stu-id="59fc8-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="59fc8-139">二维： 协作设计和工程部门</span><span class="sxs-lookup"><span data-stu-id="59fc8-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="59fc8-140">3： 订单管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-140">3: Order Management</span></span>|<span data-ttu-id="59fc8-141">3A: Quote 和订单输入</span><span class="sxs-lookup"><span data-stu-id="59fc8-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="59fc8-142">3B： 运输和分销</span><span class="sxs-lookup"><span data-stu-id="59fc8-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="59fc8-143">3c： 返回和金融</span><span class="sxs-lookup"><span data-stu-id="59fc8-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="59fc8-144">三维： 产品配置</span><span class="sxs-lookup"><span data-stu-id="59fc8-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="59fc8-145">4： 库存管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-145">4: Inventory Management</span></span>|<span data-ttu-id="59fc8-146">4A： 协作预测</span><span class="sxs-lookup"><span data-stu-id="59fc8-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="59fc8-147">4B： 清单分配</span><span class="sxs-lookup"><span data-stu-id="59fc8-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="59fc8-148">4c： 清单报表</span><span class="sxs-lookup"><span data-stu-id="59fc8-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="59fc8-149">4 D： 库存补货</span><span class="sxs-lookup"><span data-stu-id="59fc8-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="59fc8-150">4E： 销售报表</span><span class="sxs-lookup"><span data-stu-id="59fc8-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="59fc8-151">4F： 价格保护</span><span class="sxs-lookup"><span data-stu-id="59fc8-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="59fc8-152">5： 营销信息管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-152">5: Marketing Information Management</span></span>|<span data-ttu-id="59fc8-153">5A： 潜在客户机会管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="59fc8-154">5B： 市场营销活动管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="59fc8-155">6： 服务和支持</span><span class="sxs-lookup"><span data-stu-id="59fc8-155">6: Service and Support</span></span>|<span data-ttu-id="59fc8-156">6A： 提供和管理担保，服务包、 和协定服务</span><span class="sxs-lookup"><span data-stu-id="59fc8-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="59fc8-157">6B： 提供和管理资产管理 （与 6A 合并）</span><span class="sxs-lookup"><span data-stu-id="59fc8-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="59fc8-158">6 C： 请与技术支持和服务管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="59fc8-159">7： 制造</span><span class="sxs-lookup"><span data-stu-id="59fc8-159">7: Manufacturing</span></span>|<span data-ttu-id="59fc8-160">7A： 设计传输</span><span class="sxs-lookup"><span data-stu-id="59fc8-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="59fc8-161">7B： 管理生产 WO 和 WIP</span><span class="sxs-lookup"><span data-stu-id="59fc8-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="59fc8-162">7 C： 分发制造信息</span><span class="sxs-lookup"><span data-stu-id="59fc8-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="59fc8-163">每个段均包括许多特定的消息 PIP。</span><span class="sxs-lookup"><span data-stu-id="59fc8-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="59fc8-164">例如，3A4 PIP 是订单管理群集（群集 3）和报价与订单录入段（群集 3 的段 A）的一部分。</span><span class="sxs-lookup"><span data-stu-id="59fc8-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="59fc8-165">本段包括其他相关的消息 PIP，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59fc8-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="59fc8-166">群集 3： 订单管理</span><span class="sxs-lookup"><span data-stu-id="59fc8-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="59fc8-167">段答： Quote 和订单输入</span><span class="sxs-lookup"><span data-stu-id="59fc8-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="59fc8-168">PIP 3A1： 请求引号</span><span class="sxs-lookup"><span data-stu-id="59fc8-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="59fc8-169">PIP 3A2： 请求价格和可用性</span><span class="sxs-lookup"><span data-stu-id="59fc8-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="59fc8-170">PIP 3A3： 请求购物车传输</span><span class="sxs-lookup"><span data-stu-id="59fc8-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="59fc8-171">PIP 3A4： 管理采购订单</span><span class="sxs-lookup"><span data-stu-id="59fc8-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="59fc8-172">PIP 3A5： 查询订单状态</span><span class="sxs-lookup"><span data-stu-id="59fc8-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="59fc8-173">PIP 3A6： 分发订单状态</span><span class="sxs-lookup"><span data-stu-id="59fc8-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="59fc8-174">…</span><span class="sxs-lookup"><span data-stu-id="59fc8-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59fc8-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59fc8-175">See Also</span></span>  
 <span data-ttu-id="59fc8-176">[RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="59fc8-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="59fc8-177">RNIF 标准</span><span class="sxs-lookup"><span data-stu-id="59fc8-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)