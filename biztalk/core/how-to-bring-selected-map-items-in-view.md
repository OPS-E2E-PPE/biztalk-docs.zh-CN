---
title: 如何将选定的映射视图中的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd4a932b00ac2d0a89eb9cfb8f343fd9ab0d4fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342621"
---
# <a name="how-to-bring-selected-map-items-in-view"></a><span data-ttu-id="adf3b-102">如何将视图中选择映射项</span><span class="sxs-lookup"><span data-stu-id="adf3b-102">How to Bring Selected Map Items in View</span></span>
<span data-ttu-id="adf3b-103">与早期版本的 BizTalk 映射器中，如果映射包含大型架构，则必须手动滚动源架构窗格、 网格页中和目标架构窗格才能将所有相关映射项目引入单个视图。</span><span class="sxs-lookup"><span data-stu-id="adf3b-103">With earlier versions of BizTalk Mapper, if a map comprised big schemas, you had to manually scroll the source schema pane, the grid page, and the target schema pane to bring all the relevant map items into a single view.</span></span> <span data-ttu-id="adf3b-104">BizTalk 映射器与 BizTalk Server，可将所选的 functoid/链接的所有相关映射项目引入单个视图通过自动滚动网格页。</span><span class="sxs-lookup"><span data-stu-id="adf3b-104">The BizTalk Mapper with BizTalk Server allows you to bring all the relevant map items of the selected functoid/link into a single view by automatically scrolling the grid page.</span></span> <span data-ttu-id="adf3b-105">本主题提供有关如何执行该操作的信息。</span><span class="sxs-lookup"><span data-stu-id="adf3b-105">This topic provides information about how to perform the operation.</span></span>  
  
 <span data-ttu-id="adf3b-106">根据你的选择 （源架构节点、 关系视图或目标架构节点中的元素），BizTalk 映射器自动滚动架构视图和关系视图，以同步方式，并显示整体的关系的视图选定的项。</span><span class="sxs-lookup"><span data-stu-id="adf3b-106">Depending on your selection (a source schema node, an element in the relationship view, or a target schema node), the BizTalk Mapper auto-scrolls the schema views and relationship view in a synchronized fashion, and displays the overall relationship view of the selected item.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adf3b-107">BizTalk 映射器强调全部相关映射项目后自动滚动功能才会生效。</span><span class="sxs-lookup"><span data-stu-id="adf3b-107">The auto-scroll feature comes into effect after the BizTalk Mapper has emphasized all the relevant map items.</span></span> <span data-ttu-id="adf3b-108">换而言之，首先将突出显示与所选内容相关的元素，，然后 BizTalk 映射器通过自动滚动将相关的元素引入视图。</span><span class="sxs-lookup"><span data-stu-id="adf3b-108">In other words, first the elements related to the selection are highlighted, and then the BizTalk Mapper auto-scrolls to bring the related elements into view.</span></span>  
  
 <span data-ttu-id="adf3b-109">BizTalk 映射器不会实际移动网格对象。</span><span class="sxs-lookup"><span data-stu-id="adf3b-109">The BizTalk Mapper does not actually move the grid objects.</span></span> <span data-ttu-id="adf3b-110">删除或修改所选内容时，网格对象返回到其各自的位置。</span><span class="sxs-lookup"><span data-stu-id="adf3b-110">The grid objects return to their respective locations when you remove or modify the selection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="adf3b-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="adf3b-111">Prerequisites</span></span>  
 <span data-ttu-id="adf3b-112">此操作需要 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="adf3b-112">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-bring-the-selected-map-items-in-view"></a><span data-ttu-id="adf3b-113">若要在视图中将所选的映射项目</span><span class="sxs-lookup"><span data-stu-id="adf3b-113">To bring the selected map items in view</span></span>  
  
1.  <span data-ttu-id="adf3b-114">在映射器实用工具功能区中，单击自动滚动图标![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="adf3b-114">On the Mapper utility ribbon, click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it OFF.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adf3b-115">![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")图标处于打开状态默认情况下关闭。</span><span class="sxs-lookup"><span data-stu-id="adf3b-115">The ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icon is switched OFF by default.</span></span>  
  
2.  <span data-ttu-id="adf3b-116">单击 functoid 或链接;在关系中的相关映射项目将突出显示。</span><span class="sxs-lookup"><span data-stu-id="adf3b-116">Click a functoid or a link; the relevant map items in the relationship are emphasized.</span></span>  
  
     <span data-ttu-id="adf3b-117">下图以蓝色显示所选的链接。</span><span class="sxs-lookup"><span data-stu-id="adf3b-117">The following figure displays the selected link in blue color.</span></span> <span data-ttu-id="adf3b-118">依次，BizTalk 映射器突出显示与所选内容，以绿色表示相关的其他映射项目。</span><span class="sxs-lookup"><span data-stu-id="adf3b-118">In turn, BizTalk Mapper emphasizes the other map items relevant to the selection, in green color.</span></span> <span data-ttu-id="adf3b-119">从图中，可以看到当前视图中完全不是所选的关系，但是强调中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="adf3b-119">From the figure, you can see that all the elements of the selected relationship, though emphasized, are completely not in the current view.</span></span>  
  
     <span data-ttu-id="adf3b-120">![链接时自动&#45;关闭滚动](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span><span class="sxs-lookup"><span data-stu-id="adf3b-120">![Links when auto&#45;scrolling is switched off](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span></span>  
  
3.  <span data-ttu-id="adf3b-121">单击自动滚动图标![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其打开。</span><span class="sxs-lookup"><span data-stu-id="adf3b-121">Click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it ON.</span></span>  
  
     <span data-ttu-id="adf3b-122">BizTalk 映射器自动滚动到当前地图视图选定内容中将所有相关项。</span><span class="sxs-lookup"><span data-stu-id="adf3b-122">The BizTalk Mapper automatically scrolls to bring all the relevant items in the selection into the current map view.</span></span>  
  
     <span data-ttu-id="adf3b-123">![查看打开自动滚动时](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span><span class="sxs-lookup"><span data-stu-id="adf3b-123">![View when autoscrolling is switched on](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adf3b-124">或者，可以按 CTRL + M、 CTRL + U 键盘。</span><span class="sxs-lookup"><span data-stu-id="adf3b-124">Alternatively, you can press CTRL+M, CTRL+U from the keyboard.</span></span> <span data-ttu-id="adf3b-125">映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="adf3b-125">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf3b-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="adf3b-126">See Also</span></span>  
 [<span data-ttu-id="adf3b-127">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="adf3b-127">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)