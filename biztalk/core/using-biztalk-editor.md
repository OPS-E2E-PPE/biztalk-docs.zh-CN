---
title: 使用 BizTalk 编辑器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22021272-f028-4db3-ad8a-fb89a5340910
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdb293e6255042a46ecef16855d723c38543310c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287893"
---
# <a name="using-biztalk-editor"></a><span data-ttu-id="c581d-102">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="c581d-102">Using BizTalk Editor</span></span>

## <a name="overview"></a><span data-ttu-id="c581d-103">概述</span><span class="sxs-lookup"><span data-stu-id="c581d-103">Overview</span></span>
<span data-ttu-id="c581d-104">BizTalk 编辑器驻留在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 外壳程序中。</span><span class="sxs-lookup"><span data-stu-id="c581d-104">BizTalk Editor resides within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="c581d-105">某些功能在 BizTalk 编辑器依赖内的现有用户界面元素[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="c581d-105">Some of the functionality within BizTalk Editor relies upon existing user interface elements within the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="c581d-106">例如，使用**文件**，**编辑**，和**视图**菜单就像你那样内的其他开发[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c581d-106">For example, you use the **File**, **Edit**, and **View** menus just as you would for other development within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="c581d-107">有关此通用功能的信息位于**帮助**菜单。</span><span class="sxs-lookup"><span data-stu-id="c581d-107">Information about this common functionality is available from the **Help** menu.</span></span>  
  
 <span data-ttu-id="c581d-108">BizTalk 编辑器变为活动状态，当你在内 BizTalk 项目，打开现有架构 （.xsd 文件） 时，新架构添加到 BizTalk 项目，或当你单击其选项卡，在主架构进行了重新激活[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="c581d-108">BizTalk Editor becomes active when you add a new schema to a BizTalk project, when you open an existing schema (an .xsd file) within a BizTalk project, or when you reactivate a schema by clicking its tab in the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c581d-109">BizTalk 编辑器使用 utf-16 字符编码保存架构文件。</span><span class="sxs-lookup"><span data-stu-id="c581d-109">BizTalk Editor saves schema files using utf-16 character encoding.</span></span>  

## <a name="views"></a><span data-ttu-id="c581d-110">视图</span><span class="sxs-lookup"><span data-stu-id="c581d-110">Views</span></span>  
 <span data-ttu-id="c581d-111">下图显示在 Microsoft 中的各种视图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]外壳程序是 BizTalk 编辑器的一部分。</span><span class="sxs-lookup"><span data-stu-id="c581d-111">The following figure shows the various views within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell that are part of BizTalk Editor.</span></span>  
  
 <span data-ttu-id="c581d-112">![BizTalk 项目不同部分](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span><span class="sxs-lookup"><span data-stu-id="c581d-112">![Different Parts of BizTalk Project](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")</span></span>  
  
 <span data-ttu-id="c581d-113">BizTalk 编辑器包含 Microsoft 中的以下视图[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell 和其关联的对话框：</span><span class="sxs-lookup"><span data-stu-id="c581d-113">BizTalk Editor consists of the following views within the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell and their associated dialog boxes:</span></span>  
  
-   <span data-ttu-id="c581d-114">**架构树。**</span><span class="sxs-lookup"><span data-stu-id="c581d-114">**Schema Tree.**</span></span> <span data-ttu-id="c581d-115">此视图是主要左侧[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="c581d-115">This view is on the left side of the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="c581d-116">通过建立可描述架构所定义消息的结构的树结构，目前可以使用此视图构造架构。</span><span class="sxs-lookup"><span data-stu-id="c581d-116">You actively construct your schema in this view by building up the tree structure that describes the structure of the message that the schema defines.</span></span> <span data-ttu-id="c581d-117">有关 BizTalk 架构架构树视图中的表示方式的详细信息，请参阅[BizTalk 表示形式的架构](../core/biztalk-representation-of-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c581d-117">For more information about how BizTalk schemas are represented in the schema tree view, see [BizTalk Representation of Schemas](../core/biztalk-representation-of-schemas.md).</span></span>  
  
-   <span data-ttu-id="c581d-118">**XSD 视图。**</span><span class="sxs-lookup"><span data-stu-id="c581d-118">**XSD View.**</span></span> <span data-ttu-id="c581d-119">此视图是主要右侧[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="c581d-119">This view is on the right side of the main [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] editing window.</span></span> <span data-ttu-id="c581d-120">它显示了表示架构树视图中要构造的架构的 XML 架构定义 (XSD) 语言结构。</span><span class="sxs-lookup"><span data-stu-id="c581d-120">It shows the XML Schema definition (XSD) language structure that represents the schema you are constructing in the schema tree view.</span></span> <span data-ttu-id="c581d-121">此视图是只读的，其用途是帮助您习惯要创建的架构的 XSD 语法。</span><span class="sxs-lookup"><span data-stu-id="c581d-121">This view is read-only and is provided to help you become accustomed to the XSD syntax of the schema you are creating.</span></span> <span data-ttu-id="c581d-122">根据需要，您可以调整视图拆分器，以便恰好只有 XSD 视图可见。</span><span class="sxs-lookup"><span data-stu-id="c581d-122">If you prefer, you can adjust the view splitter so that the XSD view only barely visible.</span></span>  
  
-   <span data-ttu-id="c581d-123">**解决方案资源管理器。**</span><span class="sxs-lookup"><span data-stu-id="c581d-123">**Solution Explorer.**</span></span> <span data-ttu-id="c581d-124">此视图会显示在右侧[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]shell。</span><span class="sxs-lookup"><span data-stu-id="c581d-124">This view is on the right side of the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell.</span></span> <span data-ttu-id="c581d-125">它显示 BizTalk 项目及其包含的各项。</span><span class="sxs-lookup"><span data-stu-id="c581d-125">It shows the BizTalk project and the various items it contains.</span></span> <span data-ttu-id="c581d-126">使用解决方案资源管理器可以向项目添加新架构和现有架构，并且可以打开已属于该项目的架构。</span><span class="sxs-lookup"><span data-stu-id="c581d-126">Use Solution Explorer to add new and existing schemas to the project, and to open schemas that are already part of the project.</span></span> <span data-ttu-id="c581d-127">例如，若要创建新的架构，右键单击解决方案资源管理器窗口中的 BizTalk 项目，单击**添加**，单击**新项**，然后使用**添加新项**对话框框中进行命名和创建新的架构。</span><span class="sxs-lookup"><span data-stu-id="c581d-127">For example, to create a new schema, right-click the BizTalk project in the Solution Explorer window, click **Add**, click **New Item**, and then use the **Add New Item** dialog box to name and create a new schema.</span></span>  
  
-   [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="c581d-128">  **属性窗口中。**</span><span class="sxs-lookup"><span data-stu-id="c581d-128">  **Properties window.**</span></span> <span data-ttu-id="c581d-129">使用此视图可以检查和设置大多数架构和节点属性。</span><span class="sxs-lookup"><span data-stu-id="c581d-129">You use this view to examine and set most of the schema and node properties.</span></span> <span data-ttu-id="c581d-130">在架构树视图中选择节点时，或在“解决方案资源管理器”窗口中选择架构时，该节点或架构的相应属性将使用标准的 Visual Studio 范例显示在“属性”窗口中。</span><span class="sxs-lookup"><span data-stu-id="c581d-130">When you select a node in the schema tree view, or select a schema in the Solution Explorer window, the corresponding properties of that node or schema are displayed in the Properties window using the standard Visual Studio paradigms.</span></span> <span data-ttu-id="c581d-131">例如，属性将分组为不同的类别，您可以按这些类别或按字母顺序显示属性。</span><span class="sxs-lookup"><span data-stu-id="c581d-131">For example, the properties are grouped into categories, and can be displayed according to these categories or alphabetically.</span></span> <span data-ttu-id="c581d-132">有关不同的不同类型的节点或架构中，选中时可用的属性集的详细信息，请参阅**架构属性引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c581d-132">For detailed information about the different sets of properties that are available when different types of nodes, or the schema, are selected, see the **Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
 <span data-ttu-id="c581d-133">除了这些视图外，你还可以与几个对话框交互。</span><span class="sxs-lookup"><span data-stu-id="c581d-133">In addition to these views, you can interact with several dialog boxes.</span></span> <span data-ttu-id="c581d-134">在编辑诸如集合等复杂属性时，通常会打开这些对话框。</span><span class="sxs-lookup"><span data-stu-id="c581d-134">You usually open these dialog boxes when you are editing a complex property such as a collection.</span></span>  
  
 <span data-ttu-id="c581d-135">本部分提供了有关 BizTalk 编辑器中可用的视图、命令和快捷键的信息。</span><span class="sxs-lookup"><span data-stu-id="c581d-135">This section provides information about the views, commands, and shortcut keys available in BizTalk Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c581d-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c581d-136">Next steps</span></span> 
  
-   [<span data-ttu-id="c581d-137">如何管理架构树视图</span><span class="sxs-lookup"><span data-stu-id="c581d-137">How to Manage the Schema Tree View</span></span>](../core/how-to-manage-the-schema-tree-view.md)  
  
-   [<span data-ttu-id="c581d-138">如何管理 XSD 视图</span><span class="sxs-lookup"><span data-stu-id="c581d-138">How to Manage the XSD View</span></span>](../core/how-to-manage-the-xsd-view.md)  
  
-   [<span data-ttu-id="c581d-139">如何管理属性窗口</span><span class="sxs-lookup"><span data-stu-id="c581d-139">How to Manage the Properties Window</span></span>](../core/how-to-manage-the-properties-window.md)  
  
-   [<span data-ttu-id="c581d-140">如何管理其他 Visual Studio 窗口</span><span class="sxs-lookup"><span data-stu-id="c581d-140">How to Manage Other Visual Studio Windows</span></span>](../core/how-to-manage-other-visual-studio-windows.md)  
  
-   [<span data-ttu-id="c581d-141">使用 BizTalk 编辑器命令</span><span class="sxs-lookup"><span data-stu-id="c581d-141">Using BizTalk Editor Commands</span></span>](../core/using-biztalk-editor-commands.md)  
  
-   [<span data-ttu-id="c581d-142">使用大型架构</span><span class="sxs-lookup"><span data-stu-id="c581d-142">Working with Large Schemas</span></span>](../core/working-with-large-schemas.md)