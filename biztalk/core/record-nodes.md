---
title: 记录节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43af077d-5db8-43ca-8bd0-e3a9e3ebe2b0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: beb676565b539f813062e9083265903350724a09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398051"
---
# <a name="record-nodes"></a><span data-ttu-id="2c242-102">记录节点</span><span class="sxs-lookup"><span data-stu-id="2c242-102">Record Nodes</span></span>
<span data-ttu-id="2c242-103">在 BizTalk 编辑器中，使用**记录**节点，用于表示集合的信息，其中的各个项可以是：</span><span class="sxs-lookup"><span data-stu-id="2c242-103">In BizTalk Editor, you use a **Record** node to represent a collection of information, the individual items of which can be:</span></span>  

- <span data-ttu-id="2c242-104">简单类型的信息，如字符串和数字，表示为子字段节点。</span><span class="sxs-lookup"><span data-stu-id="2c242-104">Simple types of information, such as strings and numbers, represented as child field nodes.</span></span> <span data-ttu-id="2c242-105">这些子字段节点可以是**Field 元素**节点或**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="2c242-105">These child field nodes can be either **Field Element** nodes or **Field Attribute** nodes.</span></span> <span data-ttu-id="2c242-106">有关字段节点这两种类型的其他信息，请参阅[字段元素节点](../core/field-element-nodes.md)并[字段属性节点](../core/field-attribute-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="2c242-106">For additional information about these two types of field nodes, see [Field Element Nodes](../core/field-element-nodes.md) and [Field Attribute Nodes](../core/field-attribute-nodes.md).</span></span>  

- <span data-ttu-id="2c242-107">复杂类型的信息，表示为子**记录**节点或一个组节点 (**序列组**节点，**选择组**节点，或**全部组**节点)。</span><span class="sxs-lookup"><span data-stu-id="2c242-107">Complex types of information, represented as child **Record** nodes or as a group node (**Sequence Group** node, **Choice Group** node, or **All Group** node).</span></span>  

- <span data-ttu-id="2c242-108">任何未检查的类型的信息，表示为子**Any 元素**或**任何属性**节点。</span><span class="sxs-lookup"><span data-stu-id="2c242-108">Any unexamined type of information, represented as child **Any Element** or **Any Attribute** nodes.</span></span>  

- <span data-ttu-id="2c242-109">所表示的属性组的**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="2c242-109">Groups of attributes represented by an **Attribute Group** node.</span></span>  

  <span data-ttu-id="2c242-110">插入到新的子节点时**记录**节点、 子节点始终插入到当前的子节点的末尾。</span><span class="sxs-lookup"><span data-stu-id="2c242-110">When you insert a new child node into a **Record** node, the child node is always inserted at the end of the current child nodes.</span></span> <span data-ttu-id="2c242-111">在 XML 架构定义 (XSD) 语言表示形式，将新元素添加到其相应的区域，这意味着非属性元素都添加到中的元素末尾的最终**序列**， **所选**，**所有**，或**组**元素和属性元素添加到任何其他属性元素，所有这些之后发生的末尾**序列**，**选**，**所有**，或**组**元素。</span><span class="sxs-lookup"><span data-stu-id="2c242-111">Within the XML Schema definition (XSD) language representation, new elements are added to the end of their corresponding areas, meaning that nonattribute elements are added to the end of the elements within the **sequence**, **choice**, **all**, or **group** element, and attribute elements are added to the end of any other attribute elements, all of which occur after the **sequence**, **choice**, **all**, or **group** element.</span></span>  

## <a name="xsd-representation"></a><span data-ttu-id="2c242-112">XSD 表示形式</span><span class="sxs-lookup"><span data-stu-id="2c242-112">XSD representation</span></span>  
 <span data-ttu-id="2c242-113">当第一次插入的一个新的 XSD 表示形式**记录**节点只有三个行组成，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2c242-113">When first inserted, the XSD representation of a new **Record** node consists of only three lines, as shown in the following example.</span></span>  

```  
<xs:element name="Record">  
      <xs:complexType />  
</xs:element>  
```  

 <span data-ttu-id="2c242-114">当三个属性节点以外的任何子节点 (**字段属性**，**属性组**，并**任何属性**) 添加到**记录**节点，放在默认情况下**序列**元素内的**complexType**元素。</span><span class="sxs-lookup"><span data-stu-id="2c242-114">When any child node other than one of the three attribute nodes (**Field Attribute**, **Attribute Group**, and **Any Attribute**) is added to a **Record** node, by default it is placed within a **sequence** element within the **complexType** element.</span></span> <span data-ttu-id="2c242-115">**序列**时添加，并且如果删除所有非属性子节点中删除第一个非属性子节点添加元素。</span><span class="sxs-lookup"><span data-stu-id="2c242-115">The **sequence** element is added when the first nonattribute child node is added, and removed if all the nonattribute child nodes are deleted.</span></span> <span data-ttu-id="2c242-116">中添加的所有三种类型的属性节点**complexType**元素，但之外及之后任何**序列**元素。</span><span class="sxs-lookup"><span data-stu-id="2c242-116">All three types of attribute nodes are added within the **complexType** element, but outside and after any **sequence** element.</span></span>  

 <span data-ttu-id="2c242-117">**序列**中的非属性子节点将被添加的元素也可以是**选**或**所有**元素，如果更改**Group Order Type （节点所有架构的属性）** 相应的架构树中节点的属性**选**或**所有**分别。</span><span class="sxs-lookup"><span data-stu-id="2c242-117">The **sequence** element within which nonattribute child nodes are added can also be a **choice** or **all** element if you change the **Group Order Type (Node Property of All Schemas)** property of the corresponding node in the schema tree to **Choice** or **All**, respectively.</span></span>  

 <span data-ttu-id="2c242-118">在以下示例中，**记录**节点已重命名为的 shipTo。</span><span class="sxs-lookup"><span data-stu-id="2c242-118">In the following example, the **Record** node has been renamed shipTo.</span></span> <span data-ttu-id="2c242-119">中的位置**记录**其中添加属性和非属性节点的节点显示在方括号中。</span><span class="sxs-lookup"><span data-stu-id="2c242-119">The locations within the **Record** node where attribute and nonattribute nodes are added are shown in brackets.</span></span>  

```  
<xs:element name="">  
    <xs:complexType>  
        <xs:sequence>  
            [Nonattribute child nodes of the record go here.]  
            [Always add new nonattribute child nodes to the end.]  
        </xs:sequence>  
            [Attribute child nodes of the record go here.]  
            [Always add new attribute child nodes to the end.]  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a><span data-ttu-id="2c242-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c242-120">See Also</span></span>  
- [<span data-ttu-id="2c242-121">架构的 BizTalk 表示形式</span><span class="sxs-lookup"><span data-stu-id="2c242-121">BizTalk Representation of Schemas</span></span>](../core/biztalk-representation-of-schemas.md)   
- [<span data-ttu-id="2c242-122">节点属性</span><span class="sxs-lookup"><span data-stu-id="2c242-122">Node Properties</span></span>](../core/node-properties.md)   
- <span data-ttu-id="2c242-123">**记录节点属性**和**组顺序类型 （所有架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2c242-123">**Record Node Properties** and **Group Order Type (Node Property of All Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
- [<span data-ttu-id="2c242-124">如何设置节点属性</span><span class="sxs-lookup"><span data-stu-id="2c242-124">How to Set Node Properties</span></span>](../core/how-to-set-node-properties.md)
