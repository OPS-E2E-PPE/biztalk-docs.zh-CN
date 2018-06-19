---
title: BizTalk Accelerator for SWIFT 运行时 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- runtime, architecture
- developing, components
- architecture, topology
- messages, message flow diagram
- runtime, components
- SWIFT runtime
- architecture, runtime architecture
- SWIFT network
- A4SWIFT, network
- topology
ms.assetid: c0f59760-7d7d-4b22-a7dc-54e563971d4a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 340cb27daf29e08ad63f20168680c6596650ca0d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005278"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a><span data-ttu-id="4f350-102">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="4f350-102">BizTalk Accelerator for SWIFT Runtime</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="4f350-103">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]在两种形式提供的功能： 开发材料和运行时组件。</span><span class="sxs-lookup"><span data-stu-id="4f350-103"> [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides functionality in two forms: development materials and runtime components.</span></span> <span data-ttu-id="4f350-104">开发资料包括 XSD 架构，验证规则和策略，以及示例代码。</span><span class="sxs-lookup"><span data-stu-id="4f350-104">Development materials include XSD schemas, validation rules and policies, and sample code.</span></span> <span data-ttu-id="4f350-105">运行时组件包括自定义 SWIFT 反汇编程序、 自定义 SWIFT 汇编程序、 消息修复和新提交业务流程 (MrsrRepair.odx) 和 FIN 响应对帐业务流程 (FrrMain.odx)。</span><span class="sxs-lookup"><span data-stu-id="4f350-105">Runtime components include the custom SWIFT disassembler, the custom SWIFT assembler, the Message Repair and New Submission orchestration (MrsrRepair.odx), and the FIN Response Reconciliation orchestration (FrrMain.odx).</span></span> <span data-ttu-id="4f350-106">有关消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="4f350-106">For more information on Message Repair and New Submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span> <span data-ttu-id="4f350-107">FRR 的详细信息，请参阅[FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)。</span><span class="sxs-lookup"><span data-stu-id="4f350-107">For more information on FRR, see [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span></span>  
  
 <span data-ttu-id="4f350-108">下图显示了高级系统体系结构[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4f350-108">The following figure shows the high-level system architecture of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  
  
 <span data-ttu-id="4f350-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span><span class="sxs-lookup"><span data-stu-id="4f350-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span></span>  
  
 <span data-ttu-id="4f350-110">下图说明如何将消息流之间 A4SWIFT 和后端应用程序，以及如何 A4SWIFT 使用[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]MRSR 中的窗体站点消息修复和新的提交。</span><span class="sxs-lookup"><span data-stu-id="4f350-110">The following figure illustrates how messages flow between A4SWIFT and a back-end application, and how A4SWIFT uses [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms in MRSR site for Message Repair and New Submission.</span></span>  
  
 <span data-ttu-id="4f350-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span><span class="sxs-lookup"><span data-stu-id="4f350-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span></span>  
  
 <span data-ttu-id="4f350-112">下图说明了消息 A4SWIFT 和 SWIFT 网络之间的流动方式。</span><span class="sxs-lookup"><span data-stu-id="4f350-112">The following figure illustrates how messages flow between A4SWIFT and the SWIFT Network.</span></span>  
  
 <span data-ttu-id="4f350-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span><span class="sxs-lookup"><span data-stu-id="4f350-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span></span>  
  
 <span data-ttu-id="4f350-114">你可以定义所有 A4SWIFT 组件为 BizTalk Server 应用程序组件的垂直特定的实现。</span><span class="sxs-lookup"><span data-stu-id="4f350-114">You can define all A4SWIFT components as vertical-specific implementations of BizTalk Server application components.</span></span> <span data-ttu-id="4f350-115">BizTalk 加速器提供开发和运行时功能，以加速垂直特定 BizTalk 应用程序开发的顶部[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4f350-115">BizTalk accelerators provide development and runtime functionality to accelerate vertical-specific BizTalk application development on top of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4f350-116">因此，所有 A4SWIFT 组件 （开发或运行时） 遵守，并且放入 BizTalk Server 应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="4f350-116">Therefore, all A4SWIFT components (development or runtime) abide by, and fit into, the BizTalk Server application architecture.</span></span> <span data-ttu-id="4f350-117">A4SWIFT 安装运行时组件都进入[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为自定义组件的运行时。</span><span class="sxs-lookup"><span data-stu-id="4f350-117">A4SWIFT installs runtime components into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime as custom components.</span></span> <span data-ttu-id="4f350-118">编译并部署，A4SWIFT 材料后开发和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]运行时使用它们来提供消息传送和自动化功能的 SWIFT。</span><span class="sxs-lookup"><span data-stu-id="4f350-118">After development materials are compiled and deployed, A4SWIFT and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime use them to provide SWIFT messaging and automation functionality.</span></span>  
  
 <span data-ttu-id="4f350-119">下图显示了有关 BizTalk Server 的高级应用程序拓扑。</span><span class="sxs-lookup"><span data-stu-id="4f350-119">The following figure shows the high-level application topology for BizTalk Server.</span></span>  
  
 <span data-ttu-id="4f350-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span><span class="sxs-lookup"><span data-stu-id="4f350-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span></span>  
  
 <span data-ttu-id="4f350-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型使用 MessageBox 数据库和控制消息流执行和跳出执行 MessageBox 数据库的发布服务器订阅服务器模式。</span><span class="sxs-lookup"><span data-stu-id="4f350-121">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model uses the MessageBox database and the publisher-subscriber pattern that governs message flow into and out of the MessageBox database.</span></span> <span data-ttu-id="4f350-122">有关 BizTalk 体系结构和应用程序设计的详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="4f350-122">For more information about BizTalk architecture and application design, see BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="4f350-123">A4SWIFT 应用程序模型继承[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型并向其中添加 SWIFT 特定组件，用于改进 SWIFT 相关解决方案，在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4f350-123">The A4SWIFT application model inherits the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model and adds to it SWIFT-specific components to facilitate SWIFT-related solutions on [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="4f350-124">以下列表介绍了这些 A4SWIFT 特定组件：</span><span class="sxs-lookup"><span data-stu-id="4f350-124">The following list describes these A4SWIFT-specific components:</span></span>  
  
-   <span data-ttu-id="4f350-125">**运行时组件。**</span><span class="sxs-lookup"><span data-stu-id="4f350-125">**Runtime components.**</span></span> <span data-ttu-id="4f350-126">接收管道、 发送管道、 消息修复和新提交业务流程和 FIN 响应对帐业务流程中的 SWIFT 汇编程序 SWIFT 反汇编程序。</span><span class="sxs-lookup"><span data-stu-id="4f350-126">SWIFT disassembler in the receive pipeline, SWIFT assembler in the send pipeline, Message Repair and New Submission orchestration, and FIN Response Reconciliation orchestration.</span></span>  
  
-   <span data-ttu-id="4f350-127">**开发材料。**</span><span class="sxs-lookup"><span data-stu-id="4f350-127">**Development materials.**</span></span> <span data-ttu-id="4f350-128">SWIFT 架构、 规则、 业务流程和示例项目以在客户解决方案中包含与部署到的运行时执行。</span><span class="sxs-lookup"><span data-stu-id="4f350-128">SWIFT schemas, rules, orchestrations, and sample projects to be included in customer solutions and deployed onto the runtime for execution.</span></span>  
  
 <span data-ttu-id="4f350-129">本部分介绍详细信息中的 A4SWIFT 运行时。</span><span class="sxs-lookup"><span data-stu-id="4f350-129">This section describes the A4SWIFT runtime in detail.</span></span>  
  
 <span data-ttu-id="4f350-130">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="4f350-130">This section contains:</span></span>  
  
-   [<span data-ttu-id="4f350-131">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="4f350-131">SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  
  
-   [<span data-ttu-id="4f350-132">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="4f350-132">SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  
  
-   [<span data-ttu-id="4f350-133">通过接收位置和 InfoPath 表单提交消息</span><span class="sxs-lookup"><span data-stu-id="4f350-133">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  
  
-   [<span data-ttu-id="4f350-134">消息验证引擎</span><span class="sxs-lookup"><span data-stu-id="4f350-134">Message Validation Engine</span></span>](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)