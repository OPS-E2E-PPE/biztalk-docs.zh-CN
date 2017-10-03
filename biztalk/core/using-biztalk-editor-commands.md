---
title: "使用 BizTalk 编辑器命令 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e216ae5d-5bad-48ef-87d1-8aa8ee20179b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ae30305f5e23e99b5a0bc76cba9bfc7f451b03
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="use-biztalk-editor-commands"></a><span data-ttu-id="0e466-102">使用 BizTalk 编辑器命令</span><span class="sxs-lookup"><span data-stu-id="0e466-102">Use BizTalk Editor Commands</span></span>

## <a name="overview"></a><span data-ttu-id="0e466-103">概述</span><span class="sxs-lookup"><span data-stu-id="0e466-103">Overview</span></span>
<span data-ttu-id="0e466-104">BizTalk 编辑器将变为活动状态，它会添加菜单调用**BizTalk**到[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="0e466-104">When BizTalk Editor becomes active, it adds a menu called **BizTalk** to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="0e466-105">通过此菜单可以访问 BizTalk 编辑器命令及其功能。</span><span class="sxs-lookup"><span data-stu-id="0e466-105">This menu provides access to the BizTalk Editor commands and their functionality.</span></span> <span data-ttu-id="0e466-106">当 BizTalk 编辑器为活动状态， **BizTalk**菜单提供特定于编辑 BizTalk 架构的命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-106">When BizTalk Editor is active, the **BizTalk** menu provides the commands that are specific to editing BizTalk schemas.</span></span>  
  
 <span data-ttu-id="0e466-107">此外以及在何处适用，BizTalk 编辑器使用的现有[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]具有明显 parallels 标准应用程序功能的命令的菜单项。</span><span class="sxs-lookup"><span data-stu-id="0e466-107">In addition and where applicable, BizTalk Editor uses existing [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] menu items for commands that have obvious parallels to standard application functionality.</span></span> <span data-ttu-id="0e466-108">例如，BizTalk 编辑器处于活动状态时，**保存**命令**文件**菜单将更改保存到当前正在编辑的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-108">For example, when BizTalk Editor is active, the **Save** command on the **File** menu saves changes to the schema that is currently being edited.</span></span>  
  
## <a name="commands-list"></a><span data-ttu-id="0e466-109">命令列表</span><span class="sxs-lookup"><span data-stu-id="0e466-109">Commands list</span></span>
 <span data-ttu-id="0e466-110">下表对 BizTalk 编辑器内可在建立架构的过程中使用的命令进行了说明：</span><span class="sxs-lookup"><span data-stu-id="0e466-110">The following table describes the commands within BizTalk Editor that can be used in the process of developing schemas.</span></span>  
  
|<span data-ttu-id="0e466-111">Command</span><span class="sxs-lookup"><span data-stu-id="0e466-111">Command</span></span><br /><br /> <span data-ttu-id="0e466-112">（菜单位置）</span><span class="sxs-lookup"><span data-stu-id="0e466-112">(Menu Locations)</span></span>|<span data-ttu-id="0e466-113">Description</span><span class="sxs-lookup"><span data-stu-id="0e466-113">Description</span></span>|  
|------------------------------------|-----------------|  
|<span data-ttu-id="0e466-114">**打开架构**</span><span class="sxs-lookup"><span data-stu-id="0e466-114">**Open Schema**</span></span><br /><br /> <span data-ttu-id="0e466-115">(文件 &#124;打开 &#124;文件...）</span><span class="sxs-lookup"><span data-stu-id="0e466-115">(File &#124; Open &#124; File...)</span></span>|<span data-ttu-id="0e466-116">打开 BizTalk 架构以便在 BizTalk 编辑器中进行编辑。</span><span class="sxs-lookup"><span data-stu-id="0e466-116">Opens a BizTalk schema for editing in BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="0e466-117">通过在解决方案资源管理器中选定架构时出现的快捷菜单，或通过在解决方案资源管理器中双击相应的架构，也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-117">Also available on the shortcut menu in Solution Explorer when a schema is selected, and by double-clicking a schema in Solution Explorer.</span></span>|  
|<span data-ttu-id="0e466-118">**关闭架构**</span><span class="sxs-lookup"><span data-stu-id="0e466-118">**Close Schema**</span></span><br /><br /> <span data-ttu-id="0e466-119">(文件 &#124;关闭）</span><span class="sxs-lookup"><span data-stu-id="0e466-119">(File &#124; Close)</span></span>|<span data-ttu-id="0e466-120">对当前架构关闭 BizTalk 编辑器，并提示您保存所有尚未保存的更改。</span><span class="sxs-lookup"><span data-stu-id="0e466-120">Closes BizTalk Editor for the current schema, prompting to save any unsaved changes.</span></span><br /><br /> <span data-ttu-id="0e466-121">通过使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中主编辑窗口右上角的标准“关闭”按钮，也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-121">Also available by using the standard Close button in the upper-right corner of the main editing window in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>|  
|<span data-ttu-id="0e466-122">**新架构**</span><span class="sxs-lookup"><span data-stu-id="0e466-122">**New Schema**</span></span><br /><br /> <span data-ttu-id="0e466-123">(项目 &#124;添加新建项...&#124;架构）</span><span class="sxs-lookup"><span data-stu-id="0e466-123">(Project &#124; Add New Item... &#124; Schema)</span></span>|<span data-ttu-id="0e466-124">创建新的 BizTalk 架构以进行编辑，并打开 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="0e466-124">Creates a new BizTalk schema for editing and opens BizTalk Editor.</span></span><br /><br /> <span data-ttu-id="0e466-125">此外可在解决方案资源管理器中的 BizTalk 项目的快捷菜单上 (添加 &#124;新的项）。</span><span class="sxs-lookup"><span data-stu-id="0e466-125">Also available on the shortcut menu for the BizTalk project in Solution Explorer (Add &#124; New Item).</span></span>|  
|<span data-ttu-id="0e466-126">**保存架构**</span><span class="sxs-lookup"><span data-stu-id="0e466-126">**Save Schema**</span></span><br /><br /> <span data-ttu-id="0e466-127">(文件 &#124;保存 schema.xsd）</span><span class="sxs-lookup"><span data-stu-id="0e466-127">(File &#124; Save schema.xsd)</span></span><br /><br /> <span data-ttu-id="0e466-128">(文件 &#124;保存为 schema.xsd。..)</span><span class="sxs-lookup"><span data-stu-id="0e466-128">(File &#124; Save schema.xsd As...)</span></span><br /><br /> <span data-ttu-id="0e466-129">(文件 &#124;保存所有）</span><span class="sxs-lookup"><span data-stu-id="0e466-129">(File &#124; Save All)</span></span>|<span data-ttu-id="0e466-130">分别表示以当前编辑的 BizTalk 架构自己的名称保存架构，以新名称保存架构，或作为保存所有未保存更改的操作的一部分进行保存。</span><span class="sxs-lookup"><span data-stu-id="0e466-130">Saves the BizTalk schema currently being edited under its own name, under a new name, or as part of saving all unsaved changes, respectively.</span></span>|  
|<span data-ttu-id="0e466-131">**剪切、 复制、 粘贴节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-131">**Cut, Copy, Paste Node**</span></span><br /><br /> <span data-ttu-id="0e466-132">(编辑 &#124;剪切、 编辑 &#124;复制、 编辑 &#124;粘贴）</span><span class="sxs-lookup"><span data-stu-id="0e466-132">(Edit &#124; Cut, Edit &#124; Copy, Edit &#124; Paste)</span></span>|<span data-ttu-id="0e466-133">允许**架构**移动和复制在架构中的节点树视图。</span><span class="sxs-lookup"><span data-stu-id="0e466-133">Allows **Schema** nodes to be moved and duplicated within the schema tree view.</span></span><br /><br /> <span data-ttu-id="0e466-134">如果适用，这些命令在选定节点的快捷菜单上可用，通过使用标准剪切、复制和粘贴快捷键（Ctrl+X、Ctrl+C 和 Ctrl+V）也可以执行这些命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-134">When applicable, these commands are also available on the shortcut menu for the selected node, and by using the standard cut, copy, and paste shortcut keys: CTRL+X, CTRL+C, and CTRL+V.</span></span>|  
|<span data-ttu-id="0e466-135">**删除节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-135">**Delete Node**</span></span><br /><br /> <span data-ttu-id="0e466-136">(编辑 &#124;删除）</span><span class="sxs-lookup"><span data-stu-id="0e466-136">(Edit &#124; Delete)</span></span><br /><br /> <span data-ttu-id="0e466-137">(BizTalk &#124;删除）</span><span class="sxs-lookup"><span data-stu-id="0e466-137">(BizTalk &#124; Delete)</span></span>|<span data-ttu-id="0e466-138">在架构树视图中删除当前选定的节点，并提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="0e466-138">Deletes the currently selected node in the schema tree view, with confirmation prompting.</span></span><br /><br /> <span data-ttu-id="0e466-139">如果适用，通过选定节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-139">When applicable, this command is also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-140">**查找节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-140">**Find Node**</span></span><br /><br /> <span data-ttu-id="0e466-141">(编辑 &#124;查找和替换 &#124;快速查找）</span><span class="sxs-lookup"><span data-stu-id="0e466-141">(Edit &#124; Find and Replace &#124; Quick Find)</span></span>|<span data-ttu-id="0e466-142">提供对架构树视图中的节点名称的搜索功能，这对于大型架构十分有用。</span><span class="sxs-lookup"><span data-stu-id="0e466-142">Provides search functionality for node names in the schema tree view, which can be useful with large schemas.</span></span>|  
|<span data-ttu-id="0e466-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="0e466-143">**Properties**</span></span><br /><br /> <span data-ttu-id="0e466-144">(视图 &#124;属性窗口中）</span><span class="sxs-lookup"><span data-stu-id="0e466-144">(View &#124; Properties Window)</span></span><br /><br /> <span data-ttu-id="0e466-145">(BizTalk &#124;属性）</span><span class="sxs-lookup"><span data-stu-id="0e466-145">(BizTalk &#124; Properties)</span></span>|<span data-ttu-id="0e466-146">使用此命令可访问架构树视图节点的属性，以及更高级的对象（例如架构本身）。</span><span class="sxs-lookup"><span data-stu-id="0e466-146">Provides access to the properties of schema tree view nodes, and to higher-level objects like the schemas themselves.</span></span><br /><br /> <span data-ttu-id="0e466-147">通过所选节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-147">Also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-148">**插入架构节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-148">**Insert Schema Nodes**</span></span><br /><br /> <span data-ttu-id="0e466-149">(BizTalk &#124;插入架构节点 &#124;*)</span><span class="sxs-lookup"><span data-stu-id="0e466-149">(BizTalk &#124; Insert Schema Node &#124; *)</span></span>|<span data-ttu-id="0e466-150">提供将各种不同类型的节点插入架构树视图的方法。</span><span class="sxs-lookup"><span data-stu-id="0e466-150">Provides a way to insert a variety of different types of nodes into the schema tree view.</span></span> <span data-ttu-id="0e466-151">有关可以添加的节点的类型的详细信息，请参阅[BizTalk 表示形式的架构](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="0e466-151">For more information about the types of nodes that can be added, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span><br /><br /> <span data-ttu-id="0e466-152">如果适用，通过选定节点的快捷菜单也可执行这些命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-152">When applicable, these commands are also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-153">**将提升**</span><span class="sxs-lookup"><span data-stu-id="0e466-153">**Promote**</span></span><br /><br /> <span data-ttu-id="0e466-154">(BizTalk &#124;将提升 &#124;*)</span><span class="sxs-lookup"><span data-stu-id="0e466-154">(BizTalk &#124; Promote &#124; *)</span></span>|<span data-ttu-id="0e466-155">提供升级属性的不同方法。</span><span class="sxs-lookup"><span data-stu-id="0e466-155">Provides different ways to promote properties.</span></span><br /><br /> <span data-ttu-id="0e466-156">通过所选节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-156">Also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-157">**展开架构节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-157">**Expand Schema Node**</span></span><br /><br /> <span data-ttu-id="0e466-158">(BizTalk &#124;展开架构节点）</span><span class="sxs-lookup"><span data-stu-id="0e466-158">(BizTalk &#124; Expand Schema Node)</span></span>|<span data-ttu-id="0e466-159">在架构树视图中完全展开当前选定（并且至少部分折叠）的节点。</span><span class="sxs-lookup"><span data-stu-id="0e466-159">Completely expands the currently selected (and at least partially collapsed) node in the schema tree view.</span></span><br /><br /> <span data-ttu-id="0e466-160">如果适用，通过选定节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-160">When applicable, this command is also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-161">**折叠架构节点**</span><span class="sxs-lookup"><span data-stu-id="0e466-161">**Collapse Schema Node**</span></span><br /><br /> <span data-ttu-id="0e466-162">(BizTalk &#124;折叠架构节点）</span><span class="sxs-lookup"><span data-stu-id="0e466-162">(BizTalk &#124; Collapse Schema Node)</span></span>|<span data-ttu-id="0e466-163">在架构树视图中折叠当前选定（并且至少部分展开）的节点。</span><span class="sxs-lookup"><span data-stu-id="0e466-163">Collapses the currently selected (and at least partially expanded)node in the schema tree view.</span></span><br /><br /> <span data-ttu-id="0e466-164">如果适用，通过选定节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-164">When applicable, this command is also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-165">**刷新 XSD**</span><span class="sxs-lookup"><span data-stu-id="0e466-165">**Refresh XSD**</span></span><br /><br /> <span data-ttu-id="0e466-166">(BizTalk &#124;刷新 XSD）</span><span class="sxs-lookup"><span data-stu-id="0e466-166">(BizTalk &#124; Refresh XSD)</span></span>|<span data-ttu-id="0e466-167">刷新 XSD 视图，它可能被设置为不会自动刷新通过选择**打开关闭自动刷新**XSD 视图下的复选框。</span><span class="sxs-lookup"><span data-stu-id="0e466-167">Refreshes the XSD view, which may be set to not refresh automatically by selecting the **Turn Off Auto Refresh** check box below the XSD view.</span></span><br /><br /> <span data-ttu-id="0e466-168">此命令，还可以在快捷菜单，对于所选的节点中，并通过单击**刷新**XSD 视图下。</span><span class="sxs-lookup"><span data-stu-id="0e466-168">This command is also available on the shortcut menu for the selected node, and by clicking **Refresh** below the XSD view.</span></span>|  
|<span data-ttu-id="0e466-169">**重命名**</span><span class="sxs-lookup"><span data-stu-id="0e466-169">**Rename**</span></span><br /><br /> <span data-ttu-id="0e466-170">(BizTalk &#124;重命名）</span><span class="sxs-lookup"><span data-stu-id="0e466-170">(BizTalk &#124; Rename)</span></span>|<span data-ttu-id="0e466-171">允许**记录**，**字段特性**，和**Field 元素**要重命名，就地情况下，架构树视图中的节点。</span><span class="sxs-lookup"><span data-stu-id="0e466-171">Allows **Record**, **Field Attribute**, and **Field Element** nodes to be renamed, in place, within the schema tree view.</span></span><br /><br /> <span data-ttu-id="0e466-172">此命令是等效于更改**节点名称**所选节点的属性。</span><span class="sxs-lookup"><span data-stu-id="0e466-172">This command is equivalent to changing the **Node Name** property of the selected node.</span></span><br /><br /> <span data-ttu-id="0e466-173">如果适用，通过选定节点的快捷菜单也可执行此命令。</span><span class="sxs-lookup"><span data-stu-id="0e466-173">When applicable, this command is also available on the shortcut menu for the selected node.</span></span>|  
|<span data-ttu-id="0e466-174">**BizTalk 编辑器选项**</span><span class="sxs-lookup"><span data-stu-id="0e466-174">**BizTalk Editor Options**</span></span><br /><br /> <span data-ttu-id="0e466-175">(工具 &#124;选项 &#124;BizTalk 编辑器）</span><span class="sxs-lookup"><span data-stu-id="0e466-175">(Tools &#124; Options &#124; BizTalk Editor)</span></span>|<span data-ttu-id="0e466-176">允许对确认对话框（打开或关闭）进行配置，以及调整字体和背景色。</span><span class="sxs-lookup"><span data-stu-id="0e466-176">Allows configuration of confirmation dialogs (on or off), as well as font and background color adjustment.</span></span>|  
  
 <span data-ttu-id="0e466-177">下表对解决方案资源管理器中选定架构的快捷菜单上的其他可用架构命令进行了说明：</span><span class="sxs-lookup"><span data-stu-id="0e466-177">The following table describes additional schema commands that are available on the shortcut menu for the selected schema in Solution Explorer.</span></span>  
  
|<span data-ttu-id="0e466-178">架构命令</span><span class="sxs-lookup"><span data-stu-id="0e466-178">Schema command</span></span>|<span data-ttu-id="0e466-179">Description</span><span class="sxs-lookup"><span data-stu-id="0e466-179">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0e466-180">**打开**</span><span class="sxs-lookup"><span data-stu-id="0e466-180">**Open**</span></span>|<span data-ttu-id="0e466-181">在 BizTalk 编辑器中打开选定的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-181">Opens the selected schema in BizTalk Editor.</span></span>|  
|<span data-ttu-id="0e466-182">**使用打开**</span><span class="sxs-lookup"><span data-stu-id="0e466-182">**Open With**</span></span>|<span data-ttu-id="0e466-183">允许通过不同的 XSD 编辑器（包括 BizTalk 编辑器）打开选定的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-183">Allows the selected schema to be opened in a variety of XSD editors, including BizTalk Editor.</span></span>|  
|<span data-ttu-id="0e466-184">**验证架构**</span><span class="sxs-lookup"><span data-stu-id="0e466-184">**Validate Schema**</span></span>|<span data-ttu-id="0e466-185">验证选定的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-185">Validates the selected schema.</span></span>|  
|<span data-ttu-id="0e466-186">**验证实例**</span><span class="sxs-lookup"><span data-stu-id="0e466-186">**Validate Instance**</span></span>|<span data-ttu-id="0e466-187">验证指定的实例**输入实例 Filename** Visual Studio 中的属性**属性**针对所选的架构的窗口。</span><span class="sxs-lookup"><span data-stu-id="0e466-187">Validates the instance specified by the **Input Instance Filename** property in the Visual Studio **Properties** window against the selected schema.</span></span>|  
|<span data-ttu-id="0e466-188">**生成实例**</span><span class="sxs-lookup"><span data-stu-id="0e466-188">**Generate Instance**</span></span>|<span data-ttu-id="0e466-189">将生成一个实例使用指定的文件名称的所选架构**输出实例文件名**Visual Studio 中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="0e466-189">Generates an instance of the selected schema using the file name specified by the **Output Instance Filename** property in the Visual Studio **Properties** window.</span></span><br /><br /> <span data-ttu-id="0e466-190">如果没有为生成的输出实例指定任何名称，则使用默认文件名。</span><span class="sxs-lookup"><span data-stu-id="0e466-190">If no name is specified for the generated output instance, a default file name will be used.</span></span> <span data-ttu-id="0e466-191">默认文件名是字符串“_output.xml”（位于 Documents and Settings 文件夹中临时文件夹的 _SchemaData 文件夹中）之前的架构文件名。</span><span class="sxs-lookup"><span data-stu-id="0e466-191">The default file name is the schema file name prepended to the string "_output.xml" in the folder _SchemaData in a temp folder in your Documents and Settings folder.</span></span>|  
|<span data-ttu-id="0e466-192">**查看代码**</span><span class="sxs-lookup"><span data-stu-id="0e466-192">**View Code**</span></span>|<span data-ttu-id="0e466-193">显示基础 XSD。</span><span class="sxs-lookup"><span data-stu-id="0e466-193">Displays the underlying XSD.</span></span>|  
|<span data-ttu-id="0e466-194">**视图设计器**</span><span class="sxs-lookup"><span data-stu-id="0e466-194">**View Designer**</span></span>|<span data-ttu-id="0e466-195">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML 架构设计器中打开架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-195">Opens the schema in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] XML Schema Designer.</span></span>|  
|<span data-ttu-id="0e466-196">**从项目中排除**</span><span class="sxs-lookup"><span data-stu-id="0e466-196">**Exclude From Project**</span></span>|<span data-ttu-id="0e466-197">从当前的 BizTalk 项目中删除当前选定的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-197">Removes the currently selected schema from the current BizTalk project.</span></span><br /><br /> <span data-ttu-id="0e466-198">使用**添加现有项**命令以重新添加之前已从当前的 BizTalk 项目中排除的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-198">Use the **Add Existing Item** command to re-add a schema that was previously excluded from the current BizTalk project.</span></span>|  
|<span data-ttu-id="0e466-199">**剪切、 复制粘贴**</span><span class="sxs-lookup"><span data-stu-id="0e466-199">**Cut, Copy, Paste**</span></span>|<span data-ttu-id="0e466-200">使用这些命令来执行标准[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的剪切、 复制和粘贴在 BizTalk 项目中的整个架构的行为。</span><span class="sxs-lookup"><span data-stu-id="0e466-200">Use these commands to perform the standard [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] behavior of cutting, copying, and pasting entire schemas within a BizTalk project.</span></span>|  
|<span data-ttu-id="0e466-201">**删除**</span><span class="sxs-lookup"><span data-stu-id="0e466-201">**Delete**</span></span>|<span data-ttu-id="0e466-202">永久删除当前选定的架构，并提示您进行确认。</span><span class="sxs-lookup"><span data-stu-id="0e466-202">Permanently deletes the currently selected schema, with a confirmation prompting.</span></span>|  
|<span data-ttu-id="0e466-203">**重命名**</span><span class="sxs-lookup"><span data-stu-id="0e466-203">**Rename**</span></span>|<span data-ttu-id="0e466-204">允许就地重命名当前选定的架构。</span><span class="sxs-lookup"><span data-stu-id="0e466-204">Allows the currently selected schema to be renamed, in place.</span></span>|  
|<span data-ttu-id="0e466-205">**属性**</span><span class="sxs-lookup"><span data-stu-id="0e466-205">**Properties**</span></span>|<span data-ttu-id="0e466-206">打开 Visual Studio**属性**窗口对于当前所选的架构，在其中的某些架构属性可以检查和设置。</span><span class="sxs-lookup"><span data-stu-id="0e466-206">Opens the Visual Studio **Properties**  window for the currently selected schema, in which some of the properties of the schema can be examined and set.</span></span> <br/><br/><span data-ttu-id="0e466-207">**注意：**架构的其他属性都检查并在中设置[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]时选择架构属性窗口。</span><span class="sxs-lookup"><span data-stu-id="0e466-207">**Note:**  Other properties of the schema are examined and set in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window when the schema is selected.</span></span> <span data-ttu-id="0e466-208">在中设置属性**属性**窗口是为其不同的值可能时有意义的相同的架构使用多个 BizTalk 项目中的这些属性。</span><span class="sxs-lookup"><span data-stu-id="0e466-208">Properties that are set in the **Properties** window are those properties for which different values may make sense for the same schema when it is used in more than one BizTalk project.</span></span> <br /><br /> <span data-ttu-id="0e466-209">有关设置架构属性和架构的属性的详细信息，请参阅[设置架构文件和架构项属性](../core/how-to-set-schema-file-and-schema-item-properties.md)和**架构文件属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="0e466-209">For more information about setting schema properties and the properties of schemas, see [Setting Schema File and Schema Item Properties](../core/how-to-set-schema-file-and-schema-item-properties.md) and **Schema File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e466-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e466-210">See Also</span></span>  
 [<span data-ttu-id="0e466-211">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="0e466-211">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)