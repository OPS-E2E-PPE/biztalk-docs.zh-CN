---
title: "如何创建对另一个节点或类型的引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c60be9ad-01a9-40e7-b43b-8c3d09bbb32f
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 643f39b9a42e2566f77371096d7305f56e11a328
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-references-to-another-node-or-type"></a><span data-ttu-id="53c77-102">创建到另一个节点或类型的引用</span><span class="sxs-lookup"><span data-stu-id="53c77-102">Create References to Another Node or Type</span></span>
<span data-ttu-id="53c77-103">你可以使用全局节点来创建可重用的数据类型-片段的结构-，你可以在整个使用架构只要该结构适合。</span><span class="sxs-lookup"><span data-stu-id="53c77-103">You can use global nodes to create reusable data types—fragments of structure—that you can use throughout the schema wherever that structure is appropriate.</span></span> <span data-ttu-id="53c77-104">你只能使用节点的直接子级的**架构**节点来创建全局类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-104">You can only use nodes that are direct children of the **Schema** node to create global types.</span></span>  
  
 <span data-ttu-id="53c77-105">你还可以创建使用的节点不是直接后代中的数据类型的循环引用**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-105">You can also create cyclical references using the data types of nodes that are not direct descendants of the **Schema** node.</span></span> <span data-ttu-id="53c77-106">这可用于表示架构中的递归结构。</span><span class="sxs-lookup"><span data-stu-id="53c77-106">This is useful for representing recursive structures in schemas.</span></span>  
  
 <span data-ttu-id="53c77-107">本主题提供为各种类型的全局节点的分步说明和如何引用它们以使用它们。</span><span class="sxs-lookup"><span data-stu-id="53c77-107">This topic provides step-by-step instructions for various types of global nodes and how to refer to them to use them.</span></span>  
  
 <span data-ttu-id="53c77-108">**创建全局声明**</span><span class="sxs-lookup"><span data-stu-id="53c77-108">**Creating Global Declarations**</span></span>  
  
 <span data-ttu-id="53c77-109">你可以创建全局使用记录、 字段或属性的类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-109">You can create global types using records, fields or attributes.</span></span> <span data-ttu-id="53c77-110">从记录创建的全局类型可能只用于在记录中，创建从仅在字段中，仅在属性中的属性类型的字段的类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-110">Global types created from records may only be used in records, types created from fields only in fields, attribute types only in attributes.</span></span> <span data-ttu-id="53c77-111">下面的过程介绍如何定义和使用全局声明。</span><span class="sxs-lookup"><span data-stu-id="53c77-111">The following procedures describe how to define and use global declarations.</span></span>  
  
## <a name="create-a-global-declaration-from-a-node"></a><span data-ttu-id="53c77-112">从的节点创建全局声明</span><span class="sxs-lookup"><span data-stu-id="53c77-112">Create a global declaration from a node</span></span>  
  
1.  <span data-ttu-id="53c77-113">选择**记录**，**字段特性**，或**Field 元素**节点你想要使全局可用其类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-113">Select the **Record** , **Field Attribute**,or **Field Element** node whose type you want to make globally available.</span></span>  
  
2.  <span data-ttu-id="53c77-114">在**属性**窗口中，键入一个名称中**数据结构类型**列表将用作的复杂类型的全局名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="53c77-114">In the **Properties** window, type a name in the **Data Structure Type** list that will be used as the global name for the complex type, and then press ENTER.</span></span>  
  
## <a name="create-a-globally-defined-sequence-group-node-choice-group-node-or-all-group-node"></a><span data-ttu-id="53c77-115">创建全局定义的序列组节点、 选择组节点或所有组节点</span><span class="sxs-lookup"><span data-stu-id="53c77-115">Create a globally defined Sequence Group node, Choice Group node, or All Group node</span></span>  
  
1.  <span data-ttu-id="53c77-116">选择**记录**要向其中插入全局定义的组节点的节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-116">Select the **Record** node into which you want to insert the globally defined group node.</span></span>  
  
2.  <span data-ttu-id="53c77-117">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**序列组**，**选项组**，或**所有组**适当。</span><span class="sxs-lookup"><span data-stu-id="53c77-117">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Sequence Group**, **Choice Group**, or **All Group**, as appropriate.</span></span>  
  
3.  <span data-ttu-id="53c77-118">创建新插入的组中的结构。</span><span class="sxs-lookup"><span data-stu-id="53c77-118">Create a structure in the newly inserted group.</span></span> <span data-ttu-id="53c77-119">例如，插入**记录**或**Field 元素**节点 express 组节点中的数据结构。</span><span class="sxs-lookup"><span data-stu-id="53c77-119">For example, insert **Record** or **Field Element** nodes to express the structure of the data within the group node.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53c77-120">序列组**选项组**，和**所有组**节点只能包含节点对应于 XML 元素，因此不能包含**字段特性**节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-120">Sequence Group, **Choice Group**, and **All Group** nodes can only contain nodes that correspond to XML elements and therefore cannot contain **Field Attribute** nodes.</span></span>  
  
4.  <span data-ttu-id="53c77-121">选择在步骤 2 中插入的组节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-121">Select the group node inserted in step 2.</span></span>  
  
5.  <span data-ttu-id="53c77-122">在属性窗口中，单击**组引用**，向值字段中，键入一个名称，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="53c77-122">In the Properties window, click **Group Reference**, type a name into the value field, and then press ENTER.</span></span>  
  
     <span data-ttu-id="53c77-123">通过提供在名称**组引用**属性，具有全局定义组节点，此后可以将其他组节点关联与此全局定义的类型 （结构）。</span><span class="sxs-lookup"><span data-stu-id="53c77-123">By providing a name in the **Group Reference** property, you have globally defined group node, after which you can associate other group nodes with this globally defined type (structure).</span></span>  
  
## <a name="create-a-globally-defined-attribute-group-node"></a><span data-ttu-id="53c77-124">创建一个全局定义的属性组节点</span><span class="sxs-lookup"><span data-stu-id="53c77-124">Create a globally defined Attribute Group node</span></span>  
  
1.  <span data-ttu-id="53c77-125">选择**记录**要向其中插入全局定义节点**属性组**节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-125">Select the **Record** node into which you want to insert the globally defined **Attribute Group** node.</span></span>  
  
2.  <span data-ttu-id="53c77-126">上**BizTalk**菜单上，指向**插入架构节点**，然后单击**属性组**。</span><span class="sxs-lookup"><span data-stu-id="53c77-126">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Attribute Group**.</span></span>  
  
     <span data-ttu-id="53c77-127">这将添加**属性组**到末尾的所选的子节点的节点**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-127">This adds an **Attribute Group** node to the end of the child nodes in the selected **Record** node.</span></span>  
  
3.  <span data-ttu-id="53c77-128">添加相应**字段特性**或**属性组**节点你**属性组**。</span><span class="sxs-lookup"><span data-stu-id="53c77-128">Add the appropriate **Field Attribute** or **Attribute Group** nodes to your **Attribute Group**.</span></span>  
  
4.  <span data-ttu-id="53c77-129">（可选） 如果你想要重命名**属性组**节点中，选择**属性组**节点，然后更改其**组引用**属性设置为你选择的新名称。</span><span class="sxs-lookup"><span data-stu-id="53c77-129">Optionally, if you want to rename the **Attribute Group** node, select the **Attribute Group** node and change its **Group Reference** property to a new name of your choosing.</span></span>  
  
     <span data-ttu-id="53c77-130">属性组始终是全局性的从使用其点引用。</span><span class="sxs-lookup"><span data-stu-id="53c77-130">Attribute groups are always global and referenced from their point of use.</span></span>  
  
## <a name="use-a-type-or-group-that-has-been-globally-defined"></a><span data-ttu-id="53c77-131">使用的类型或全局范围内定义的组</span><span class="sxs-lookup"><span data-stu-id="53c77-131">Use a type or group that has been globally defined</span></span>  
  
1.  <span data-ttu-id="53c77-132">选择你想要使用全局定义的类型的节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-132">Select the node for which you want to use a globally defined type.</span></span>  
  
2.  <span data-ttu-id="53c77-133">在属性窗口中，选择全局定义的类型从下拉列表中为**数据结构类型**属性 (**记录**节点)，**数据类型**属性 (**字段元素**和**字段特性**节点)，或**组引用**(**序列组**，**选项组**，**所有组**，和**属性组**节点)。</span><span class="sxs-lookup"><span data-stu-id="53c77-133">In the Properties window, select the globally defined type from the drop-down list for the **Data Structure Type** property (**Record** nodes), **Data Type** property (**Field Element** and **Field Attribute** nodes), or **Group Reference** (**Sequence Group**, **Choice Group**, **All Group**, and **Attribute Group** nodes).</span></span> <span data-ttu-id="53c77-134">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="53c77-134">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
    > [!NOTE]
    >  <span data-ttu-id="53c77-135">对全局定义的类型或组的后续更改可采用任何它在其中出现的架构位置。</span><span class="sxs-lookup"><span data-stu-id="53c77-135">Subsequent changes to the globally defined type or group can be made in any of the schema locations in which it appears.</span></span> <span data-ttu-id="53c77-136">在单个的任意位置进行，将在所有此类位置中应用这些更改。</span><span class="sxs-lookup"><span data-stu-id="53c77-136">These changes will be applied in all such locations as you make them in the single, arbitrary location.</span></span>  
  
 <span data-ttu-id="53c77-137">创建全局声明后，你不能在单个步骤中将其删除。</span><span class="sxs-lookup"><span data-stu-id="53c77-137">After you have created a global declaration, you cannot delete it in a single step.</span></span> <span data-ttu-id="53c77-138">但是，可以通过使用删除它**清理全局数据类型**对话框中保存架构后，使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="53c77-138">However, you can delete it by using the **Cleanup Global DataTypes** dialog box when the schema is saved, using the following procedure.</span></span>  
  
## <a name="delete-a-global-declaration"></a><span data-ttu-id="53c77-139">删除全局声明</span><span class="sxs-lookup"><span data-stu-id="53c77-139">Delete a global declaration</span></span>  
  
1.  <span data-ttu-id="53c77-140">删除所有使用该全局类型或组，其中的节点，或指定要在所有这些节点，或它们的某些组合中使用的不同类型或组。</span><span class="sxs-lookup"><span data-stu-id="53c77-140">Delete all of the nodes where this global type or group is used, or specify a different type or group to be used in all of those nodes, or some combination thereof.</span></span> <span data-ttu-id="53c77-141">删除节点的分步说明，请参阅[删除节点](../core/how-to-delete-nodes.md)。</span><span class="sxs-lookup"><span data-stu-id="53c77-141">For step-by-step instructions for deleting a node, see [Deleting Nodes](../core/how-to-delete-nodes.md).</span></span>  
  
2.  <span data-ttu-id="53c77-142">在保存您的规范，**清理全局数据类型**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="53c77-142">Upon saving your specification, the **Cleanup Global DataTypes** dialog box appears.</span></span> <span data-ttu-id="53c77-143">选择你想要从您的规范，完全删除，然后单击是全局声明**确定**。</span><span class="sxs-lookup"><span data-stu-id="53c77-143">Select the global declaration you want to completely delete from your specification, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="53c77-144">**清理全局数据类型**对话框中将显示每次将架构保存与未使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-144">The **Cleanup Global DataTypes** dialog box appears every time you save a schema with unused data types.</span></span> <span data-ttu-id="53c77-145">如果未显示此对话框中，在架构中某个位置使用的所有数据类型或因为它已打开尚未修改架构 （在后一种情况下，它可能仍然包含以前保留的未使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-145">If this dialog box does not appear, either all data types are used somewhere in the schema or the schema has not been modified since it was opened (in the latter case, it might still contain unused data types that were previously retained.</span></span>  
  
## <a name="create-cyclical-references-to-another-node"></a><span data-ttu-id="53c77-146">创建到另一个节点的循环引用</span><span class="sxs-lookup"><span data-stu-id="53c77-146">Create Cyclical References to Another Node</span></span>  
 <span data-ttu-id="53c77-147">你可以创建到节点来表示递归架构元素的循环引用。</span><span class="sxs-lookup"><span data-stu-id="53c77-147">You can create cyclical references to a node to represent recursive schema elements.</span></span> <span data-ttu-id="53c77-148">通过创建其类型由一个封闭的记录节点执行此操作。</span><span class="sxs-lookup"><span data-stu-id="53c77-148">You do this by creating a node whose type is defined by an enclosing record.</span></span> <span data-ttu-id="53c77-149">例如，考虑实例消息包装在任意数目的具有相同结构的信封中。</span><span class="sxs-lookup"><span data-stu-id="53c77-149">For example, consider an instance message that is wrapped in an arbitrary number of envelopes having the same structure.</span></span> <span data-ttu-id="53c77-150">使用循环引用，可以创建定义此类实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="53c77-150">Using cyclical references, you can create a schema that defines such instance messages.</span></span>  
  
### <a name="create-a-cyclical-reference"></a><span data-ttu-id="53c77-151">创建循环引用</span><span class="sxs-lookup"><span data-stu-id="53c77-151">Create a cyclical reference</span></span>  
  
1.  <span data-ttu-id="53c77-152">选择**记录**想要创建的递归引用节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-152">Select a **Record** node for which you want to create a recursive reference.</span></span> <span data-ttu-id="53c77-153">这是表示递归结构的顶部的节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-153">This is the node representing the top of the recursive structure.</span></span>  
  
2.  <span data-ttu-id="53c77-154">在属性窗口中，确保**数据结构类型**具有值。</span><span class="sxs-lookup"><span data-stu-id="53c77-154">In the Properties window, verify that the **Data Structure Type** has a value.</span></span>  
  
     <span data-ttu-id="53c77-155">验证**记录**命名节点都有与之关联的类型是必需的因为递归结构定义时包含本身的类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-155">Verifying that the **Record** node has a named type associated with it is necessary because recursive structures are defined when a type contains itself.</span></span> <span data-ttu-id="53c77-156">类型仅可包含本身通过嵌套使用命名的全局类型。</span><span class="sxs-lookup"><span data-stu-id="53c77-156">Types can only contain themselves through nested use of named global types.</span></span>  
  
3.  <span data-ttu-id="53c77-157">选择子**记录**节点或插入子**记录**节点。</span><span class="sxs-lookup"><span data-stu-id="53c77-157">Select a child **Record** node or insert a child **Record** node.</span></span>  
  
4.  <span data-ttu-id="53c77-158">为子**记录**节点中的属性窗口中，在**数据结构类型**列表中，选择在步骤 2 中标识的数据结构。</span><span class="sxs-lookup"><span data-stu-id="53c77-158">For the child **Record** node, in the Properties window, in the **Data Structure Type** list, select the data structure identified in step 2.</span></span>  
  
> [!IMPORTANT]
>  - <span data-ttu-id="53c77-159">**最小出现次数**重复节点的属性必须设置为零 (**0**)。</span><span class="sxs-lookup"><span data-stu-id="53c77-159">The **Min Occurs** property for the repeating node must be set to zero (**0**).</span></span> <span data-ttu-id="53c77-160">将其设置为一个 (**1**) 将导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="53c77-160">Setting it to one (**1**) causes an infinite loop.</span></span>  
>
>  - <span data-ttu-id="53c77-161">如果你导入包含递归元素的架构，BizTalk 编辑器不会自动检查以确保递归元素有效。</span><span class="sxs-lookup"><span data-stu-id="53c77-161">If you import a schema that contains a recursive element, BizTalk Editor does not automatically check to ensure that the recursive element is valid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c77-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53c77-162">See Also</span></span>  
 [<span data-ttu-id="53c77-163">管理在架构中的节点</span><span class="sxs-lookup"><span data-stu-id="53c77-163">Managing the Nodes Within a Schema</span></span>](../core/managing-the-nodes-within-a-schema.md)