---
title: 字段元素节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65b5e1f6-283f-4172-9bc2-f04a0ea6753d
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74c3732ee315ad307f49760e367449216c3e01da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245981"
---
# <a name="field-element-nodes"></a><span data-ttu-id="d043d-102">“字段元素”节点</span><span class="sxs-lookup"><span data-stu-id="d043d-102">Field Element Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="d043d-103">概述</span><span class="sxs-lookup"><span data-stu-id="d043d-103">Overview</span></span>
<span data-ttu-id="d043d-104">在 BizTalk 编辑器中，使用**Field 元素**节点来描述信息的简单的性质，如字符串和数字的项。</span><span class="sxs-lookup"><span data-stu-id="d043d-104">In BizTalk Editor, you use **Field Element** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="d043d-105">此外，它们时，使用问题的信息显示为一条消息，而不是显示为一个 XML 元素与关联属性的值的实际实例中的 XML 元素的内容。</span><span class="sxs-lookup"><span data-stu-id="d043d-105">Further, they are used when the information in question appears as the content of an XML element in an actual instance of a message, as opposed to appearing as the value of an attribute associated with an XML element.</span></span> <span data-ttu-id="d043d-106">有关存储作为特性值的信息的其他信息，请参阅[字段属性节点](../core/field-attribute-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="d043d-106">For additional information about information that is stored as attribute values, see [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d043d-107">在 BizTalk 编辑器中，元素和属性元素可以通过表示**字段**节点，但它们具有不同架构树视图中，在 XSD 窗口中，不同的 XML 表示形式中与其关联的图标和在 Visual Studio 属性窗口中的不同属性。</span><span class="sxs-lookup"><span data-stu-id="d043d-107">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, although they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  
  
 <span data-ttu-id="d043d-108">对于任何给定项的 XML 消息，其中的信息项表示一个单个的离散简单类型，例如字符串或数字中的信息有始终是一个有关是否应作为元素，或作为该属性表示该信息的问题该元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="d043d-108">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="d043d-109">作为一般规则、 表示一条信息项，如属性往往是更合适时可能的值为离散、 几个在编号、 和往往会修改该元素本身的语义。</span><span class="sxs-lookup"><span data-stu-id="d043d-109">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="d043d-110">子元素往往是更合适时可能的值可以重复变量次数，代表一条信息项很可能会有更广泛范围值、 可能会很长，如下所示的长字符串，和是几个同级值之一，其顺序并相关。</span><span class="sxs-lookup"><span data-stu-id="d043d-110">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="d043d-111">如果你只需创建的现有类型的 XML 架构文档，你选择使用**Field 元素**节点或**字段特性**已为你进行特定项的信息的节点并且，你必须使用 XML 与匹配的节点。</span><span class="sxs-lookup"><span data-stu-id="d043d-111">If you are just creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  
  
## <a name="xsd-representation"></a><span data-ttu-id="d043d-112">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="d043d-112">XSD representation</span></span>  
 <span data-ttu-id="d043d-113">当**Field 元素**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**序列**中的元素**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="d043d-113">When a **Field Element** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence** element in the **Record** node.</span></span> <span data-ttu-id="d043d-114">下面的示例演示一个新**Field 元素**节点，以粗体显示，在末尾插入**序列**中的元素**记录**节点 （带有名为以阐明其标识的节点).</span><span class="sxs-lookup"><span data-stu-id="d043d-114">The following example shows a new **Field Element** node, in bold, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:element name="EmptyNestedRecord">  
                <xs:complexType />  
            </xs:element>  
  
        </xs:sequence>  
        <xs:attribute name="ExistingFieldAttribute" type="xs:string" />  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="d043d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d043d-115">See Also</span></span>  
-  [<span data-ttu-id="d043d-116">BizTalk 表示形式架构</span><span class="sxs-lookup"><span data-stu-id="d043d-116">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
-  [<span data-ttu-id="d043d-117">节点属性</span><span class="sxs-lookup"><span data-stu-id="d043d-117">Node Properties</span></span>](../core/node-properties.md)   
-  <span data-ttu-id="d043d-118">**字段元素节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="d043d-118">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
-  [<span data-ttu-id="d043d-119">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="d043d-119">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)