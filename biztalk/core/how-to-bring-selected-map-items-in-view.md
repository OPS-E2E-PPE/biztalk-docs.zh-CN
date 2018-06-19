---
title: 如何将所选的地图视图中的项目 |Microsoft 文档
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
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005542"
---
# <a name="how-to-bring-selected-map-items-in-view"></a><span data-ttu-id="349d5-102">如何在视图中移动所选的映射项</span><span class="sxs-lookup"><span data-stu-id="349d5-102">How to Bring Selected Map Items in View</span></span>
<span data-ttu-id="349d5-103">使用早期版本的 BizTalk 映射器时，如果映射包含大型架构，则必须手动滚动源架构窗格、网格页和目标架构窗格，以便将全部的相关映射项目引入单个视图中。</span><span class="sxs-lookup"><span data-stu-id="349d5-103">With earlier versions of BizTalk Mapper, if a map comprised big schemas, you had to manually scroll the source schema pane, the grid page, and the target schema pane to bring all the relevant map items into a single view.</span></span> <span data-ttu-id="349d5-104">与 BizTalk Server BizTalk 映射程序，可将所选 functoid/链接的所有相关映射项引入的单一视图自动滚动的网格页。</span><span class="sxs-lookup"><span data-stu-id="349d5-104">The BizTalk Mapper with BizTalk Server allows you to bring all the relevant map items of the selected functoid/link into a single view by automatically scrolling the grid page.</span></span> <span data-ttu-id="349d5-105">本主题提供有关如何执行此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="349d5-105">This topic provides information about how to perform the operation.</span></span>  
  
 <span data-ttu-id="349d5-106">根据您的选择（源架构节点、关系视图中的元素或目标架构节点），BizTalk 映射器以同步方式自动滚动架构视图和关系视图，并显示选定项目的全部关系视图。</span><span class="sxs-lookup"><span data-stu-id="349d5-106">Depending on your selection (a source schema node, an element in the relationship view, or a target schema node), the BizTalk Mapper auto-scrolls the schema views and relationship view in a synchronized fashion, and displays the overall relationship view of the selected item.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="349d5-107">BizTalk 映射器强调全部相关的映射项目后，自动滚动功能才会生效。</span><span class="sxs-lookup"><span data-stu-id="349d5-107">The auto-scroll feature comes into effect after the BizTalk Mapper has emphasized all the relevant map items.</span></span> <span data-ttu-id="349d5-108">换言之，将首先突出显示与所选内容相关的元素，然后 BizTalk 映射器通过自动滚动将相关元素引入视图中。</span><span class="sxs-lookup"><span data-stu-id="349d5-108">In other words, first the elements related to the selection are highlighted, and then the BizTalk Mapper auto-scrolls to bring the related elements into view.</span></span>  
  
 <span data-ttu-id="349d5-109">BizTalk 映射器不会实际移动网格对象。</span><span class="sxs-lookup"><span data-stu-id="349d5-109">The BizTalk Mapper does not actually move the grid objects.</span></span> <span data-ttu-id="349d5-110">当您删除或修改所选内容时，网格对象将返回其各自的位置。</span><span class="sxs-lookup"><span data-stu-id="349d5-110">The grid objects return to their respective locations when you remove or modify the selection.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="349d5-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="349d5-111">Prerequisites</span></span>  
 <span data-ttu-id="349d5-112">此操作要求 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="349d5-112">This operation requires that BizTalk Mapper is running.</span></span>  
  
### <a name="to-bring-the-selected-map-items-in-view"></a><span data-ttu-id="349d5-113">将所选映射项目引入视图中</span><span class="sxs-lookup"><span data-stu-id="349d5-113">To bring the selected map items in view</span></span>  
  
1.  <span data-ttu-id="349d5-114">在映射器实用程序功能区，单击自动滚动图标![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其关闭。</span><span class="sxs-lookup"><span data-stu-id="349d5-114">On the Mapper utility ribbon, click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it OFF.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="349d5-115">![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")切换图标默认情况下的关闭。</span><span class="sxs-lookup"><span data-stu-id="349d5-115">The ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") icon is switched OFF by default.</span></span>  
  
2.  <span data-ttu-id="349d5-116">单击 functoid 或链接后，将突出显示关系中的相关映射项目。</span><span class="sxs-lookup"><span data-stu-id="349d5-116">Click a functoid or a link; the relevant map items in the relationship are emphasized.</span></span>  
  
     <span data-ttu-id="349d5-117">下图以蓝色显示了所选链接。</span><span class="sxs-lookup"><span data-stu-id="349d5-117">The following figure displays the selected link in blue color.</span></span> <span data-ttu-id="349d5-118">依次，BizTalk 映射器以绿色突出显示与所选内容相关的其他映射项目。</span><span class="sxs-lookup"><span data-stu-id="349d5-118">In turn, BizTalk Mapper emphasizes the other map items relevant to the selection, in green color.</span></span> <span data-ttu-id="349d5-119">从图中可以看到，尽管已经突出显示，但所选关系的全部元素并未完全出现在当前视图中。</span><span class="sxs-lookup"><span data-stu-id="349d5-119">From the figure, you can see that all the elements of the selected relationship, though emphasized, are completely not in the current view.</span></span>  
  
     <span data-ttu-id="349d5-120">![链接时自动 &#45; 滚动处于关闭](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span><span class="sxs-lookup"><span data-stu-id="349d5-120">![Links when auto&#45;scrolling is switched off](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")</span></span>  
  
3.  <span data-ttu-id="349d5-121">单击自动滚动图标![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")若要切换到。</span><span class="sxs-lookup"><span data-stu-id="349d5-121">Click the auto-scroll icon ![Auto&#45;scroll icon](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll") to switch it ON.</span></span>  
  
     <span data-ttu-id="349d5-122">BizTalk 映射器将自动滚动，以将所选内容中的全部相关项目引入当前映射视图。</span><span class="sxs-lookup"><span data-stu-id="349d5-122">The BizTalk Mapper automatically scrolls to bring all the relevant items in the selection into the current map view.</span></span>  
  
     <span data-ttu-id="349d5-123">![查看时自动滚动接通](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span><span class="sxs-lookup"><span data-stu-id="349d5-123">![View when autoscrolling is switched on](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="349d5-124">此外，还可以在键盘上按 Ctrl+M、Ctrl+U。</span><span class="sxs-lookup"><span data-stu-id="349d5-124">Alternatively, you can press CTRL+M, CTRL+U from the keyboard.</span></span> <span data-ttu-id="349d5-125">映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="349d5-125">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="349d5-126">See Also</span></span>  
 [<span data-ttu-id="349d5-127">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="349d5-127">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)