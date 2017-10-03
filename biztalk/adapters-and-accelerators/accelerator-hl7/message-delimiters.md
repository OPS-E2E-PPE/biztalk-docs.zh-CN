---
title: "消息分隔符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e5cf3c013f0a9bedf8c412206aebe1ce2e3f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-delimiters"></a><span data-ttu-id="3eb12-102">消息分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-102">Message Delimiters</span></span>
<span data-ttu-id="3eb12-103">由 HL7 标准定义的消息事件采用以下形式：</span><span class="sxs-lookup"><span data-stu-id="3eb12-103">Message events defined by HL7 standards take the following form:</span></span>  
  
-   <span data-ttu-id="3eb12-104">**平面文件**。</span><span class="sxs-lookup"><span data-stu-id="3eb12-104">**Flat files**.</span></span> <span data-ttu-id="3eb12-105">由 HL7 版本 2.4 及更早版本定义的消息事件采用平面文件的格式。</span><span class="sxs-lookup"><span data-stu-id="3eb12-105">Message events defined by HL7 versions 2.4 and earlier take the form of flat files.</span></span>  
  
-   <span data-ttu-id="3eb12-106">**XML**。</span><span class="sxs-lookup"><span data-stu-id="3eb12-106">**XML**.</span></span> <span data-ttu-id="3eb12-107">由 HL7 版本 2.XML 和版本 3 的消息事件采用 XML 文件的格式。</span><span class="sxs-lookup"><span data-stu-id="3eb12-107">Message events defined by HL7 versions 2.XML and version 3 take the form of XML files.</span></span>  
  
 <span data-ttu-id="3eb12-108">由于标准 HL7 未遵循位置格式，它使用分隔符来定义段、 字段、 组件和子组件级别的平面文件。</span><span class="sxs-lookup"><span data-stu-id="3eb12-108">Since the HL7 standard does not follow positional format, it uses delimiters to define the segment, field, component, and subcomponent levels of flat files.</span></span> <span data-ttu-id="3eb12-109">下表列出由 HL7 平面文件的默认分隔符。</span><span class="sxs-lookup"><span data-stu-id="3eb12-109">The following table lists the default delimiters used by HL7 flat files.</span></span>  
  
|<span data-ttu-id="3eb12-110">分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-110">Delimiter</span></span>|<span data-ttu-id="3eb12-111">值</span><span class="sxs-lookup"><span data-stu-id="3eb12-111">Value</span></span>|<span data-ttu-id="3eb12-112">用法</span><span class="sxs-lookup"><span data-stu-id="3eb12-112">Usage</span></span>|  
|---------------|-----------|-----------|  
|<span data-ttu-id="3eb12-113">段终止符</span><span class="sxs-lookup"><span data-stu-id="3eb12-113">Segment terminator</span></span>|<span data-ttu-id="3eb12-114">\<cr ></span><span class="sxs-lookup"><span data-stu-id="3eb12-114">\<cr></span></span>|<span data-ttu-id="3eb12-115">返回一个回车符终止段记录。</span><span class="sxs-lookup"><span data-stu-id="3eb12-115">A carriage return terminates a segment record.</span></span> <span data-ttu-id="3eb12-116">无法更改此值。</span><span class="sxs-lookup"><span data-stu-id="3eb12-116">You cannot change this value.</span></span>|  
|<span data-ttu-id="3eb12-117">字段分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-117">Field separator</span></span>|<span data-ttu-id="3eb12-118">&#124;</span><span class="sxs-lookup"><span data-stu-id="3eb12-118">&#124;</span></span>|<span data-ttu-id="3eb12-119">管道字符用于分隔段内的两个相邻的数据字段。</span><span class="sxs-lookup"><span data-stu-id="3eb12-119">A pipe character separates two adjacent data fields within a segment.</span></span> <span data-ttu-id="3eb12-120">此字符，还会分隔分段 ID 从每个段中的第一个数据字段。</span><span class="sxs-lookup"><span data-stu-id="3eb12-120">This character also separates the segment ID from the first data field in each segment.</span></span>|  
|<span data-ttu-id="3eb12-121">复合元素分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-121">Component separator</span></span>|^|<span data-ttu-id="3eb12-122">Hat 字符分隔相邻组成部分数据字段在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="3eb12-122">A hat character separates adjacent components of data fields where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="3eb12-123">子组件分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-123">Subcomponent separator</span></span>|&|<span data-ttu-id="3eb12-124">& 号字符分隔的数据的相邻子组件字段在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="3eb12-124">An ampersand character separates adjacent subcomponents of data fields where allowed by the HL7 standard.</span></span> <span data-ttu-id="3eb12-125">如果有不需要子组件，则可以省略此字符。</span><span class="sxs-lookup"><span data-stu-id="3eb12-125">If there are no subcomponents, then you can omit this character.</span></span>|  
|<span data-ttu-id="3eb12-126">重复分隔符</span><span class="sxs-lookup"><span data-stu-id="3eb12-126">Repetition separator</span></span>|~|<span data-ttu-id="3eb12-127">波形符字符分隔的组件或字段中的子组件的多个匹配项在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="3eb12-127">A tilde character separates multiple occurrences of components or subcomponents in a field where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="3eb12-128">转义字符</span><span class="sxs-lookup"><span data-stu-id="3eb12-128">Escape character</span></span>|\|<span data-ttu-id="3eb12-129">使用符合 ST、 德克萨斯州或 FT 数据类型，任何域或 ED 数据类型的数据 （第四个） 组件，你可以使用转义符。</span><span class="sxs-lookup"><span data-stu-id="3eb12-129">You use an escape character with any field that conforms to an ST, TX, or FT data type, or with the data (fourth) component of the ED data type.</span></span> <span data-ttu-id="3eb12-130">如果在消息中不存在任何转义字符，则可以省略此字符。</span><span class="sxs-lookup"><span data-stu-id="3eb12-130">If no escape characters exist in a message, you can omit this character.</span></span> <span data-ttu-id="3eb12-131">但是，如果消息中使用子组件必须将其包含。</span><span class="sxs-lookup"><span data-stu-id="3eb12-131">However, you must include it if you use subcomponents in the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3eb12-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3eb12-132">See Also</span></span>  
 <span data-ttu-id="3eb12-133">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="3eb12-133">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="3eb12-134">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="3eb12-134">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="3eb12-135">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="3eb12-135">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)