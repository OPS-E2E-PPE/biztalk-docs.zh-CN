---
title: 如何管理视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a865d7-b319-4264-a085-15f2155bdb2d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d68fcb7518a73d18974b15cb9328baa2c74f83a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384616"
---
# <a name="how-to-manage-views"></a><span data-ttu-id="2315b-102">如何管理视图</span><span class="sxs-lookup"><span data-stu-id="2315b-102">How to Manage Views</span></span>
<span data-ttu-id="2315b-103">在开发 BizTalk 映射，过程中您可能想要更改源或目标架构树视图的大小或网格视图的大小。</span><span class="sxs-lookup"><span data-stu-id="2315b-103">In the process of developing BizTalk maps, you may want to change the sizes of the source or destination schema tree views, or the size of the grid view.</span></span> <span data-ttu-id="2315b-104">有时，你可能想要在之前关闭的同一视图中打开您的映射。</span><span class="sxs-lookup"><span data-stu-id="2315b-104">Sometimes, you may want to open your map in the same view you had closed earlier.</span></span> <span data-ttu-id="2315b-105">本主题提供有关这些任务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="2315b-105">This topic provides step-by-step instructions for these tasks.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2315b-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="2315b-106">Prerequisites</span></span>  
 <span data-ttu-id="2315b-107">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="2315b-107">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-taller-or-shorter"></a><span data-ttu-id="2315b-108">若要使架构树视图或更高或较短的网格视图</span><span class="sxs-lookup"><span data-stu-id="2315b-108">To make the schema tree views or the grid view taller or shorter</span></span>  
  
1.  <span data-ttu-id="2315b-109">将鼠标指针移动到主编辑窗口 （显示在网格视图的任何一侧上的架构树视图） 的下边缘中，直到光标更改为标准的窗口垂直调整图标。</span><span class="sxs-lookup"><span data-stu-id="2315b-109">Move the mouse pointer to the bottom edge of the main editing window (which displays the schema tree views on either side of the grid view) until the cursor changes to the standard window vertical resizing icon.</span></span>  
  
2.  <span data-ttu-id="2315b-110">单击并按住鼠标左键，然后向上或向下拖动窗口边缘。</span><span class="sxs-lookup"><span data-stu-id="2315b-110">Click and hold the left mouse button, and then drag the window edge either up or down.</span></span>  
  
     <span data-ttu-id="2315b-111">您已通过垂直调整整个主编辑窗口垂直调整架构树视图和网格视图。</span><span class="sxs-lookup"><span data-stu-id="2315b-111">You have vertically resized the schema tree views and the grid view by vertically resizing the entire main editing window.</span></span>  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-wider-or-more-narrow"></a><span data-ttu-id="2315b-112">若要在架构树视图或网格视图更宽或更窄的</span><span class="sxs-lookup"><span data-stu-id="2315b-112">To make the schema tree views or the grid view wider or more narrow</span></span>  
  
1.  <span data-ttu-id="2315b-113">将鼠标指针移动到主编辑窗口 （该分隔符将架构树视图与它们之间的网格视图） 中的两个窗格分隔条之一中，直到光标更改为标准的窗口水平调整图标。</span><span class="sxs-lookup"><span data-stu-id="2315b-113">Move the mouse pointer to one of the two pane dividers in the main editing window (which divides the schema tree views from the grid view between them) until the cursor changes to the standard window horizontal resizing icon.</span></span>  
  
2.  <span data-ttu-id="2315b-114">单击并按住鼠标左键，然后拖动窗格边缘向左 （更窄） 或向右 （更宽）。</span><span class="sxs-lookup"><span data-stu-id="2315b-114">Click and hold the left mouse button, and then drag the pane edge either left (narrower) or right (wider).</span></span>  
  
     <span data-ttu-id="2315b-115">通过您已水平调整架构树视图和网格视图的一个更改的专用主编辑窗口为每个视图。</span><span class="sxs-lookup"><span data-stu-id="2315b-115">You have horizontally resized one of the schema tree views and the grid view by changing the amount of the main editing window dedicated to each of these views.</span></span>  
  
     <span data-ttu-id="2315b-116">或者，您还可以在架构树视图和网格视图更宽或窄通过水平调整整个主编辑窗口。</span><span class="sxs-lookup"><span data-stu-id="2315b-116">Alternatively, you can also make the schema tree views and the grid view wider or narrower by horizontally resizing the entire main editing window.</span></span>  
  
## <a name="remembering-the-current-view-of-mapper"></a><span data-ttu-id="2315b-117">记住映射器的当前视图</span><span class="sxs-lookup"><span data-stu-id="2315b-117">Remembering the current view of Mapper</span></span>  
 <span data-ttu-id="2315b-118">BizTalk 映射器会记住所有设置的缩放级别，如都切换状态的实用工具功能区选项和当前链接 /functoid 的对齐。</span><span class="sxs-lookup"><span data-stu-id="2315b-118">BizTalk Mapper remembers all the settings, such as zoom level, toggle states of utility ribbon options, and current alignment of links/functoids.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2315b-119">如果有多个映射的 BizTalk 项目或解决方案中，分别记住每个映射的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2315b-119">If you have multiple maps in a BizTalk project or solution, individual details of each map are remembered separately.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="2315b-120">上一个视图的设置存储在 **\*.suo**文件。</span><span class="sxs-lookup"><span data-stu-id="2315b-120">The settings for previous view are stored in the **\*.suo** file.</span></span> <span data-ttu-id="2315b-121">请确保从 Visual Studio 中的项目文件夹不删除此文件。</span><span class="sxs-lookup"><span data-stu-id="2315b-121">Ensure you do not delete this file from the project folder in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2315b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="2315b-122">See Also</span></span>  
 <span data-ttu-id="2315b-123">[使用 BizTalk 映射器命令](../core/using-biztalk-mapper-commands.md) </span><span class="sxs-lookup"><span data-stu-id="2315b-123">[Using BizTalk Mapper Commands](../core/using-biztalk-mapper-commands.md) </span></span>  
 <span data-ttu-id="2315b-124">[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md) </span><span class="sxs-lookup"><span data-stu-id="2315b-124">[BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md) </span></span>  
 <span data-ttu-id="2315b-125">[如何将视图中选择映射项](../core/how-to-bring-selected-map-items-in-view.md) </span><span class="sxs-lookup"><span data-stu-id="2315b-125">[How to Bring Selected Map Items in View](../core/how-to-bring-selected-map-items-in-view.md) </span></span>  
 [<span data-ttu-id="2315b-126">如何优化架构树视图</span><span class="sxs-lookup"><span data-stu-id="2315b-126">How to Optimize the Schema Tree View</span></span>](../core/how-to-optimize-the-schema-tree-view.md)