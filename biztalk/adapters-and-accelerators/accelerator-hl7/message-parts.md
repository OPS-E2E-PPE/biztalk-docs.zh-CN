---
title: 消息部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c67694dbfe2e0cdfbc330e36d51dcf8e5a3fccd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303688"
---
# <a name="message-parts"></a><span data-ttu-id="a3460-102">消息部分</span><span class="sxs-lookup"><span data-stu-id="a3460-102">Message Parts</span></span>
<span data-ttu-id="a3460-103">HL7 消息包含以下几个部分： 段、 数据字段、 组件和 （可选） 子组件。</span><span class="sxs-lookup"><span data-stu-id="a3460-103">An HL7 message contains the following parts: segments, data fields, components, and optionally subcomponents.</span></span> <span data-ttu-id="a3460-104">HL7 消息具有以下层次结构：</span><span class="sxs-lookup"><span data-stu-id="a3460-104">HL7 messages have the following hierarchical structure:</span></span>  
  
 <span data-ttu-id="a3460-105">段</span><span class="sxs-lookup"><span data-stu-id="a3460-105">Segment</span></span>  
  
 <span data-ttu-id="a3460-106">数据字段</span><span class="sxs-lookup"><span data-stu-id="a3460-106">Data Field</span></span>  
  
 <span data-ttu-id="a3460-107">组件</span><span class="sxs-lookup"><span data-stu-id="a3460-107">Component</span></span>  
  
 <span data-ttu-id="a3460-108">子组件 （可选）</span><span class="sxs-lookup"><span data-stu-id="a3460-108">Subcomponent (optional)</span></span>  
  
 <span data-ttu-id="a3460-109">**段**</span><span class="sxs-lookup"><span data-stu-id="a3460-109">**Segments**</span></span>  
  
 <span data-ttu-id="a3460-110">一个段是数据字段的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="a3460-110">A segment is a logical grouping of data fields.</span></span> <span data-ttu-id="a3460-111">段在消息层次结构的最高级别 （深度为 1）。</span><span class="sxs-lookup"><span data-stu-id="a3460-111">Segments are at the highest level (depth 1) of the message hierarchy.</span></span> <span data-ttu-id="a3460-112">每个分段有一个包括三个字符的文本值的名称。</span><span class="sxs-lookup"><span data-stu-id="a3460-112">Each segment has a name that includes a three-character literal value.</span></span> <span data-ttu-id="a3460-113">下表显示了段名称所包含的 ADT 消息类型的示例。</span><span class="sxs-lookup"><span data-stu-id="a3460-113">The following table shows examples of segment names contained by ADT message types.</span></span>  
  
|<span data-ttu-id="a3460-114">段代码</span><span class="sxs-lookup"><span data-stu-id="a3460-114">Segment code</span></span>|<span data-ttu-id="a3460-115">Description</span><span class="sxs-lookup"><span data-stu-id="a3460-115">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="a3460-116">MSH</span><span class="sxs-lookup"><span data-stu-id="a3460-116">MSH</span></span>|<span data-ttu-id="a3460-117">消息标头</span><span class="sxs-lookup"><span data-stu-id="a3460-117">Message Header</span></span>|  
|<span data-ttu-id="a3460-118">EVN</span><span class="sxs-lookup"><span data-stu-id="a3460-118">EVN</span></span>|<span data-ttu-id="a3460-119">事件类型</span><span class="sxs-lookup"><span data-stu-id="a3460-119">Event Type</span></span>|  
|<span data-ttu-id="a3460-120">PID</span><span class="sxs-lookup"><span data-stu-id="a3460-120">PID</span></span>|<span data-ttu-id="a3460-121">患者信息</span><span class="sxs-lookup"><span data-stu-id="a3460-121">Patient Information</span></span>|  
  
 <span data-ttu-id="a3460-122">HL7 消息具有*消息标头*并*正文*。</span><span class="sxs-lookup"><span data-stu-id="a3460-122">HL7 messages have a *message header* and *body*.</span></span> <span data-ttu-id="a3460-123">MSH 段定义消息的标头和所有其他类型的段构成消息的正文。</span><span class="sxs-lookup"><span data-stu-id="a3460-123">The MSH segments define the header of the message and all other types of segments form the body of the message.</span></span>  
  
 <span data-ttu-id="a3460-124">**数据字段**</span><span class="sxs-lookup"><span data-stu-id="a3460-124">**Data Fields**</span></span>  
  
 <span data-ttu-id="a3460-125">数据字段是发生在消息层次结构的深度 2 的字符的字符串。</span><span class="sxs-lookup"><span data-stu-id="a3460-125">A data field is a string of characters that occur at depth 2 of the message hierarchy.</span></span> <span data-ttu-id="a3460-126">数据类型定义数据字段：简单和复杂。</span><span class="sxs-lookup"><span data-stu-id="a3460-126">Data types define data fields: Simple and Complex.</span></span>  
  
 <span data-ttu-id="a3460-127">下面的示例显示了包含 MSH.1 和 EVN.1 数据字段的 MSH 和 EVN 段的层次结构的消息结构：</span><span class="sxs-lookup"><span data-stu-id="a3460-127">The following example shows the hierarchical message structure of the MSH and EVN segments containing the MSH.1 and EVN.1 data fields:</span></span>  
  
 <span data-ttu-id="a3460-128">MSH</span><span class="sxs-lookup"><span data-stu-id="a3460-128">MSH</span></span>  
  
 <span data-ttu-id="a3460-129">MSH.1</span><span class="sxs-lookup"><span data-stu-id="a3460-129">MSH.1</span></span>  
  
 <span data-ttu-id="a3460-130">EVN</span><span class="sxs-lookup"><span data-stu-id="a3460-130">EVN</span></span>  
  
 <span data-ttu-id="a3460-131">EVN.1</span><span class="sxs-lookup"><span data-stu-id="a3460-131">EVN.1</span></span>  
  
 <span data-ttu-id="a3460-132">**组件和子组件**</span><span class="sxs-lookup"><span data-stu-id="a3460-132">**Components and Subcomponents**</span></span>  
  
 <span data-ttu-id="a3460-133">组件和子组件进一步包含数据字段中的数据。</span><span class="sxs-lookup"><span data-stu-id="a3460-133">Components and subcomponents further contain the data within data fields.</span></span> <span data-ttu-id="a3460-134">组件和子组件可以重复相同的字段中。</span><span class="sxs-lookup"><span data-stu-id="a3460-134">Components and subcomponents can repeat within the same field.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3460-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3460-135">See Also</span></span>  
 <span data-ttu-id="a3460-136">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a3460-136">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="a3460-137">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="a3460-137">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="a3460-138">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="a3460-138">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)