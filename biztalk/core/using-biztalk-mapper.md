---
title: 使用 BizTalk 映射器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.grid
ms.assetid: 07c69603-ee79-44b2-80b1-6ae4e4c8fb4e
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdefb8c35f817008d0727db82eaf0fe2b04b9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401689"
---
# <a name="using-biztalk-mapper"></a><span data-ttu-id="3d531-102">使用 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="3d531-102">Using BizTalk Mapper</span></span>

## <a name="overview"></a><span data-ttu-id="3d531-103">概述</span><span class="sxs-lookup"><span data-stu-id="3d531-103">Overview</span></span>
<span data-ttu-id="3d531-104">BizTalk 映射器驻留在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="3d531-104">The BizTalk Mapper resides in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="3d531-105">在 BizTalk 映射器功能的一些依赖的用户界面元素[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="3d531-105">Some of the functionality in the BizTalk Mapper relies on the user interface elements of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="3d531-106">例如，使用**文件**，**编辑**，并**视图**菜单正如您将在执行其他开发[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d531-106">For example, you use the **File**, **Edit**, and **View** menus just as you would for other development in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="3d531-107">提供了有关此通用功能的信息**帮助**菜单。</span><span class="sxs-lookup"><span data-stu-id="3d531-107">Information about this common functionality is available from the **Help** menu.</span></span>  
  
 <span data-ttu-id="3d531-108">添加新映射到 BizTalk 项目中，打开现有的映射 （.btm 文件），或通过单击主其选项卡重新激活该映射，BizTalk 映射器将变为活动[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="3d531-108">The BizTalk Mapper becomes active when you add a new map to a BizTalk project, when you open an existing map (a .btm file), or when you reactivate a map by clicking its tab in the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d531-109">BizTalk 映射器保存映射文件使用 utf-16 字符编码。</span><span class="sxs-lookup"><span data-stu-id="3d531-109">The BizTalk Mapper saves map files using UTF-16 character encoding.</span></span>  
>
>  <span data-ttu-id="3d531-110">生成操作时向 BizTalk 项目添加现有项目，请始终设置为**BtsCompile**。</span><span class="sxs-lookup"><span data-stu-id="3d531-110">When you add an existing artifact to a BizTalk project, the build action is always set to **BtsCompile**.</span></span> <span data-ttu-id="3d531-111">即使在重命名现有项目，其生成操作设置为默认值**BtsCompile**。</span><span class="sxs-lookup"><span data-stu-id="3d531-111">Even when you rename an existing artifact, its build action is set to the default value **BtsCompile**.</span></span> <span data-ttu-id="3d531-112">因此，在添加或重命名现有项目时，你需要设置适当地根据是否想要或不生成该特殊项目的生成操作。</span><span class="sxs-lookup"><span data-stu-id="3d531-112">Hence, while adding or renaming an existing artifact, you need to set the build action appropriately depending on whether you want to build that particular artifact or not.</span></span>  

## <a name="parts-of-the-biztalk-mapper"></a><span data-ttu-id="3d531-113">BizTalk 映射器的各个部分</span><span class="sxs-lookup"><span data-stu-id="3d531-113">Parts of the BizTalk Mapper</span></span>  
 <span data-ttu-id="3d531-114">下图显示了 BizTalk 映射器中的各个部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d531-114">The following figure shows various parts of BizTalk Mapper within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
 <span data-ttu-id="3d531-115">![BizTalk 映射器](../core/media/mapper-views.gif "Mapper_Views")</span><span class="sxs-lookup"><span data-stu-id="3d531-115">![BizTalk Mapper](../core/media/mapper-views.gif "Mapper_Views")</span></span>  
  
 <span data-ttu-id="3d531-116">每个视图的功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d531-116">The functionality of each of the views is as follows:</span></span>  
  
- <span data-ttu-id="3d531-117">**Visual Studio 映射器实用工具功能区。**</span><span class="sxs-lookup"><span data-stu-id="3d531-117">**Visual Studio Mapper Utility Ribbon.**</span></span> <span data-ttu-id="3d531-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]映射器提供了显示映射器相关命令的实用工具功能区。</span><span class="sxs-lookup"><span data-stu-id="3d531-118">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Mapper provides a utility ribbon to surface Mapper-related commands.</span></span> <span data-ttu-id="3d531-119">关联视图的源和目标架构，切换按钮来显示或隐藏所有作用域的链接，切换开关以启用自动滚动开还是关，若要进行平移映射器图面的按钮控件添加到功能区提供源架构信息、 切换按钮放大或缩小扩展，并在搜索文本框。</span><span class="sxs-lookup"><span data-stu-id="3d531-119">The ribbon provides source schema information, toggle button for relevance view for source and destination schemas, toggle button to show or hide totally out of scope links, toggle switch to turn auto-scrolling on or off, button to pan the Mapper surface, controls to zoom in or zoom out, and the search text box.</span></span> <span data-ttu-id="3d531-120">下图显示了您可以在网格页的顶部看到实用工具功能区。</span><span class="sxs-lookup"><span data-stu-id="3d531-120">The following figure shows the utility ribbon you can see at the top of the grid page.</span></span>  
  
   <span data-ttu-id="3d531-121">![映射器功能区](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span><span class="sxs-lookup"><span data-stu-id="3d531-121">![Mapper ribbon](../core/media/mapper-ribbon.gif "Mapper_Ribbon")</span></span>  
  
- <span data-ttu-id="3d531-122">**源架构树视图。**</span><span class="sxs-lookup"><span data-stu-id="3d531-122">**Source schema tree view.**</span></span> <span data-ttu-id="3d531-123">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与目标架构树视图和网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="3d531-123">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the destination schema tree view and the grid view.</span></span>  
  
   <span data-ttu-id="3d531-124">顾名思义，此视图将显示描述是映射的源实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="3d531-124">As the name suggests, this view displays the schema that describes the instance messages that are the source of mapping.</span></span> <span data-ttu-id="3d531-125">定义的映射的链接可引导的源架构树视图从网格视图，则从根本上讲，对目标架构树视图。</span><span class="sxs-lookup"><span data-stu-id="3d531-125">The links that define the mapping lead from the source schema tree view to the grid view, and, ultimately, to the destination schema tree view.</span></span>  
  
   <span data-ttu-id="3d531-126">有关 BizTalk 架构在架构树视图中的表示方式的详细信息，请参阅[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="3d531-126">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
- <span data-ttu-id="3d531-127">**目标架构树视图。**</span><span class="sxs-lookup"><span data-stu-id="3d531-127">**Destination schema tree view.**</span></span> <span data-ttu-id="3d531-128">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和网格视图窗口。</span><span class="sxs-lookup"><span data-stu-id="3d531-128">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the grid view.</span></span>  
  
   <span data-ttu-id="3d531-129">顾名思义，此视图将显示描述所映射的目标实例消息的架构。</span><span class="sxs-lookup"><span data-stu-id="3d531-129">As the name suggests, this view displays the schema that describes the instance messages that are the destination of the mapping.</span></span> <span data-ttu-id="3d531-130">定义的映射的链接可引导到目标架构树视图从网格视图中，并最终从源架构树视图中。</span><span class="sxs-lookup"><span data-stu-id="3d531-130">The links that define the mapping lead into the destination schema tree view from the grid view, and ultimately from the source schema tree view.</span></span>  
  
   <span data-ttu-id="3d531-131">有关 BizTalk 架构在架构树视图中的表示方式的详细信息，请参阅[BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="3d531-131">For more information about how BizTalk schemas are represented in a schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
- <span data-ttu-id="3d531-132">**网格视图。**</span><span class="sxs-lookup"><span data-stu-id="3d531-132">**Grid view.**</span></span> <span data-ttu-id="3d531-133">此视图共享主[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑与源架构树视图和目标架构树视图中，使用左侧的源架构树视图和目标架构树视图右侧的窗口。</span><span class="sxs-lookup"><span data-stu-id="3d531-133">This view shares the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window with the source schema tree view and the destination schema tree view, with the source schema tree view to the left and the destination schema tree view to the right.</span></span>  
  
   <span data-ttu-id="3d531-134">顾名思义，此视图播放的控制如何将源实例消息中的数据转换为符合目标架构的实例消息中的地图，其中包含的链接和 functoid 定义的关键角色。</span><span class="sxs-lookup"><span data-stu-id="3d531-134">As the name suggests, this view plays a critical role in the definition of maps, containing the links and functoids that control how data in a source instance message is transformed into an instance message that conforms to the destination schema.</span></span>  
  
   <span data-ttu-id="3d531-135">网格视图中可以有多个层，我们称之为网格页面，从而允许您将复杂映射组织到映射的逻辑分支。</span><span class="sxs-lookup"><span data-stu-id="3d531-135">The grid view can have multiple layers, called grid pages, allowing you to organize complex maps into logical subdivisions of mappings.</span></span> <span data-ttu-id="3d531-136">网格页通常使用比一次可显示更多的空间并且有多种有效方法在网格页内滚动。</span><span class="sxs-lookup"><span data-stu-id="3d531-136">Grid pages generally use more space than can be displayed at one time, and there are several effective ways to scroll within a grid page.</span></span>  
  
   <span data-ttu-id="3d531-137">目前您可使用此视图构建映射中。</span><span class="sxs-lookup"><span data-stu-id="3d531-137">You actively work in this view to construct your map.</span></span>  
  
- <span data-ttu-id="3d531-138">**Visual Studio 工具箱窗口。**</span><span class="sxs-lookup"><span data-stu-id="3d531-138">**Visual Studio Toolbox window.**</span></span> <span data-ttu-id="3d531-139">此视图用于显示可供使用的 functoid，在 BizTalk 映射，并作为拖放操作以将 functoid 置于网格页的源。</span><span class="sxs-lookup"><span data-stu-id="3d531-139">You use this view to display the functoids available for use in BizTalk maps, and as the source of the drag-and-drop operations to place functoids in a grid page.</span></span>  
  
   <span data-ttu-id="3d531-140">显示在工具箱中的 functoid 根据类别进行组织。</span><span class="sxs-lookup"><span data-stu-id="3d531-140">The functoids shown in the Toolbox are organized according to their categories.</span></span> <span data-ttu-id="3d531-141">有关可用的 functoid 的详细信息，请参阅[映射中的 Functoid](../core/functoids-in-maps.md)。</span><span class="sxs-lookup"><span data-stu-id="3d531-141">For more information about the available functoids, see [Functoids in Maps](../core/functoids-in-maps.md).</span></span> <span data-ttu-id="3d531-142">另请参阅**Functoid 参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="3d531-142">Also see the **Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
- <span data-ttu-id="3d531-143">**Visual Studio 属性窗口。**</span><span class="sxs-lookup"><span data-stu-id="3d531-143">**Visual Studio Properties window.**</span></span> <span data-ttu-id="3d531-144">使用此视图中和其关联的对话框，可以查看和设置的链接和 functoid 创建为定义映射的属性。</span><span class="sxs-lookup"><span data-stu-id="3d531-144">You use this view, and its associated dialog boxes, to examine and set the properties of the links and functoids that you create to define your map.</span></span>  
  
   <span data-ttu-id="3d531-145">在网格视图中的网格页中选择链接或 functoid，在源或目标架构树视图，选择 schema 节点或中选择映射**解决方案资源管理器**窗口; 该链接，functoid 的相应属性schema 节点或映射中出现**属性**窗口使用标准的 Visual Studio 约定。</span><span class="sxs-lookup"><span data-stu-id="3d531-145">When you select a link or functoid in a grid page in the Grid view, select a schema node in the source or destination schema tree views, or select a map in the **Solution Explorer** window; the corresponding properties of that link, functoid, schema node, or map appear in the **Properties** window using the standard Visual Studio conventions.</span></span> <span data-ttu-id="3d531-146">例如，属性都分组到类别，并可以根据这些类别或按字母顺序显示。</span><span class="sxs-lookup"><span data-stu-id="3d531-146">For example, the properties are grouped into categories, and can be displayed according to these categories or alphabetically.</span></span>  
  
   <span data-ttu-id="3d531-147">有关不同的可用于链接、 functoid、 schema 节点或映射本身的属性集的详细信息，请参阅**映射属性参考**和**Schema Property Reference**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="3d531-147">For detailed information about the different sets of properties that are available for links, functoids, schema nodes, or the map itself, see the **Map Property Reference** and the **Schema Property Reference**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
- <span data-ttu-id="3d531-148">**Visual Studio 任务列表和输出窗口。**</span><span class="sxs-lookup"><span data-stu-id="3d531-148">**Visual Studio Task List and Output windows.**</span></span> <span data-ttu-id="3d531-149">使用这些视图以检查验证、 编译和测试 BizTalk 映射在很大程度相同的方式编译源代码时，使用这些视图和生成其他类型的项目的结果。</span><span class="sxs-lookup"><span data-stu-id="3d531-149">You use these views to examine the results of validating, compiling, and testing your BizTalk maps in much the same way that these views are used when compiling source code and building other types of projects.</span></span>  
  
  <span data-ttu-id="3d531-150">除了这些视图中，您可以交互与几个对话框。</span><span class="sxs-lookup"><span data-stu-id="3d531-150">In addition to these views, you can interact with several dialog boxes.</span></span> <span data-ttu-id="3d531-151">在编辑诸如 functoid 的输入参数等复杂属性时，通常会打开这些对话框。</span><span class="sxs-lookup"><span data-stu-id="3d531-151">You usually open these dialog boxes when you are editing a complex property such as the input parameters to a functoid.</span></span>  
  
  <span data-ttu-id="3d531-152">您通常使用 BizTalk 映射器结合使用解决方案资源管理器窗口。</span><span class="sxs-lookup"><span data-stu-id="3d531-152">You often use the Solution Explorer window in conjunction with BizTalk Mapper.</span></span> <span data-ttu-id="3d531-153">例如，若要创建新的映射，请右键单击 BizTalk 项目中的**解决方案资源管理器**窗口中，单击**添加**，单击**添加新项**，然后使用**添加新项**对话框进行命名和创建新的映射。</span><span class="sxs-lookup"><span data-stu-id="3d531-153">For example, to create a new map, right-click the BizTalk project in the **Solution Explorer** window, click **Add**, click **Add New Item**, and then use the **Add New Item** dialog box to name and create a new map.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="3d531-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3d531-154">Next steps</span></span>
  
-   [<span data-ttu-id="3d531-155">使用 BizTalk 映射器命令</span><span class="sxs-lookup"><span data-stu-id="3d531-155">Using BizTalk Mapper Commands</span></span>](../core/using-biztalk-mapper-commands.md)  
  
-   [<span data-ttu-id="3d531-156">使用网格页</span><span class="sxs-lookup"><span data-stu-id="3d531-156">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)  
  
-   [<span data-ttu-id="3d531-157">如何管理视图</span><span class="sxs-lookup"><span data-stu-id="3d531-157">How to Manage Views</span></span>](../core/how-to-manage-views.md)  
  
-   [<span data-ttu-id="3d531-158">如何自定义的颜色和字体在 BizTalk 映射器</span><span class="sxs-lookup"><span data-stu-id="3d531-158">How to Customize Colors and Font in BizTalk Mapper</span></span>](../core/how-to-customize-colors-and-font-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="3d531-159">如何展开和折叠架构树</span><span class="sxs-lookup"><span data-stu-id="3d531-159">How to Expand and Collapse the Schema Trees</span></span>](../core/how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees.md)  
  
-   [<span data-ttu-id="3d531-160">如何撤消或重做用户操作</span><span class="sxs-lookup"><span data-stu-id="3d531-160">How to Undo or Redo User Operations</span></span>](../core/how-to-undo-or-redo-user-operations.md)  
  
-   [<span data-ttu-id="3d531-161">如何搜索映射项</span><span class="sxs-lookup"><span data-stu-id="3d531-161">How to Search for Map Items</span></span>](../core/how-to-search-for-map-items.md)  
  
-   [<span data-ttu-id="3d531-162">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="3d531-162">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)  
  
-   [<span data-ttu-id="3d531-163">如何查看信息提示和工具提示</span><span class="sxs-lookup"><span data-stu-id="3d531-163">How to View Infotip and Tooltip</span></span>](../core/how-to-view-infotip-and-tooltip.md)  
  
## <a name="see-also"></a><span data-ttu-id="3d531-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d531-164">See Also</span></span>  
 [<span data-ttu-id="3d531-165">如何优化链接的显示</span><span class="sxs-lookup"><span data-stu-id="3d531-165">How to Optimize the Display of Links</span></span>](../core/how-to-optimize-the-display-of-links.md)