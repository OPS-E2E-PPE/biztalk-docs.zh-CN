---
title: "如何优化架构树视图 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab4ad6b5-5bbd-443b-9041-6cddf9d64735
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeeddd0893b80c1c7b37b2d0ee5f9f6cd68849d6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-optimize-the-schema-tree-view"></a><span data-ttu-id="7a993-102">如何优化架构树视图</span><span class="sxs-lookup"><span data-stu-id="7a993-102">How to Optimize the Schema Tree View</span></span>
<span data-ttu-id="7a993-103">你可以使用**相关性视图**BizTalk 映射程序来优化的源和/或目标架构树中。</span><span class="sxs-lookup"><span data-stu-id="7a993-103">You can use the **Relevance View** in BizTalk Mapper to optimize the source and/or target schema trees.</span></span> <span data-ttu-id="7a993-104">本主题提供了有关如何执行该操作的说明。</span><span class="sxs-lookup"><span data-stu-id="7a993-104">This topic provides instructions about how to perform the operation.</span></span>  
  
 <span data-ttu-id="7a993-105">关联视图使用同级合并来折叠非关联架构元素，以提供更全面的架构视图。</span><span class="sxs-lookup"><span data-stu-id="7a993-105">The relevance view uses sibling coalescence to collapse the non-relevant schema elements to provide a more compact view of the schema.</span></span> <span data-ttu-id="7a993-106">这进一步降低了滚动的需求，可帮助您专注于使用架构和映射。</span><span class="sxs-lookup"><span data-stu-id="7a993-106">This further reduces the need of scrolling and helps you focus on your requirement for using schemas and maps.</span></span>  
  
 <span data-ttu-id="7a993-107">下图显示了关联视图处于关闭状态时的架构。</span><span class="sxs-lookup"><span data-stu-id="7a993-107">The following figure shows a schema when the relevance view is turned OFF.</span></span> <span data-ttu-id="7a993-108">该架构窗格显示所有节点，而不考虑这些节点是否属于任何关系。</span><span class="sxs-lookup"><span data-stu-id="7a993-108">The schema pane displays all nodes, irrespective of whether the nodes are part of any relationship or not.</span></span>  
  
 <span data-ttu-id="7a993-109">![架构相关性视图关闭时](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span><span class="sxs-lookup"><span data-stu-id="7a993-109">![Schema when relevance view is switched off](../core/media/off-schema-relevance-view.gif "Off_Schema_Relevance_View")</span></span>  
  
 <span data-ttu-id="7a993-110">单击![切换到相关性视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")开启相关性视图映射器实用程序功能区上的图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-110">Click the ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icon on the Mapper utility ribbon to turn the relevance view ON.</span></span> <span data-ttu-id="7a993-111">您可以切换到源架构和/或目标架构的关联视图，单击源架构和目标架构各自的图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-111">You can switch to relevance view for any one or both the source schema and the target schema; click the respective icons for source and target schemas.</span></span>  
  
 <span data-ttu-id="7a993-112">当切换到一个架构的关联视图时：</span><span class="sxs-lookup"><span data-stu-id="7a993-112">When you switch to relevance view for a schema:</span></span>  
  
-   <span data-ttu-id="7a993-113">所有不包含任何链接的记录元素或其子字段元素都将被折叠。</span><span class="sxs-lookup"><span data-stu-id="7a993-113">All the record elements that do not have any links either for them or their child field elements are collapsed.</span></span>  
  
-   <span data-ttu-id="7a993-114">不具有任何链接的所有后续节点合并和替换为![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-114">All successive nodes that do not have any links are coalesced and are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span> <span data-ttu-id="7a993-115">BizTalk 映射器可最少查找两个可合并的连续非关联节点。</span><span class="sxs-lookup"><span data-stu-id="7a993-115">The BizTalk Mapper looks for a minimum of two successive non-relevant nodes that can be coalesced.</span></span> <span data-ttu-id="7a993-116">您可以将鼠标移至图标上以查看合并节点的列表。</span><span class="sxs-lookup"><span data-stu-id="7a993-116">You can move the mouse over the icon to view the list of coalesced nodes.</span></span> <span data-ttu-id="7a993-117">请注意，信息提示将只能列出头三个合并节点的名称，即使还存在更多的合并节点。</span><span class="sxs-lookup"><span data-stu-id="7a993-117">Note that the infotip will only list the names of the first three coalesced nodes, even if there are more coalesced nodes.</span></span> <span data-ttu-id="7a993-118">你可以通过单击查看所有节点![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-118">You can view all the nodes by clicking the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a993-119">有关信息提示的详细信息，请参阅[视图信息提示和工具提示如何](../core/how-to-view-infotip-and-tooltip.md)。</span><span class="sxs-lookup"><span data-stu-id="7a993-119">For more information about infotip, see [How to View Infotip and Tooltip](../core/how-to-view-infotip-and-tooltip.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7a993-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="7a993-120">Prerequisites</span></span>  
 <span data-ttu-id="7a993-121">此操作要求 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="7a993-121">This operation requires that BizTalk Mapper is running.</span></span>  
  
## <a name="to-optimize-the-schema-tree-view"></a><span data-ttu-id="7a993-122">若要优化架构树视图，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7a993-122">To optimize the schema tree view</span></span>  
 <span data-ttu-id="7a993-123">在映射器实用程序功能区中，打开用于源和/或目标架构的相关性视图上通过单击相应![切换到相关性视图](../core/media/mapper-intellitree.gif "Mapper_IntelliTree")图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-123">On the Mapper utility ribbon, turn ON the relevance view for source and/or target schemas by clicking the respective ![Switch to relevance view](../core/media/mapper-intellitree.gif "Mapper_IntelliTree") icons.</span></span> <span data-ttu-id="7a993-124">下图显示了在关联视图处于打开状态时的相同架构。</span><span class="sxs-lookup"><span data-stu-id="7a993-124">The following figure shows the same schema when the relevance view is turned ON.</span></span> <span data-ttu-id="7a993-125">所有非相关节点替换为![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")图标以提供更紧凑视图的架构。</span><span class="sxs-lookup"><span data-stu-id="7a993-125">All the non-relevant nodes are replaced by the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") icon to provide a more compact view of the schema.</span></span>  
  
 <span data-ttu-id="7a993-126">![当相关性视图为 ON 时的架构](../core/media/on-schema.gif "On_schema")</span><span class="sxs-lookup"><span data-stu-id="7a993-126">![Schema when relevance view is ON](../core/media/on-schema.gif "On_schema")</span></span>  
  
 <span data-ttu-id="7a993-127">当扩展在源和/或目标架构中，合并后的节点![合并隐藏的节点](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On")更改为![合并所示节点](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence")图标。</span><span class="sxs-lookup"><span data-stu-id="7a993-127">When you expand the coalesced nodes in source and/or destination schemas, the ![Coalesced nodes hidden](../core/media/mapper-coalescence-on.gif "Mapper_Coalescence_On") changes to ![Coalesced nodes shown](../core/media/switchoff-mapper-coalesence.jpg "SwitchOff_Mapper_Coalesence") icon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7a993-128">可以按 Ctrl+M、Ctrl+E 或 Ctrl+M、Ctrl+C，分别展开或折叠源架构中的树节点。</span><span class="sxs-lookup"><span data-stu-id="7a993-128">You can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in source schema respectively.</span></span> <span data-ttu-id="7a993-129">同样，你可以按 CTRL + M、 CTRL + E 或 CTRL + M、 CTRL + C 以展开或折叠分别目标架构中的树节点。</span><span class="sxs-lookup"><span data-stu-id="7a993-129">Similarly, you can press CTRL+M, CTRL+E or CTRL+M, CTRL+C to expand or collapse the tree nodes in destination schema respectively.</span></span> <span data-ttu-id="7a993-130">此外可以按 Ctrl + M、 Ctrl + H 或 Ctrl + M、 Ctrl + D 有关源或目标分别合并。</span><span class="sxs-lookup"><span data-stu-id="7a993-130">You can also press Ctrl+M, Ctrl+H or Ctrl+M, Ctrl+D for source or target coalescing respectively.</span></span> <span data-ttu-id="7a993-131">映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="7a993-131">For a list of Mapper keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a993-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a993-132">See Also</span></span>  
 [<span data-ttu-id="7a993-133">在 BizTalk 映射程序中使用增强的功能</span><span class="sxs-lookup"><span data-stu-id="7a993-133">Using Enhanced Features in BizTalk Mapper</span></span>](../core/using-enhanced-features-in-biztalk-mapper.md)