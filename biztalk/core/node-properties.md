---
title: 节点属性 |Microsoft 文档
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
ms.openlocfilehash: d41f0f3b0fe0b302a763629b8777669b54f6cc86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264213"
---
# <a name="node-properties"></a><span data-ttu-id="79ade-102">节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-102">Node Properties</span></span>

## <a name="overview"></a><span data-ttu-id="79ade-103">概述</span><span class="sxs-lookup"><span data-stu-id="79ade-103">Overview</span></span>
<span data-ttu-id="79ade-104">在 BizTalk 编辑器中，可以在“Visual Studio 属性”窗口中检查和设置节点属性。</span><span class="sxs-lookup"><span data-stu-id="79ade-104">In BizTalk Editor, you examine and set node properties in the Visual Studio Properties window.</span></span> <span data-ttu-id="79ade-105">在架构树视图中选择不同类型的节点时，“属性”窗口中将显示不同的属性集。</span><span class="sxs-lookup"><span data-stu-id="79ade-105">As you select different types of nodes in the schema tree view, different sets of properties are displayed in the Properties window.</span></span> <span data-ttu-id="79ade-106">按原样标准中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，可以显示这些属性，按类别或它们的类别未指示按字母顺序。</span><span class="sxs-lookup"><span data-stu-id="79ade-106">As is standard in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], these properties can be displayed either in categories or alphabetically with no indication of their categories.</span></span> <span data-ttu-id="79ade-107">使用靠近“属性”窗口顶部的标准按钮可以切换此设置。</span><span class="sxs-lookup"><span data-stu-id="79ade-107">Use the standard buttons near the top of the Properties window to toggle this setting.</span></span>  
  
 <span data-ttu-id="79ade-108">节点属性（尤其是设置为默认值之外的值时）通常在 XML 架构定义 (XSD) 语言中表示为与相应元素关联的特性和特性值。</span><span class="sxs-lookup"><span data-stu-id="79ade-108">Node properties, especially when set to values other than their defaults, are generally represented in the XML Schema definition (XSD) language as attributes and attribute values associated with the corresponding element.</span></span> <span data-ttu-id="79ade-109">例如，在属性设置为**最小出现次数**和**Max Occurs**属性，可用于多个不同节点类型，设置的值可用作值**minOccurs**和**maxOccurs**特性，分别为其表示的节点的元素与关联**最小出现次数**和**最大值发生**正在设置属性。</span><span class="sxs-lookup"><span data-stu-id="79ade-109">For example, when properties are set for the **Min Occurs** and **Max Occurs** properties, which are available for several different node types, the values that are set are used as the values of the **minOccurs** and **maxOccurs** attributes, respectively, associated with the element that represents the node for which the **Min Occurs** and **Max Occurs** properties are being set.</span></span>  

## <a name="property-types"></a><span data-ttu-id="79ade-110">属性类型</span><span class="sxs-lookup"><span data-stu-id="79ade-110">Property types</span></span>
 <span data-ttu-id="79ade-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]开发人员参考包含组织按类别和按字母顺序的各种节点类型的属性的参考部分。</span><span class="sxs-lookup"><span data-stu-id="79ade-111">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] developer reference contains a reference section for the properties of the various node types, organized by category and alphabetically.</span></span> <span data-ttu-id="79ade-112">以下汇总每个节点类型与关联的属性：</span><span class="sxs-lookup"><span data-stu-id="79ade-112">The following summarize the properties associated with each node type:</span></span>  
  
-   <span data-ttu-id="79ade-113">架构节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-113">Schema Node Properties</span></span>
  
-   <span data-ttu-id="79ade-114">记录节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-114">Record Node Properties</span></span>
  
-   <span data-ttu-id="79ade-115">字段元素节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-115">Field Element Node Properties</span></span>
  
-   <span data-ttu-id="79ade-116">字段属性节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-116">Field Attribute Node Properties</span></span>
  
-   <span data-ttu-id="79ade-117">序列组节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-117">Sequence Group Node Properties</span></span>
  
-   <span data-ttu-id="79ade-118">选择组节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-118">Choice Group Node Properties</span></span> 
  
-   <span data-ttu-id="79ade-119">所有组节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-119">All Group Node Properties</span></span>
  
-   <span data-ttu-id="79ade-120">属性组节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-120">Attribute Group Node Properties</span></span>
  
-   <span data-ttu-id="79ade-121">“任何元素”节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-121">Any Element Node Properties</span></span>
  
-   <span data-ttu-id="79ade-122">“任何属性”节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-122">Any Attribute Node Properties</span></span>
  
-   <span data-ttu-id="79ade-123">等效的节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-123">Equivalent Node Properties</span></span>
  
-   <span data-ttu-id="79ade-124">等效的子节点属性</span><span class="sxs-lookup"><span data-stu-id="79ade-124">Equivalent Child Node Properties</span></span>

<span data-ttu-id="79ade-125">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="79ade-125">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="79ade-126">**节点属性-按字母顺序排列列表**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]包含的所有独立参考主题的每个节点属性，其中一些适用于各种类型的节点。</span><span class="sxs-lookup"><span data-stu-id="79ade-126">**Node Properties — Alphabetical Listings** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] contains all of the individual reference topics for each node property, some of which apply to various types of nodes.</span></span> <span data-ttu-id="79ade-127">分立参考主题按照是适用于所有架构类型的基本属性还是与架构编辑器扩展（例如，平面文件扩展）关联的特殊属性进行分类。</span><span class="sxs-lookup"><span data-stu-id="79ade-127">The individual reference topics are categorized according to whether they are basic properties that apply to all types of schemas, or a specialized properties that are associated with a schema editor extension, such as the flat file extension.</span></span> <span data-ttu-id="79ade-128">在这些类别中，它们按字母顺序列出。</span><span class="sxs-lookup"><span data-stu-id="79ade-128">Within these categories, they are listed alphabetically.</span></span>  
  
 <span data-ttu-id="79ade-129">BizTalk 编辑器使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口使您能够在架构树中检查和设置节点的属性。</span><span class="sxs-lookup"><span data-stu-id="79ade-129">BizTalk Editor uses the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window to enable you to examine and set the properties of the nodes in the schema tree.</span></span> <span data-ttu-id="79ade-130">本部分介绍使用属性在属性窗口中，包括有关的特殊注意事项的一些特征**节点名称**属性、 属性，之间相互依赖关系的说明和属性或类型的属性，对于某些允许的最大长度有关的信息。</span><span class="sxs-lookup"><span data-stu-id="79ade-130">This section describes some characteristics of working with properties in the Properties window, including special considerations for the **Node Name** property, an explanation of the interdependencies between properties, and information about the maximum lengths allowed for certain properties or types of properties.</span></span>  
  
 <span data-ttu-id="79ade-131">本部分的其余内容提供有关特定的特殊节点属性的其他信息，以及通常适用于节点属性的其他信息。</span><span class="sxs-lookup"><span data-stu-id="79ade-131">The remainder of this section provides additional information about particular, special node properties and other information that applies generally to node properties.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="79ade-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="79ade-132">Next steps</span></span>
  
-   [<span data-ttu-id="79ade-133">节点名称属性</span><span class="sxs-lookup"><span data-stu-id="79ade-133">Node Name Property</span></span>](../core/node-name-property.md)  
  
-   [<span data-ttu-id="79ade-134">属性相互依赖关系</span><span class="sxs-lookup"><span data-stu-id="79ade-134">Property Interdependencies</span></span>](../core/property-interdependencies.md)  
  
-   [<span data-ttu-id="79ade-135">其他平面文件属性</span><span class="sxs-lookup"><span data-stu-id="79ade-135">Additional Flat File Properties</span></span>](../core/additional-flat-file-properties.md)