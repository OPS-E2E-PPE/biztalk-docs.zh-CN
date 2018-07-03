---
title: 消息分隔符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3339ded8edf46f7c5b96317cdf7a3ec822ec808b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001494"
---
# <a name="message-delimiters"></a><span data-ttu-id="b6538-102">消息分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-102">Message Delimiters</span></span>
<span data-ttu-id="b6538-103">HL7 标准中定义的消息事件采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="b6538-103">Message events defined by HL7 standards take the following form:</span></span>  
  
- <span data-ttu-id="b6538-104">**平面文件**。</span><span class="sxs-lookup"><span data-stu-id="b6538-104">**Flat files**.</span></span> <span data-ttu-id="b6538-105">HL7 版本 2.4 及更早版本中定义的消息事件采用平面文件的形式。</span><span class="sxs-lookup"><span data-stu-id="b6538-105">Message events defined by HL7 versions 2.4 and earlier take the form of flat files.</span></span>  
  
- <span data-ttu-id="b6538-106">**XML**。</span><span class="sxs-lookup"><span data-stu-id="b6538-106">**XML**.</span></span> <span data-ttu-id="b6538-107">定义的 HL7 版本 2.XML 和版本 3 的消息事件采用 XML 文件的形式。</span><span class="sxs-lookup"><span data-stu-id="b6538-107">Message events defined by HL7 versions 2.XML and version 3 take the form of XML files.</span></span>  
  
  <span data-ttu-id="b6538-108">标准 HL7 不遵循位置格式，因为它使用分隔符来定义段、 字段、 组件和子组件级别的平面文件。</span><span class="sxs-lookup"><span data-stu-id="b6538-108">Since the HL7 standard does not follow positional format, it uses delimiters to define the segment, field, component, and subcomponent levels of flat files.</span></span> <span data-ttu-id="b6538-109">下表列出了 HL7 平面文件所使用的默认分隔符。</span><span class="sxs-lookup"><span data-stu-id="b6538-109">The following table lists the default delimiters used by HL7 flat files.</span></span>  
  
|<span data-ttu-id="b6538-110">分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-110">Delimiter</span></span>|<span data-ttu-id="b6538-111">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="b6538-111">Value</span></span>|<span data-ttu-id="b6538-112">用法</span><span class="sxs-lookup"><span data-stu-id="b6538-112">Usage</span></span>|  
|---------------|-----------|-----------|  
|<span data-ttu-id="b6538-113">段终止符</span><span class="sxs-lookup"><span data-stu-id="b6538-113">Segment terminator</span></span>|<span data-ttu-id="b6538-114">\<cr\></span><span class="sxs-lookup"><span data-stu-id="b6538-114">\<cr\></span></span>|<span data-ttu-id="b6538-115">返回一个回车符将终止段记录。</span><span class="sxs-lookup"><span data-stu-id="b6538-115">A carriage return terminates a segment record.</span></span> <span data-ttu-id="b6538-116">不能更改此值。</span><span class="sxs-lookup"><span data-stu-id="b6538-116">You cannot change this value.</span></span>|  
|<span data-ttu-id="b6538-117">字段分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-117">Field separator</span></span>|<span data-ttu-id="b6538-118">&#124;</span><span class="sxs-lookup"><span data-stu-id="b6538-118">&#124;</span></span>|<span data-ttu-id="b6538-119">管道字符用于分隔段中的两个相邻的数据字段。</span><span class="sxs-lookup"><span data-stu-id="b6538-119">A pipe character separates two adjacent data fields within a segment.</span></span> <span data-ttu-id="b6538-120">此字符还用于分隔每个段中的第一个数据字段中的段 ID。</span><span class="sxs-lookup"><span data-stu-id="b6538-120">This character also separates the segment ID from the first data field in each segment.</span></span>|  
|<span data-ttu-id="b6538-121">复合元素分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-121">Component separator</span></span>|^|<span data-ttu-id="b6538-122">Hat 字符分隔相邻组件的数据字段在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="b6538-122">A hat character separates adjacent components of data fields where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="b6538-123">子组件分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-123">Subcomponent separator</span></span>|&|<span data-ttu-id="b6538-124">一个 & 字符分隔相邻子组件的数据字段在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="b6538-124">An ampersand character separates adjacent subcomponents of data fields where allowed by the HL7 standard.</span></span> <span data-ttu-id="b6538-125">如果不有任何子组件，则可以省略此字符。</span><span class="sxs-lookup"><span data-stu-id="b6538-125">If there are no subcomponents, then you can omit this character.</span></span>|  
|<span data-ttu-id="b6538-126">重复分隔符</span><span class="sxs-lookup"><span data-stu-id="b6538-126">Repetition separator</span></span>|~|<span data-ttu-id="b6538-127">波形符字符分隔组件或字段中的子组件的多个匹配项在允许的 HL7 标准。</span><span class="sxs-lookup"><span data-stu-id="b6538-127">A tilde character separates multiple occurrences of components or subcomponents in a field where allowed by the HL7 standard.</span></span>|  
|<span data-ttu-id="b6538-128">转义符</span><span class="sxs-lookup"><span data-stu-id="b6538-128">Escape character</span></span>|<span data-ttu-id="b6538-129">\|与符合到 ST、 德克萨斯州或 FT 数据类型，任何字段或 ED 数据类型的数据 （第四个） 组件，请使用转义符。</span><span class="sxs-lookup"><span data-stu-id="b6538-129">\|You use an escape character with any field that conforms to an ST, TX, or FT data type, or with the data (fourth) component of the ED data type.</span></span> <span data-ttu-id="b6538-130">如果在消息中不存在任何转义字符，则可以省略此字符。</span><span class="sxs-lookup"><span data-stu-id="b6538-130">If no escape characters exist in a message, you can omit this character.</span></span> <span data-ttu-id="b6538-131">但是，如果消息中使用子组件必须将其包含。</span><span class="sxs-lookup"><span data-stu-id="b6538-131">However, you must include it if you use subcomponents in the message.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6538-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6538-132">See Also</span></span>  
 <span data-ttu-id="b6538-133">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b6538-133">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 <span data-ttu-id="b6538-134">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="b6538-134">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="b6538-135">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="b6538-135">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)