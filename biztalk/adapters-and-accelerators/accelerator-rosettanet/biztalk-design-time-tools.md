---
title: BizTalk 设计时工具 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- schemas, tools
- BizTalk Orchestration Designer
- schemas, BTARN schemas
- BizTalk Editor
- BizTalk Mapper
- tools, schemas
- BTARN, schemas
- BizTalk Pipeline Designer
ms.assetid: a981e167-f178-4fef-be0e-02fa15feffc2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f259167112ab87da5af14ca73f735ae38d8789e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006622"
---
# <a name="biztalk-design-time-tools"></a><span data-ttu-id="567b6-102">BizTalk 设计时工具</span><span class="sxs-lookup"><span data-stu-id="567b6-102">BizTalk Design-Time Tools</span></span>
<span data-ttu-id="567b6-103">开发人员处理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ，可以使用 BizTalk Server 中内置的设计时工具集。</span><span class="sxs-lookup"><span data-stu-id="567b6-103">Developers working on [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] can use the set of design-time tools built into BizTalk Server.</span></span> <span data-ttu-id="567b6-104">这些工具集成到[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="567b6-104">These tools are integrated into [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].</span></span> <span data-ttu-id="567b6-105">有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具，请参阅[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="567b6-105">For more information about [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools, see [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server Help.</span></span>  
  
## <a name="biztalk-editor"></a><span data-ttu-id="567b6-106">BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="567b6-106">BizTalk Editor</span></span>  
 <span data-ttu-id="567b6-107">使用 BizTalk 编辑器来管理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]RosettaNet 合作伙伴接口进程 (Pip) 基于的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="567b6-107">You use BizTalk Editor to manage [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] XSD schemas that are based on RosettaNet Partner Interface Processes (PIPs).</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="567b6-108">安装解决方案开发的以下架构：</span><span class="sxs-lookup"><span data-stu-id="567b6-108"> installs the following schemas for your solution development:</span></span>  
  
-   <span data-ttu-id="567b6-109">0A1_FailureNotificationPropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-109">0A1_FailureNotificationPropertySchema.xsd</span></span>  
  
-   <span data-ttu-id="567b6-110">0A1_MS_V02_00_FailureNotification.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-110">0A1_MS_V02_00_FailureNotification.xsd</span></span>  
  
-   <span data-ttu-id="567b6-111">0A1_V1_FailureNotificationMessageGuideline.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-111">0A1_V1_FailureNotificationMessageGuideline.xsd</span></span>  
  
-   <span data-ttu-id="567b6-112">0C1_MS_R01_02_AsynchronousTestNotification.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-112">0C1_MS_R01_02_AsynchronousTestNotification.xsd</span></span>  
  
-   <span data-ttu-id="567b6-113">0C2_MS_R01_02_AsynchronousTestConfirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-113">0C2_MS_R01_02_AsynchronousTestConfirmation.xsd</span></span>  
  
-   <span data-ttu-id="567b6-114">0C2_MS_R01_02_AsynchronousTestRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-114">0C2_MS_R01_02_AsynchronousTestRequest.xsd</span></span>  
  
-   <span data-ttu-id="567b6-115">0C3_MS_R01_02_SynchronousTestNotification.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-115">0C3_MS_R01_02_SynchronousTestNotification.xsd</span></span>  
  
-   <span data-ttu-id="567b6-116">0C4_MS_R01_02_SynchronousTestQuery.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-116">0C4_MS_R01_02_SynchronousTestQuery.xsd</span></span>  
  
-   <span data-ttu-id="567b6-117">0C4_MS_R01_02_SynchronousTestResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-117">0C4_MS_R01_02_SynchronousTestResponse.xsd</span></span>  
  
-   <span data-ttu-id="567b6-118">2A12_MS_V01_03_ProductMasterNotification.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-118">2A12_MS_V01_03_ProductMasterNotification.xsd</span></span>  
  
-   <span data-ttu-id="567b6-119">3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-119">3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.xsd</span></span>  
  
-   <span data-ttu-id="567b6-120">3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-120">3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.xsd</span></span>  
  
-   <span data-ttu-id="567b6-121">3A4_MS_V02_02_PurchaseOrderConfirmation.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-121">3A4_MS_V02_02_PurchaseOrderConfirmation.xsd</span></span>  
  
-   <span data-ttu-id="567b6-122">3A4_MS_V02_02_PurchaseOrderRequest.xsd</span><span class="sxs-lookup"><span data-stu-id="567b6-122">3A4_MS_V02_02_PurchaseOrderRequest.xsd</span></span>  
  
 <span data-ttu-id="567b6-123">这些架构位于\<*驱动器*\>: \Program Files\\ [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk\<版本\>RosettaNet\SDK\Schemas 快捷键。</span><span class="sxs-lookup"><span data-stu-id="567b6-123">These schemas are available at \<*drive*\>:\Program Files\\[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk \<version\> Accelerator for RosettaNet\SDK\Schemas.</span></span>  
  
 <span data-ttu-id="567b6-124">你可以通过从 RosettaNet Web 站点下载 Pip 添加多个架构[http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859)。</span><span class="sxs-lookup"><span data-stu-id="567b6-124">You can add more schemas by downloading PIPs from the RosettaNet Web site at [http://go.microsoft.com/fwlink/?linkid=33859](http://go.microsoft.com/fwlink/?linkid=33859).</span></span> <span data-ttu-id="567b6-125">有关详细信息，请参阅[合并新的合作伙伴接口进程](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)。</span><span class="sxs-lookup"><span data-stu-id="567b6-125">For more information, see [Incorporating a New Partner Interface Process](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md).</span></span>  
  
## <a name="biztalk-mapper"></a><span data-ttu-id="567b6-126">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="567b6-126">BizTalk Mapper</span></span>  
 <span data-ttu-id="567b6-127">你可以使用 BizTalk 映射器来创建并自定义用以定义数据转换的映射。</span><span class="sxs-lookup"><span data-stu-id="567b6-127">You use BizTalk Mapper to create and customize maps that define data transformations.</span></span> <span data-ttu-id="567b6-128">还可以使用 BizTalk 映射器来映射入站和出站 RosettaNet 消息类型的转换。</span><span class="sxs-lookup"><span data-stu-id="567b6-128">You use BizTalk Mapper to map transformations for both inbound and outbound RosettaNet message types.</span></span>  
  
## <a name="biztalk-orchestration-designer"></a><span data-ttu-id="567b6-129">BizTalk 业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="567b6-129">BizTalk Orchestration Designer</span></span>  
 <span data-ttu-id="567b6-130">你可以使用 BizTalk 业务流程设计器来设计和实现业务流程。</span><span class="sxs-lookup"><span data-stu-id="567b6-130">You use BizTalk Orchestration Designer to design and implement business processes.</span></span> <span data-ttu-id="567b6-131">还可以自定义 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 中提供的专用流程。</span><span class="sxs-lookup"><span data-stu-id="567b6-131">You can customize the private processes provided in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK.</span></span> <span data-ttu-id="567b6-132">有关详细信息，请参阅[私有进程 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)和[自定义私有进程 &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/customizing-private-processes.md).</span><span class="sxs-lookup"><span data-stu-id="567b6-132">For more information, see [Private Processes &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) and [Customizing Private Processes &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/customizing-private-processes.md).</span></span> <span data-ttu-id="567b6-133">你不能自定义公用流程，否则将破坏公用流程的 RosettaNet 兼容性。</span><span class="sxs-lookup"><span data-stu-id="567b6-133">You cannot customize public processes; doing this would invalidate their RosettaNet compliance.</span></span>  
  
## <a name="biztalk-pipeline-designer"></a><span data-ttu-id="567b6-134">BizTalk 管道设计器</span><span class="sxs-lookup"><span data-stu-id="567b6-134">BizTalk Pipeline Designer</span></span>  
 <span data-ttu-id="567b6-135">你可以使用 BizTalk 管道设计器来创建和配置用以定义和链接消息处理步骤的管道。</span><span class="sxs-lookup"><span data-stu-id="567b6-135">You use BizTalk Pipeline Designer to create and configure the pipelines that define and link message-processing steps.</span></span> <span data-ttu-id="567b6-136">管道将消息处理分为不同的阶段，并确定执行每类工作的顺序。</span><span class="sxs-lookup"><span data-stu-id="567b6-136">Pipelines divide message processing into stages, and determine the sequence in which you perform each category of work.</span></span>  
  
 <span data-ttu-id="567b6-137">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括接收 RosettaNet 实现框架 (RNIF) 管道和传输 RosettaNet 实现框架 (RNIF) 管道。</span><span class="sxs-lookup"><span data-stu-id="567b6-137">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes both receive and transmit RosettaNet Implementation Framework (RNIF) pipelines.</span></span> <span data-ttu-id="567b6-138">有关详细信息，请参阅[RNIF 管道](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md)。</span><span class="sxs-lookup"><span data-stu-id="567b6-138">For more information, see [RNIF Pipelines](../../adapters-and-accelerators/accelerator-rosettanet/rnif-pipelines.md).</span></span>  
  
## <a name="biztalk-adapter-framework"></a><span data-ttu-id="567b6-139">BizTalk 适配器框架</span><span class="sxs-lookup"><span data-stu-id="567b6-139">BizTalk Adapter Framework</span></span>  
 <span data-ttu-id="567b6-140">你可以使用带有终结点适配器的 BizTalk 适配器框架与合作伙伴及应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="567b6-140">You use the BizTalk Adapter Framework with end-point adapters to integrate with partners and applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="567b6-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="567b6-141">See Also</span></span>  
 <span data-ttu-id="567b6-142">[工具和功能的 BizTalk Server 和 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/tools-and-features-of-biztalk-server-and-btarn.md) </span><span class="sxs-lookup"><span data-stu-id="567b6-142">[Tools and Features of BizTalk Server and BTARN](../../adapters-and-accelerators/accelerator-rosettanet/tools-and-features-of-biztalk-server-and-btarn.md) </span></span>  
 <span data-ttu-id="567b6-143">[管理和运行时工具](../../adapters-and-accelerators/accelerator-rosettanet/administration-and-run-time-tools.md) </span><span class="sxs-lookup"><span data-stu-id="567b6-143">[Administration and Run-Time Tools](../../adapters-and-accelerators/accelerator-rosettanet/administration-and-run-time-tools.md) </span></span>  
 <span data-ttu-id="567b6-144">[分析工具](../../adapters-and-accelerators/accelerator-rosettanet/analysis-tools1.md) </span><span class="sxs-lookup"><span data-stu-id="567b6-144">[Analysis Tools](../../adapters-and-accelerators/accelerator-rosettanet/analysis-tools1.md) </span></span>  
 [<span data-ttu-id="567b6-145">并入新的合作伙伴接口流程</span><span class="sxs-lookup"><span data-stu-id="567b6-145">Incorporating a New Partner Interface Process</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/incorporating-a-new-partner-interface-process.md)