---
title: "创建链接 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87570b82dc63a02c629e0fc024c2e44d57df1401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-links"></a><span data-ttu-id="2db99-102">创建链接</span><span class="sxs-lookup"><span data-stu-id="2db99-102">Creating Links</span></span>
<span data-ttu-id="2db99-103">BizTalk 映射器可帮助您自动化在创建链接过程中所涉及的一些元素。</span><span class="sxs-lookup"><span data-stu-id="2db99-103">BizTalk Mapper helps you automate some elements involved in link creation.</span></span> <span data-ttu-id="2db99-104">简单链接创建类似于简单数据类型。</span><span class="sxs-lookup"><span data-stu-id="2db99-104">Simple link creation is similar to simple data types.</span></span> <span data-ttu-id="2db99-105">还有一些较为复杂的链接创建形式，类似于编程语言中的结构分配。</span><span class="sxs-lookup"><span data-stu-id="2db99-105">There are more sophisticated forms of link creation that are more like structure assignment in a programming language.</span></span> <span data-ttu-id="2db99-106">例如，使用单个链接创建指定如何将多个数据项从输入实例消息移至相应的输出实例消息。</span><span class="sxs-lookup"><span data-stu-id="2db99-106">An example is a single link creation that specifies how multiple items of data are to be moved from input instance messages to corresponding output instance messages.</span></span>  
  
 <span data-ttu-id="2db99-107">可以使用以下方法来创建链接：</span><span class="sxs-lookup"><span data-stu-id="2db99-107">You create links using the following methods:</span></span>  
  
-   <span data-ttu-id="2db99-108">**简单链接创建。**</span><span class="sxs-lookup"><span data-stu-id="2db99-108">**Simple link creation.**</span></span> <span data-ttu-id="2db99-109">在简单链接创建中，通过拖动即可生成链接。</span><span class="sxs-lookup"><span data-stu-id="2db99-109">In simple link creation, you produce a link by dragging.</span></span> <span data-ttu-id="2db99-110">将源架构中的字段拖至目标架构中的字段将在输出实例消息中创建元素或属性，并在消息中插入元素或属性的值。</span><span class="sxs-lookup"><span data-stu-id="2db99-110">Dragging a field in the source schema to a field in the destination schema causes the creation of an element or attribute in an output instance message and inserts the value of the element or attribute in the message.</span></span> <span data-ttu-id="2db99-111">直接之间可以进行此类链接**记录**和**字段**节点在源和目标架构中，或它们可以在之间的链接路径中包含一个或多个 functoid**记录**和**字段**源和目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="2db99-111">Such links can be made directly between **Record** and **Field** nodes in the source and destination schema, or they can include one or more functoids in a link path between **Record** and **Field** nodes in the source and destination schemas.</span></span>  
  
-   <span data-ttu-id="2db99-112">**结构的链接。**</span><span class="sxs-lookup"><span data-stu-id="2db99-112">**Structure links.**</span></span> <span data-ttu-id="2db99-113">在创建结构链接，你生成多个简单的链接在同一时间之间**记录**和**字段**具有相同的相对结构的源和目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="2db99-113">In creating structure links, you produce multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas that have the same relative structure.</span></span> <span data-ttu-id="2db99-114">若要使用结构链接，两个架构的相关部分的结构必须相同。</span><span class="sxs-lookup"><span data-stu-id="2db99-114">To use structure linking, the structure of the relevant parts of the two schemas must be the same.</span></span> <span data-ttu-id="2db99-115">有关配置结构链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="2db99-115">For more information about configuring structure links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
-   <span data-ttu-id="2db99-116">**名称匹配的链接。**</span><span class="sxs-lookup"><span data-stu-id="2db99-116">**Name-matching links.**</span></span> <span data-ttu-id="2db99-117">当你使用此方法时，你将在同一时间之间创建多个简单链接**记录**和**字段**源和目标架构中的节点的名称基于**记录**和**字段**节点。</span><span class="sxs-lookup"><span data-stu-id="2db99-117">When you use this method, you create multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas based on the names of the **Records** and **Field** nodes.</span></span> <span data-ttu-id="2db99-118">若要使用名称匹配链接，源架构和目标架构的结构必须非常相似，但无需完全相同。</span><span class="sxs-lookup"><span data-stu-id="2db99-118">To use name-matching linking, the structure of the source and destination schemas must be very similar, but not exactly the same.</span></span> <span data-ttu-id="2db99-119">有关配置名称匹配的链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="2db99-119">For more information about configuring name-matching links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2db99-120">你还可以看到[如何管理现有链接](../core/how-to-manage-existing-links.md)有关如何更改/修改的现有链接的信息。</span><span class="sxs-lookup"><span data-stu-id="2db99-120">You can also see [How to Manage Existing Links](../core/how-to-manage-existing-links.md) for information about how to change/modify the existing links.</span></span>  
  
## <a name="preserving-whitespace-in-a-link"></a><span data-ttu-id="2db99-121">保留链接中的空格</span><span class="sxs-lookup"><span data-stu-id="2db99-121">Preserving Whitespace in a Link</span></span>  
 <span data-ttu-id="2db99-122">如果在将源元素映射到目标元素或 functoid 时，想要保留源元素中的空格，则需要编写自定义脚本。</span><span class="sxs-lookup"><span data-stu-id="2db99-122">If you want to preserve whitespace from a source element when mapping to a target element or functoid, you will need to write a custom script.</span></span>  
  
 <span data-ttu-id="2db99-123">在映射器或运行时系统中不保留空格。</span><span class="sxs-lookup"><span data-stu-id="2db99-123">Whitespace is not preserved either in the Mapper or in the runtime system.</span></span> <span data-ttu-id="2db99-124">映射器和运行时系统都使用 BTSXslTransform.Transform，它处理大消息转换，并依靠 XmlReader 通过 XPath 数据模型进行定位。</span><span class="sxs-lookup"><span data-stu-id="2db99-124">Both the Mapper and the runtime system use BTSXslTransform.Transform which handles large-message transformations and relies on XmlReader to navigate using the XPath data model.</span></span>  
  
 <span data-ttu-id="2db99-125">若要保留空格，可编写能返回所需数量的空格的自定义脚本。</span><span class="sxs-lookup"><span data-stu-id="2db99-125">To preserve whitespace, you can write a custom script that returns the required amount of whitespace.</span></span> <span data-ttu-id="2db99-126">例如，以下代码始终返回包含 5 个空格字符的字符串：</span><span class="sxs-lookup"><span data-stu-id="2db99-126">For example, the code below always returns a string containing 5 whitespace characters:</span></span>  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 <span data-ttu-id="2db99-127">如果你源元素链接到此脚本和目标元素的输入作为输出，执行映射时，输出元素将包含 5 空白字符。</span><span class="sxs-lookup"><span data-stu-id="2db99-127">If you link a source element to the input of this script and a target element as the output, when the map is executed, the output element will contain 5 whitespace characters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2db99-128">如果您查看输出使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，元素将显示为空。</span><span class="sxs-lookup"><span data-stu-id="2db99-128">If you view the output using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the element will appear empty.</span></span> <span data-ttu-id="2db99-129">这是因为 XML 查看器将包含空格的元素仅作为空白处理。</span><span class="sxs-lookup"><span data-stu-id="2db99-129">This is because the XML viewer treats elements containing whitespace only as empty.</span></span> <span data-ttu-id="2db99-130">若要查看空白，右键单击 XML 视图，然后选择**查看源**。</span><span class="sxs-lookup"><span data-stu-id="2db99-130">To see the whitespace, right-click the XML view and select **View Source**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2db99-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2db99-131">See Also</span></span>  
 [<span data-ttu-id="2db99-132">如何编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="2db99-132">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)