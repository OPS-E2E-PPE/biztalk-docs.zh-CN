---
title: "如何管理视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4a865d7-b319-4264-a085-15f2155bdb2d
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 553e471826cf4744638e7498fd2bb7d52b2e326a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-views"></a><span data-ttu-id="e445e-102">如何管理视图</span><span class="sxs-lookup"><span data-stu-id="e445e-102">How to Manage Views</span></span>
<span data-ttu-id="e445e-103">在开发 BizTalk 映射的过程中，您可能需要更改源或目标架构树视图的大小，或网格视图的大小。</span><span class="sxs-lookup"><span data-stu-id="e445e-103">In the process of developing BizTalk maps, you may want to change the sizes of the source or destination schema tree views, or the size of the grid view.</span></span> <span data-ttu-id="e445e-104">有时，您可能需要用之前关闭的同一视图打开您的映射。</span><span class="sxs-lookup"><span data-stu-id="e445e-104">Sometimes, you may want to open your map in the same view you had closed earlier.</span></span> <span data-ttu-id="e445e-105">本主题提供有关这些任务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="e445e-105">This topic provides step-by-step instructions for these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e445e-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="e445e-106">Prerequisites</span></span>  
 <span data-ttu-id="e445e-107">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="e445e-107">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-taller-or-shorter"></a><span data-ttu-id="e445e-108">增大或减小架构树视图或网格视图的高度</span><span class="sxs-lookup"><span data-stu-id="e445e-108">To make the schema tree views or the grid view taller or shorter</span></span>  
  
1.  <span data-ttu-id="e445e-109">将鼠标指针移动到主编辑窗口（该窗口在网格视图的左右两侧显示架构树视图）的下边缘，直到光标更改为标准的窗口垂直调整图标。</span><span class="sxs-lookup"><span data-stu-id="e445e-109">Move the mouse pointer to the bottom edge of the main editing window (which displays the schema tree views on either side of the grid view) until the cursor changes to the standard window vertical resizing icon.</span></span>  
  
2.  <span data-ttu-id="e445e-110">单击并按住鼠标左键，然后向上或向下拖动窗口边缘。</span><span class="sxs-lookup"><span data-stu-id="e445e-110">Click and hold the left mouse button, and then drag the window edge either up or down.</span></span>  
  
     <span data-ttu-id="e445e-111">通过垂直调整整个主编辑窗口，您已垂直调整了架构树视图和网格视图的大小。</span><span class="sxs-lookup"><span data-stu-id="e445e-111">You have vertically resized the schema tree views and the grid view by vertically resizing the entire main editing window.</span></span>  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-wider-or-more-narrow"></a><span data-ttu-id="e445e-112">增大或减小架构树视图或网格视图的宽度</span><span class="sxs-lookup"><span data-stu-id="e445e-112">To make the schema tree views or the grid view wider or more narrow</span></span>  
  
1.  <span data-ttu-id="e445e-113">将鼠标指针移动到主编辑窗口中两个窗格分隔符（该分隔符将架构树视图与中间的网格视图分隔开来）中的任一分隔符处，直到光标变为标准的窗口水平调整图标。</span><span class="sxs-lookup"><span data-stu-id="e445e-113">Move the mouse pointer to one of the two pane dividers in the main editing window (which divides the schema tree views from the grid view between them) until the cursor changes to the standard window horizontal resizing icon.</span></span>  
  
2.  <span data-ttu-id="e445e-114">单击并按住鼠标左键，然后向左（更窄）或向右（更宽）拖动窗格边缘。</span><span class="sxs-lookup"><span data-stu-id="e445e-114">Click and hold the left mouse button, and then drag the pane edge either left (narrower) or right (wider).</span></span>  
  
     <span data-ttu-id="e445e-115">通过更改主编辑窗口为每个视图分配的宽度，您已水平调整了其中一个架构树视图，以及网格视图的大小。</span><span class="sxs-lookup"><span data-stu-id="e445e-115">You have horizontally resized one of the schema tree views and the grid view by changing the amount of the main editing window dedicated to each of these views.</span></span>  
  
     <span data-ttu-id="e445e-116">此外，通过水平调整整个主编辑窗口，您还可以同时增大或减小架构树视图和网格视图的宽度。</span><span class="sxs-lookup"><span data-stu-id="e445e-116">Alternatively, you can also make the schema tree views and the grid view wider or narrower by horizontally resizing the entire main editing window.</span></span>  
  
## <a name="remembering-the-current-view-of-mapper"></a><span data-ttu-id="e445e-117">记住映射器的当前视图</span><span class="sxs-lookup"><span data-stu-id="e445e-117">Remembering the current view of Mapper</span></span>  
 <span data-ttu-id="e445e-118">BizTalk 映射器会记住所有设置，如缩放级别、实用工具功能区选项的切换状态，以及当前链接/functoid 的对齐。</span><span class="sxs-lookup"><span data-stu-id="e445e-118">BizTalk Mapper remembers all the settings, such as zoom level, toggle states of utility ribbon options, and current alignment of links/functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e445e-119">如果在 BizTalk 项目或解决方案中有多个映射，则分别记住每个映射的单独详细信息。</span><span class="sxs-lookup"><span data-stu-id="e445e-119">If you have multiple maps in a BizTalk project or solution, individual details of each map are remembered separately.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e445e-120">上一个视图的设置存储在 **\*.suo**文件。</span><span class="sxs-lookup"><span data-stu-id="e445e-120">The settings for previous view are stored in the **\*.suo** file.</span></span> <span data-ttu-id="e445e-121">请确保不要从 Visual Studio 中的项目文件夹删除此文件。</span><span class="sxs-lookup"><span data-stu-id="e445e-121">Ensure you do not delete this file from the project folder in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e445e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e445e-122">See Also</span></span>  
 <span data-ttu-id="e445e-123">[使用 BizTalk 映射程序命令](../core/using-biztalk-mapper-commands.md) </span><span class="sxs-lookup"><span data-stu-id="e445e-123">[Using BizTalk Mapper Commands](../core/using-biztalk-mapper-commands.md) </span></span>  
 <span data-ttu-id="e445e-124">[BizTalk 映射程序键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md) </span><span class="sxs-lookup"><span data-stu-id="e445e-124">[BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md) </span></span>  
 <span data-ttu-id="e445e-125">[如何将视图中选择映射项](../core/how-to-bring-selected-map-items-in-view.md) </span><span class="sxs-lookup"><span data-stu-id="e445e-125">[How to Bring Selected Map Items in View](../core/how-to-bring-selected-map-items-in-view.md) </span></span>  
 [<span data-ttu-id="e445e-126">如何优化架构树视图</span><span class="sxs-lookup"><span data-stu-id="e445e-126">How to Optimize the Schema Tree View</span></span>](../core/how-to-optimize-the-schema-tree-view.md)