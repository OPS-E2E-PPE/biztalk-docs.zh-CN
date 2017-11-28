---
title: "字段理由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da9209040e64380b3a7a167dd013a15232543a75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="field-justification"></a><span data-ttu-id="7e856-102">字段理由</span><span class="sxs-lookup"><span data-stu-id="7e856-102">Field Justification</span></span>

## <a name="overview"></a><span data-ttu-id="7e856-103">概述</span><span class="sxs-lookup"><span data-stu-id="7e856-103">Overview</span></span>
<span data-ttu-id="7e856-104">字段对齐主要解决的问题是，字段中的数据字符将出现在所有伴随的填充字符之前（左对齐）还是之后（右对齐）。</span><span class="sxs-lookup"><span data-stu-id="7e856-104">Field justification concerns whether the data characters in a field occur before (left-aligned) or after (right-aligned) any accompanying pad characters.</span></span>  
  
 <span data-ttu-id="7e856-105">有时，字段中包含的数据字符可能无需占用该字段所有空间。</span><span class="sxs-lookup"><span data-stu-id="7e856-105">Sometimes the data characters contained within a field do not require all of the space dedicated to that field.</span></span> <span data-ttu-id="7e856-106">这是最常在位置记录，其中的字节或专用于字段的字符数固定的则返回 true，所确定的那样**位置长度**和**位置偏移量**属性。</span><span class="sxs-lookup"><span data-stu-id="7e856-106">This is true most frequently in positional records, where the number of bytes or characters dedicated to a field is fixed, as determined by the **Positional Length** and **Positional Offset** properties.</span></span> <span data-ttu-id="7e856-107">在此类方案中，通常数据项会小于字段长度，并以填充字符来填充字段的未使用部分。</span><span class="sxs-lookup"><span data-stu-id="7e856-107">It is common in such scenarios that the item of data is smaller than the field length, with the unused portion of the field being filled with pad characters.</span></span>  
  
 <span data-ttu-id="7e856-108">此类填充也可以分隔记录中出现时的值**填充字符的最小长度**属性超过存储数据的相关项所需的空间。</span><span class="sxs-lookup"><span data-stu-id="7e856-108">Such padding can also occur in delimited records when the value of the **Minimum Length with Pad Character** property exceeds the space required to store the relevant item of data.</span></span>  
  
 <span data-ttu-id="7e856-109">在这两个此类情况下，值**理由**属性 (**左**或**右**) 的相关**Field 元素**或**字段特性**节点确定是否填充字符将后面的数据字符 （左对齐） 或是否填充字符将前面 （右对齐） 的数据字符。</span><span class="sxs-lookup"><span data-stu-id="7e856-109">In both such cases, the value of the **Justification** property (**Left** or **Right**) of the relevant **Field Element** or **Field Attribute** node determines whether the pad characters will follow the data characters (left-aligned) or whether the pad characters will precede the data characters (right-aligned).</span></span>  
  
 <span data-ttu-id="7e856-110">平面文件反汇编程序将平面文件实例消息转换为等效的 XML 实例消息，当**理由**分析相应的字段时使用属性。</span><span class="sxs-lookup"><span data-stu-id="7e856-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the **Justification** property is used when parsing the corresponding field.</span></span> <span data-ttu-id="7e856-111">平面文件汇编器是将 XML 实例消息转换为等效的平面文件实例消息，**理由**属性用于确定当填充字符与关联的特定字段中，如果有的话，应添加到数据流： 之前或之后的相应数据字符。</span><span class="sxs-lookup"><span data-stu-id="7e856-111">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the **Justification** property is used to determine when the pad characters associated with a particular field, if any, should be added to the data stream: either before or after the corresponding data characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e856-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e856-112">See Also</span></span>  
- [<span data-ttu-id="7e856-113">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="7e856-113">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="7e856-114">以下属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="7e856-114">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="7e856-115">两端对齐 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="7e856-115">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="7e856-116">位置偏移量 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="7e856-116">Positional Offset (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="7e856-117">位置的长度 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="7e856-117">Positional Length (Node Property of Flat File Schemas)</span></span>