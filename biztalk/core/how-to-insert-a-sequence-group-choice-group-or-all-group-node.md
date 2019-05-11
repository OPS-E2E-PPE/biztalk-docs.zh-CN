---
title: 如何插入序列组、 选择组或全部组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19aee400-1369-4310-b1b4-1bfeb2643236
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfc4b4f244c0a265a0b65efaf2f8f7bbd25e9ebd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384955"
---
# <a name="how-to-insert-a-sequence-group-choice-group-or-all-group-node"></a><span data-ttu-id="f738b-102">如何插入序列组、 选择组或全部组节点</span><span class="sxs-lookup"><span data-stu-id="f738b-102">How to Insert a Sequence Group, Choice Group, or All Group Node</span></span>
<span data-ttu-id="f738b-103">BizTalk 编辑器支持三种类型的组节点的元素：**序列组**，**选择组**，和**全部组**。</span><span class="sxs-lookup"><span data-stu-id="f738b-103">BizTalk Editor supports three types of group nodes for elements: **Sequence Group**, **Choice Group**, and **All Group**.</span></span> <span data-ttu-id="f738b-104">这些不同类型的组节点在相应实例消息中建立组的子节点上的各种约束。</span><span class="sxs-lookup"><span data-stu-id="f738b-104">These different types of group nodes establish different constraints on the child nodes of the group in corresponding instance messages.</span></span> <span data-ttu-id="f738b-105">有关这些不同类型的组的约束，您应请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。</span><span class="sxs-lookup"><span data-stu-id="f738b-105">For information about the constraints of these different types of groups, you should refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="f738b-106">此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。</span><span class="sxs-lookup"><span data-stu-id="f738b-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  
  
 <span data-ttu-id="f738b-107">BizTalk 编辑器还支持组节点对于属性，**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="f738b-107">BizTalk Editor also supports a group node for attributes, the **Attribute Group** node.</span></span> <span data-ttu-id="f738b-108">此类节点允许一组要定义一次，并会与多个相关联的特性**记录**架构中的节点。</span><span class="sxs-lookup"><span data-stu-id="f738b-108">This type of node allows a set of attributes to be defined once, and then be associated with more than one **Record** node within the schema.</span></span>  
  
 <span data-ttu-id="f738b-109">到您的架构中生成结构时**记录**节点假定为包含子节点的有序的序列默认情况下，并使用来表示**序列**的 XSD 表示形式中的元素架构。</span><span class="sxs-lookup"><span data-stu-id="f738b-109">When you build structure into your schema, **Record** nodes are assumed to contain ordered sequences of child nodes by default, and are represented by using **sequence** elements in the XSD representation of the schema.</span></span> <span data-ttu-id="f738b-110">可以通过更改更改组节点的类型及其**Order Type**属性。</span><span class="sxs-lookup"><span data-stu-id="f738b-110">You can change the type of a group node by changing its **Order Type** property.</span></span>  
  
### <a name="to-insert-a-sequence-group-node-or-a-choice-group-node"></a><span data-ttu-id="f738b-111">若要插入顺序组节点或选择组节点</span><span class="sxs-lookup"><span data-stu-id="f738b-111">To insert a Sequence Group node or a Choice Group node</span></span>  
  
1.  <span data-ttu-id="f738b-112">在架构树视图中，选择**记录**你想要插入的节点**序列组**节点或**选择组**节点。</span><span class="sxs-lookup"><span data-stu-id="f738b-112">In the schema tree view, select the **Record** node in which you want to insert the **Sequence Group** node or the **Choice Group** node.</span></span>  
  
2.  <span data-ttu-id="f738b-113">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**序列组**或**选择组**根据。</span><span class="sxs-lookup"><span data-stu-id="f738b-113">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group** or **Choice Group**, as appropriate.</span></span>  
  
### <a name="to-insert-an-all-group-node"></a><span data-ttu-id="f738b-114">若要插入全部组节点</span><span class="sxs-lookup"><span data-stu-id="f738b-114">To insert an All Group node</span></span>  
  
1.  <span data-ttu-id="f738b-115">在架构树视图中，选择新**记录**你想要插入的节点**全部组**节点。</span><span class="sxs-lookup"><span data-stu-id="f738b-115">In the schema tree view, select the new **Record** node in which you want to insert the **All Group** node.</span></span>  
  
2.  <span data-ttu-id="f738b-116">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**全部组**。</span><span class="sxs-lookup"><span data-stu-id="f738b-116">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **All Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f738b-117">**全部组**选项才可用的 BizTalk （或快捷） 菜单上时相关的父**记录**节点符合 XSD 的使用施加的约束**所有**元素。</span><span class="sxs-lookup"><span data-stu-id="f738b-117">The **All Group** choice is only available on the BizTalk (or shortcut) menu when the relevant parent **Record** node meets the constraints that XSD imposes on the use of the **all** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f738b-118">**全部组**选择需要**记录**节点具有基本数据类型。</span><span class="sxs-lookup"><span data-stu-id="f738b-118">The **All Group** choice requires that the **Record** node have a base data type.</span></span> <span data-ttu-id="f738b-119">为节点指定数据类型的快速方法是设置其**内容类型**到**复杂**。</span><span class="sxs-lookup"><span data-stu-id="f738b-119">A quick way to give the node a data type is to set its **Content Type** to **Complex**.</span></span>  
  
### <a name="to-insert-an-attribute-group-node"></a><span data-ttu-id="f738b-120">若要插入属性组节点</span><span class="sxs-lookup"><span data-stu-id="f738b-120">To insert an Attribute Group node</span></span>  
  
1.  <span data-ttu-id="f738b-121">在架构树视图中，选择**记录**你想要插入的节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="f738b-121">In the schema tree view, select the **Record** node in which you want to insert the **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="f738b-122">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**属性组**。</span><span class="sxs-lookup"><span data-stu-id="f738b-122">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f738b-123">如果你想要更改新插入的名称**属性组**节点中，键入新名称在其**组参考**属性。</span><span class="sxs-lookup"><span data-stu-id="f738b-123">If you want to change the name of the newly inserted **Attribute Group** node, type the new name in its **Group Reference** property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f738b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="f738b-124">See Also</span></span>  
 [<span data-ttu-id="f738b-125">向架构插入节点</span><span class="sxs-lookup"><span data-stu-id="f738b-125">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)