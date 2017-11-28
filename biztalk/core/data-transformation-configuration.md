---
title: "数据转换配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XSLT
- maps, compiling
- Source Links property
- BizTalk Mapper, compiler directives
- code samples, XSLT
- compiler directives, copy text and subcontentent value
- compiler directives, copy text value
- maps, XSLT
- compiler directives, copy name
- compiler directives
- maps, code sample [XSLT]
- XSLT, code samples
ms.assetid: 05abe091-5202-4590-99ec-e60ca53a4324
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8304d43f59f63e474a3257915521d5dc36c38d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-transformation-configuration"></a><span data-ttu-id="f8507-102">数据转换配置</span><span class="sxs-lookup"><span data-stu-id="f8507-102">Data Transformation Configuration</span></span>
<span data-ttu-id="f8507-103">当映射的元素中，典型的可扩展样式表语言转换 (XSLT) 将如下所示。</span><span class="sxs-lookup"><span data-stu-id="f8507-103">When mapping from an element, a typical Extensible Stylesheet Language Transformations (XSLT) looks as follows.</span></span>  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 <span data-ttu-id="f8507-104">如果元素**BCT01**包含混合内容，使用 text （） 会使它可以访问仅第一个子元素，直到第一个文本如果有的话。</span><span class="sxs-lookup"><span data-stu-id="f8507-104">If the element **BCT01** contains mixed content, the use of text() makes it possible to access the first text only up to the point of the first subelement, if any.</span></span> <span data-ttu-id="f8507-105">如果未在此 XSLT 语句中使用 text （），结果将是所有文本内容，加上任何文本内容的子元素，将映射为一个文本字符串。</span><span class="sxs-lookup"><span data-stu-id="f8507-105">If text() were not used in this XSLT statement, the result would be that all text content, plus any text content of subelements, would be mapped as one string of text.</span></span> <span data-ttu-id="f8507-106">配置**源链接**用于链接的属性可以控制复制到目标架构中定义的结构的数据源。</span><span class="sxs-lookup"><span data-stu-id="f8507-106">Configuring the **Source Links** property for a link allows you to control the source of the data that is copied into the structure defined by the destination schema.</span></span>  
  
 <span data-ttu-id="f8507-107">当显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**源链接**属性。</span><span class="sxs-lookup"><span data-stu-id="f8507-107">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Source Links** property.</span></span> <span data-ttu-id="f8507-108">你可以选择你的代码图中每个链接以下可能的值：</span><span class="sxs-lookup"><span data-stu-id="f8507-108">You can choose between the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="f8507-109">**复制文本值。**</span><span class="sxs-lookup"><span data-stu-id="f8507-109">**Copy text value.**</span></span> <span data-ttu-id="f8507-110">使用此值（默认值）可复制输入实例消息中的元素或属性值。</span><span class="sxs-lookup"><span data-stu-id="f8507-110">Use this value, which is the default, to copy the value of the element or attribute in the input instance message.</span></span> <span data-ttu-id="f8507-111">例如，如果相关元素为 BoldExample，如下如示：</span><span class="sxs-lookup"><span data-stu-id="f8507-111">For example, if the relevant element is BoldExample, as follows:</span></span>  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     <span data-ttu-id="f8507-112">则复制到输出实例消息中的相关元素或属性的值为“This is a ”。</span><span class="sxs-lookup"><span data-stu-id="f8507-112">The value copied into the relevant element or attribute in the output instance message is "This is a ".</span></span> <span data-ttu-id="f8507-113">对于这样的混合内容，结果可能不是所期望的内容。</span><span class="sxs-lookup"><span data-stu-id="f8507-113">For mixed content elements like this, this result may not be what is desired.</span></span> <span data-ttu-id="f8507-114">但是，由于混合内容的元素都是相对很少，**复制文本值**设置**源链接**属性是在大多数情况下可能适用。</span><span class="sxs-lookup"><span data-stu-id="f8507-114">But because mixed content elements are relatively rare, the **Copy text value** setting for the **Source Links** property is probably appropriate in most cases.</span></span>  
  
-   <span data-ttu-id="f8507-115">**复制名称。**</span><span class="sxs-lookup"><span data-stu-id="f8507-115">**Copy name.**</span></span> <span data-ttu-id="f8507-116">使用此值可复制输入实例消息中的节点名称。</span><span class="sxs-lookup"><span data-stu-id="f8507-116">Use this value to copy the name of the node in the input instance message.</span></span> <span data-ttu-id="f8507-117">对于中的示例**复制文本值**说明，结果为"BoldExample"，这是元素的实际名称。</span><span class="sxs-lookup"><span data-stu-id="f8507-117">For the example in the **Copy text value** description, the result is "BoldExample", which is the actual name of the element.</span></span>  
  
-   <span data-ttu-id="f8507-118">**将文本复制和子内容的值。**</span><span class="sxs-lookup"><span data-stu-id="f8507-118">**Copy text and sub content value.**</span></span> <span data-ttu-id="f8507-119">使用此值可将输入实例消息中的节点值及其子节点中的所有值连接到一起。</span><span class="sxs-lookup"><span data-stu-id="f8507-119">Use this value to concatenate the values of the node and all values of its child nodes in the input instance message.</span></span> <span data-ttu-id="f8507-120">对于中的示例**复制文本值**说明，结果是"这是显示为粗体文本示例。"，这很好地可能会定义为包含混合的内容的元素的相应结果。</span><span class="sxs-lookup"><span data-stu-id="f8507-120">For the example in the **Copy text value** description, the result is "This is a Bold Text example.", which might very well be the appropriate result for elements defined to contain mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8507-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f8507-121">See Also</span></span>  
 <span data-ttu-id="f8507-122">[大容量复制 Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="f8507-122">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="f8507-123">[如何将源链接编译器值设置](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="f8507-123">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="f8507-124">节点层次结构级别匹配</span><span class="sxs-lookup"><span data-stu-id="f8507-124">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)