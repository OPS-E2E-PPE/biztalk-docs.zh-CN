---
title: "在反汇编程序管道组件中的属性提升 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9770b0e66b85dcc41400002e2e0c1780bc51c3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a><span data-ttu-id="16ec9-102">在反汇编程序管道组件中的属性提升</span><span class="sxs-lookup"><span data-stu-id="16ec9-102">Property Promotion in Disassembler Pipeline Components</span></span>
<span data-ttu-id="16ec9-103">属性升级是使用 XPath 表达式从 XML 文档中提取属性值，再将其放置到消息上下文中以便用于消息路由的过程。</span><span class="sxs-lookup"><span data-stu-id="16ec9-103">Property promotion is a process by which a property value is extracted from an XML document by using an XPath expression and placed on the message context so that it can be used for message routing.</span></span>  
  
 <span data-ttu-id="16ec9-104">如果已提升的属性没有默认值或固定值，该属性的 XML 字段是缺失，并且验证文档结构属性是**False**，该属性不提升。</span><span class="sxs-lookup"><span data-stu-id="16ec9-104">If a promoted property does not have a default or fixed value, the XML field for that property is missing, and the Validate Document Structure property is **False**, the property is not promoted.</span></span>  
  
 <span data-ttu-id="16ec9-105">自定义管道组件可以升级多值（即数组）属性。</span><span class="sxs-lookup"><span data-stu-id="16ec9-105">A custom pipeline component can promote multivalued (that is, arrayed) properties.</span></span> <span data-ttu-id="16ec9-106">只有在基于内容的路由 (CBR) 方案中，才支持包含多值属性的消息；此类消息无法路由到业务流程或用于跟踪用途。</span><span class="sxs-lookup"><span data-stu-id="16ec9-106">Messages that contain multivalued properties are only supported in content-based routing (CBR) scenarios; they cannot be routed to orchestrations or be used for tracking purposes.</span></span>  
  
 <span data-ttu-id="16ec9-107">如果空元素带有结束标记，则 XML 拆装器不会升级其默认值或固定值。</span><span class="sxs-lookup"><span data-stu-id="16ec9-107">The XML Disassembler does not promote default or fixed values for an empty element if it has a closing tag.</span></span> <span data-ttu-id="16ec9-108">例如， \<field1 > 在下面的 XML 中不会对其进行提升。</span><span class="sxs-lookup"><span data-stu-id="16ec9-108">For example, \<field1> is not promoted in the following XML.</span></span>  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 <span data-ttu-id="16ec9-109">但是，没有结束标记的空元素将升级，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="16ec9-109">However, an empty element without a closing tag (as shown in the following example) is promoted.</span></span>  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 <span data-ttu-id="16ec9-110">从文档中读取日期时间数据并将其放在上下文属性中时，如果数据采用 UTC 格式，则保留该格式。</span><span class="sxs-lookup"><span data-stu-id="16ec9-110">When reading datetime data from a document and placing it into the context property, if the data is in UTC format, that format is preserved.</span></span> <span data-ttu-id="16ec9-111">如果日期时间数据采用“本地时间+偏移量”格式，则 BizTalk Server 将日期时间格式转换为偏移量加本地时间所得到的 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="16ec9-111">If the datetime data is in local+offset format, BizTalk Server converts the datetime format to the UTC format that results from adding the offset to the local time.</span></span> <span data-ttu-id="16ec9-112">如果日期时间格式没有指定时区或 UTC 格式，则时间假定为本地时间，并基于当前时区转换为 UTC 格式。</span><span class="sxs-lookup"><span data-stu-id="16ec9-112">If the datetime format does not specify time zone or UTC format, the time is assumed to be local and is converted to UTC based on the current time zone.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ec9-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16ec9-113">See Also</span></span>  
 <span data-ttu-id="16ec9-114">[XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="16ec9-114">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="16ec9-115">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="16ec9-115">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)