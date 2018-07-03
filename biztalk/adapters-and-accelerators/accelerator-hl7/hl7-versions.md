---
title: HL7 版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b3806ed8db2272068ff60c6656b73cdf4a726bd9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005894"
---
# <a name="hl7-versions"></a><span data-ttu-id="53292-102">HL7 版本</span><span class="sxs-lookup"><span data-stu-id="53292-102">HL7 Versions</span></span>
<span data-ttu-id="53292-103">HL7 版本 2 是系列密切相关的标准，而不是单个标准。</span><span class="sxs-lookup"><span data-stu-id="53292-103">HL7 Version 2 is a family of closely related standards rather than a single standard.</span></span> <span data-ttu-id="53292-104">HL7 组织经过设计，这些标准通过 HL7 版本间的兼容性规则的应用程序向上兼容。</span><span class="sxs-lookup"><span data-stu-id="53292-104">The HL7 organization has designed these standards to be upwards compatible through the application of the HL7 inter-version compatibility rules.</span></span> <span data-ttu-id="53292-105">这些规则保证，在版本 2 的篇幅所限，HL7 版本的规则下定义的接口仍可正常工作后续版本的定义中。</span><span class="sxs-lookup"><span data-stu-id="53292-105">These rules guarantee that, within the confines of Version 2, an interface defined under the rules of an HL7 version will still function within the definition of successor versions.</span></span> <span data-ttu-id="53292-106">以便接收系统将能够接受来自更高版本的消息而不会破坏其实现并发送系统将能够继续将消息发送到接收方人员支持更高版本。</span><span class="sxs-lookup"><span data-stu-id="53292-106">So that a receiving system will be able to accept messages from later versions without breaking its implementation and a sending system will be able to continue to send messages to receivers who support later versions.</span></span>  
  
 <span data-ttu-id="53292-107">务必要注意的 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span><span class="sxs-lookup"><span data-stu-id="53292-107">It is important to note that Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]):</span></span>  
  
- <span data-ttu-id="53292-108">支持从版本 2.1 到版本 2.5 的所有实时 HL7 版本</span><span class="sxs-lookup"><span data-stu-id="53292-108">Supports all live HL7 versions from Version 2.1 through Version 2.5</span></span>  
  
- <span data-ttu-id="53292-109">提供所需 HL7 版本之间进行映射的功能并使位于单个站点的多个版本的互操作性</span><span class="sxs-lookup"><span data-stu-id="53292-109">Provides the functionality needed to map between HL7 versions, and enables the interoperability of multiple versions at a single site</span></span>  
  
- <span data-ttu-id="53292-110">通过支持的 Z 段支持本地化和启用备用解释之间的映射或使用的标准消息</span><span class="sxs-lookup"><span data-stu-id="53292-110">Supports localization by supporting Z segments, and enables mapping between alternate interpretations or uses of the standard messages</span></span>  
  
  <span data-ttu-id="53292-111">请务必要注意的消息传送标准版本之间的区别：</span><span class="sxs-lookup"><span data-stu-id="53292-111">It is important to note the difference between the versions of the messaging standard:</span></span>  
  
- <span data-ttu-id="53292-112">版本 1 的职能的概念证明</span><span class="sxs-lookup"><span data-stu-id="53292-112">Version 1 functioned as a proof of concept</span></span>  
  
- <span data-ttu-id="53292-113">版本 2 提供了一系列消息规范，支持应用程序之间交换消息</span><span class="sxs-lookup"><span data-stu-id="53292-113">Version 2 provides a collection of message specifications to support message exchange between applications</span></span>  
  
- <span data-ttu-id="53292-114">第 3 版将提供的基于模型的集成的一组规范支持范围的互操作性需求</span><span class="sxs-lookup"><span data-stu-id="53292-114">Version 3 will provide a model-based integrated set of specifications to support a range of interoperability needs</span></span>  
  
  <span data-ttu-id="53292-115">从本质上讲，第 2 版侧重于向用户提供他们需要执行指定的任务，而版本 3 侧重于确保一致性和正文作为消息规范的长期可扩展性的规范的编程之法整体。</span><span class="sxs-lookup"><span data-stu-id="53292-115">In essence, Version 2 focuses on a pragmatic approach to providing users with the specifications they need to carry out specified tasks, while Version 3 focuses on assuring consistency and long-term extensibility for the body of message specifications taken as a whole.</span></span>  
  
  <span data-ttu-id="53292-116">临床文档体系结构提供通过引入临床文档，使用 XML 的表示形式的标准 HL7 标准的重要扩展。</span><span class="sxs-lookup"><span data-stu-id="53292-116">The Clinical Document Architecture provides a significant extension to the HL7 standard by introducing standards for the representation of clinical documents using XML.</span></span>  
  
  <span data-ttu-id="53292-117">下表显示了 HL7 标准开发进度。</span><span class="sxs-lookup"><span data-stu-id="53292-117">The following table shows the HL7 standard development progression.</span></span>  
  
|<span data-ttu-id="53292-118">事件</span><span class="sxs-lookup"><span data-stu-id="53292-118">Event</span></span>|<span data-ttu-id="53292-119">Year</span><span class="sxs-lookup"><span data-stu-id="53292-119">Year</span></span>|<span data-ttu-id="53292-120">详细信息</span><span class="sxs-lookup"><span data-stu-id="53292-120">Details</span></span>|  
|-----------|----------|-------------|  
|<span data-ttu-id="53292-121">HL7 成立了</span><span class="sxs-lookup"><span data-stu-id="53292-121">HL7 Founded</span></span>|<span data-ttu-id="53292-122">1987</span><span class="sxs-lookup"><span data-stu-id="53292-122">1987</span></span>|<span data-ttu-id="53292-123">第一次会议中，在斯坦福，CA 中，包含 12 位与会者。</span><span class="sxs-lookup"><span data-stu-id="53292-123">The first meeting, in Stanford, CA, included 12 attendees.</span></span>|  
|<span data-ttu-id="53292-124">V1.0</span><span class="sxs-lookup"><span data-stu-id="53292-124">V1.0</span></span>|<span data-ttu-id="53292-125">1987</span><span class="sxs-lookup"><span data-stu-id="53292-125">1987</span></span>|<span data-ttu-id="53292-126">提供给 HL7 全体会议的草稿。</span><span class="sxs-lookup"><span data-stu-id="53292-126">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="53292-127">V2.0</span><span class="sxs-lookup"><span data-stu-id="53292-127">V2.0</span></span>|<span data-ttu-id="53292-128">1988</span><span class="sxs-lookup"><span data-stu-id="53292-128">1988</span></span>|<span data-ttu-id="53292-129">提供给 HL7 全体会议的草稿。</span><span class="sxs-lookup"><span data-stu-id="53292-129">Draft presented to HL7 plenary meeting.</span></span>|  
|<span data-ttu-id="53292-130">2.1 版发布</span><span class="sxs-lookup"><span data-stu-id="53292-130">V2.1 published</span></span>|<span data-ttu-id="53292-131">1990</span><span class="sxs-lookup"><span data-stu-id="53292-131">1990</span></span>|<span data-ttu-id="53292-132">第一个广泛的实施版本</span><span class="sxs-lookup"><span data-stu-id="53292-132">The first widely implemented version</span></span>|  
|<span data-ttu-id="53292-133">V2.2 发布</span><span class="sxs-lookup"><span data-stu-id="53292-133">V2.2 published</span></span>|<span data-ttu-id="53292-134">1994</span><span class="sxs-lookup"><span data-stu-id="53292-134">1994</span></span>||  
|<span data-ttu-id="53292-135">V.2.3 发布</span><span class="sxs-lookup"><span data-stu-id="53292-135">V.2.3 published</span></span>|<span data-ttu-id="53292-136">1997</span><span class="sxs-lookup"><span data-stu-id="53292-136">1997</span></span>|<span data-ttu-id="53292-137">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="53292-137">ANSI approved</span></span>|  
|<span data-ttu-id="53292-138">适用于版本 V2.3.1 发布</span><span class="sxs-lookup"><span data-stu-id="53292-138">V2.3.1 published</span></span>|<span data-ttu-id="53292-139">1999</span><span class="sxs-lookup"><span data-stu-id="53292-139">1999</span></span>|<span data-ttu-id="53292-140">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="53292-140">ANSI approved</span></span>|  
|<span data-ttu-id="53292-141">发布于 V2.4</span><span class="sxs-lookup"><span data-stu-id="53292-141">V2.4 published</span></span>|<span data-ttu-id="53292-142">2000</span><span class="sxs-lookup"><span data-stu-id="53292-142">2000</span></span>|<span data-ttu-id="53292-143">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="53292-143">ANSI approved</span></span>|  
|<span data-ttu-id="53292-144">临床文档体系结构</span><span class="sxs-lookup"><span data-stu-id="53292-144">Clinical Document Architecture</span></span>|<span data-ttu-id="53292-145">2000</span><span class="sxs-lookup"><span data-stu-id="53292-145">2000</span></span>|<span data-ttu-id="53292-146">ANSI 批准</span><span class="sxs-lookup"><span data-stu-id="53292-146">ANSI approved</span></span>|  
|<span data-ttu-id="53292-147">已发布的版本 2.5</span><span class="sxs-lookup"><span data-stu-id="53292-147">V2.5 published</span></span>|<span data-ttu-id="53292-148">2003</span><span class="sxs-lookup"><span data-stu-id="53292-148">2003</span></span>|<span data-ttu-id="53292-149">完成审批中 HL7，为 ANSI 提交以供审核。</span><span class="sxs-lookup"><span data-stu-id="53292-149">Completed approval within HL7, submitted to ANSI for approval.</span></span>|  
|<span data-ttu-id="53292-150">正在进行中的 3.0 版</span><span class="sxs-lookup"><span data-stu-id="53292-150">V3.0 in progress</span></span>|<span data-ttu-id="53292-151">2003</span><span class="sxs-lookup"><span data-stu-id="53292-151">2003</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="53292-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="53292-152">See Also</span></span>  
 <span data-ttu-id="53292-153">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="53292-153">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="53292-154">[使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="53292-154">[Using HL7 2.X Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md) </span></span>  
 <span data-ttu-id="53292-155">[使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="53292-155">[Using HL7 2.XML Schemas](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md) </span></span>  
 <span data-ttu-id="53292-156">[消息模式](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span><span class="sxs-lookup"><span data-stu-id="53292-156">[Message Modes](../../adapters-and-accelerators/accelerator-hl7/message-modes.md) </span></span>  
 [<span data-ttu-id="53292-157">HL7 消息传送</span><span class="sxs-lookup"><span data-stu-id="53292-157">HL7 Messaging</span></span>](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)