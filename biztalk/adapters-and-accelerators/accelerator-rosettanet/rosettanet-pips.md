---
title: RosettaNet Pip |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PIPs, clusters
- RosettaNet, PIPs
- PIPs, PIP specifications
- PIPs, segments
- PIPs, RosettaNet
- DTDs, DTD files
ms.assetid: 2f7e8db3-9ccb-403a-9fe7-58fbba3c4cb1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20c29c3f295d4401b30bfeecc32d9df3aa532e16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282046"
---
# <a name="rosettanet-pips"></a><span data-ttu-id="8ced2-102">RosettaNet Pip</span><span class="sxs-lookup"><span data-stu-id="8ced2-102">RosettaNet PIPs</span></span>
<span data-ttu-id="8ced2-103">RosettaNet 组织创建并维护合作伙伴接口流程 (Pip) 提供通用的业务流程定义为所有 RosettaNet 消息交换。</span><span class="sxs-lookup"><span data-stu-id="8ced2-103">The RosettaNet organization creates and maintains Partner Interface Processes (PIPs) to provide common business-process definitions for all RosettaNet message exchanges.</span></span>  
  
 <span data-ttu-id="8ced2-104">每个 PIP 规范提供的文档类型定义 (DTD) 文件和消息指南文档。</span><span class="sxs-lookup"><span data-stu-id="8ced2-104">Each PIP specification provides a document type definition (DTD) file and a message guideline document.</span></span> <span data-ttu-id="8ced2-105">DTD 文件定义的服务内容消息结构。</span><span class="sxs-lookup"><span data-stu-id="8ced2-105">The DTD file defines the service-content message structure.</span></span> <span data-ttu-id="8ced2-106">消息指南文档，这是用户可读的 HTML 文件，指定了元素级的约束。</span><span class="sxs-lookup"><span data-stu-id="8ced2-106">The message-guideline document, which is a human-readable HTML file, specifies element-level constraints.</span></span> <span data-ttu-id="8ced2-107">同时，还提供业务流程的完整定义。</span><span class="sxs-lookup"><span data-stu-id="8ced2-107">Together, they provide a complete definition of the business process.</span></span>  
  
 <span data-ttu-id="8ced2-108">有关 PIP 规范的详细信息，请参阅 RosettaNet 网站下载，网址[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=33859)。</span><span class="sxs-lookup"><span data-stu-id="8ced2-108">For more information about PIP specifications, see the RosettaNet Web site at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=33859).</span></span>  
  
## <a name="pip-contents"></a><span data-ttu-id="8ced2-109">PIP 内容</span><span class="sxs-lookup"><span data-stu-id="8ced2-109">PIP Contents</span></span>  
 <span data-ttu-id="8ced2-110">PIP 规范将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ced2-110">A PIP specification does the following:</span></span>  
  
- <span data-ttu-id="8ced2-111">介绍了它实现了哪种公用流程模式</span><span class="sxs-lookup"><span data-stu-id="8ced2-111">Describes which public process pattern it implements</span></span>  
  
- <span data-ttu-id="8ced2-112">介绍如何配置公用流程</span><span class="sxs-lookup"><span data-stu-id="8ced2-112">Describes how to configure the public process</span></span>  
  
- <span data-ttu-id="8ced2-113">提供对 PIP 内进行交换的文档的引用</span><span class="sxs-lookup"><span data-stu-id="8ced2-113">Provides references to the documents to exchange within the PIP</span></span>  
  
  <span data-ttu-id="8ced2-114">PIP 规范包括三个主要部分： 业务操作视图 (BOV)、 功能服务视图 (FSV) 和实现框架视图 (IFV)。</span><span class="sxs-lookup"><span data-stu-id="8ced2-114">A PIP specification includes three major parts: a Business Operational View (BOV), Functional Service View (FSV), and an Implementation Framework View (IFV).</span></span> <span data-ttu-id="8ced2-115">每个视图指定了元素级的约束：</span><span class="sxs-lookup"><span data-stu-id="8ced2-115">Each of these views specifies element-level constraints:</span></span>  
  
- <span data-ttu-id="8ced2-116">BOV 指定了业务数据实体的语义和业务流程。</span><span class="sxs-lookup"><span data-stu-id="8ced2-116">The BOV specifies the semantics of business data entities and the business process flow.</span></span> <span data-ttu-id="8ced2-117">它介绍了开始和结束状态，以及合作伙伴的角色。</span><span class="sxs-lookup"><span data-stu-id="8ced2-117">It describes start and end states, and partner roles.</span></span> <span data-ttu-id="8ced2-118">它描述了角色，并详细信息安全、 审核和流程控制之间的交互。</span><span class="sxs-lookup"><span data-stu-id="8ced2-118">It describes the interaction between roles, and details security, audit, and process controls.</span></span> <span data-ttu-id="8ced2-119">它指定的业务文档和业务数据实体。</span><span class="sxs-lookup"><span data-stu-id="8ced2-119">It specifies the business documents and business data entities.</span></span>  
  
- <span data-ttu-id="8ced2-120">FSV 指定了网络组件服务、 代理和交互。</span><span class="sxs-lookup"><span data-stu-id="8ced2-120">The FSV specifies network component services, agents, and interactions.</span></span> <span data-ttu-id="8ced2-121">它提供了运行 Pip 所需的网络组件设计，并描述了可能的网络组件交互。</span><span class="sxs-lookup"><span data-stu-id="8ced2-121">It provides the network component design required to run the PIPs, and describes possible network component interactions.</span></span>  
  
- <span data-ttu-id="8ced2-122">IFV 指定网络协议消息格式和运行 PIP 所需的通信要求。</span><span class="sxs-lookup"><span data-stu-id="8ced2-122">The IFV specifies the network-protocol message formats and communication requirements required to run the PIP.</span></span>  
  
## <a name="clusters-and-segments"></a><span data-ttu-id="8ced2-123">群集和段</span><span class="sxs-lookup"><span data-stu-id="8ced2-123">Clusters and Segments</span></span>  
 <span data-ttu-id="8ced2-124">对 Pip 进行分类的高级业务功能 （群集） 和子功能 （段）。</span><span class="sxs-lookup"><span data-stu-id="8ced2-124">You categorize PIPs by a high-level business function (cluster) and a subfunction (segment).</span></span> <span data-ttu-id="8ced2-125">群集和段将业务消息组织成可识别的类别。</span><span class="sxs-lookup"><span data-stu-id="8ced2-125">Clusters and segments organize business messages into recognizable categories.</span></span> <span data-ttu-id="8ced2-126">下表列出了这些群集和段。</span><span class="sxs-lookup"><span data-stu-id="8ced2-126">The following table lists these clusters and segments.</span></span>  
  
|<span data-ttu-id="8ced2-127">Clusters</span><span class="sxs-lookup"><span data-stu-id="8ced2-127">Clusters</span></span>|<span data-ttu-id="8ced2-128">段</span><span class="sxs-lookup"><span data-stu-id="8ced2-128">Segments</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="8ced2-129">0：RosettaNet 支持</span><span class="sxs-lookup"><span data-stu-id="8ced2-129">0: RosettaNet Support</span></span>|<span data-ttu-id="8ced2-130">0A:管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-130">0A: Administrative</span></span><br /><br /> <span data-ttu-id="8ced2-131">0 C:正在测试</span><span class="sxs-lookup"><span data-stu-id="8ced2-131">0C: Testing</span></span>|  
|<span data-ttu-id="8ced2-132">1:合作伙伴的产品和服务审查</span><span class="sxs-lookup"><span data-stu-id="8ced2-132">1: Partner Product & Service Review</span></span>|<span data-ttu-id="8ced2-133">1A:合作伙伴审核</span><span class="sxs-lookup"><span data-stu-id="8ced2-133">1A: Partner Review</span></span><br /><br /> <span data-ttu-id="8ced2-134">1B:产品和服务审查</span><span class="sxs-lookup"><span data-stu-id="8ced2-134">1B: Product & Service Review</span></span>|  
|<span data-ttu-id="8ced2-135">2:产品信息</span><span class="sxs-lookup"><span data-stu-id="8ced2-135">2: Product Information</span></span>|<span data-ttu-id="8ced2-136">2A:准备分发</span><span class="sxs-lookup"><span data-stu-id="8ced2-136">2A: Preparation for Distribution</span></span><br /><br /> <span data-ttu-id="8ced2-137">2B:产品更改通知</span><span class="sxs-lookup"><span data-stu-id="8ced2-137">2B: Product Change Notification</span></span><br /><br /> <span data-ttu-id="8ced2-138">2C:产品设计信息</span><span class="sxs-lookup"><span data-stu-id="8ced2-138">2C: Product Design Information</span></span><br /><br /> <span data-ttu-id="8ced2-139">2D:协作设计和工程</span><span class="sxs-lookup"><span data-stu-id="8ced2-139">2D: Collaborative Design & Engineering</span></span>|  
|<span data-ttu-id="8ced2-140">3:订单管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-140">3: Order Management</span></span>|<span data-ttu-id="8ced2-141">3A:报价和订单录入</span><span class="sxs-lookup"><span data-stu-id="8ced2-141">3A: Quote & Order Entry</span></span><br /><br /> <span data-ttu-id="8ced2-142">3B:运输和分发</span><span class="sxs-lookup"><span data-stu-id="8ced2-142">3B: Transportation & Distribution</span></span><br /><br /> <span data-ttu-id="8ced2-143">3C:返回和金融</span><span class="sxs-lookup"><span data-stu-id="8ced2-143">3C: Returns & Finance</span></span><br /><br /> <span data-ttu-id="8ced2-144">3D:产品配置</span><span class="sxs-lookup"><span data-stu-id="8ced2-144">3D: Product Configuration</span></span>|  
|<span data-ttu-id="8ced2-145">4:库存管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-145">4: Inventory Management</span></span>|<span data-ttu-id="8ced2-146">4A:协作预测</span><span class="sxs-lookup"><span data-stu-id="8ced2-146">4A: Collaborative Forecasting</span></span><br /><br /> <span data-ttu-id="8ced2-147">4B:库存分配</span><span class="sxs-lookup"><span data-stu-id="8ced2-147">4B: Inventory Allocation</span></span><br /><br /> <span data-ttu-id="8ced2-148">4 C:清单报表</span><span class="sxs-lookup"><span data-stu-id="8ced2-148">4C: Inventory Reporting</span></span><br /><br /> <span data-ttu-id="8ced2-149">4D:库存补货</span><span class="sxs-lookup"><span data-stu-id="8ced2-149">4D: Inventory Replenishment</span></span><br /><br /> <span data-ttu-id="8ced2-150">4E:销售报告</span><span class="sxs-lookup"><span data-stu-id="8ced2-150">4E: Sales Reporting</span></span><br /><br /> <span data-ttu-id="8ced2-151">4F:价格保护</span><span class="sxs-lookup"><span data-stu-id="8ced2-151">4F: Price Protection</span></span>|  
|<span data-ttu-id="8ced2-152">5:市场营销信息管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-152">5: Marketing Information Management</span></span>|<span data-ttu-id="8ced2-153">5A:线索与机会管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-153">5A: Lead Opportunity Management</span></span><br /><br /> <span data-ttu-id="8ced2-154">图 5B:市场营销活动管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-154">5B: Marketing Campaign Management</span></span>|  
|<span data-ttu-id="8ced2-155">6:服务和支持</span><span class="sxs-lookup"><span data-stu-id="8ced2-155">6: Service and Support</span></span>|<span data-ttu-id="8ced2-156">6A:提供并管理保修、 服务包及合同服务</span><span class="sxs-lookup"><span data-stu-id="8ced2-156">6A: Provide and Administer Warranties, Service Packages, and Contract Services</span></span><br /><br /> <span data-ttu-id="8ced2-157">6B:提供并管理资产管理 （与 6a 结合）</span><span class="sxs-lookup"><span data-stu-id="8ced2-157">6B: Provide and Administer Asset Management (Merged with 6A)</span></span><br /><br /> <span data-ttu-id="8ced2-158">6 C:技术支持和服务管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-158">6C: Technical Support and Service Management</span></span>|  
|<span data-ttu-id="8ced2-159">7:生产</span><span class="sxs-lookup"><span data-stu-id="8ced2-159">7: Manufacturing</span></span>|<span data-ttu-id="8ced2-160">7A:传送设计</span><span class="sxs-lookup"><span data-stu-id="8ced2-160">7A: Design Transfer</span></span><br /><br /> <span data-ttu-id="8ced2-161">7B:管理制造 WO 与 WIP</span><span class="sxs-lookup"><span data-stu-id="8ced2-161">7B: Manage Manufacturing WO & WIP</span></span><br /><br /> <span data-ttu-id="8ced2-162">7 C:分发制造信息</span><span class="sxs-lookup"><span data-stu-id="8ced2-162">7C: Distribute Manufacturing Information</span></span>|  
  
 <span data-ttu-id="8ced2-163">每个段包括大量的特定的消息 Pip。</span><span class="sxs-lookup"><span data-stu-id="8ced2-163">Each segment includes a number of specific message PIPs.</span></span> <span data-ttu-id="8ced2-164">例如，3A4 PIP 是订单管理群集 (群集 3) 和报价与订单录入段 (群集 3 的段) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8ced2-164">For example, the 3A4 PIP is a part of the Order Management cluster (Cluster 3) and the Quote and Order Entry segment (Segment A of Cluster 3).</span></span> <span data-ttu-id="8ced2-165">此段包括其他相关的消息 Pip，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8ced2-165">This segment includes other related message PIPs, as follows:</span></span>  
  
 <span data-ttu-id="8ced2-166">群集 3:订单管理</span><span class="sxs-lookup"><span data-stu-id="8ced2-166">Cluster 3: Order Management</span></span>  
  
-   <span data-ttu-id="8ced2-167">段 a:报价与订单录入</span><span class="sxs-lookup"><span data-stu-id="8ced2-167">Segment A: Quote and Order Entry</span></span>  
  
    -   <span data-ttu-id="8ced2-168">PIP 3A1:请求报价</span><span class="sxs-lookup"><span data-stu-id="8ced2-168">PIP 3A1: Request Quote</span></span>  
  
    -   <span data-ttu-id="8ced2-169">PIP 3A2:请求价格与可用性</span><span class="sxs-lookup"><span data-stu-id="8ced2-169">PIP 3A2: Request Price and Availability</span></span>  
  
    -   <span data-ttu-id="8ced2-170">PIP 3A3:请求购物车传送</span><span class="sxs-lookup"><span data-stu-id="8ced2-170">PIP 3A3: Request Shopping Cart Transfer</span></span>  
  
    -   <span data-ttu-id="8ced2-171">PIP 3A4:管理采购订单</span><span class="sxs-lookup"><span data-stu-id="8ced2-171">PIP 3A4: Manage Purchase Order</span></span>  
  
    -   <span data-ttu-id="8ced2-172">PIP 3A5:查询订单状态</span><span class="sxs-lookup"><span data-stu-id="8ced2-172">PIP 3A5: Query Order Status</span></span>  
  
    -   <span data-ttu-id="8ced2-173">PIP 3A6:分配订单状态</span><span class="sxs-lookup"><span data-stu-id="8ced2-173">PIP 3A6: Distribute Order Status</span></span>  
  
    -   <span data-ttu-id="8ced2-174">…</span><span class="sxs-lookup"><span data-stu-id="8ced2-174">…</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ced2-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ced2-175">See Also</span></span>  
 <span data-ttu-id="8ced2-176">[RosettaNet 和 CIDX 标准消息传送](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="8ced2-176">[RosettaNet and CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/rosettanet-and-cidx-messaging-standards.md) </span></span>  
 [<span data-ttu-id="8ced2-177">RNIF 标准</span><span class="sxs-lookup"><span data-stu-id="8ced2-177">RNIF Standard</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/rnif-standard.md)