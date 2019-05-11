---
title: 组装器管道组件中的属性降级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b114d4a66b4fcb0139403fc22dcacc5c8ec1675
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398483"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a><span data-ttu-id="a7b31-102">组装器管道组件中的属性降级</span><span class="sxs-lookup"><span data-stu-id="a7b31-102">Property Demotion in Assembler Pipeline Components</span></span>
<span data-ttu-id="a7b31-103">可以使用属性降级将属性值从消息上下文复制，传入消息内容或其标头或尾部。</span><span class="sxs-lookup"><span data-stu-id="a7b31-103">You can use property demotion to copy a property value from the message context into the message content or to its header or trailer.</span></span> <span data-ttu-id="a7b31-104">通过使用在文档或标头和尾部架构中指定的 XPath 表达式完成属性降级。</span><span class="sxs-lookup"><span data-stu-id="a7b31-104">You accomplish property demotion by using an XPath expression specified in the document or in the header and trailer schema.</span></span>  
  
 <span data-ttu-id="a7b31-105">当从上下文属性的日期时间数据写入到生成的文档，BizTalk Server 假定所有日期时间数据采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="a7b31-105">When writing datetime data from the context property into the resulting document, BizTalk Server assumes that all datetime data is in UTC format.</span></span>  
  
 <span data-ttu-id="a7b31-106">用于将属性写入到数据格式由下表中所示的 XSD 数据类型决定。</span><span class="sxs-lookup"><span data-stu-id="a7b31-106">The format used to write properties into the data is determined by the XSD data type as shown in the following table.</span></span>  
  
|<span data-ttu-id="a7b31-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="a7b31-107">Data type</span></span>|<span data-ttu-id="a7b31-108">格式</span><span class="sxs-lookup"><span data-stu-id="a7b31-108">Format</span></span>|  
|---------------|------------|  
|<span data-ttu-id="a7b31-109">xs: datetime</span><span class="sxs-lookup"><span data-stu-id="a7b31-109">xs:datetime</span></span>|<span data-ttu-id="a7b31-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span></span>|  
|<span data-ttu-id="a7b31-111">xs:date</span><span class="sxs-lookup"><span data-stu-id="a7b31-111">xs:date</span></span>|<span data-ttu-id="a7b31-112">yyyy-MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-112">yyyy-MM-ddZ</span></span>|  
|<span data-ttu-id="a7b31-113">xs:gDay</span><span class="sxs-lookup"><span data-stu-id="a7b31-113">xs:gDay</span></span>|<span data-ttu-id="a7b31-114">---ddZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-114">---ddZ</span></span>|  
|<span data-ttu-id="a7b31-115">xs:gMonth</span><span class="sxs-lookup"><span data-stu-id="a7b31-115">xs:gMonth</span></span>|<span data-ttu-id="a7b31-116">--MM—Z</span><span class="sxs-lookup"><span data-stu-id="a7b31-116">--MM—Z</span></span>|  
|<span data-ttu-id="a7b31-117">xs:gMonthDay</span><span class="sxs-lookup"><span data-stu-id="a7b31-117">xs:gMonthDay</span></span>|<span data-ttu-id="a7b31-118">--MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-118">--MM-ddZ</span></span>|  
|<span data-ttu-id="a7b31-119">xs:gYear</span><span class="sxs-lookup"><span data-stu-id="a7b31-119">xs:gYear</span></span>|<span data-ttu-id="a7b31-120">yyyyZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-120">yyyyZ</span></span>|  
|<span data-ttu-id="a7b31-121">xs:gYearMonth</span><span class="sxs-lookup"><span data-stu-id="a7b31-121">xs:gYearMonth</span></span>|<span data-ttu-id="a7b31-122">yyyy-MMZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-122">yyyy-MMZ</span></span>|  
|<span data-ttu-id="a7b31-123">xs:time</span><span class="sxs-lookup"><span data-stu-id="a7b31-123">xs:time</span></span>|<span data-ttu-id="a7b31-124">HH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="a7b31-124">HH:mm:ss.fffffffZ</span></span>|  
  
## <a name="property-demotion-and-envelopes"></a><span data-ttu-id="a7b31-125">属性降级和信封</span><span class="sxs-lookup"><span data-stu-id="a7b31-125">Property Demotion and Envelopes</span></span>  
 <span data-ttu-id="a7b31-126">通常它可用于将值从一个或多个系统命名空间或某个你自己的命名空间-降级组装在信封中的文件时。</span><span class="sxs-lookup"><span data-stu-id="a7b31-126">It is often useful to demote values from one or more of the system namespaces -- or one of your own namespaces -- when assembling files within an envelope.</span></span> <span data-ttu-id="a7b31-127">一些常见方案包括：</span><span class="sxs-lookup"><span data-stu-id="a7b31-127">Some common scenarios include:</span></span>  
  
- <span data-ttu-id="a7b31-128">你想要包括提交到出站消息中的系统，因此后端系统可以跟踪的数据的来源的原始文件名。</span><span class="sxs-lookup"><span data-stu-id="a7b31-128">You want to include the original file name submitted to the system in outbound messages so back-end systems can track the origin of data.</span></span>  
  
- <span data-ttu-id="a7b31-129">你想要将数据从正文消息写入到的标头。</span><span class="sxs-lookup"><span data-stu-id="a7b31-129">You want to write data from the body message to the header.</span></span> <span data-ttu-id="a7b31-130">例如，对于采购订单可能有用飞船写入到信封的下游系统的名称。</span><span class="sxs-lookup"><span data-stu-id="a7b31-130">For example, for a purchase order it might be useful to write the ship to name to the envelope for down-stream systems.</span></span>  
  
- <span data-ttu-id="a7b31-131">你想要将许多不同的字段合并到标头，而无需编写自定义代码。</span><span class="sxs-lookup"><span data-stu-id="a7b31-131">You want to combine many different fields into the header without writing custom code.</span></span> <span data-ttu-id="a7b31-132">Xml 组装器或平面文件组装器中的属性降级可以实现这一点。</span><span class="sxs-lookup"><span data-stu-id="a7b31-132">Property demotion in the Xml assembler or flat file assembler can do the job.</span></span>  
  
  <span data-ttu-id="a7b31-133">请务必记住 XML 和平面文件组装器组件都允许您指定要用于信封和文档正文的架构。</span><span class="sxs-lookup"><span data-stu-id="a7b31-133">It is important to remember that the XML and flat file assembler components both allow you to specify which schema to use for the envelope and document body.</span></span> <span data-ttu-id="a7b31-134">可以选择在拆卸中使用相同的架构，也可以使用不同的字段创建新的信封架构。</span><span class="sxs-lookup"><span data-stu-id="a7b31-134">You can choose the same schemas used in disassembly or create a new envelope schema with different fields.</span></span>  
  
  <span data-ttu-id="a7b31-135">有关这些概念的示例，请参阅[EnvelopeProcessing （BizTalk Server 示例）](../core/envelopeprocessing-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="a7b31-135">For an example of these concepts, see [EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b31-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7b31-136">See Also</span></span>  
 <span data-ttu-id="a7b31-137">[平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="a7b31-137">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="a7b31-138">如何配置平面文件组装器管道组件</span><span class="sxs-lookup"><span data-stu-id="a7b31-138">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)