---
title: 节点属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 366080f0-c21a-467d-8051-fd280264c5c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec003c92f374489d59986bb5324f66100adf9e63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323543"
---
# <a name="node-properties"></a><span data-ttu-id="23381-102">节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-102">Node Properties</span></span>

## <a name="overview"></a><span data-ttu-id="23381-103">概述</span><span class="sxs-lookup"><span data-stu-id="23381-103">Overview</span></span>
<span data-ttu-id="23381-104">在 BizTalk 编辑器中，检查并在 Visual Studio 属性窗口中设置节点属性。</span><span class="sxs-lookup"><span data-stu-id="23381-104">In BizTalk Editor, you examine and set node properties in the Visual Studio Properties window.</span></span> <span data-ttu-id="23381-105">在架构树视图中选择不同类型的节点，在属性窗口中显示不同的属性集。</span><span class="sxs-lookup"><span data-stu-id="23381-105">As you select different types of nodes in the schema tree view, different sets of properties are displayed in the Properties window.</span></span> <span data-ttu-id="23381-106">按原样在标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以在类别中或未指示其类别按字母顺序显示这些属性。</span><span class="sxs-lookup"><span data-stu-id="23381-106">As is standard in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], these properties can be displayed either in categories or alphabetically with no indication of their categories.</span></span> <span data-ttu-id="23381-107">使用属性窗口的顶部附近的标准按钮可以切换此设置。</span><span class="sxs-lookup"><span data-stu-id="23381-107">Use the standard buttons near the top of the Properties window to toggle this setting.</span></span>  
  
 <span data-ttu-id="23381-108">节点属性，尤其是当设置为值默认设置时，通常表示 XML 架构定义 (XSD) 语言中为属性和属性值与相应元素关联。</span><span class="sxs-lookup"><span data-stu-id="23381-108">Node properties, especially when set to values other than their defaults, are generally represented in the XML Schema definition (XSD) language as attributes and attribute values associated with the corresponding element.</span></span> <span data-ttu-id="23381-109">例如，当属性设置为**最小出现次数**并**Max Occurs**属性，可用于多个不同的节点类型设置的值用作值**minOccurs**并**maxOccurs**属性，分别为其表示的节点的元素与关联**Min Occurs**和**最大值发生**设置属性。</span><span class="sxs-lookup"><span data-stu-id="23381-109">For example, when properties are set for the **Min Occurs** and **Max Occurs** properties, which are available for several different node types, the values that are set are used as the values of the **minOccurs** and **maxOccurs** attributes, respectively, associated with the element that represents the node for which the **Min Occurs** and **Max Occurs** properties are being set.</span></span>  

## <a name="property-types"></a><span data-ttu-id="23381-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="23381-110">Property types</span></span>
 <span data-ttu-id="23381-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员参考包含按类别和按字母顺序组织的各种节点类型的属性的参考部分。</span><span class="sxs-lookup"><span data-stu-id="23381-111">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] developer reference contains a reference section for the properties of the various node types, organized by category and alphabetically.</span></span> <span data-ttu-id="23381-112">下面总结了与每个节点类型关联的属性：</span><span class="sxs-lookup"><span data-stu-id="23381-112">The following summarize the properties associated with each node type:</span></span>  
  
-   <span data-ttu-id="23381-113">Schema 节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-113">Schema Node Properties</span></span>
  
-   <span data-ttu-id="23381-114">记录节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-114">Record Node Properties</span></span>
  
-   <span data-ttu-id="23381-115">字段元素节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-115">Field Element Node Properties</span></span>
  
-   <span data-ttu-id="23381-116">字段属性节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-116">Field Attribute Node Properties</span></span>
  
-   <span data-ttu-id="23381-117">序列组节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-117">Sequence Group Node Properties</span></span>
  
-   <span data-ttu-id="23381-118">选择组节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-118">Choice Group Node Properties</span></span> 
  
-   <span data-ttu-id="23381-119">所有组节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-119">All Group Node Properties</span></span>
  
-   <span data-ttu-id="23381-120">属性组节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-120">Attribute Group Node Properties</span></span>
  
-   <span data-ttu-id="23381-121">任何元素节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-121">Any Element Node Properties</span></span>
  
-   <span data-ttu-id="23381-122">任何特性节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-122">Any Attribute Node Properties</span></span>
  
-   <span data-ttu-id="23381-123">等价节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-123">Equivalent Node Properties</span></span>
  
-   <span data-ttu-id="23381-124">等价子节点属性</span><span class="sxs-lookup"><span data-stu-id="23381-124">Equivalent Child Node Properties</span></span>

<span data-ttu-id="23381-125">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="23381-125">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="23381-126">**节点属性 — 字母顺序列表**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]包含的所有分立参考主题的每个节点属性，其中一些适用于各种类型的节点。</span><span class="sxs-lookup"><span data-stu-id="23381-126">**Node Properties — Alphabetical Listings** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contains all of the individual reference topics for each node property, some of which apply to various types of nodes.</span></span> <span data-ttu-id="23381-127">分立参考主题进行了分类根据它们是适用于所有类型的架构的基本属性还是与架构编辑器扩展，例如平面文件扩展相关联的特殊的属性。</span><span class="sxs-lookup"><span data-stu-id="23381-127">The individual reference topics are categorized according to whether they are basic properties that apply to all types of schemas, or a specialized properties that are associated with a schema editor extension, such as the flat file extension.</span></span> <span data-ttu-id="23381-128">这些类别中它们是按字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="23381-128">Within these categories, they are listed alphabetically.</span></span>  
  
 <span data-ttu-id="23381-129">BizTalk 编辑器使用[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口使您可以查看和设置在架构树中节点的属性。</span><span class="sxs-lookup"><span data-stu-id="23381-129">BizTalk Editor uses the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window to enable you to examine and set the properties of the nodes in the schema tree.</span></span> <span data-ttu-id="23381-130">本部分介绍使用属性窗口，其中包括有关的特殊注意事项中的属性的某些特征**节点名称**属性、 属性之间的相互依赖项的说明和属性或类型的属性，对于某些允许的最大长度有关的信息。</span><span class="sxs-lookup"><span data-stu-id="23381-130">This section describes some characteristics of working with properties in the Properties window, including special considerations for the **Node Name** property, an explanation of the interdependencies between properties, and information about the maximum lengths allowed for certain properties or types of properties.</span></span>  
  
 <span data-ttu-id="23381-131">本部分的其余部分提供有关特定的特殊节点属性的详细信息和其他通常适用于节点属性的信息。</span><span class="sxs-lookup"><span data-stu-id="23381-131">The remainder of this section provides additional information about particular, special node properties and other information that applies generally to node properties.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="23381-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23381-132">Next steps</span></span>
  
-   [<span data-ttu-id="23381-133">“节点名称”属性</span><span class="sxs-lookup"><span data-stu-id="23381-133">Node Name Property</span></span>](../core/node-name-property.md)  
  
-   [<span data-ttu-id="23381-134">属性依赖项</span><span class="sxs-lookup"><span data-stu-id="23381-134">Property Interdependencies</span></span>](../core/property-interdependencies.md)  
  
-   [<span data-ttu-id="23381-135">其他平面文件属性</span><span class="sxs-lookup"><span data-stu-id="23381-135">Additional Flat File Properties</span></span>](../core/additional-flat-file-properties.md)