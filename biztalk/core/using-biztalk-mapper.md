---
title: "使用 BizTalk 映射程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf339069f4868aa7c7bff07ae8bdbbb029c5f81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-mapper"></a><span data-ttu-id="0bb90-102">使用 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="0bb90-102">Using BizTalk Mapper</span></span>

## <a name="overview"></a><span data-ttu-id="0bb90-103">概述</span><span class="sxs-lookup"><span data-stu-id="0bb90-103">Overview</span></span>
<span data-ttu-id="0bb90-104">BizTalk 映射器驻留在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Shell 中。</span><span class="sxs-lookup"><span data-stu-id="0bb90-104">The BizTalk Mapper resides in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="0bb90-105">BizTalk 映射器中的某些功能依赖于 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Shell 的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="0bb90-105">Some of the functionality in the BizTalk Mapper relies on the user interface elements of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="0bb90-106">例如，使用**文件**，**编辑**，和**视图**就像你的菜单将中的其他开发的[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0bb90-106">For example, you use the **File**, **Edit**, and **View** menus just as you would for other development in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="0bb90-107">有关此通用功能的信息位于**帮助**菜单。</span><span class="sxs-lookup"><span data-stu-id="0bb90-107">Information about this common functionality is available from the **Help** menu.</span></span>  
  
 <span data-ttu-id="0bb90-108">在向 BizTalk 项目添加新的映射，打开现有的映射（.btm 文件）或在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 主编辑窗口中单击与映射相应的选项卡重新激活该映射时，BizTalk 映射器将变为活动状态。</span><span class="sxs-lookup"><span data-stu-id="0bb90-108">The BizTalk Mapper becomes active when you add a new map to a BizTalk project, when you open an existing map (a .btm file), or when you reactivate a map by clicking its tab in the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bb90-109">BizTalk 映射器使用 UTF-16 字符编码保存映射文件。</span><span class="sxs-lookup"><span data-stu-id="0bb90-109">The BizTalk Mapper saves map files using UTF-16 character encoding.</span></span>  
>
>  <span data-ttu-id="0bb90-110">当你将现有项目添加到 BizTalk 项目时，生成操作始终设置为**BtsCompile**。</span><span class="sxs-lookup"><span data-stu-id="0bb90-110">When you add an existing artifact to a BizTalk project, the build action is always set to **BtsCompile**.</span></span> <span data-ttu-id="0bb90-111">即使重命名现有项目，其生成操作设置为默认值**BtsCompile**。</span><span class="sxs-lookup"><span data-stu-id="0bb90-111">Even when you rename an existing artifact, its build action is set to the default value **BtsCompile**.</span></span> <span data-ttu-id="0bb90-112">因此，添加或重命名现有项目时，您需要根据是否需要生成该特殊项目来对生成操作进行相应设置。</span><span class="sxs-lookup"><span data-stu-id="0bb90-112">Hence, while adding or renaming an existing artifact, you need to set the build action appropriately depending on whether you want to build that particular artifact or not.</span></span>  

## <a name="parts-of-the-biztalk-mapper"></a><span data-ttu-id="0bb90-113">BizTalk 映射程序的部分</span><span class="sxs-lookup"><span data-stu-id="0bb90-113">Parts of the BizTalk Mapper</span></span>  
 <span data-ttu-id="0bb90-114">下图显示了 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中 BizTalk 映射器的各个部分。</span><span class="sxs-lookup"><span data-stu-id="0bb90-114">The following figure shows various parts of BizTalk Mapper within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="0bb90-115">![BizTalk 映射程序](../core/media/mapper-views.gif "Mapper_Views")</span><span class="sxs-lookup"><span data-stu-id="0bb90-115">![BizTalk Mapper](../core/media/mapper-views.gif "Mapper_Views")</span></span>  
  
 <span data-ttu-id="0bb90-116">每个视图的功能如下：</span><span class="sxs-lookup"><span data-stu-id="0bb90-116">The functionality of each of the views is as follows:</span></span>  
  
-   <span data-ttu-id="0bb90-117">**Visual Studio 映射器实用工具的功能区。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-117">**Visual Studio Mapper Utility Ribbon.**</span></span> <span data-ttu-id="0bb90-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射器提供了与图面映射器相关的命令实用工具功能区。</span><span class="sxs-lookup"><span data-stu-id="0bb90-118">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Mapper provides a utility ribbon to surface Mapper-related commands.</span></span> <span data-ttu-id="0bb90-119">该功能区提供源架构信息、用于源和目标架构的关联视图的切换按钮、用于显示或隐藏所有作用域链接的切换按钮、用于打开或关闭自动滚动的切换开关、用于平移映射器界面的按钮、用于放大或缩小的控件以及搜索文本框。</span><span class="sxs-lookup"><span data-stu-id="0bb90-119">The ribbon provides source schema information, toggle button for relevance view for source and destination schemas, toggle button to show or hide totally out of scope links, toggle switch to turn auto-scrolling on or off, button to pan the Mapper surface, controls to zoom in or zoom out, and the search text box.</span></span> <span data-ttu-id="0bb90-120">下图显示了您可以在网格页顶部看到的实用工具功能区。</span><span class="sxs-lookup"><span data-stu-id="0bb90-120">The following figure shows the utility ribbon you can see at the top of the grid page.</span></span>  
  
     <span data-ttu-id="0bb90-121">![映射器功能区](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span><span class="sxs-lookup"><span data-stu-id="0bb90-121">![Mapper ribbon](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span></span>  
  
-   <span data-ttu-id="0bb90-122">**源架构树视图。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-122">**Source schema tree view.**</span></span> <span data-ttu-id="0bb90-123">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与目标架构树视图和网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="0bb90-123">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the destination schema tree view and the grid view.</span></span>  
  
     <span data-ttu-id="0bb90-124">顾名思义，此视图显示了描述作为映射源的实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="0bb90-124">As the name suggests, this view displays the schema that describes the instance messages that are the source of mapping.</span></span> <span data-ttu-id="0bb90-125">定义映射的链接可引导您从源架构树视图进入网格视图，并最终进入目标架构树视图。</span><span class="sxs-lookup"><span data-stu-id="0bb90-125">The links that define the mapping lead from the source schema tree view to the grid view, and, ultimately, to the destination schema tree view.</span></span>  
  
     <span data-ttu-id="0bb90-126">有关 BizTalk 架构的架构树视图中的表示方式的详细信息，请参阅[BizTalk 表示形式的架构](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb90-126">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
-   <span data-ttu-id="0bb90-127">**目标架构树视图。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-127">**Destination schema tree view.**</span></span> <span data-ttu-id="0bb90-128">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="0bb90-128">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the grid view.</span></span>  
  
     <span data-ttu-id="0bb90-129">顾名思义，此视图显示了描述作为映射目标的实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="0bb90-129">As the name suggests, this view displays the schema that describes the instance messages that are the destination of the mapping.</span></span> <span data-ttu-id="0bb90-130">定义映射的链接可引导您从网格视图进入目标架构树视图，并最终从源架构树视图进入。</span><span class="sxs-lookup"><span data-stu-id="0bb90-130">The links that define the mapping lead into the destination schema tree view from the grid view, and ultimately from the source schema tree view.</span></span>  
  
     <span data-ttu-id="0bb90-131">有关 BizTalk 架构的架构树视图中的表示方式的详细信息，请参阅[BizTalk 表示形式的架构](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb90-131">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
-   <span data-ttu-id="0bb90-132">**网格视图。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-132">**Grid view.**</span></span> <span data-ttu-id="0bb90-133">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和目标架构树视图中，使用左侧的源架构树视图和目标架构树视图向右的窗口。</span><span class="sxs-lookup"><span data-stu-id="0bb90-133">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the destination schema tree view, with the source schema tree view to the left and the destination schema tree view to the right.</span></span>  
  
     <span data-ttu-id="0bb90-134">顾名思义，此视图在映射定义中扮演着关键角色，其中包含控制如何将源实例消息中的数据转换至符合目标架构的实例消息的链接和 functoid。</span><span class="sxs-lookup"><span data-stu-id="0bb90-134">As the name suggests, this view plays a critical role in the definition of maps, containing the links and functoids that control how data in a source instance message is transformed into an instance message that conforms to the destination schema.</span></span>  
  
     <span data-ttu-id="0bb90-135">网格视图可以具有多个层（称为网格页），通过使用这些层，可以将复杂映射组织到映射的逻辑分支中。</span><span class="sxs-lookup"><span data-stu-id="0bb90-135">The grid view can have multiple layers, called grid pages, allowing you to organize complex maps into logical subdivisions of mappings.</span></span> <span data-ttu-id="0bb90-136">网格页所使用的空间通常比一次可以显示的空间要多，有多种有效方法可以在网格页中进行滚动。</span><span class="sxs-lookup"><span data-stu-id="0bb90-136">Grid pages generally use more space than can be displayed at one time, and there are several effective ways to scroll within a grid page.</span></span>  
  
     <span data-ttu-id="0bb90-137">目前您可使用此视图构建映射。</span><span class="sxs-lookup"><span data-stu-id="0bb90-137">You actively work in this view to construct your map.</span></span>  
  
-   <span data-ttu-id="0bb90-138">**Visual Studio 工具箱窗口。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-138">**Visual Studio Toolbox window.**</span></span> <span data-ttu-id="0bb90-139">此视图用于显示可在 BizTalk 映射中使用的 functoid，并用作拖放操作源以将 functoid 置于网格页中。</span><span class="sxs-lookup"><span data-stu-id="0bb90-139">You use this view to display the functoids available for use in BizTalk maps, and as the source of the drag-and-drop operations to place functoids in a grid page.</span></span>  
  
     <span data-ttu-id="0bb90-140">“工具箱”中显示的 functoid 按类别进行组织。</span><span class="sxs-lookup"><span data-stu-id="0bb90-140">The functoids shown in the Toolbox are organized according to their categories.</span></span> <span data-ttu-id="0bb90-141">有关可用的 functoid 的详细信息，请参阅[Maps 中的 Functoid](../core/functoids-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="0bb90-141">For more information about the available functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span> <span data-ttu-id="0bb90-142">另请参阅**Functoid 引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="0bb90-142">Also see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
-   <span data-ttu-id="0bb90-143">**Visual Studio 属性窗口。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-143">**Visual Studio Properties window.**</span></span> <span data-ttu-id="0bb90-144">此视图及其关联对话框用于检查和设置你为定义映射而创建的链接和 functoid。</span><span class="sxs-lookup"><span data-stu-id="0bb90-144">You use this view, and its associated dialog boxes, to examine and set the properties of the links and functoids that you create to define your map.</span></span>  
  
     <span data-ttu-id="0bb90-145">当在网格视图中的网格页中选择的是链接或 functoid 时，在源或目标架构树视图中，选择架构节点或选择地图中的**解决方案资源管理器**窗口中; 该链接时，functoid 的相应属性架构节点或出现在代码图**属性**使用标准 Visual Studio 约定的窗口。</span><span class="sxs-lookup"><span data-stu-id="0bb90-145">When you select a link or functoid in a grid page in the Grid view, select a schema node in the source or destination schema tree views, or select a map in the **Solution Explorer** window; the corresponding properties of that link, functoid, schema node, or map appear in the **Properties** window using the standard Visual Studio conventions.</span></span> <span data-ttu-id="0bb90-146">例如，属性将分组为不同的类别，您可以按这些类别或按字母顺序显示属性。</span><span class="sxs-lookup"><span data-stu-id="0bb90-146">For example, the properties are grouped into categories, and can be displayed according to these categories or alphabetically.</span></span>  
  
     <span data-ttu-id="0bb90-147">有关不同的可用于链接、 functoid、 架构节点或映射本身的属性集的详细信息，请参阅**映射属性引用**和**架构属性引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  </span><span class="sxs-lookup"><span data-stu-id="0bb90-147">For detailed information about the different sets of properties that are available for links, functoids, schema nodes, or the map itself, see the **Map Property Reference** and the **Schema Property Reference**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
-   <span data-ttu-id="0bb90-148">**Visual Studio 任务列表和输出窗口。**</span><span class="sxs-lookup"><span data-stu-id="0bb90-148">**Visual Studio Task List and Output windows.**</span></span> <span data-ttu-id="0bb90-149">这些视图用于检查执行以下操作的结果：通过在编译源代码和生成其他类型的项目时使用这些视图的相同方式，验证、编译和测试 BizTalk 映射。</span><span class="sxs-lookup"><span data-stu-id="0bb90-149">You use these views to examine the results of validating, compiling, and testing your BizTalk maps in much the same way that these views are used when compiling source code and building other types of projects.</span></span>  
  
 <span data-ttu-id="0bb90-150">除了这些视图外，你还可以与几个对话框交互。</span><span class="sxs-lookup"><span data-stu-id="0bb90-150">In addition to these views, you can interact with several dialog boxes.</span></span> <span data-ttu-id="0bb90-151">在编辑诸如 functoid 输入参数等复杂属性时，通常会打开这些对话框。</span><span class="sxs-lookup"><span data-stu-id="0bb90-151">You usually open these dialog boxes when you are editing a complex property such as the input parameters to a functoid.</span></span>  
  
 <span data-ttu-id="0bb90-152">“解决方案资源管理器”窗口通常与 BizTalk 映射器结合使用。</span><span class="sxs-lookup"><span data-stu-id="0bb90-152">You often use the Solution Explorer window in conjunction with BizTalk Mapper.</span></span> <span data-ttu-id="0bb90-153">例如，若要创建新的映射，右键单击中的 BizTalk 项目**解决方案资源管理器**窗口中，单击**添加**，单击**添加新项**，然后使用**添加新项**对话框中进行命名和创建新的图。</span><span class="sxs-lookup"><span data-stu-id="0bb90-153">For example, to create a new map, right-click the BizTalk project in the **Solution Explorer** window, click **Add**, click **Add New Item**, and then use the **Add New Item** dialog box to name and create a new map.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0bb90-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0bb90-154">Next steps</span></span>
  
-   [<span data-ttu-id="0bb90-155">使用 BizTalk 映射程序命令</span><span class="sxs-lookup"><span data-stu-id="0bb90-155">Using BizTalk Mapper Commands</span></span>](../core/using-biztalk-mapper-commands.md)  
  
-   [<span data-ttu-id="0bb90-156">使用网格页</span><span class="sxs-lookup"><span data-stu-id="0bb90-156">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)  
  
-   [<span data-ttu-id="0bb90-157">如何管理视图</span><span class="sxs-lookup"><span data-stu-id="0bb90-157">How to Manage Views</span></span>](../core/how-to-manage-views.md)  
  
-   [<span data-ttu-id="0bb90-158">如何自定义颜色和字体在 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="0bb90-158">How to Customize Colors and Font in BizTalk Mapper</span></span>](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="0bb90-159">如何展开和折叠架构树</span><span class="sxs-lookup"><span data-stu-id="0bb90-159">How to Expand and Collapse the Schema Trees</span></span>](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [<span data-ttu-id="0bb90-160">如何撤消或重做用户操作</span><span class="sxs-lookup"><span data-stu-id="0bb90-160">How to Undo or Redo User Operations</span></span>](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [<span data-ttu-id="0bb90-161">如何搜索映射项</span><span class="sxs-lookup"><span data-stu-id="0bb90-161">How to Search for Map Items</span></span>](../core/how-to-search-for-map-items.md)  
  
-   [<span data-ttu-id="0bb90-162">在 BizTalk 映射程序中使用增强的功能</span><span class="sxs-lookup"><span data-stu-id="0bb90-162">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="0bb90-163">如何查看信息提示和工具提示</span><span class="sxs-lookup"><span data-stu-id="0bb90-163">How to View Infotip and Tooltip</span></span>](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a><span data-ttu-id="0bb90-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bb90-164">See Also</span></span>  
 [<span data-ttu-id="0bb90-165">如何优化的链接显示</span><span class="sxs-lookup"><span data-stu-id="0bb90-165">How to Optimize the Display of Links</span></span>](../core/how-to-optimize-the-display-of-links.md)