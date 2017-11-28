---
title: "消息部分 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-parts"></a><span data-ttu-id="c0268-102">消息部分</span><span class="sxs-lookup"><span data-stu-id="c0268-102">Message Parts</span></span>
<span data-ttu-id="c0268-103">HL7 消息包含以下部分： 段、 数据字段、 组件和 （可选） 子组件。</span><span class="sxs-lookup"><span data-stu-id="c0268-103">An HL7 message contains the following parts: segments, data fields, components, and optionally subcomponents.</span></span> <span data-ttu-id="c0268-104">HL7 消息具有以下层次结构：</span><span class="sxs-lookup"><span data-stu-id="c0268-104">HL7 messages have the following hierarchical structure:</span></span>  
  
 <span data-ttu-id="c0268-105">段</span><span class="sxs-lookup"><span data-stu-id="c0268-105">Segment</span></span>  
  
 <span data-ttu-id="c0268-106">数据字段</span><span class="sxs-lookup"><span data-stu-id="c0268-106">Data Field</span></span>  
  
 <span data-ttu-id="c0268-107">组件</span><span class="sxs-lookup"><span data-stu-id="c0268-107">Component</span></span>  
  
 <span data-ttu-id="c0268-108">子组件 （可选）</span><span class="sxs-lookup"><span data-stu-id="c0268-108">Subcomponent (optional)</span></span>  
  
 <span data-ttu-id="c0268-109">**段**</span><span class="sxs-lookup"><span data-stu-id="c0268-109">**Segments**</span></span>  
  
 <span data-ttu-id="c0268-110">段是数据字段的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="c0268-110">A segment is a logical grouping of data fields.</span></span> <span data-ttu-id="c0268-111">段是在消息层次结构最高级别 （深度为 1）。</span><span class="sxs-lookup"><span data-stu-id="c0268-111">Segments are at the highest level (depth 1) of the message hierarchy.</span></span> <span data-ttu-id="c0268-112">每个段都有一个名称，包含三个字符的文本值。</span><span class="sxs-lookup"><span data-stu-id="c0268-112">Each segment has a name that includes a three-character literal value.</span></span> <span data-ttu-id="c0268-113">下表显示了段名称包含的 ADT 消息类型的示例。</span><span class="sxs-lookup"><span data-stu-id="c0268-113">The following table shows examples of segment names contained by ADT message types.</span></span>  
  
|<span data-ttu-id="c0268-114">段代码</span><span class="sxs-lookup"><span data-stu-id="c0268-114">Segment code</span></span>|<span data-ttu-id="c0268-115">Description</span><span class="sxs-lookup"><span data-stu-id="c0268-115">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="c0268-116">MSH</span><span class="sxs-lookup"><span data-stu-id="c0268-116">MSH</span></span>|<span data-ttu-id="c0268-117">消息标头</span><span class="sxs-lookup"><span data-stu-id="c0268-117">Message Header</span></span>|  
|<span data-ttu-id="c0268-118">EVN</span><span class="sxs-lookup"><span data-stu-id="c0268-118">EVN</span></span>|<span data-ttu-id="c0268-119">事件类型</span><span class="sxs-lookup"><span data-stu-id="c0268-119">Event Type</span></span>|  
|<span data-ttu-id="c0268-120">PID</span><span class="sxs-lookup"><span data-stu-id="c0268-120">PID</span></span>|<span data-ttu-id="c0268-121">患者信息</span><span class="sxs-lookup"><span data-stu-id="c0268-121">Patient Information</span></span>|  
  
 <span data-ttu-id="c0268-122">HL7 消息具有*消息标头*和*正文*。</span><span class="sxs-lookup"><span data-stu-id="c0268-122">HL7 messages have a *message header* and *body*.</span></span> <span data-ttu-id="c0268-123">MSH 段定义消息的标头和所有其他类型的段窗体消息的正文。</span><span class="sxs-lookup"><span data-stu-id="c0268-123">The MSH segments define the header of the message and all other types of segments form the body of the message.</span></span>  
  
 <span data-ttu-id="c0268-124">**数据字段**</span><span class="sxs-lookup"><span data-stu-id="c0268-124">**Data Fields**</span></span>  
  
 <span data-ttu-id="c0268-125">数据字段出现在消息层次结构的深度 2 的字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="c0268-125">A data field is a string of characters that occur at depth 2 of the message hierarchy.</span></span> <span data-ttu-id="c0268-126">数据类型定义数据字段： 简单和复杂。</span><span class="sxs-lookup"><span data-stu-id="c0268-126">Data types define data fields: Simple and Complex.</span></span>  
  
 <span data-ttu-id="c0268-127">下面的示例显示 MSH 和 EVN 段，其中包含 MSH.1 和 EVN.1 数据字段的分层消息结构：</span><span class="sxs-lookup"><span data-stu-id="c0268-127">The following example shows the hierarchical message structure of the MSH and EVN segments containing the MSH.1 and EVN.1 data fields:</span></span>  
  
 <span data-ttu-id="c0268-128">MSH</span><span class="sxs-lookup"><span data-stu-id="c0268-128">MSH</span></span>  
  
 <span data-ttu-id="c0268-129">MSH.1</span><span class="sxs-lookup"><span data-stu-id="c0268-129">MSH.1</span></span>  
  
 <span data-ttu-id="c0268-130">EVN</span><span class="sxs-lookup"><span data-stu-id="c0268-130">EVN</span></span>  
  
 <span data-ttu-id="c0268-131">EVN.1</span><span class="sxs-lookup"><span data-stu-id="c0268-131">EVN.1</span></span>  
  
 <span data-ttu-id="c0268-132">**组件和子组件**</span><span class="sxs-lookup"><span data-stu-id="c0268-132">**Components and Subcomponents**</span></span>  
  
 <span data-ttu-id="c0268-133">组件和子组件进一步包含在数据字段的数据。</span><span class="sxs-lookup"><span data-stu-id="c0268-133">Components and subcomponents further contain the data within data fields.</span></span> <span data-ttu-id="c0268-134">组件和子组件可以重复执行相同字段中。</span><span class="sxs-lookup"><span data-stu-id="c0268-134">Components and subcomponents can repeat within the same field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0268-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0268-135">See Also</span></span>  
 <span data-ttu-id="c0268-136">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c0268-136">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="c0268-137">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="c0268-137">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="c0268-138">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="c0268-138">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)