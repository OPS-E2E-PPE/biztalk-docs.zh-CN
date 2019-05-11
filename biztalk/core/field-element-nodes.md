---
title: 字段元素节点 |Microsoft Docs
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
ms.openlocfilehash: f56c7f70822a37a7da5211eb8be0604b1e9f5a6b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388091"
---
# <a name="field-element-nodes"></a><span data-ttu-id="4ea5f-102">字段元素节点</span><span class="sxs-lookup"><span data-stu-id="4ea5f-102">Field Element Nodes</span></span>

## <a name="overview"></a><span data-ttu-id="4ea5f-103">概述</span><span class="sxs-lookup"><span data-stu-id="4ea5f-103">Overview</span></span>
<span data-ttu-id="4ea5f-104">在 BizTalk 编辑器中，使用**Field 元素**节点可以是简单在本质上，如字符串和数字信息的项进行说明。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-104">In BizTalk Editor, you use **Field Element** nodes to describe items of information that are simple in nature, such as strings and numbers.</span></span> <span data-ttu-id="4ea5f-105">此外，它们用于时有问题的信息显示为一条消息，而不是显示为一个 XML 元素与关联的属性的值的实际实例中的 XML 元素的内容。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-105">Further, they are used when the information in question appears as the content of an XML element in an actual instance of a message, as opposed to appearing as the value of an attribute associated with an XML element.</span></span> <span data-ttu-id="4ea5f-106">有关其他信息存储为属性值的信息，请参阅[字段属性节点](../core/field-attribute-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-106">For additional information about information that is stored as attribute values, see [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  

> [!NOTE]
>  <span data-ttu-id="4ea5f-107">在 BizTalk 编辑器中的元素和属性元素只能通过**字段**节点，但它们具有不同的图标与它们关联在架构树视图中，XSD 窗口中的不同 XML 表示形式和在 Visual Studio 属性窗口中的不同属性。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-107">In BizTalk Editor, both the element and attribute elements can be represented by a **Field** node, although they have different icons associated with them in the schema tree view, a different XML representation in the XSD window, and different properties in the Visual Studio Properties window.</span></span>  

 <span data-ttu-id="4ea5f-108">对于任何给定项的项信息意味着单一的离散简单类型，例如字符串或数字，其中一条 XML 消息中的信息有始终是一个有关是否应将该信息表示为属性的元素，或作为的问题该元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-108">For any given item of information in an XML message, where item of information means a single discrete simple type, such as a string or number, there is always a question regarding whether that information should be represented as the attribute of an element, or as a subelement of that element.</span></span> <span data-ttu-id="4ea5f-109">作为一般规则，表示的某项信息，如属性往往是更合适时可能的值为离散，几个单位，往往可以修改该元素本身的语义。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-109">As a general rule, representing an item of information as an attribute tends to be more appropriate when the possible values are discrete, few in number, and tend to modify the semantics of the element itself.</span></span> <span data-ttu-id="4ea5f-110">代表，往往是更合适时的可能值可以重复的次数，可变数量的子元素的某项信息可能具有更广泛范围的值，可能会很长，如下所示的长字符串，并同级的几个值之一，它们的顺序是相关。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-110">Representing an item of information as a subelement tends to be more appropriate when the possible values can repeat a variable number of times, are likely to have more widely ranging values, might be long, as in long strings, and are one of several sibling values where their order is relevant.</span></span> <span data-ttu-id="4ea5f-111">如果您只需创建为现有类型的 XML 架构文档，使用的所选**Field 元素**节点或**字段属性**节点信息的特定项的已完成，并且必须使用与 XML 相匹配的节点。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-111">If you are just creating a schema for an existing type of XML document, your choice of using a **Field Element** node or a **Field Attribute** node for a particular item of information has already been made for you, and you must use the node that matches the XML.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="4ea5f-112">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="4ea5f-112">XSD representation</span></span>  
 <span data-ttu-id="4ea5f-113">当**字段元素**节点插入到**记录**节点中的其他所有子节点结尾处插入该实体**序列**中的元素**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="4ea5f-113">When a **Field Element** node is inserted into a **Record** node, it is inserted at the end of any other child nodes within the **sequence** element in the **Record** node.</span></span> <span data-ttu-id="4ea5f-114">下面的示例显示了一个新**Field 元素**节点，以粗体显示的末尾插入**序列**中的元素**记录**节点，其中对节点进行了命名以说明其标识).</span><span class="sxs-lookup"><span data-stu-id="4ea5f-114">The following example shows a new **Field Element** node, in bold, inserted at the end of the **sequence** element in a **Record** node (with nodes named to clarify their identity).</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="4ea5f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ea5f-115">See Also</span></span>  
- [<span data-ttu-id="4ea5f-116">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="4ea5f-116">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="4ea5f-117">节点属性</span><span class="sxs-lookup"><span data-stu-id="4ea5f-117">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="4ea5f-118">**字段元素节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="4ea5f-118">**Field Element Node Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="4ea5f-119">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="4ea5f-119">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
