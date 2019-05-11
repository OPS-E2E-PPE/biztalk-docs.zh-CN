---
title: 数据转换配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017f5b38c30acd37728fc1834ff39b3125f4f07f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352702"
---
# <a name="data-transformation-configuration"></a><span data-ttu-id="09048-102">数据转换配置</span><span class="sxs-lookup"><span data-stu-id="09048-102">Data Transformation Configuration</span></span>
<span data-ttu-id="09048-103">映射用于从元素，典型的可扩展样式表语言转换 (XSLT) 如下所示。</span><span class="sxs-lookup"><span data-stu-id="09048-103">When mapping from an element, a typical Extensible Stylesheet Language Transformations (XSLT) looks as follows.</span></span>  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 <span data-ttu-id="09048-104">如果该元素**BCT01**包含混合内容，使用 text （） 就可访问仅第一个子元素，直到第一个文本如果有的话。</span><span class="sxs-lookup"><span data-stu-id="09048-104">If the element **BCT01** contains mixed content, the use of text() makes it possible to access the first text only up to the point of the first subelement, if any.</span></span> <span data-ttu-id="09048-105">如果未在此 XSLT 语句中使用 text （），结果将是所有文本内容，加上任何文本内容的子元素将映射为一个文本字符串。</span><span class="sxs-lookup"><span data-stu-id="09048-105">If text() were not used in this XSLT statement, the result would be that all text content, plus any text content of subelements, would be mapped as one string of text.</span></span> <span data-ttu-id="09048-106">配置**源链接**属性的链接，可控制将被复制到目标架构所定义的结构的数据源。</span><span class="sxs-lookup"><span data-stu-id="09048-106">Configuring the **Source Links** property for a link allows you to control the source of the data that is copied into the structure defined by the destination schema.</span></span>  
  
 <span data-ttu-id="09048-107">当在显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**源链接**属性。</span><span class="sxs-lookup"><span data-stu-id="09048-107">When you select a link in the displayed grid page, one of the properties displayed in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window is the **Source Links** property.</span></span> <span data-ttu-id="09048-108">你可以选择以下可能值为在映射中每个链接：</span><span class="sxs-lookup"><span data-stu-id="09048-108">You can choose between the following possible values for each link in your map:</span></span>  
  
-   <span data-ttu-id="09048-109">**复制文本值。**</span><span class="sxs-lookup"><span data-stu-id="09048-109">**Copy text value.**</span></span> <span data-ttu-id="09048-110">使用此值，该值为默认值，输入的实例消息中复制的元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="09048-110">Use this value, which is the default, to copy the value of the element or attribute in the input instance message.</span></span> <span data-ttu-id="09048-111">例如，如果相关元素为 BoldExample，如下所示：</span><span class="sxs-lookup"><span data-stu-id="09048-111">For example, if the relevant element is BoldExample, as follows:</span></span>  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     <span data-ttu-id="09048-112">值复制到相关的元素或输出实例消息中的属性是"这是"。</span><span class="sxs-lookup"><span data-stu-id="09048-112">The value copied into the relevant element or attribute in the output instance message is "This is a ".</span></span> <span data-ttu-id="09048-113">对于此类的混合内容元素，此结果可能不是正确的结果。</span><span class="sxs-lookup"><span data-stu-id="09048-113">For mixed content elements like this, this result may not be what is desired.</span></span> <span data-ttu-id="09048-114">但是，由于混合内容元素都是相对较少**复制文本值**设置为**源链接**适合属性可能在大多数情况下。</span><span class="sxs-lookup"><span data-stu-id="09048-114">But because mixed content elements are relatively rare, the **Copy text value** setting for the **Source Links** property is probably appropriate in most cases.</span></span>  
  
-   <span data-ttu-id="09048-115">**复制名称。**</span><span class="sxs-lookup"><span data-stu-id="09048-115">**Copy name.**</span></span> <span data-ttu-id="09048-116">使用此值复制输入的实例消息中的节点的名称。</span><span class="sxs-lookup"><span data-stu-id="09048-116">Use this value to copy the name of the node in the input instance message.</span></span> <span data-ttu-id="09048-117">对于中的示例**复制文本值**说明，结果为"BoldExample"，这是元素的实际名称。</span><span class="sxs-lookup"><span data-stu-id="09048-117">For the example in the **Copy text value** description, the result is "BoldExample", which is the actual name of the element.</span></span>  
  
-   <span data-ttu-id="09048-118">**复制文本和子内容值。**</span><span class="sxs-lookup"><span data-stu-id="09048-118">**Copy text and sub content value.**</span></span> <span data-ttu-id="09048-119">此值用于连接的节点值和子节点输入的实例消息中的所有值。</span><span class="sxs-lookup"><span data-stu-id="09048-119">Use this value to concatenate the values of the node and all values of its child nodes in the input instance message.</span></span> <span data-ttu-id="09048-120">对于中的示例**复制文本值**说明，结果为"This is"，这可能很好地定义为包含混合的内容的元素的相应结果。 Bold Text example。</span><span class="sxs-lookup"><span data-stu-id="09048-120">For the example in the **Copy text value** description, the result is "This is a Bold Text example.", which might very well be the appropriate result for elements defined to contain mixed content.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09048-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="09048-121">See Also</span></span>  
 <span data-ttu-id="09048-122">[批量复制 Functoid](../core/mass-copy-functoid.md) </span><span class="sxs-lookup"><span data-stu-id="09048-122">[Mass Copy Functoid](../core/mass-copy-functoid.md) </span></span>  
 <span data-ttu-id="09048-123">[如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md) </span><span class="sxs-lookup"><span data-stu-id="09048-123">[How to Set the Source Links Compiler Value](../core/how-to-set-the-source-links-compiler-value.md) </span></span>  
 [<span data-ttu-id="09048-124">节点层次结构级匹配</span><span class="sxs-lookup"><span data-stu-id="09048-124">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)