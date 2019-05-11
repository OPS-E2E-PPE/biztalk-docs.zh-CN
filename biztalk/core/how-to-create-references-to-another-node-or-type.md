---
title: 如何创建对其他节点或类型的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c60be9ad-01a9-40e7-b43b-8c3d09bbb32f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a1c8f2d988068f5a49a5d2f69064c4d9a46a207
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338993"
---
# <a name="create-references-to-another-node-or-type"></a><span data-ttu-id="83ab2-102">创建对其他节点或类型的引用</span><span class="sxs-lookup"><span data-stu-id="83ab2-102">Create References to Another Node or Type</span></span>
<span data-ttu-id="83ab2-103">可以使用全局节点来创建可重用的数据类型-结构片段 —，您可以使用整个架构任何该结构是适当位置。</span><span class="sxs-lookup"><span data-stu-id="83ab2-103">You can use global nodes to create reusable data types—fragments of structure—that you can use throughout the schema wherever that structure is appropriate.</span></span> <span data-ttu-id="83ab2-104">只能使用节点的直接子级**架构**节点来创建全局类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-104">You can only use nodes that are direct children of the **Schema** node to create global types.</span></span>  
  
 <span data-ttu-id="83ab2-105">您还可以创建使用不是直接子代的节点的数据类型的循环引用**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-105">You can also create cyclical references using the data types of nodes that are not direct descendants of the **Schema** node.</span></span> <span data-ttu-id="83ab2-106">这可用于表示架构中的递归结构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-106">This is useful for representing recursive structures in schemas.</span></span>  
  
 <span data-ttu-id="83ab2-107">本主题提供有关各种类型的全局节点的分步说明和如何引用才能使用它们。</span><span class="sxs-lookup"><span data-stu-id="83ab2-107">This topic provides step-by-step instructions for various types of global nodes and how to refer to them to use them.</span></span>  
  
 <span data-ttu-id="83ab2-108">**创建全局声明**</span><span class="sxs-lookup"><span data-stu-id="83ab2-108">**Creating Global Declarations**</span></span>  
  
 <span data-ttu-id="83ab2-109">您可以创建全局使用的记录、 字段或属性的类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-109">You can create global types using records, fields or attributes.</span></span> <span data-ttu-id="83ab2-110">从记录创建的全局类型只能用于在记录中，创建从仅在字段中，仅在属性的属性类型的字段的类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-110">Global types created from records may only be used in records, types created from fields only in fields, attribute types only in attributes.</span></span> <span data-ttu-id="83ab2-111">以下过程介绍如何定义和使用全局声明。</span><span class="sxs-lookup"><span data-stu-id="83ab2-111">The following procedures describe how to define and use global declarations.</span></span>  
  
## <a name="create-a-global-declaration-from-a-node"></a><span data-ttu-id="83ab2-112">从节点创建一个全局声明</span><span class="sxs-lookup"><span data-stu-id="83ab2-112">Create a global declaration from a node</span></span>  
  
1.  <span data-ttu-id="83ab2-113">选择**记录**， **Field 特性**，或**字段元素**节点你想要设为全局可用的类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-113">Select the **Record** , **Field Attribute**,or **Field Element** node whose type you want to make globally available.</span></span>  
  
2.  <span data-ttu-id="83ab2-114">在中**属性**窗口中，键入一个名称中**Data Structure Type**列表将用作复杂类型的全局名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="83ab2-114">In the **Properties** window, type a name in the **Data Structure Type** list that will be used as the global name for the complex type, and then press ENTER.</span></span>  
  
## <a name="create-a-globally-defined-sequence-group-node-choice-group-node-or-all-group-node"></a><span data-ttu-id="83ab2-115">创建全局定义的顺序组节点、 选择组节点或全部组节点</span><span class="sxs-lookup"><span data-stu-id="83ab2-115">Create a globally defined Sequence Group node, Choice Group node, or All Group node</span></span>  
  
1.  <span data-ttu-id="83ab2-116">选择**记录**要在其中插入全局定义的组节点的节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-116">Select the **Record** node into which you want to insert the globally defined group node.</span></span>  
  
2.  <span data-ttu-id="83ab2-117">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**序列组**，**选择组**，或**所有组**根据。</span><span class="sxs-lookup"><span data-stu-id="83ab2-117">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group**, **Choice Group**, or **All Group**, as appropriate.</span></span>  
  
3.  <span data-ttu-id="83ab2-118">新插入的组中创建的结构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-118">Create a structure in the newly inserted group.</span></span> <span data-ttu-id="83ab2-119">例如，插入**记录**或**Field 元素**节点，以表示组节点内数据的结构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-119">For example, insert **Record** or **Field Element** nodes to express the structure of the data within the group node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83ab2-120">序列组**选择组**，并**全部组**节点只能包含节点的 XML 元素相对应的因此不能包含**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-120">Sequence Group, **Choice Group**, and **All Group** nodes can only contain nodes that correspond to XML elements and therefore cannot contain **Field Attribute** nodes.</span></span>  
  
4.  <span data-ttu-id="83ab2-121">选择插入在步骤 2 中的组节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-121">Select the group node inserted in step 2.</span></span>  
  
5.  <span data-ttu-id="83ab2-122">在属性窗口中，单击**组参考**，到值字段中，键入一个名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="83ab2-122">In the Properties window, click **Group Reference**, type a name into the value field, and then press ENTER.</span></span>  
  
     <span data-ttu-id="83ab2-123">中的名称，从而**组参考**属性，拥有全局定义组节点之后, 你可以使用此全局定义的类型 （结构） 关联的其他组节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-123">By providing a name in the **Group Reference** property, you have globally defined group node, after which you can associate other group nodes with this globally defined type (structure).</span></span>  
  
## <a name="create-a-globally-defined-attribute-group-node"></a><span data-ttu-id="83ab2-124">创建一个全局定义的属性组节点</span><span class="sxs-lookup"><span data-stu-id="83ab2-124">Create a globally defined Attribute Group node</span></span>  
  
1.  <span data-ttu-id="83ab2-125">选择**记录**要在其中插入全局定义的节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-125">Select the **Record** node into which you want to insert the globally defined **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="83ab2-126">上**BizTalk**菜单，依次指向**插入 Schema 节点**，然后单击**属性组**。</span><span class="sxs-lookup"><span data-stu-id="83ab2-126">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
     <span data-ttu-id="83ab2-127">这将添加**属性组**节点中所选的子节点末尾**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-127">This adds an **Attribute Group** node to the end of the child nodes in the selected **Record** node.</span></span>  
  
3.  <span data-ttu-id="83ab2-128">添加适当**字段属性**或**属性组**节点到你**属性组**。</span><span class="sxs-lookup"><span data-stu-id="83ab2-128">Add the appropriate **Field Attribute** or **Attribute Group** nodes to your **Attribute Group**.</span></span>  
  
4.  <span data-ttu-id="83ab2-129">（可选） 如果你想要重命名**属性组**节点中，选择**属性组**节点，然后更改其**组参考**属性设置为所选的新名称。</span><span class="sxs-lookup"><span data-stu-id="83ab2-129">Optionally, if you want to rename the **Attribute Group** node, select the **Attribute Group** node and change its **Group Reference** property to a new name of your choosing.</span></span>  
  
     <span data-ttu-id="83ab2-130">属性组始终是全局性的从使用其点引用。</span><span class="sxs-lookup"><span data-stu-id="83ab2-130">Attribute groups are always global and referenced from their point of use.</span></span>  
  
## <a name="use-a-type-or-group-that-has-been-globally-defined"></a><span data-ttu-id="83ab2-131">使用的类型或全局范围内定义的组</span><span class="sxs-lookup"><span data-stu-id="83ab2-131">Use a type or group that has been globally defined</span></span>  
  
1. <span data-ttu-id="83ab2-132">选择你想要使用的全局定义的类型的节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-132">Select the node for which you want to use a globally defined type.</span></span>  
  
2. <span data-ttu-id="83ab2-133">在属性窗口中，选择全局定义的类型从下拉列表中为**Data Structure Type**属性 (**记录**节点)，**数据类型**属性 (**字段元素**并**Field 特性**节点)，或**组参考**(**序列组**，**选择组**，**全部组**，并**属性组**节点)。</span><span class="sxs-lookup"><span data-stu-id="83ab2-133">In the Properties window, select the globally defined type from the drop-down list for the **Data Structure Type** property (**Record** nodes), **Data Type** property (**Field Element** and **Field Attribute** nodes), or **Group Reference** (**Sequence Group**, **Choice Group**, **All Group**, and **Attribute Group** nodes).</span></span> <span data-ttu-id="83ab2-134">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="83ab2-134">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
   > [!NOTE]
   >  <span data-ttu-id="83ab2-135">可采用它所在的架构位置的任何后续更改的全局定义的类型或组。</span><span class="sxs-lookup"><span data-stu-id="83ab2-135">Subsequent changes to the globally defined type or group can be made in any of the schema locations in which it appears.</span></span> <span data-ttu-id="83ab2-136">在单一的任意位置进行，将在所有此类位置应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="83ab2-136">These changes will be applied in all such locations as you make them in the single, arbitrary location.</span></span>  
  
   <span data-ttu-id="83ab2-137">创建全局声明后，不能在单个步骤中将其删除。</span><span class="sxs-lookup"><span data-stu-id="83ab2-137">After you have created a global declaration, you cannot delete it in a single step.</span></span> <span data-ttu-id="83ab2-138">但是，可以通过删除它**清除全局数据类型**对话框保存架构时，使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="83ab2-138">However, you can delete it by using the **Cleanup Global DataTypes** dialog box when the schema is saved, using the following procedure.</span></span>  
  
## <a name="delete-a-global-declaration"></a><span data-ttu-id="83ab2-139">删除全局声明</span><span class="sxs-lookup"><span data-stu-id="83ab2-139">Delete a global declaration</span></span>  
  
1.  <span data-ttu-id="83ab2-140">删除所有使用此全局类型或组，其中的节点或指定要在所有这些节点，或它们的某种组合中使用的不同类型或组。</span><span class="sxs-lookup"><span data-stu-id="83ab2-140">Delete all of the nodes where this global type or group is used, or specify a different type or group to be used in all of those nodes, or some combination thereof.</span></span> <span data-ttu-id="83ab2-141">有关删除节点的分步说明，请参阅[删除节点](../core/how-to-delete-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="83ab2-141">For step-by-step instructions for deleting a node, see [Deleting Nodes](../core/how-to-delete-nodes.md).</span></span>  
  
2.  <span data-ttu-id="83ab2-142">在保存规范时，**清除全局数据类型**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="83ab2-142">Upon saving your specification, the **Cleanup Global DataTypes** dialog box appears.</span></span> <span data-ttu-id="83ab2-143">选择你想要完全删除从规范，然后依次是全局声明**确定**。</span><span class="sxs-lookup"><span data-stu-id="83ab2-143">Select the global declaration you want to completely delete from your specification, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83ab2-144">**清除全局数据类型**对话框将显示每次使用未使用的数据类型保存架构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-144">The **Cleanup Global DataTypes** dialog box appears every time you save a schema with unused data types.</span></span> <span data-ttu-id="83ab2-145">如果未显示此对话框中，在架构中某处使用的所有数据类型或因为它已打开尚未修改架构 （在后一种情况下，它可能仍然包含以前保留的未使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-145">If this dialog box does not appear, either all data types are used somewhere in the schema or the schema has not been modified since it was opened (in the latter case, it might still contain unused data types that were previously retained.</span></span>  
  
## <a name="create-cyclical-references-to-another-node"></a><span data-ttu-id="83ab2-146">创建到另一个节点的循环引用</span><span class="sxs-lookup"><span data-stu-id="83ab2-146">Create Cyclical References to Another Node</span></span>  
 <span data-ttu-id="83ab2-147">您可以创建对节点来表示递归架构元素的循环引用。</span><span class="sxs-lookup"><span data-stu-id="83ab2-147">You can create cyclical references to a node to represent recursive schema elements.</span></span> <span data-ttu-id="83ab2-148">通过创建其类型定义的封闭的记录节点执行此操作。</span><span class="sxs-lookup"><span data-stu-id="83ab2-148">You do this by creating a node whose type is defined by an enclosing record.</span></span> <span data-ttu-id="83ab2-149">例如，请考虑在任意数量的具有相同结构的信封中包装的实例消息。</span><span class="sxs-lookup"><span data-stu-id="83ab2-149">For example, consider an instance message that is wrapped in an arbitrary number of envelopes having the same structure.</span></span> <span data-ttu-id="83ab2-150">使用循环引用，可以创建定义此类的实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-150">Using cyclical references, you can create a schema that defines such instance messages.</span></span>  
  
### <a name="create-a-cyclical-reference"></a><span data-ttu-id="83ab2-151">创建循环引用</span><span class="sxs-lookup"><span data-stu-id="83ab2-151">Create a cyclical reference</span></span>  
  
1.  <span data-ttu-id="83ab2-152">选择**记录**你想要创建的递归引用节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-152">Select a **Record** node for which you want to create a recursive reference.</span></span> <span data-ttu-id="83ab2-153">这是表示递归结构的顶层节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-153">This is the node representing the top of the recursive structure.</span></span>  
  
2.  <span data-ttu-id="83ab2-154">在属性窗口中，验证是否**Data Structure Type**具有值。</span><span class="sxs-lookup"><span data-stu-id="83ab2-154">In the Properties window, verify that the **Data Structure Type** has a value.</span></span>  
  
     <span data-ttu-id="83ab2-155">验证是否**记录**命名节点都有与之关联的类型是有必要，因为如果一个类型包含本身定义递归结构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-155">Verifying that the **Record** node has a named type associated with it is necessary because recursive structures are defined when a type contains itself.</span></span> <span data-ttu-id="83ab2-156">类型仅可以包含本身嵌套使用名为全局类型。</span><span class="sxs-lookup"><span data-stu-id="83ab2-156">Types can only contain themselves through nested use of named global types.</span></span>  
  
3.  <span data-ttu-id="83ab2-157">选择子**记录**节点或插入子**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="83ab2-157">Select a child **Record** node or insert a child **Record** node.</span></span>  
  
4.  <span data-ttu-id="83ab2-158">子**记录**节点中的属性窗口中在**Data Structure Type**列表中，选择在步骤 2 中标识的数据结构。</span><span class="sxs-lookup"><span data-stu-id="83ab2-158">For the child **Record** node, in the Properties window, in the **Data Structure Type** list, select the data structure identified in step 2.</span></span>  
  
> [!IMPORTANT]
>  - <span data-ttu-id="83ab2-159">**最小出现次数**重复节点的属性必须设置为零 (**0**)。</span><span class="sxs-lookup"><span data-stu-id="83ab2-159">The **Min Occurs** property for the repeating node must be set to zero (**0**).</span></span> <span data-ttu-id="83ab2-160">将其设置为一个 (**1**) 将导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="83ab2-160">Setting it to one (**1**) causes an infinite loop.</span></span>  
>
>  - <span data-ttu-id="83ab2-161">如果您导入包含一个递归元素的架构，BizTalk 编辑器中不会自动检查以确保递归元素有效。</span><span class="sxs-lookup"><span data-stu-id="83ab2-161">If you import a schema that contains a recursive element, BizTalk Editor does not automatically check to ensure that the recursive element is valid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ab2-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="83ab2-162">See Also</span></span>  
 [<span data-ttu-id="83ab2-163">管理架构中的节点</span><span class="sxs-lookup"><span data-stu-id="83ab2-163">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)