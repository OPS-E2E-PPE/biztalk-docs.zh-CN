---
title: 如何优化架构树视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3655e3bdf60aafc243c2d415f70da26224140a67
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384470"
---
# <a name="how-to-optimize-the-schema-tree-view"></a><span data-ttu-id="4da37-102">如何优化架构树视图</span><span class="sxs-lookup"><span data-stu-id="4da37-102">How to Optimize the Schema Tree View</span></span>
<span data-ttu-id="4da37-103">可以使用**关联视图**BizTalk 映射器以优化源和/或目标架构树中。</span><span class="sxs-lookup"><span data-stu-id="4da37-103">You can use the **Relevance View** in BizTalk Mapper to optimize the source and/or target schema trees.</span></span> <span data-ttu-id="4da37-104">本主题提供有关如何执行该操作的说明。</span><span class="sxs-lookup"><span data-stu-id="4da37-104">This topic provides instructions about how to perform the operation.</span></span>  
  
 <span data-ttu-id="4da37-105">关联视图使用同级合并来折叠非相关架构元素，以提供更精简的架构的视图。</span><span class="sxs-lookup"><span data-stu-id="4da37-105">The relevance view uses sibling coalescence to collapse the non-relevant schema elements to provide a more compact view of the schema.</span></span> <span data-ttu-id="4da37-106">这进一步降低滚动并可帮助你专注于使用架构和映射你的要求了。</span><span class="sxs-lookup"><span data-stu-id="4da37-106">This further reduces the need of scrolling and helps you focus on your requirement for using schemas and maps.</span></span>  
  
 <span data-ttu-id="4da37-107">下图显示了关联视图时的架构已关闭。</span><span class="sxs-lookup"><span data-stu-id="4da37-107">The following figure shows a schema when the relevance view is turned OFF.</span></span> <span data-ttu-id="4da37-108">架构窗格显示所有节点，不管节点是否属于任何关系。</span><span class="sxs-lookup"><span data-stu-id="4da37-108">The schema pane displays all nodes, irrespective of whether the nodes are part of any relationship or not.</span></span>  
  
 <span data-ttu-id="4da37-109">![关联视图关闭时的架构](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span><span class="sxs-lookup"><span data-stu-id="4da37-109">![Schema when relevance view is switched off](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span></span>  
  
 <span data-ttu-id="4da37-110">单击![切换到关联视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")打开关联视图映射器实用工具功能区上的图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-110">Click the ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icon on the Mapper utility ribbon to turn the relevance view ON.</span></span> <span data-ttu-id="4da37-111">可以切换到的任何一个或源架构和目标架构中; 关联视图单击源和目标架构各自的图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-111">You can switch to relevance view for any one or both the source schema and the target schema; click the respective icons for source and target schemas.</span></span>  
  
 <span data-ttu-id="4da37-112">当切换到关联视图的架构：</span><span class="sxs-lookup"><span data-stu-id="4da37-112">When you switch to relevance view for a schema:</span></span>  
  
-   <span data-ttu-id="4da37-113">没有为其任何链接的所有记录元素或其子字段元素处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="4da37-113">All the record elements that do not have any links either for them or their child field elements are collapsed.</span></span>  
  
-   <span data-ttu-id="4da37-114">不包含任何链接的所有后续节点都会合并并替换为![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-114">All successive nodes that do not have any links are coalesced and are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span> <span data-ttu-id="4da37-115">BizTalk 映射器查找两个可合并的连续非关联节点的最小值。</span><span class="sxs-lookup"><span data-stu-id="4da37-115">The BizTalk Mapper looks for a minimum of two successive non-relevant nodes that can be coalesced.</span></span> <span data-ttu-id="4da37-116">可以将鼠标移到该图标可以查看合并节点的列表。</span><span class="sxs-lookup"><span data-stu-id="4da37-116">You can move the mouse over the icon to view the list of coalesced nodes.</span></span> <span data-ttu-id="4da37-117">请注意，信息提示将仅列出的前三个合并节点，名称即使有更多合并的节点。</span><span class="sxs-lookup"><span data-stu-id="4da37-117">Note that the infotip will only list the names of the first three coalesced nodes, even if there are more coalesced nodes.</span></span> <span data-ttu-id="4da37-118">可以通过单击查看所有节点![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-118">You can view all the nodes by clicking the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4da37-119">有关信息提示的详细信息，请参阅[如何查看信息提示和工具提示](../core/how-to-view-infotip-and-tooltip.md)。</span><span class="sxs-lookup"><span data-stu-id="4da37-119">For more information about infotip, see [How to View Infotip and Tooltip](../core/how-to-view-infotip-and-tooltip.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4da37-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="4da37-120">Prerequisites</span></span>  
 <span data-ttu-id="4da37-121">此操作需要 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="4da37-121">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-optimize-the-schema-tree-view"></a><span data-ttu-id="4da37-122">若要优化架构树视图</span><span class="sxs-lookup"><span data-stu-id="4da37-122">To optimize the schema tree view</span></span>  
 <span data-ttu-id="4da37-123">在映射器实用工具功能区中，源和/或目标架构的关联视图通过单击来打开各自![切换到关联视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-123">On the Mapper utility ribbon, turn ON the relevance view for source and/or target schemas by clicking the respective ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icons.</span></span> <span data-ttu-id="4da37-124">下图显示了相同的架构关联视图时启用。</span><span class="sxs-lookup"><span data-stu-id="4da37-124">The following figure shows the same schema when the relevance view is turned ON.</span></span> <span data-ttu-id="4da37-125">所有非关联节点替换为![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标以提供更精简的架构的视图。</span><span class="sxs-lookup"><span data-stu-id="4da37-125">All the non-relevant nodes are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon to provide a more compact view of the schema.</span></span>  
  
 <span data-ttu-id="4da37-126">![当关联视图为 ON 时的架构](../core/media/on-schema.gif "On_schema")</span><span class="sxs-lookup"><span data-stu-id="4da37-126">![Schema when relevance view is ON](../core/media/on-schema.gif "On_schema")</span></span>  
  
 <span data-ttu-id="4da37-127">展开合并的节点在源和/或目标架构中，当![合并节点隐藏](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")更改为![合并节点显示](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")图标。</span><span class="sxs-lookup"><span data-stu-id="4da37-127">When you expand the coalesced nodes in source and/or destination schemas, the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") changes to ![Coalesced nodes shown](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence") icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4da37-128">可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 将分别展开或折叠源架构中的树节点。</span><span class="sxs-lookup"><span data-stu-id="4da37-128">You can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in source schema respectively.</span></span> <span data-ttu-id="4da37-129">同样，可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 将分别展开或折叠树节点在目标架构中。</span><span class="sxs-lookup"><span data-stu-id="4da37-129">Similarly, you can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in destination schema respectively.</span></span> <span data-ttu-id="4da37-130">此外可以按 Ctrl + M、 Ctrl + H 或 Ctrl + M、 Ctrl + D 的源或目标分别合并。</span><span class="sxs-lookup"><span data-stu-id="4da37-130">You can also press Ctrl+M, Ctrl+H or Ctrl+M, Ctrl+D for source or target coalescing respectively.</span></span> <span data-ttu-id="4da37-131">映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="4da37-131">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da37-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="4da37-132">See Also</span></span>  
 [<span data-ttu-id="4da37-133">使用 BizTalk 映射器中的增强功能</span><span class="sxs-lookup"><span data-stu-id="4da37-133">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)