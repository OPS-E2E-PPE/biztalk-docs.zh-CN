---
title: 属性组节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea02fae8-4e03-486a-8d9d-185ae230d3a0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31814f9bd38bd07a75be0d4a2cc3e9d8b838720e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965331"
---
# <a name="attribute-group-nodes"></a><span data-ttu-id="5a4f3-102">属性组节点</span><span class="sxs-lookup"><span data-stu-id="5a4f3-102">Attribute Group Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="5a4f3-103">概述</span><span class="sxs-lookup"><span data-stu-id="5a4f3-103">Overview</span></span>
<span data-ttu-id="5a4f3-104">在 BizTalk 编辑器中，你可以添加**属性组**节点**记录**节点或其他**属性组**节点以包含你希望使用更多的属性组个**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-104">In BizTalk Editor, you can add an **Attribute Group** node to a **Record** node or to another **Attribute Group** node to contain a group of attributes that you expect to use in more than one **Record** node.</span></span> <span data-ttu-id="5a4f3-105">添加**属性组**到另一个节点**属性组**节点来实现的属性组嵌套。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-105">Adding an **Attribute Group** node to another **Attribute Group** node achieves attribute group nesting.</span></span> <span data-ttu-id="5a4f3-106">这允许你在一个位置，可在多个定义一组属性**记录**或**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-106">This allows you to define a group of attributes in one place that can be used in multiple **Record** or **Attribute Group** nodes.</span></span> <span data-ttu-id="5a4f3-107">对属性组的后续修改将传播到该属性组所关联的所有节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-107">Subsequent modifications to the attribute group will propagate to all of the nodes with which that attribute group is associated.</span></span> <span data-ttu-id="5a4f3-108">不论在何种节点上下文中进行修改都是如此。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-108">This is true regardless of the node context in which the modifications are made.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a4f3-109">在 BizTalk 编辑器中， **AttributeGroup**节点表示默认情况下，使用字符串\<AttribGroup:attribGroup*N* \>在架构树视图中，其中*N*是单调递增的数字。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-109">In BizTalk Editor, the **AttributeGroup** node is represented by default with the string \<AttribGroup:attribGroup*N*\> in the schema tree view, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="5a4f3-110">你可以更改 attribGroup*N*通过键入新的唯一名称，在其名称一部分其**组引用**属性。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-110">You can change the attribGroup*N* portion of its name by typing a new unique name in its **Group Reference** property.</span></span>  
  
 <span data-ttu-id="5a4f3-111">最初创建时**属性组**节点，你只需将其插入到之一**记录**或**属性组**节点，它将使用，并选择性地更改其名称在其**组引用**属性。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-111">When initially creating an **Attribute Group** node, you simply insert it into one of the **Record** or **Attribute Group** nodes in which it will be used, and optionally change its name in its **Group Reference** property.</span></span> <span data-ttu-id="5a4f3-112">有两种方法要在另一个中使用相同的属性组**记录**或**属性组**节点：</span><span class="sxs-lookup"><span data-stu-id="5a4f3-112">There are two ways to use the same attribute group in another **Record** or **Attribute Group** node:</span></span>  
  
-   <span data-ttu-id="5a4f3-113">你可以复制现有**属性组**节点然后将其粘贴到该其他**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-113">You can copy the existing **Attribute Group** node and then paste it into that other **Record** node.</span></span>  
  
-   <span data-ttu-id="5a4f3-114">你可以将插入一个新**属性组**节点到该其他**记录**节点，再然后将其设置**组引用**属性的新**属性组**节点以引用现有**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-114">You can insert a new **Attribute Group** node into that other **Record** node, and then set the **Group Reference** property of the new **Attribute Group** node to reference an existing **Attribute Group** node.</span></span>  
  
 <span data-ttu-id="5a4f3-115">此后，你可以修改**属性组**节点-例如，通过添加或删除**字段特性**节点-任何的上下文中**记录**或**属性组**粘贴到其中的节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-115">Thereafter, you can modify the **Attribute Group** node—for example, by adding or deleting a **Field Attribute** node—in the context of any **Record** or **Attribute Group** node into which you pasted it.</span></span> <span data-ttu-id="5a4f3-116">更改将传播到所有其他**记录**或**属性组**属性组与之关联的节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-116">That change will propagate to all other **Record** or **Attribute Group** nodes with which the attribute group is associated.</span></span>  
  
 <span data-ttu-id="5a4f3-117">它毫无添加**属性组**而无需添加至少一个相关节点，其中包括相关节点的节点**字段特性**节点，**任何属性**节点，和 （嵌套）**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-117">It would be pointless to add an **Attribute Group** node without adding at least one relevant node to it, where relevant nodes include **Field Attribute** nodes, **Any Attribute** nodes, and (nested) **Attribute Group** nodes.</span></span> <span data-ttu-id="5a4f3-118">事实上，仅包含一个属性的属性组是有些考虑不周的，除非您计划以后将添加更多属性。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-118">In fact, an attribute group that contains only a single attribute is somewhat ill-conceived, unless you are making a point of planning for the addition of more attributes in the future.</span></span>  
  
 <span data-ttu-id="5a4f3-119">**属性组**节点可以相互嵌套，从而可以如何构造和组合属性组的更多的可能性。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-119">**Attribute Group** nodes can be nested, allowing more possibilities in how groups of attributes can be constructed and combined.</span></span> <span data-ttu-id="5a4f3-120">**属性组**节点还可以包含**任何属性**节点，使属性组以包含通配符字符功能来处理可以适应将属性实例。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-120">**Attribute Group** nodes can also contain the **Any Attribute** node, allowing an attribute group to contain wildcard character capabilities with respect to the attribute instances it can accommodate.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="5a4f3-121">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="5a4f3-121">XSD representation</span></span>  
 <span data-ttu-id="5a4f3-122">当**属性组**首先将节点添加到**记录**节点或其他**属性组**节点中，相应的 XML 架构定义 (XSD) 的两个不同的区域语言架构表示形式会受到影响。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-122">When an **Attribute Group** node is first added to a **Record** node or to another **Attribute Group** node, two distinct areas of the corresponding XML Schema definition (XSD) language representation of the schema are affected.</span></span> <span data-ttu-id="5a4f3-123">在下面的示例中，新**属性组**节点，在加粗，并且已添加到现有**记录**已包含的现有节点**Field 元素**节点。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-123">In the following example, a new **Attribute Group** node, in bold, has been added to an existing **Record** node that already contains an existing **Field Element** node.</span></span>  
  
```  
        ...  
        <xs:element name="ExistingRecord">  
            <xs:complexType>  
                <xs:sequence>  
                    <xs:element name="ExistingFieldElement" type="xs:string" />  
                </xs:sequence>  
                <xs:attributeGroup ref="attrGroup0" />  
            </xs:complexType>  
        </xs:element>  
        ...   
    <xs:attributeGroup name="attrGroup0" />  
</xs:schema>  
```  
  
 <span data-ttu-id="5a4f3-124">请注意如何**attributeGroup**的 XSD 表示形式中的元素**记录**节点引用全局**attributeGroup**作为子级添加的元素**架构**元素。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-124">Note how the **attributeGroup** element within the XSD representation of the **Record** node references a global **attributeGroup** element that is added as a child of the **schema** element.</span></span> <span data-ttu-id="5a4f3-125">架构的 XSD 表示形式中的此属性组全局定义允许在整个架构的多个位置引用属性组。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-125">This global definition of the attribute group within the XSD representation of the schema allows the attribute group to be referenced in multiple locations throughout the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a4f3-126">会自动提供的默认属性组名称都具有窗体 attrGroup*N*，其中*N*是单调递增的数字。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-126">Default attribute group names that are supplied automatically have the form attrGroup*N*, where *N* is a monotonically increasing numeral.</span></span> <span data-ttu-id="5a4f3-127">可以通过提供新的、 唯一的名称，在属性组重命名其**组引用**属性。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-127">You can rename an attribute group by providing a new, unique name in its **Group Reference** property.</span></span> <span data-ttu-id="5a4f3-128">不能在架构树中对属性组进行重命名。</span><span class="sxs-lookup"><span data-stu-id="5a4f3-128">An attribute group cannot be renamed in place within the schema tree.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a4f3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a4f3-129">See Also</span></span>  
-  [<span data-ttu-id="5a4f3-130">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="5a4f3-130">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="5a4f3-131">节点属性</span><span class="sxs-lookup"><span data-stu-id="5a4f3-131">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="5a4f3-132">**序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="5a4f3-132">**Sequence Group Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="5a4f3-133">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="5a4f3-133">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
-  [<span data-ttu-id="5a4f3-134">“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="5a4f3-134">Field Attribute Nodes</span></span>](../core/field-attribute-nodes.md)   
-  [<span data-ttu-id="5a4f3-135">“任何属性”节点</span><span class="sxs-lookup"><span data-stu-id="5a4f3-135">Any Attribute Nodes</span></span>](../core/any-attribute-nodes.md)