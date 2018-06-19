---
title: 汇编程序管道组件中的属性降级 |Microsoft 文档
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
ms.openlocfilehash: af634d302f01b18c91ebdbb7533673e8b9c545c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268829"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a><span data-ttu-id="2a39c-102">汇编程序管道组件中的属性降级</span><span class="sxs-lookup"><span data-stu-id="2a39c-102">Property Demotion in Assembler Pipeline Components</span></span>
<span data-ttu-id="2a39c-103">您可以使用属性降级将属性值从消息上下文复制到消息内容中，或复制到该消息的头部或尾部。</span><span class="sxs-lookup"><span data-stu-id="2a39c-103">You can use property demotion to copy a property value from the message context into the message content or to its header or trailer.</span></span> <span data-ttu-id="2a39c-104">通过使用文档中指定的 XPath 表达式，或头部和尾部架构中指定的 XPath 表达式可以完成属性降级。</span><span class="sxs-lookup"><span data-stu-id="2a39c-104">You accomplish property demotion by using an XPath expression specified in the document or in the header and trailer schema.</span></span>  
  
 <span data-ttu-id="2a39c-105">在将日期时间数据从上下文属性写入最终文档时，BizTalk Server 假定所有日期时间数据均采用 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="2a39c-105">When writing datetime data from the context property into the resulting document, BizTalk Server assumes that all datetime data is in UTC format.</span></span>  
  
 <span data-ttu-id="2a39c-106">用于将属性写入数据的格式由下表中显示的 XSD 数据类型确定：</span><span class="sxs-lookup"><span data-stu-id="2a39c-106">The format used to write properties into the data is determined by the XSD data type as shown in the following table.</span></span>  
  
|<span data-ttu-id="2a39c-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="2a39c-107">Data type</span></span>|<span data-ttu-id="2a39c-108">格式</span><span class="sxs-lookup"><span data-stu-id="2a39c-108">Format</span></span>|  
|---------------|------------|  
|<span data-ttu-id="2a39c-109">xs:datetime</span><span class="sxs-lookup"><span data-stu-id="2a39c-109">xs:datetime</span></span>|<span data-ttu-id="2a39c-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-110">yyyy-MM-ddTHH:mm:ss.fffffffZ</span></span>|  
|<span data-ttu-id="2a39c-111">xs:date</span><span class="sxs-lookup"><span data-stu-id="2a39c-111">xs:date</span></span>|<span data-ttu-id="2a39c-112">yyyy-MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-112">yyyy-MM-ddZ</span></span>|  
|<span data-ttu-id="2a39c-113">xs:gDay</span><span class="sxs-lookup"><span data-stu-id="2a39c-113">xs:gDay</span></span>|<span data-ttu-id="2a39c-114">---ddZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-114">---ddZ</span></span>|  
|<span data-ttu-id="2a39c-115">xs:gMonth</span><span class="sxs-lookup"><span data-stu-id="2a39c-115">xs:gMonth</span></span>|<span data-ttu-id="2a39c-116">--MM—Z</span><span class="sxs-lookup"><span data-stu-id="2a39c-116">--MM—Z</span></span>|  
|<span data-ttu-id="2a39c-117">xs:gMonthDay</span><span class="sxs-lookup"><span data-stu-id="2a39c-117">xs:gMonthDay</span></span>|<span data-ttu-id="2a39c-118">--MM-ddZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-118">--MM-ddZ</span></span>|  
|<span data-ttu-id="2a39c-119">xs:gYear</span><span class="sxs-lookup"><span data-stu-id="2a39c-119">xs:gYear</span></span>|<span data-ttu-id="2a39c-120">yyyyZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-120">yyyyZ</span></span>|  
|<span data-ttu-id="2a39c-121">xs:gYearMonth</span><span class="sxs-lookup"><span data-stu-id="2a39c-121">xs:gYearMonth</span></span>|<span data-ttu-id="2a39c-122">yyyy-MMZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-122">yyyy-MMZ</span></span>|  
|<span data-ttu-id="2a39c-123">xs:time</span><span class="sxs-lookup"><span data-stu-id="2a39c-123">xs:time</span></span>|<span data-ttu-id="2a39c-124">HH:mm:ss.fffffffZ</span><span class="sxs-lookup"><span data-stu-id="2a39c-124">HH:mm:ss.fffffffZ</span></span>|  
  
## <a name="property-demotion-and-envelopes"></a><span data-ttu-id="2a39c-125">属性降级和信封</span><span class="sxs-lookup"><span data-stu-id="2a39c-125">Property Demotion and Envelopes</span></span>  
 <span data-ttu-id="2a39c-126">在信封中组装文件时，经常需要从一个或多个系统命名空间中，或自己的一个命名空间中降级值。</span><span class="sxs-lookup"><span data-stu-id="2a39c-126">It is often useful to demote values from one or more of the system namespaces -- or one of your own namespaces -- when assembling files within an envelope.</span></span> <span data-ttu-id="2a39c-127">一些常见情形包括：</span><span class="sxs-lookup"><span data-stu-id="2a39c-127">Some common scenarios include:</span></span>  
  
-   <span data-ttu-id="2a39c-128">希望在出站消息中包含提交给系统的原始文件名称，以便后端系统可以跟踪数据的起源。</span><span class="sxs-lookup"><span data-stu-id="2a39c-128">You want to include the original file name submitted to the system in outbound messages so back-end systems can track the origin of data.</span></span>  
  
-   <span data-ttu-id="2a39c-129">希望将数据从正文消息写入到标题中。</span><span class="sxs-lookup"><span data-stu-id="2a39c-129">You want to write data from the body message to the header.</span></span> <span data-ttu-id="2a39c-130">例如，对于采购订单，可能需要将“发送到”的名称写到下游系统的信封中。</span><span class="sxs-lookup"><span data-stu-id="2a39c-130">For example, for a purchase order it might be useful to write the ship to name to the envelope for down-stream systems.</span></span>  
  
-   <span data-ttu-id="2a39c-131">希望将许多不同的字段合并到标题中，而无需编写自定义代码。</span><span class="sxs-lookup"><span data-stu-id="2a39c-131">You want to combine many different fields into the header without writing custom code.</span></span> <span data-ttu-id="2a39c-132">Xml 组装器或平面文件组装器中的属性降级就可以实现这一点。</span><span class="sxs-lookup"><span data-stu-id="2a39c-132">Property demotion in the Xml assembler or flat file assembler can do the job.</span></span>  
  
 <span data-ttu-id="2a39c-133">需要特别记住的是，XML 组装器组件和 平面文件组装器组件都可以指定用于信封和文档正文的架构。</span><span class="sxs-lookup"><span data-stu-id="2a39c-133">It is important to remember that the XML and flat file assembler components both allow you to specify which schema to use for the envelope and document body.</span></span> <span data-ttu-id="2a39c-134">您可以选择在拆卸中使用相同的架构，也可以创建带有不同的字段的新信封架构。</span><span class="sxs-lookup"><span data-stu-id="2a39c-134">You can choose the same schemas used in disassembly or create a new envelope schema with different fields.</span></span>  
  
 <span data-ttu-id="2a39c-135">有关这些概念的示例，请参阅[EnvelopeProcessing （BizTalk Server 示例）](../core/envelopeprocessing-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="2a39c-135">For an example of these concepts, see [EnvelopeProcessing (BizTalk Server Sample)](../core/envelopeprocessing-biztalk-server-sample.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a39c-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a39c-136">See Also</span></span>  
 <span data-ttu-id="2a39c-137">[平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="2a39c-137">[Flat File Assembler Pipeline Component](../core/flat-file-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="2a39c-138">如何配置平面文件汇编管道组件</span><span class="sxs-lookup"><span data-stu-id="2a39c-138">How to Configure the Flat File Assembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)