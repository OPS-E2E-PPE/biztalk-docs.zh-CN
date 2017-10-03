---
title: "设计时工具 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Adapter Framework
- BTAHL7, tools
- Starter Project
- Pipeline Designer
- BizTalk Editor
- Visual Studio Starter Project
- BizTalk Mapper
- design-time tools
- Orchestration Designer
ms.assetid: 709bd782-d2ad-49be-ba33-e957eba2a0cc
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e22272fd04dd3bf2461e4b9fef104657cf007fbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="design-time-tools"></a><span data-ttu-id="24d06-102">设计时工具</span><span class="sxs-lookup"><span data-stu-id="24d06-102">Design Time Tools</span></span>
<span data-ttu-id="24d06-103">开发人员处理[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 具有一套内置的设计时工具使用[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24d06-103">Developers working on [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) have the use of a set of design time tools built into [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="24d06-104">这些工具集成到[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="24d06-104">These tools are integrated into [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="24d06-105">有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]工具，请参阅[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="24d06-105">For more information about [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] tools, see [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
## <a name="biztalk-editor"></a><span data-ttu-id="24d06-106">BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="24d06-106">BizTalk Editor</span></span>  
 <span data-ttu-id="24d06-107">使用 BizTalk 编辑器来管理 HL7 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-107">You use BizTalk Editor to manage HL7 XSD schemas.</span></span> <span data-ttu-id="24d06-108">为你解决方案的开发，可以使用以下的支持的架构模板 （为 XSD 文件）：</span><span class="sxs-lookup"><span data-stu-id="24d06-108">You can use the following supported schema templates (as XSD files) for your solution development:</span></span>  
  
-   <span data-ttu-id="24d06-109">HL7: 2.1 （包括 37 事件）</span><span class="sxs-lookup"><span data-stu-id="24d06-109">HL7: 2.1 (includes 37 events)</span></span>  
  
-   <span data-ttu-id="24d06-110">HL7: 2.2 （包括 56 事件）</span><span class="sxs-lookup"><span data-stu-id="24d06-110">HL7: 2.2 (includes 56 events)</span></span>  
  
-   <span data-ttu-id="24d06-111">HL7: 2.3 （包括 182 事件）</span><span class="sxs-lookup"><span data-stu-id="24d06-111">HL7: 2.3 (includes 182 events)</span></span>  
  
-   <span data-ttu-id="24d06-112">HL7: 2.3.1 （包括 189 事件）</span><span class="sxs-lookup"><span data-stu-id="24d06-112">HL7: 2.3.1 (includes 189 events)</span></span>  
  
-   <span data-ttu-id="24d06-113">HL7: 2.4 （包括 288 事件）</span><span class="sxs-lookup"><span data-stu-id="24d06-113">HL7: 2.4 (includes 288 events)</span></span>  
  
-   <span data-ttu-id="24d06-114">HL7: 2.5 （包括大约 390 架构）</span><span class="sxs-lookup"><span data-stu-id="24d06-114">HL7: 2.5 (includes approximately 390 schemas)</span></span>  
  
-   <span data-ttu-id="24d06-115">HL7: 2.（V2.3.1 和 2.4 包括大约 450 架构） 的 XML</span><span class="sxs-lookup"><span data-stu-id="24d06-115">HL7: 2.XML (includes approximately 450 schemas for V2.3.1 and 2.4)</span></span>  
  
## <a name="biztalk-mapper"></a><span data-ttu-id="24d06-116">BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="24d06-116">BizTalk Mapper</span></span>  
 <span data-ttu-id="24d06-117">你可以使用 BizTalk 映射器来创建并自定义用以定义数据转换的映射。</span><span class="sxs-lookup"><span data-stu-id="24d06-117">You use BizTalk Mapper to create and customize maps that define data transformations.</span></span> <span data-ttu-id="24d06-118">使用 BizTalk 映射程序将转换为入站和出站映射[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息类型。</span><span class="sxs-lookup"><span data-stu-id="24d06-118">You use BizTalk Mapper to map transformations for both inbound and outbound [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] message types.</span></span>  
  
## <a name="biztalk-orchestration-designer"></a><span data-ttu-id="24d06-119">BizTalk 业务流程设计器</span><span class="sxs-lookup"><span data-stu-id="24d06-119">BizTalk Orchestration Designer</span></span>  
 <span data-ttu-id="24d06-120">你可以使用 BizTalk 业务流程设计器来设计和实现业务流程。</span><span class="sxs-lookup"><span data-stu-id="24d06-120">You use BizTalk Orchestration Designer to design and implement business processes.</span></span>  
  
## <a name="biztalk-pipeline-designer"></a><span data-ttu-id="24d06-121">BizTalk 管道设计器</span><span class="sxs-lookup"><span data-stu-id="24d06-121">BizTalk Pipeline Designer</span></span>  
 <span data-ttu-id="24d06-122">使用 BizTalk 管道设计器创建和配置定义管道和处理步骤的链接。</span><span class="sxs-lookup"><span data-stu-id="24d06-122">You use BizTalk Pipeline Designer to create and configure the pipelines that define and link processing steps.</span></span> <span data-ttu-id="24d06-123">管道将处理到阶段，并确定在其中执行工作的每个类别的顺序。</span><span class="sxs-lookup"><span data-stu-id="24d06-123">Pipelines divide processing into stages, and determine the sequence in which you perform each category of work.</span></span>  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-124">提供同时接收和发送针对所有支持的 HL7 版本的管道。</span><span class="sxs-lookup"><span data-stu-id="24d06-124"> provides both receive and transmit pipelines for all supported HL7 versions.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-125">提供了一个具有自定义的 HL7 分析器和反汇编程序/汇编程序组件的管道模板。</span><span class="sxs-lookup"><span data-stu-id="24d06-125"> provides a pipeline template that has a custom HL7 parser and disassembler/assembler component.</span></span>  
  
## <a name="biztalk-adapter-framework"></a><span data-ttu-id="24d06-126">BizTalk 适配器框架</span><span class="sxs-lookup"><span data-stu-id="24d06-126">BizTalk Adapter Framework</span></span>  
 <span data-ttu-id="24d06-127">你可以使用带有终结点适配器的 BizTalk 适配器框架与合作伙伴及应用程序集成。</span><span class="sxs-lookup"><span data-stu-id="24d06-127">You use the BizTalk Adapter Framework with end-point adapters to integrate with partners and applications.</span></span>  
  
## <a name="visual-studio-starter-project"></a><span data-ttu-id="24d06-128">Visual Studio 初学者项目</span><span class="sxs-lookup"><span data-stu-id="24d06-128">Visual Studio Starter Project</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-129">包括[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]初学者项目，你可以使用该快速入门 HL7 解决方案实现。</span><span class="sxs-lookup"><span data-stu-id="24d06-129"> includes the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Starter Project, which you can use to quick-start your HL7 solution implementation.</span></span> <span data-ttu-id="24d06-130">初学者项目包括以下项目：</span><span class="sxs-lookup"><span data-stu-id="24d06-130">The Starter Project includes the following projects:</span></span>  
  
-   <span data-ttu-id="24d06-131">**空**[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]**项目**。    </span><span class="sxs-lookup"><span data-stu-id="24d06-131">**Empty**  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]  **Project**.</span></span> <span data-ttu-id="24d06-132">不包括任何架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-132">Does not include any schemas.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-133">**V2XCommon 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-133"> **V2XCommon Project**.</span></span> <span data-ttu-id="24d06-134">包括标头和确认架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-134">Includes header and acknowledgment schemas.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-135">**V21Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-135"> **V21Common Project**.</span></span> <span data-ttu-id="24d06-136">包括用于 HL7 版本 2.1 的通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-136">Includes common schemas for HL7 version 2.1.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-137">**V22Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-137"> **V22Common Project**.</span></span> <span data-ttu-id="24d06-138">包括 HL7 版本 2.2 的通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-138">Includes common schemas for HL7 version 2.2.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-139">**V23Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-139"> **V23Common Project**.</span></span> <span data-ttu-id="24d06-140">包括 HL7 版本 2.3 通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-140">Includes common schemas for HL7 version 2.3.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-141">**V231Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-141"> **V231Common Project**.</span></span> <span data-ttu-id="24d06-142">包括 HL7 版本 2.3.1 的通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-142">Includes common schemas for HL7 version 2.3.1.</span></span>  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="24d06-143">**V24Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-143"> **V24Common Project**.</span></span> <span data-ttu-id="24d06-144">包括 HL7 版本 2.4 的通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-144">Includes common schemas for HL7 version 2.4.</span></span>  
  
-   <span data-ttu-id="24d06-145">BTAHL7**V25Common 项目**。</span><span class="sxs-lookup"><span data-stu-id="24d06-145">BTAHL7**V25Common Project**.</span></span> <span data-ttu-id="24d06-146">包括 HL7 版本 2.5 的通用架构。</span><span class="sxs-lookup"><span data-stu-id="24d06-146">Includes common schemas for HL7 version 2.5.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24d06-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24d06-147">See Also</span></span>  
 <span data-ttu-id="24d06-148">[工具和功能](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md) </span><span class="sxs-lookup"><span data-stu-id="24d06-148">[Tools and Features](../../adapters-and-accelerators/accelerator-hl7/tools-and-features.md) </span></span>  
 [<span data-ttu-id="24d06-149">分析工具</span><span class="sxs-lookup"><span data-stu-id="24d06-149">Analysis Tools</span></span>](../../adapters-and-accelerators/accelerator-hl7/analysis-tools2.md)