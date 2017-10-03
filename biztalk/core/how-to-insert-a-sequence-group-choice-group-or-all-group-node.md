---
title: "如何插入序列组、 选择组或所有组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e498eb5ec8e7aa1398cfb58732f978faa9d0b415
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a><span data-ttu-id="a8ff1-102">如何插入序列组、 选择组或所有组节点</span><span class="sxs-lookup"><span data-stu-id="a8ff1-102">How to Insert a Sequence Group, Choice Group, or All Group Node</span></span>
<span data-ttu-id="a8ff1-103">BizTalk 编辑器支持三种类型的组节点的元素：**序列组**，**选项组**，和**所有组**。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-103">BizTalk Editor supports three types of group nodes for elements: **Sequence Group**, **Choice Group**, and **All Group**.</span></span> <span data-ttu-id="a8ff1-104">这些不同类型的组节点可以在相应的实例消息中建立对组的子节点的不同约束。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-104">These different types of group nodes establish different constraints on the child nodes of the group in corresponding instance messages.</span></span> <span data-ttu-id="a8ff1-105">有关这些不同类型的组所受约束的信息，请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-105">For information about the constraints of these different types of groups, you should refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="a8ff1-106">此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="a8ff1-107">BizTalk 编辑器还支持组节点的属性，**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-107">BizTalk Editor also supports a group node for attributes, the **Attribute Group** node.</span></span> <span data-ttu-id="a8ff1-108">此类节点允许一组要定义一次，，然后与多个关联的特性**记录**架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-108">This type of node allows a set of attributes to be defined once, and then be associated with more than one **Record** node within the schema.</span></span>  
  
 <span data-ttu-id="a8ff1-109">到您的架构生成结构时**记录**节点被假定为包含的子节点的有序的序列默认情况下，而通过使用表示**序列**的 XSD 表示形式中的元素架构。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-109">When you build structure into your schema, **Record** nodes are assumed to contain ordered sequences of child nodes by default, and are represented by using **sequence** elements in the XSD representation of the schema.</span></span> <span data-ttu-id="a8ff1-110">您可以通过更改更改组节点的类型及其**顺序类型**属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-110">You can change the type of a group node by changing its **Order Type** property.</span></span>  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a><span data-ttu-id="a8ff1-111">插入“顺序组”节点或“选择组”节点</span><span class="sxs-lookup"><span data-stu-id="a8ff1-111">To insert a Sequence Group node or a Choice Group node</span></span>  
  
1.  <span data-ttu-id="a8ff1-112">在架构树视图中，选择**记录**你想要插入的节点**序列组**节点或**选项组**节点。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-112">In the schema tree view, select the **Record** node in which you want to insert the **Sequence Group** node or the **Choice Group** node.</span></span>  
  
2.  <span data-ttu-id="a8ff1-113">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**序列组**或**选项组**适当。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-113">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group** or **Choice Group**, as appropriate.</span></span>  
  
### <a name="to-insert-an-all-group-node"></a><span data-ttu-id="a8ff1-114">插入“全部组”节点</span><span class="sxs-lookup"><span data-stu-id="a8ff1-114">To insert an All Group node</span></span>  
  
1.  <span data-ttu-id="a8ff1-115">在架构树视图中，选择新**记录**你想要插入的节点**所有组**节点。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-115">In the schema tree view, select the new **Record** node in which you want to insert the **All Group** node.</span></span>  
  
2.  <span data-ttu-id="a8ff1-116">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**所有组**。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **All Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8ff1-117">**所有组**选择是仅在 BizTalk （或快捷方式） 菜单上可用时相关的父**记录**节点满足 XSD 有一定的使用约束**所有**元素。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-117">The **All Group** choice is only available on the BizTalk (or shortcut) menu when the relevant parent **Record** node meets the constraints that XSD imposes on the use of the **all** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8ff1-118">**所有组**选择需要**记录**节点具有一个基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-118">The **All Group** choice requires that the **Record** node have a base data type.</span></span> <span data-ttu-id="a8ff1-119">快速的方法来为数据类型的节点是若要设置其**内容类型**到**复杂**。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-119">A quick way to give the node a data type is to set its **Content Type** to **Complex**.</span></span>  
  
### <a name="to-insert-an-attribute-group-node"></a><span data-ttu-id="a8ff1-120">插入“属性组”节点</span><span class="sxs-lookup"><span data-stu-id="a8ff1-120">To insert an Attribute Group node</span></span>  
  
1.  <span data-ttu-id="a8ff1-121">在架构树视图中，选择**记录**你想要插入的节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-121">In the schema tree view, select the **Record** node in which you want to insert the **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="a8ff1-122">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**属性组**。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-122">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8ff1-123">如果你想要更改新插入的名称**属性组**节点，键入新名称出现在其**组引用**属性。</span><span class="sxs-lookup"><span data-stu-id="a8ff1-123">If you want to change the name of the newly inserted **Attribute Group** node, type the new name in its **Group Reference** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8ff1-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8ff1-124">See Also</span></span>  
 [<span data-ttu-id="a8ff1-125">将节点插入到架构</span><span class="sxs-lookup"><span data-stu-id="a8ff1-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)