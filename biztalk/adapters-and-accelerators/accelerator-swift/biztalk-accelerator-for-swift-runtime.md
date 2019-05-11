---
title: BizTalk Accelerator for SWIFT 运行时 |Microsoft Docs
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
ms.openlocfilehash: 946bd3fa788f3d133e509c905e86178a94d0c5e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378892"
---
# <a name="biztalk-accelerator-for-swift-runtime"></a><span data-ttu-id="da1bb-102">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="da1bb-102">BizTalk Accelerator for SWIFT Runtime</span></span>
<span data-ttu-id="da1bb-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提供了两种形式的功能： 开发材料和运行时组件。</span><span class="sxs-lookup"><span data-stu-id="da1bb-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] provides functionality in two forms: development materials and runtime components.</span></span> <span data-ttu-id="da1bb-104">开发材料包括 XSD 架构、 验证规则和策略和示例代码。</span><span class="sxs-lookup"><span data-stu-id="da1bb-104">Development materials include XSD schemas, validation rules and policies, and sample code.</span></span> <span data-ttu-id="da1bb-105">运行时组件包括自定义的 SWIFT 反汇编程序、 自定义的 SWIFT 汇编程序、 消息修复和新提交业务流程 (MrsrRepair.odx) 和 FIN 响应对帐业务流程 (FrrMain.odx)。</span><span class="sxs-lookup"><span data-stu-id="da1bb-105">Runtime components include the custom SWIFT disassembler, the custom SWIFT assembler, the Message Repair and New Submission orchestration (MrsrRepair.odx), and the FIN Response Reconciliation orchestration (FrrMain.odx).</span></span> <span data-ttu-id="da1bb-106">消息修复和新提交的详细信息，请参阅[消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)。</span><span class="sxs-lookup"><span data-stu-id="da1bb-106">For more information on Message Repair and New Submission, see [Message Repair and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md).</span></span> <span data-ttu-id="da1bb-107">FRR 的详细信息，请参阅[FIN 响应对帐](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md)。</span><span class="sxs-lookup"><span data-stu-id="da1bb-107">For more information on FRR, see [FIN Response Reconciliation](../../adapters-and-accelerators/accelerator-swift/fin-response-reconciliation.md).</span></span>  

 <span data-ttu-id="da1bb-108">下图显示的高级系统体系结构[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da1bb-108">The following figure shows the high-level system architecture of [!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)].</span></span>  

 <span data-ttu-id="da1bb-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span><span class="sxs-lookup"><span data-stu-id="da1bb-109">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-end-to-end.gif "A4SWIFTSystemArchitecture_End_to_End")</span></span>  

 <span data-ttu-id="da1bb-110">下图说明消息 A4SWIFT 和后端应用程序之间的流动方式以及如何使用 A4SWIFT [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR 中的窗体站点用于消息修复和新提交。</span><span class="sxs-lookup"><span data-stu-id="da1bb-110">The following figure illustrates how messages flow between A4SWIFT and a back-end application, and how A4SWIFT uses [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] forms in MRSR site for Message Repair and New Submission.</span></span>  

 <span data-ttu-id="da1bb-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span><span class="sxs-lookup"><span data-stu-id="da1bb-111">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswithbackendapplications.gif "A4SWIFTSystemArchitecture_InterfaceswithBackEndApplications")</span></span>  

 <span data-ttu-id="da1bb-112">下图说明了消息 A4SWIFT 和 SWIFT 网络之间的流动方式。</span><span class="sxs-lookup"><span data-stu-id="da1bb-112">The following figure illustrates how messages flow between A4SWIFT and the SWIFT Network.</span></span>  

 <span data-ttu-id="da1bb-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span><span class="sxs-lookup"><span data-stu-id="da1bb-113">![](../../adapters-and-accelerators/accelerator-swift/media/a4swiftsystemarchitecture-interfaceswiththeswiftnetwork.gif "A4SWIFTSystemArchitecture_InterfaceswiththeSWIFTNetwork")</span></span>  

 <span data-ttu-id="da1bb-114">您可以定义所有 A4SWIFT 组件为 BizTalk Server 应用程序组件的特定于垂直的实现。</span><span class="sxs-lookup"><span data-stu-id="da1bb-114">You can define all A4SWIFT components as vertical-specific implementations of BizTalk Server application components.</span></span> <span data-ttu-id="da1bb-115">BizTalk 加速器提供了开发和运行时功能，以加速的顶部垂直特定于 BizTalk 应用程序开发[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da1bb-115">BizTalk accelerators provide development and runtime functionality to accelerate vertical-specific BizTalk application development on top of [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="da1bb-116">因此，所有 A4SWIFT 组件 （开发或运行时） 遵守，并放入 BizTalk Server 应用程序体系结构。</span><span class="sxs-lookup"><span data-stu-id="da1bb-116">Therefore, all A4SWIFT components (development or runtime) abide by, and fit into, the BizTalk Server application architecture.</span></span> <span data-ttu-id="da1bb-117">A4SWIFT 安装到运行时组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为自定义组件的运行时。</span><span class="sxs-lookup"><span data-stu-id="da1bb-117">A4SWIFT installs runtime components into the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime as custom components.</span></span> <span data-ttu-id="da1bb-118">编译并部署 A4SWIFT 材料后开发和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]运行时使用它们来提供 SWIFT 消息传送和自动化功能。</span><span class="sxs-lookup"><span data-stu-id="da1bb-118">After development materials are compiled and deployed, A4SWIFT and the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] runtime use them to provide SWIFT messaging and automation functionality.</span></span>  

 <span data-ttu-id="da1bb-119">下图显示了 BizTalk server 的高级别应用程序拓扑。</span><span class="sxs-lookup"><span data-stu-id="da1bb-119">The following figure shows the high-level application topology for BizTalk Server.</span></span>  

 <span data-ttu-id="da1bb-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span><span class="sxs-lookup"><span data-stu-id="da1bb-120">![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro1.gif "FSA_Intro1")</span></span>  

 <span data-ttu-id="da1bb-121">[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型使用 MessageBox 数据库和控制消息流入和流出 MessageBox 数据库的发布服务器订阅服务器模式。</span><span class="sxs-lookup"><span data-stu-id="da1bb-121">The [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model uses the MessageBox database and the publisher-subscriber pattern that governs message flow into and out of the MessageBox database.</span></span> <span data-ttu-id="da1bb-122">有关 BizTalk 体系结构和应用程序设计的详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="da1bb-122">For more information about BizTalk architecture and application design, see BizTalk Server Help.</span></span>  

 <span data-ttu-id="da1bb-123">A4SWIFT 应用程序模型继承[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序模型并向其添加特定于 SWIFT 的组件，以便与 SWIFT 相关的解决方案上[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da1bb-123">The A4SWIFT application model inherits the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] application model and adds to it SWIFT-specific components to facilitate SWIFT-related solutions on [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="da1bb-124">以下列表介绍了这些特定于 A4SWIFT 的组件：</span><span class="sxs-lookup"><span data-stu-id="da1bb-124">The following list describes these A4SWIFT-specific components:</span></span>  

- <span data-ttu-id="da1bb-125">**运行时组件。**</span><span class="sxs-lookup"><span data-stu-id="da1bb-125">**Runtime components.**</span></span> <span data-ttu-id="da1bb-126">SWIFT 反汇编程序中的接收管道、 SWIFT 汇编程序发送管道、 消息修复和新提交业务流程和 FIN 响应对帐业务流程中。</span><span class="sxs-lookup"><span data-stu-id="da1bb-126">SWIFT disassembler in the receive pipeline, SWIFT assembler in the send pipeline, Message Repair and New Submission orchestration, and FIN Response Reconciliation orchestration.</span></span>  

- <span data-ttu-id="da1bb-127">**开发材料。**</span><span class="sxs-lookup"><span data-stu-id="da1bb-127">**Development materials.**</span></span> <span data-ttu-id="da1bb-128">SWIFT 架构、 规则、 业务流程和示例项目包含在客户解决方案中并部署到执行的运行时上。</span><span class="sxs-lookup"><span data-stu-id="da1bb-128">SWIFT schemas, rules, orchestrations, and sample projects to be included in customer solutions and deployed onto the runtime for execution.</span></span>  

  <span data-ttu-id="da1bb-129">本部分介绍详细信息中的 A4SWIFT 运行时。</span><span class="sxs-lookup"><span data-stu-id="da1bb-129">This section describes the A4SWIFT runtime in detail.</span></span>  

  <span data-ttu-id="da1bb-130">本部分包含：</span><span class="sxs-lookup"><span data-stu-id="da1bb-130">This section contains:</span></span>  

- [<span data-ttu-id="da1bb-131">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="da1bb-131">SWIFT Disassembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-disassembler.md)  

- [<span data-ttu-id="da1bb-132">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="da1bb-132">SWIFT Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/swift-assembler.md)  

- [<span data-ttu-id="da1bb-133">通过接收位置和 InfoPath 表单提交消息</span><span class="sxs-lookup"><span data-stu-id="da1bb-133">Submitting Messages Through Receive Locations and InfoPath Forms</span></span>](../../adapters-and-accelerators/accelerator-swift/submitting-messages-through-receive-locations-and-infopath-forms.md)  

- [<span data-ttu-id="da1bb-134">消息验证引擎</span><span class="sxs-lookup"><span data-stu-id="da1bb-134">Message Validation Engine</span></span>](../../adapters-and-accelerators/accelerator-swift/message-validation-engine.md)
