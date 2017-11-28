---
title: "字段属性节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 701acadc9d1612cc5b05a05970fc2c1b92bfbb9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="field-attribute-nodes"></a><span data-ttu-id="ec5b8-102">“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="ec5b8-102">Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="ec5b8-103">概述</span><span class="sxs-lookup"><span data-stu-id="ec5b8-103">Overview</span></span>
<span data-ttu-id="ec5b8-104">在 BizTalk 编辑器中，使用**字段特性**节点来描述信息的简单的性质，如字符串和数字的项。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-104">In BizTalk Editor, you use **Field Attribute** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="ec5b8-105">此外，它们时，使用问题的信息显示为一条消息，而不是显示为 XML 元素的内容的实际实例中的属性的值。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-105">Further, they are used when the information in question appears as the value of an attribute in an actual instance of a message, as opposed to appearing as the content of an XML element.</span></span> <span data-ttu-id="ec5b8-106">有关存储为元素内容的信息的其他信息，请参阅[字段元素节点](../core/field-element-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-106">For additional information about information that is stored as element content, see [Field Element Nodes](../core/field-element-nodes.md).</span></span>  
  
 <span data-ttu-id="ec5b8-107">虽然最简单利用**字段特性**作为的子节点的节点是**记录**节点，它们还可作为的子节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-107">Although the most straightforward use of **Field Attribute** nodes is as child nodes of **Record** nodes, they can also be used as child nodes of **Attribute Group** nodes.</span></span> <span data-ttu-id="ec5b8-108">在后一种情况下，**字段特性**节点的子级的**属性组**节点都可用作属性的任何**记录**包括该的节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-108">In the latter case, the **Field Attribute** nodes that are children of an **Attribute Group** node are available as attributes of any **Record** node that includes that **Attribute Group** node.</span></span> <span data-ttu-id="ec5b8-109">有关详细信息**属性组**节点，请参阅[特性组节点](../core/attribute-group-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-109">For more information about **Attribute Group** nodes, see [Attribute Group Nodes](../core/attribute-group-nodes.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5b8-110">在 BizTalk 编辑器中，元素和属性元素可以通过表示**字段**节点，但它们具有不同架构树视图中，在 XSD 窗口中，不同的 XML 表示形式中与其关联的图标和在 Visual Studio 属性窗口中的不同属性。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-110">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, though they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  
  
 <span data-ttu-id="ec5b8-111">对于任何给定项的 XML 消息，其中的信息项表示一个单个的离散简单类型，例如字符串或数字中的信息有始终是一个有关是否应作为元素，或作为该属性表示该信息的问题该元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-111">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="ec5b8-112">作为一般规则、 表示一条信息项，如属性往往是更合适时可能的值为离散、 几个在编号、 和往往会修改该元素本身的语义。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-112">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="ec5b8-113">子元素往往是更合适时可能的值可以重复变量次数，代表一条信息项很可能会有更广泛范围值、 可能会很长，如下所示的长字符串，和是几个同级值之一，其顺序并相关。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-113">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="ec5b8-114">如果你创建现有类型的 XML 架构文档，你选择使用**Field 元素**节点或**字段特性**已为你进行特定项的信息的节点和你必须使用 XML 与匹配的节点。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-114">If you are creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ec5b8-115">根节点可能没有**字段**属性。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="ec5b8-116">**字段**属性附加到**根**节点不会保存具有架构。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="ec5b8-117">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="ec5b8-117">XSD representation</span></span>  
 <span data-ttu-id="ec5b8-118">当**字段特性**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-118">When a **Field Attribute** node is inserted into a **Record** node, it is inserted at the end of any other child nodes in the **Record** node.</span></span> <span data-ttu-id="ec5b8-119">这包括正在之后插入**序列**，**选择**，或**所有**元素，其中包含的任何非属性节点，和任何以前的属性节点之后插入。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-119">This includes being inserted after the **sequence**, **choice**, or **all** element containing any nonattribute nodes, and after any attribute nodes that were previously inserted.</span></span> <span data-ttu-id="ec5b8-120">下面的示例演示一个新**字段特性**节点，以粗体显示，在末尾插入**记录**节点 （带有名为以阐明其标识的节点）。</span><span class="sxs-lookup"><span data-stu-id="ec5b8-120">The following example shows a new **Field Attribute** node, in bold, inserted at the end of a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="FieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec5b8-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec5b8-121">See Also</span></span>  
-  [<span data-ttu-id="ec5b8-122">BizTalk 表示形式架构</span><span class="sxs-lookup"><span data-stu-id="ec5b8-122">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="ec5b8-123">节点属性</span><span class="sxs-lookup"><span data-stu-id="ec5b8-123">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="ec5b8-124">**字段元素节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="ec5b8-124">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
-  [<span data-ttu-id="ec5b8-125">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="ec5b8-125">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
-  [<span data-ttu-id="ec5b8-126">属性组节点</span><span class="sxs-lookup"><span data-stu-id="ec5b8-126">Attribute Group Nodes</span></span>](../core/attribute-group-nodes.md)