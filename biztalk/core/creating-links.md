---
title: 创建链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps, links
- BizTalk Mapper, links
ms.assetid: e8596c50-62e9-40a7-ad61-29cbdb4f4fc9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 441ae9536dec11f8eead5544e95b7ba7f7814852
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353644"
---
# <a name="creating-links"></a><span data-ttu-id="a670e-102">创建链接</span><span class="sxs-lookup"><span data-stu-id="a670e-102">Creating Links</span></span>
<span data-ttu-id="a670e-103">BizTalk 映射器可帮助你自动执行某些链接创建中涉及的元素。</span><span class="sxs-lookup"><span data-stu-id="a670e-103">BizTalk Mapper helps you automate some elements involved in link creation.</span></span> <span data-ttu-id="a670e-104">简单链接创建类似于简单数据类型。</span><span class="sxs-lookup"><span data-stu-id="a670e-104">Simple link creation is similar to simple data types.</span></span> <span data-ttu-id="a670e-105">有多个类似于编程语言中的结构分配的更复杂的链接创建窗体。</span><span class="sxs-lookup"><span data-stu-id="a670e-105">There are more sophisticated forms of link creation that are more like structure assignment in a programming language.</span></span> <span data-ttu-id="a670e-106">例如，使用指定的数据如何将多个项的从输入的实例消息移动到相应的输出实例消息的单个链接创建。</span><span class="sxs-lookup"><span data-stu-id="a670e-106">An example is a single link creation that specifies how multiple items of data are to be moved from input instance messages to corresponding output instance messages.</span></span>  
  
 <span data-ttu-id="a670e-107">创建使用以下方法链接：</span><span class="sxs-lookup"><span data-stu-id="a670e-107">You create links using the following methods:</span></span>  
  
-   <span data-ttu-id="a670e-108">**简单链接创建。**</span><span class="sxs-lookup"><span data-stu-id="a670e-108">**Simple link creation.**</span></span> <span data-ttu-id="a670e-109">在简单链接创建通过拖动生成链接。</span><span class="sxs-lookup"><span data-stu-id="a670e-109">In simple link creation, you produce a link by dragging.</span></span> <span data-ttu-id="a670e-110">将源架构中的字段拖至目标架构中的字段输出实例消息中将导致创建元素或属性，并将元素或属性的值插入消息中。</span><span class="sxs-lookup"><span data-stu-id="a670e-110">Dragging a field in the source schema to a field in the destination schema causes the creation of an element or attribute in an output instance message and inserts the value of the element or attribute in the message.</span></span> <span data-ttu-id="a670e-111">此类链接可以之间直接进行**记录**并**字段**节点在源和目标架构中，或它们可以包括一个或多个 functoid 之间的链接路径中**记录**并**字段**源和目标架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="a670e-111">Such links can be made directly between **Record** and **Field** nodes in the source and destination schema, or they can include one or more functoids in a link path between **Record** and **Field** nodes in the source and destination schemas.</span></span>  
  
-   <span data-ttu-id="a670e-112">**结构链接。**</span><span class="sxs-lookup"><span data-stu-id="a670e-112">**Structure links.**</span></span> <span data-ttu-id="a670e-113">在创建结构链接时，你生成多个简单链接在同一时间之间**记录**并**字段**中具有相同的相对结构的源和目标架构的节点。</span><span class="sxs-lookup"><span data-stu-id="a670e-113">In creating structure links, you produce multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas that have the same relative structure.</span></span> <span data-ttu-id="a670e-114">若要使用结构链接，这两种架构的相关部分的结构必须相同。</span><span class="sxs-lookup"><span data-stu-id="a670e-114">To use structure linking, the structure of the relevant parts of the two schemas must be the same.</span></span> <span data-ttu-id="a670e-115">有关配置结构链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="a670e-115">For more information about configuring structure links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
-   <span data-ttu-id="a670e-116">**名称匹配链接。**</span><span class="sxs-lookup"><span data-stu-id="a670e-116">**Name-matching links.**</span></span> <span data-ttu-id="a670e-117">当使用此方法时，在同一时间之间创建多个简单链接**记录**并**字段**源和目标架构中的节点上的名称基于**记录**并**字段**节点。</span><span class="sxs-lookup"><span data-stu-id="a670e-117">When you use this method, you create multiple simple links at the same time between **Record** and **Field** nodes in the source and destination schemas based on the names of the **Records** and **Field** nodes.</span></span> <span data-ttu-id="a670e-118">若要使用名称匹配链接，源和目标架构的结构必须非常相似，但又不完全相同。</span><span class="sxs-lookup"><span data-stu-id="a670e-118">To use name-matching linking, the structure of the source and destination schemas must be very similar, but not exactly the same.</span></span> <span data-ttu-id="a670e-119">有关配置名称匹配链接的详细信息，请参阅[如何自动链接记录](../core/how-to-link-records-automatically.md)。</span><span class="sxs-lookup"><span data-stu-id="a670e-119">For more information about configuring name-matching links, see [How to Link Records Automatically](../core/how-to-link-records-automatically.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a670e-120">你还可以看到[如何管理现有链接](../core/how-to-manage-existing-links.md)有关如何更改/修改现有链接的信息。</span><span class="sxs-lookup"><span data-stu-id="a670e-120">You can also see [How to Manage Existing Links](../core/how-to-manage-existing-links.md) for information about how to change/modify the existing links.</span></span>  
  
## <a name="preserving-whitespace-in-a-link"></a><span data-ttu-id="a670e-121">保留链接中的空格</span><span class="sxs-lookup"><span data-stu-id="a670e-121">Preserving Whitespace in a Link</span></span>  
 <span data-ttu-id="a670e-122">如果您想要保留源元素中的空格，映射到目标元素或 functoid 时，需要编写自定义脚本。</span><span class="sxs-lookup"><span data-stu-id="a670e-122">If you want to preserve whitespace from a source element when mapping to a target element or functoid, you will need to write a custom script.</span></span>  
  
 <span data-ttu-id="a670e-123">在映射器或运行时系统中，不保留空格。</span><span class="sxs-lookup"><span data-stu-id="a670e-123">Whitespace is not preserved either in the Mapper or in the runtime system.</span></span> <span data-ttu-id="a670e-124">映射器和运行时系统使用 BTSXslTransform.Transform，它处理大消息转换，并依靠 XmlReader 使用 XPath 数据模型进行导航。</span><span class="sxs-lookup"><span data-stu-id="a670e-124">Both the Mapper and the runtime system use BTSXslTransform.Transform which handles large-message transformations and relies on XmlReader to navigate using the XPath data model.</span></span>  
  
 <span data-ttu-id="a670e-125">若要保留空白，可以编写自定义脚本返回所需的数量的空格。</span><span class="sxs-lookup"><span data-stu-id="a670e-125">To preserve whitespace, you can write a custom script that returns the required amount of whitespace.</span></span> <span data-ttu-id="a670e-126">例如，下面的代码始终返回一个包含 5 个空格字符的字符串：</span><span class="sxs-lookup"><span data-stu-id="a670e-126">For example, the code below always returns a string containing 5 whitespace characters:</span></span>  
  
```  
public string Whitespace(string param1)  
{  
  return "     ";  
}  
```  
  
 <span data-ttu-id="a670e-127">如果您的源元素时链接到此脚本和目标元素的输入作为输出，在执行映射时，输出元素将包含 5 个空格字符。</span><span class="sxs-lookup"><span data-stu-id="a670e-127">If you link a source element to the input of this script and a target element as the output, when the map is executed, the output element will contain 5 whitespace characters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a670e-128">如果您查看输出使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，该元素将显示为空。</span><span class="sxs-lookup"><span data-stu-id="a670e-128">If you view the output using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], the element will appear empty.</span></span> <span data-ttu-id="a670e-129">这是因为 XML 查看器将包含空格仅作为空白的元素。</span><span class="sxs-lookup"><span data-stu-id="a670e-129">This is because the XML viewer treats elements containing whitespace only as empty.</span></span> <span data-ttu-id="a670e-130">若要查看空格，用鼠标右键单击 XML 视图，然后选择**查看源**。</span><span class="sxs-lookup"><span data-stu-id="a670e-130">To see the whitespace, right-click the XML view and select **View Source**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a670e-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="a670e-131">See Also</span></span>  
 [<span data-ttu-id="a670e-132">如何编辑链接属性</span><span class="sxs-lookup"><span data-stu-id="a670e-132">How to Edit Link Properties</span></span>](../core/how-to-edit-link-properties.md)