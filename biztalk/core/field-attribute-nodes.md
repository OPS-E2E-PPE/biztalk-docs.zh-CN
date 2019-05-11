---
title: 字段属性节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e964c07-53e5-473f-84f2-05af4796cbbe
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b804223622a197f9de0b18cce34f8ab57d6a6fc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345631"
---
# <a name="field-attribute-nodes"></a><span data-ttu-id="9d02a-102">字段属性节点</span><span class="sxs-lookup"><span data-stu-id="9d02a-102">Field Attribute Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="9d02a-103">概述</span><span class="sxs-lookup"><span data-stu-id="9d02a-103">Overview</span></span>
<span data-ttu-id="9d02a-104">在 BizTalk 编辑器中，使用**字段属性**节点可以是简单在本质上，如字符串和数字信息的项进行说明。</span><span class="sxs-lookup"><span data-stu-id="9d02a-104">In BizTalk Editor, you use **Field Attribute** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="9d02a-105">此外，它们用于时有问题的信息显示为一条消息，而不是显示为一个 XML 元素的内容的实际实例中的属性的值。</span><span class="sxs-lookup"><span data-stu-id="9d02a-105">Further, they are used when the information in question appears as the value of an attribute in an actual instance of a message, as opposed to appearing as the content of an XML element.</span></span> <span data-ttu-id="9d02a-106">有关其他信息存储为元素内容的信息，请参阅[字段元素节点](../core/field-element-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="9d02a-106">For additional information about information that is stored as element content, see [Field Element Nodes](../core/field-element-nodes.md).</span></span>  

 <span data-ttu-id="9d02a-107">虽然最简单的方式使用**字段属性**节点是为的子节点**记录**节点，它们还可以使用为的子节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="9d02a-107">Although the most straightforward use of **Field Attribute** nodes is as child nodes of **Record** nodes, they can also be used as child nodes of **Attribute Group** nodes.</span></span> <span data-ttu-id="9d02a-108">在后一种情况下，**字段属性**节点的子级**属性组**节点都可用作属性的任何**记录**包括该的节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="9d02a-108">In the latter case, the **Field Attribute** nodes that are children of an **Attribute Group** node are available as attributes of any **Record** node that includes that **Attribute Group** node.</span></span> <span data-ttu-id="9d02a-109">有关详细信息**属性组**节点，请参阅[属性组节点](../core/attribute-group-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="9d02a-109">For more information about **Attribute Group** nodes, see [Attribute Group Nodes](../core/attribute-group-nodes.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="9d02a-110">在 BizTalk 编辑器中的元素和属性元素只能通过**字段**节点，但它们具有不同的图标与它们关联在架构树视图中，XSD 窗口中的不同 XML 表示形式和在 Visual Studio 属性窗口中的不同属性。</span><span class="sxs-lookup"><span data-stu-id="9d02a-110">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, though they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  

 <span data-ttu-id="9d02a-111">对于任何给定项的项信息意味着单一的离散简单类型，例如字符串或数字，其中一条 XML 消息中的信息有始终是一个有关是否应将该信息表示为属性的元素，或作为的问题该元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="9d02a-111">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="9d02a-112">作为一般规则，表示的某项信息，如属性往往是更合适时可能的值为离散，几个单位，往往可以修改该元素本身的语义。</span><span class="sxs-lookup"><span data-stu-id="9d02a-112">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="9d02a-113">代表，往往是更合适时的可能值可以重复的次数，可变数量的子元素的某项信息可能具有更广泛范围的值，可能会很长，如下所示的长字符串，并同级的几个值之一，它们的顺序是相关。</span><span class="sxs-lookup"><span data-stu-id="9d02a-113">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="9d02a-114">如果你创建现有类型的 XML 架构文档，使用的所选**字段元素**节点或**字段属性**节点信息的特定项的已完成，并您必须使用与 XML 相匹配的节点。</span><span class="sxs-lookup"><span data-stu-id="9d02a-114">If you are creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  

> [!NOTE]
>  <span data-ttu-id="9d02a-115">根节点可能没有**字段**属性。</span><span class="sxs-lookup"><span data-stu-id="9d02a-115">Root nodes may not have **Field** attributes.</span></span> <span data-ttu-id="9d02a-116">**字段**特性附加到**根**节点将不与架构一起保存。</span><span class="sxs-lookup"><span data-stu-id="9d02a-116">**Field** attributes attached to the **Root** node are not saved with the schema.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="9d02a-117">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="9d02a-117">XSD representation</span></span>  
 <span data-ttu-id="9d02a-118">当**字段属性**节点插入到**记录**节点，在任何其他子节点结尾处插入该实体**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="9d02a-118">When a **Field Attribute** node is inserted into a **Record** node, it is inserted at the end of any other child nodes in the **Record** node.</span></span> <span data-ttu-id="9d02a-119">其中包括之后插入**序列**，**选**，或**所有**元素，其中包含任何非属性节点，和以前的所有属性节点后插入。</span><span class="sxs-lookup"><span data-stu-id="9d02a-119">This includes being inserted after the **sequence**, **choice**, or **all** element containing any nonattribute nodes, and after any attribute nodes that were previously inserted.</span></span> <span data-ttu-id="9d02a-120">下面的示例显示了一个新**字段属性**节点，以粗体显示的末尾插入**记录**节点，其中对节点进行了命名以说明其标识）。</span><span class="sxs-lookup"><span data-stu-id="9d02a-120">The following example shows a new **Field Attribute** node, in bold, inserted at the end of a **Record** node (with nodes named to clarify their identity).</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="9d02a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d02a-121">See Also</span></span>  
- [<span data-ttu-id="9d02a-122">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="9d02a-122">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="9d02a-123">节点属性</span><span class="sxs-lookup"><span data-stu-id="9d02a-123">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="9d02a-124">**字段元素节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9d02a-124">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
- [<span data-ttu-id="9d02a-125">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="9d02a-125">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)   
- [<span data-ttu-id="9d02a-126">“属性组”节点</span><span class="sxs-lookup"><span data-stu-id="9d02a-126">Attribute Group Nodes</span></span>](../core/attribute-group-nodes.md)
