---
title: "如何插入记录、 Field 元素或字段属性节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c26f2281-f1b8-4788-8593-8d6ad29a53f0
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1341a0f2d89070d42620396a8c86d497b5d646ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-record-field-element-or-field-attribute-node"></a><span data-ttu-id="ee748-102">如何插入记录、 Field 元素或字段属性节点</span><span class="sxs-lookup"><span data-stu-id="ee748-102">How to Insert a Record, Field Element, or Field Attribute Node</span></span>
<span data-ttu-id="ee748-103">**记录**节点 (包括**根**节点)，**字段特性**节点，和**Field 元素**节点是唯一的因为可以重命名，以便其名称表示的相应实例消息中的实际、 自定义名为元素的名称。</span><span class="sxs-lookup"><span data-stu-id="ee748-103">**Record** nodes (including the **Root** node), **Field Attribute** nodes, and **Field Element** nodes are unique in that they can be renamed so that their names represent the names of the actual, custom-named elements in a corresponding instance message.</span></span> <span data-ttu-id="ee748-104">例如，如果您命名**记录**节点 FullName，在名为 FullName XML 元素应实例消息中的相应位置。</span><span class="sxs-lookup"><span data-stu-id="ee748-104">For example, if you name a **Record** node FullName, at the corresponding location in an instance message an XML element named FullName is expected.</span></span> <span data-ttu-id="ee748-105">如果该**记录**名为 FullName 节点中有一个子**字段特性**节点名为 RequireFullMiddleName (使用其**最小出现次数**和**Max Occurs**属性设置为**1**)，则**FullName**相应的实例消息中的元素需要具有一个名为特性**RequireFullMiddleName**与之关联。</span><span class="sxs-lookup"><span data-stu-id="ee748-105">If that **Record** node named FullName has a child **Field Attribute** node named RequireFullMiddleName (with its **Min Occurs** and **Max Occurs** properties set to **1**), the **FullName** element in a corresponding instance message will need to have an attribute named **RequireFullMiddleName** associated with it.</span></span>  
  
 <span data-ttu-id="ee748-106">所有**记录**节点，在最初插入、 都包含在与作为 XSD **complexType**元素，但不是与后续**序列**，**选择**，或**所有**元素。</span><span class="sxs-lookup"><span data-stu-id="ee748-106">All **Record** nodes, when initially inserted, are represented in the XSD as with a **complexType** element, but not with a subsequent **sequence**, **choice**, or **all** element.</span></span> <span data-ttu-id="ee748-107">为此，**组顺序类型**，**组 Max Occurs**，和**组最小出现次数**属性**记录**节点不可用以进行修改。</span><span class="sxs-lookup"><span data-stu-id="ee748-107">For this reason, the **Group Order Type**, **Group Max Occurs**, and **Group Min Occurs** properties of the **Record** node are not available for modification.</span></span>  
  
 <span data-ttu-id="ee748-108">一旦添加子级**记录**或**Field 元素**节点**记录**节点，**序列**元素添加到 XSD中的表示形式**complexType**元素以包含此第一个子节点，和**组顺序类型**属性**记录**节点显示的值**序列**。</span><span class="sxs-lookup"><span data-stu-id="ee748-108">As soon as you add a child **Record** or **Field Element** node to the **Record** node, a **sequence** element is added to the XSD representation within the **complexType** element to contain this first child node, and the **Group Order Type** property of the **Record** node shows a value of **Sequence**.</span></span> <span data-ttu-id="ee748-109">在大多数情况下，你可以更改**组顺序类型**属性从**序列**到**选择**，并在更多限制的情况下，从**序列**到**所有**，从而更改包含为相应的子节点的元素对**complexType/选择**或**complexType 或所有**分别。</span><span class="sxs-lookup"><span data-stu-id="ee748-109">In most circumstances, you can change the **Group Order Type** property from **Sequence** to **Choice**, and in more limited circumstances, from **Sequence** to **All**, thereby changing the element pair that contains the corresponding child nodes to either **complexType/choice** or **complexType/all**, respectively.</span></span>  
  
 <span data-ttu-id="ee748-110">**字段特性**节点不能有同一范围内的相同节点名称。</span><span class="sxs-lookup"><span data-stu-id="ee748-110">**Field Attribute** nodes cannot have the same node names while in the same scope.</span></span>  
  
 <span data-ttu-id="ee748-111">**记录**和**Field 元素**节点可以具有相同的节点名称与同一范围中，仅当满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="ee748-111">**Record** and **Field Element** nodes can have the same node names while in the same scope only if the following conditions are met:</span></span>  
  
-   <span data-ttu-id="ee748-112">它们具有相同的数据类型。</span><span class="sxs-lookup"><span data-stu-id="ee748-112">They have the same data type.</span></span>  
  
-   <span data-ttu-id="ee748-113">它们不在**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="ee748-113">They are not within an **All Group** node.</span></span>  
  
### <a name="to-insert-a-new-child-record-node-field-element-node-or-field-attribute-node-within-the-schema-node-or-an-existing-record-node"></a><span data-ttu-id="ee748-114">在 Schema 节点或现有“记录”节点中插入新的子“记录”节点、“字段元素”节点或“字段属性”节点</span><span class="sxs-lookup"><span data-stu-id="ee748-114">To insert a new child Record node, Field Element node, or Field Attribute node within the Schema node or an existing Record node</span></span>  
  
1.  <span data-ttu-id="ee748-115">选择**架构**节点或现有**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="ee748-115">Select the **Schema** node or an existing **Record** node.</span></span>  
  
2.  <span data-ttu-id="ee748-116">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**子记录**，**子字段元素**，或**子字段特性**适当。</span><span class="sxs-lookup"><span data-stu-id="ee748-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Child Record**, **Child Field Element**, or **Child Field Attribute**, as appropriate.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ee748-117">所选类型的子节点添加后的最后一个节点在架构树中 (在插入时**架构**节点) 或之后的所选现有的最后一个子节点**记录**节点 （当中的现有插入**记录**节点)。</span><span class="sxs-lookup"><span data-stu-id="ee748-117">A child node of the chosen type is added after either the last node in the schema tree (when inserting within the **Schema** node) or after the last existing child node of the selected **Record** node (when inserting within an existing **Record** node).</span></span>  
  
3.  <span data-ttu-id="ee748-118">键入新插入的名称**记录**， **Field 元素**，或**字段特性**节点，然后再按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ee748-118">Type a name for the newly inserted **Record**, **Field Element**, or **Field Attribute** node, and then press ENTER.</span></span>  
  
### <a name="to-insert-a-sibling-record-node-field-attribute-node-or-field-element-node-within-an-existing-record-node"></a><span data-ttu-id="ee748-119">在现有“记录”节点中插入同级“记录”节点、“字段属性”节点或“字段元素”节点</span><span class="sxs-lookup"><span data-stu-id="ee748-119">To insert a sibling Record node, Field Attribute node, or Field Element node within an existing Record node</span></span>  
  
1.  <span data-ttu-id="ee748-120">选择的任何子节点**记录**要向其中插入同级节点**记录**，**字段特性**，或**Field 元素**节点。</span><span class="sxs-lookup"><span data-stu-id="ee748-120">Select any child node of the **Record** node into which you want to insert the sibling **Record**, **Field Attribute**, or **Field Element** node.</span></span>  
  
2.  <span data-ttu-id="ee748-121">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**同级记录**，**同级字段特性**，或**同级 Field 元素**适当。</span><span class="sxs-lookup"><span data-stu-id="ee748-121">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sibling Record**, **Sibling Field Attribute**, or **Sibling Field Element**, as appropriate.</span></span>  
  
     <span data-ttu-id="ee748-122">所选类型的同级节点将插入到所选节点的同级节点的末尾。</span><span class="sxs-lookup"><span data-stu-id="ee748-122">A sibling node of the chosen type is inserted at the end of the siblings of the selected node.</span></span>  
  
3.  <span data-ttu-id="ee748-123">键入新插入的名称**记录**，**字段特性**，或**Field 元素**节点，然后再按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="ee748-123">Type a name for the newly inserted **Record**, **Field Attribute**, or **Field Element** node, and then press ENTER.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee748-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee748-124">See Also</span></span>  
 [<span data-ttu-id="ee748-125">将节点插入到架构</span><span class="sxs-lookup"><span data-stu-id="ee748-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)