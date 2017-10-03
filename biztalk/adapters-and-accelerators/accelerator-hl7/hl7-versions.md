---
title: "HL7 版本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c7edcfa6c44467c0660efd8a9b4b02df7010de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-versions"></a><span data-ttu-id="6ba81-102">HL7 版本</span><span class="sxs-lookup"><span data-stu-id="6ba81-102">HL7 Versions</span></span>
<span data-ttu-id="6ba81-103">HL7 版本 2 是一系列的密切相关的标准，而不是单个标准。</span><span class="sxs-lookup"><span data-stu-id="6ba81-103">HL7 Version 2 is a family of closely related standards rather than a single standard.</span></span> <span data-ttu-id="6ba81-104">HL7 组织已设计为向上兼容的 HL7 版本间的兼容性规则的应用程序通过这些标准。</span><span class="sxs-lookup"><span data-stu-id="6ba81-104">The HL7 organization has designed these standards to be upwards compatible through the application of the HL7 inter-version compatibility rules.</span></span> <span data-ttu-id="6ba81-105">这些规则保证，范围内的版本 2 的接口定义的 HL7 版本的规则下仍可正常工作的定义后续版本中。</span><span class="sxs-lookup"><span data-stu-id="6ba81-105">These rules guarantee that, within the confines of Version 2, an interface defined under the rules of an HL7 version will still function within the definition of successor versions.</span></span> <span data-ttu-id="6ba81-106">以便接收系统将能够接受来自更高版本的消息而不会破坏其实现和发送系统将能够继续将消息发送给支持更高版本的接收者。</span><span class="sxs-lookup"><span data-stu-id="6ba81-106">So that a receiving system will be able to accept messages from later versions without breaking its implementation and a sending system will be able to continue to send messages to receivers who support later versions.</span></span>  
  
 <span data-ttu-id="6ba81-107">务必请注意， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="6ba81-107">It is important to note that [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span></span>  
  
-   <span data-ttu-id="6ba81-108">支持从版本 2.5 通过 2.1 版的所有实时 HL7 版本</span><span class="sxs-lookup"><span data-stu-id="6ba81-108">Supports all live HL7 versions from Version 2.1 through Version 2.5</span></span>  
  
-   <span data-ttu-id="6ba81-109">提供功能需要 HL7 版本之间进行映射，并启用在单一站点的多个版本的互操作性</span><span class="sxs-lookup"><span data-stu-id="6ba81-109">Provides the functionality needed to map between HL7 versions, and enables the interoperability of multiple versions at a single site</span></span>  
  
-   <span data-ttu-id="6ba81-110">通过支持 Z 段支持本地化和启用备用解释之间的映射或使用的标准的消息</span><span class="sxs-lookup"><span data-stu-id="6ba81-110">Supports localization by supporting Z segments, and enables mapping between alternate interpretations or uses of the standard messages</span></span>  
  
 <span data-ttu-id="6ba81-111">请务必要注意的消息的标准版本之间的差异：</span><span class="sxs-lookup"><span data-stu-id="6ba81-111">It is important to note the difference between the versions of the messaging standard:</span></span>  
  
-   <span data-ttu-id="6ba81-112">版本 1 作为概念证明工作正常</span><span class="sxs-lookup"><span data-stu-id="6ba81-112">Version 1 functioned as a proof of concept</span></span>  
  
-   <span data-ttu-id="6ba81-113">版本 2 提供要支持应用程序之间的消息交换的消息规范的集合</span><span class="sxs-lookup"><span data-stu-id="6ba81-113">Version 2 provides a collection of message specifications to support message exchange between applications</span></span>  
  
-   <span data-ttu-id="6ba81-114">版本 3 将提供基于模型的集成的一组规范以支持各种互操作性需求</span><span class="sxs-lookup"><span data-stu-id="6ba81-114">Version 3 will provide a model-based integrated set of specifications to support a range of interoperability needs</span></span>  
  
 <span data-ttu-id="6ba81-115">从本质上讲，版本 2 侧重于向用户提供他们需要执行指定的任务，虽然版本 3 着重介绍确保一致性和正文的消息的规范作为长期扩展性的规范的实用方法常规首选项。</span><span class="sxs-lookup"><span data-stu-id="6ba81-115">In essence, Version 2 focuses on a pragmatic approach to providing users with the specifications they need to carry out specified tasks, while Version 3 focuses on assuring consistency and long-term extensibility for the body of message specifications taken as a whole.</span></span>  
  
 <span data-ttu-id="6ba81-116">通过引入临床文档使用 XML 的表示形式的标准，临床文档体系结构提供了 HL7 标准的重要扩展。</span><span class="sxs-lookup"><span data-stu-id="6ba81-116">The Clinical Document Architecture provides a significant extension to the HL7 standard by introducing standards for the representation of clinical documents using XML.</span></span>  
  
 <span data-ttu-id="6ba81-117">下表显示 HL7 标准开发前进。</span><span class="sxs-lookup"><span data-stu-id="6ba81-117">The following table shows the HL7 standard development progression.</span></span>  
  
|<span data-ttu-id="6ba81-118">事件</span><span class="sxs-lookup"><span data-stu-id="6ba81-118">Event</span></span>|<span data-ttu-id="6ba81-119">Year</span><span class="sxs-lookup"><span data-stu-id="6ba81-119">Year</span></span>|<span data-ttu-id="6ba81-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="6ba81-120">Details</span></span>|  
|-----------|----------|-------------|  
|<span data-ttu-id="6ba81-121">HL7 成立</span><span class="sxs-lookup"><span data-stu-id="6ba81-121">HL7 Founded</span></span>|<span data-ttu-id="6ba81-122">1987</span><span class="sxs-lookup"><span data-stu-id="6ba81-122">1987</span></span>|<span data-ttu-id="6ba81-123">在第一个会议在斯坦福，CA 中，包含 12 与会者。</span><span class="sxs-lookup"><span data-stu-id="6ba81-123">The first meeting, in Stanford, CA, included 12 attendees.</span></span>|  
|<span data-ttu-id="6ba81-124">V1.0</span><span class="sxs-lookup"><span data-stu-id="6ba81-124">V1.0</span></span>|<span data-ttu-id="6ba81-125">1987</span><span class="sxs-lookup"><span data-stu-id="6ba81-125">1987</span></span>|<span data-ttu-id="6ba81-126">提供给 HL7 全体会议的草稿。</span><span class="sxs-lookup"><span data-stu-id="6ba81-126">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="6ba81-127">2.0 版</span><span class="sxs-lookup"><span data-stu-id="6ba81-127">V2.0</span></span>|<span data-ttu-id="6ba81-128">1988</span><span class="sxs-lookup"><span data-stu-id="6ba81-128">1988</span></span>|<span data-ttu-id="6ba81-129">提供给 HL7 全体会议的草稿。</span><span class="sxs-lookup"><span data-stu-id="6ba81-129">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="6ba81-130">2.1 版发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-130">V2.1 published</span></span>|<span data-ttu-id="6ba81-131">1990</span><span class="sxs-lookup"><span data-stu-id="6ba81-131">1990</span></span>|<span data-ttu-id="6ba81-132">第一个广泛实现版本</span><span class="sxs-lookup"><span data-stu-id="6ba81-132">The first widely implemented version</span></span>|  
|<span data-ttu-id="6ba81-133">V2.2 发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-133">V2.2 published</span></span>|<span data-ttu-id="6ba81-134">1994</span><span class="sxs-lookup"><span data-stu-id="6ba81-134">1994</span></span>||  
|<span data-ttu-id="6ba81-135">V.2.3 发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-135">V.2.3 published</span></span>|<span data-ttu-id="6ba81-136">1997</span><span class="sxs-lookup"><span data-stu-id="6ba81-136">1997</span></span>|<span data-ttu-id="6ba81-137">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="6ba81-137">ANSI approved</span></span>|  
|<span data-ttu-id="6ba81-138">V2.3.1 发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-138">V2.3.1 published</span></span>|<span data-ttu-id="6ba81-139">1999</span><span class="sxs-lookup"><span data-stu-id="6ba81-139">1999</span></span>|<span data-ttu-id="6ba81-140">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="6ba81-140">ANSI approved</span></span>|  
|<span data-ttu-id="6ba81-141">V2.4 发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-141">V2.4 published</span></span>|<span data-ttu-id="6ba81-142">2000</span><span class="sxs-lookup"><span data-stu-id="6ba81-142">2000</span></span>|<span data-ttu-id="6ba81-143">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="6ba81-143">ANSI approved</span></span>|  
|<span data-ttu-id="6ba81-144">临床文档体系结构</span><span class="sxs-lookup"><span data-stu-id="6ba81-144">Clinical Document Architecture</span></span>|<span data-ttu-id="6ba81-145">2000</span><span class="sxs-lookup"><span data-stu-id="6ba81-145">2000</span></span>|<span data-ttu-id="6ba81-146">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="6ba81-146">ANSI approved</span></span>|  
|<span data-ttu-id="6ba81-147">V2.5 发布</span><span class="sxs-lookup"><span data-stu-id="6ba81-147">V2.5 published</span></span>|<span data-ttu-id="6ba81-148">2003</span><span class="sxs-lookup"><span data-stu-id="6ba81-148">2003</span></span>|<span data-ttu-id="6ba81-149">完成批准内 HL7，为 ANSI 提交以供审批。</span><span class="sxs-lookup"><span data-stu-id="6ba81-149">Completed approval within HL7, submitted to ANSI for approval.</span></span>|  
|<span data-ttu-id="6ba81-150">正在进行的 V3.0</span><span class="sxs-lookup"><span data-stu-id="6ba81-150">V3.0 in progress</span></span>|<span data-ttu-id="6ba81-151">2003</span><span class="sxs-lookup"><span data-stu-id="6ba81-151">2003</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="6ba81-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ba81-152">See Also</span></span>  
 <span data-ttu-id="6ba81-153">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6ba81-153">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="6ba81-154">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6ba81-154">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="6ba81-155">[使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6ba81-155">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="6ba81-156">[消息模式](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span><span class="sxs-lookup"><span data-stu-id="6ba81-156">[Message Modes](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span></span>  
 [<span data-ttu-id="6ba81-157">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="6ba81-157">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)