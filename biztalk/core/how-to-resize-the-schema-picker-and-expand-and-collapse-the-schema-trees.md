---
title: "如何调整大小架构选取器，以及展开和折叠架构树 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972be8ca5f412c39e1eb6fa2c81ccd9a21e65a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a><span data-ttu-id="dfd5c-102">如何调整大小架构选取器，以及展开和折叠架构树</span><span class="sxs-lookup"><span data-stu-id="dfd5c-102">How to resize the schema picker, and expand and collapse the schema trees</span></span>
<span data-ttu-id="dfd5c-103">开发 BizTalk 映射时，可能需要展开和折叠源架构树及目标架构树，以显示或隐藏各 schema 节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-103">When developing BizTalk maps, you are likely to need to expand and collapse the source and destination schema trees to expose or to hide the various schema nodes.</span></span> <span data-ttu-id="dfd5c-104">本主题提供了分步说明，若要调整大小架构选取器，并可展开和折叠架构树。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-104">This topic provides step-by-step instructions to resize the schema picker, and to expand and collapse the schema tree.</span></span>  

## <a name="resize-the-schema-picker"></a><span data-ttu-id="dfd5c-105">调整大小架构选取器</span><span class="sxs-lookup"><span data-stu-id="dfd5c-105">Resize the schema picker</span></span>

<span data-ttu-id="dfd5c-106">在创建地图时，你可以添加一个源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-106">When you create a map, you add a source schema, and a destination schema.</span></span> <span data-ttu-id="dfd5c-107">当你添加或替换架构时，BizTalk 类型选取器窗口将打开，并且你选择您的架构。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-107">When you add or replace a schema, the BizTalk Type Picker window opens, and you select your schema.</span></span> 

<span data-ttu-id="dfd5c-108">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，则可以调整此类型选取器窗口。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize this Type Picker window.</span></span> <span data-ttu-id="dfd5c-109">此功能允许你查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-109">This feature allows you to see the full name of your schema.</span></span>

1. <span data-ttu-id="dfd5c-110">在映射中，选择**打开目标架构**，或**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-110">In your map, select **Open Destination Schema**, or **Open Source Schema**.</span></span>
2. <span data-ttu-id="dfd5c-111">在**BizTalk 类型选取器**窗口中，拖动右下角来增加或减少的窗口大小。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-111">In the **BizTalk Type Picker** window, drag the bottom-right corner to increase or decrease the window size.</span></span>
  
## <a name="expand-all-or-part-of-a-schema-tree"></a><span data-ttu-id="dfd5c-112">展开所有或部分架构树</span><span class="sxs-lookup"><span data-stu-id="dfd5c-112">Expand all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="dfd5c-113">选择希望完全展开其下级架构树的节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-113">Select the node under which you want to completely expand the schema tree.</span></span>  
  
     <span data-ttu-id="dfd5c-114">所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-114">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="dfd5c-115">上**BizTalk**菜单上，或者在该节点的快捷菜单，单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-115">On the **BizTalk** menu, or on the shortcut menu for that node, click **Expand Tree Node**.</span></span> <span data-ttu-id="dfd5c-116">此时，所选节点的所有下级节点均将完全展开。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-116">All nodes below the selected node are completely expanded.</span></span>  
  
     <span data-ttu-id="dfd5c-117">如果已完全展开所选节点下面的架构树，**展开树节点**菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-117">If the schema tree below the selected node is already completely expanded, the **Expand Tree Node** menu item is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfd5c-118">此外，还可以按 Ctrl+M、E 来展开架构树节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-118">Alternatively you can press CTRL+M, E to expand the schema tree nodes.</span></span> <span data-ttu-id="dfd5c-119">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-119">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfd5c-120">在大型和复杂架构中，当你单击**展开树节点**包含复杂类型的节点，架构中的某些节点中可能会保留折叠状态。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-120">In a large and complex schema, when you click **Expand Tree Node** on a node that contains complex types, some nodes in the schema may remain in the collapsed state.</span></span> <span data-ttu-id="dfd5c-121">其原因在于，递归进程只展开当前视图中出现的第一个给定复杂类型。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-121">This is because the recursive process expands only the first occurrence of a given complex type.</span></span> <span data-ttu-id="dfd5c-122">您必须手动展开之后出现的同一类型。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-122">You must manually expand later occurrences of the same type.</span></span> <span data-ttu-id="dfd5c-123">设计此行为是为了优化在复杂的大型架构中展开节点时的性能。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-123">This behavior is designed to optimize performance when expanding nodes in large and complex schemas.</span></span>  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a><span data-ttu-id="dfd5c-124">折叠所有或部分架构树</span><span class="sxs-lookup"><span data-stu-id="dfd5c-124">Collapse all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="dfd5c-125">选择希望完全折叠其下级架构树的节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-125">Select the node under which you want to completely collapse the schema tree.</span></span>  
  
     <span data-ttu-id="dfd5c-126">所选节点必须是旁边有加号 (+) 或减号 (-) 图标的节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-126">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="dfd5c-127">上**BizTalk**菜单上，或者在该节点的快捷菜单，单击**折叠树节点**。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-127">On the **BizTalk** menu, or on the shortcut menu for that node, click **Collapse Tree Node**.</span></span>  
  
     <span data-ttu-id="dfd5c-128">此时，所选节点的所有下级节点均将完全折叠。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-128">All nodes below the selected node are completely collapsed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dfd5c-129">此外，还可以按 Ctrl+M、C 来折叠架构树节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-129">Alternatively you can press CTRL+M, C to collapse the schema tree nodes.</span></span> <span data-ttu-id="dfd5c-130">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="dfd5c-131">如果所选节点下面的架构树已处于折叠状态，**折叠树节点**菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-131">If the schema tree below the selected node is already collapsed, the **Collapse Tree Node** menu item is disabled.</span></span>  
  
 <span data-ttu-id="dfd5c-132">此操作不会记忆所选节点的各个下级节点的展开和折叠设置。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-132">This operation will not remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="dfd5c-133">重新展开折叠的节点时，以前的设置会丢失，您必须按节点逐级展开该节点的下级架构树，或将其完全展开。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-133">When you re-expand the collapsed node, previous settings are lost, and you must expand the schema tree below that point node-by-node, or expand it entirely.</span></span>  
  
### <a name="expand-a-node"></a><span data-ttu-id="dfd5c-134">展开节点</span><span class="sxs-lookup"><span data-stu-id="dfd5c-134">Expand a node</span></span>
  
-   <span data-ttu-id="dfd5c-135">单击要展开的节点旁边的加号 (+) 图标。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-135">Click the plus (+) icon next to the node you want to expand.</span></span>  
  
 <span data-ttu-id="dfd5c-136">展开所选的节点。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-136">The selected node is expanded.</span></span> <span data-ttu-id="dfd5c-137">及其子代节点是展开还是折叠取决于所选的节点已折叠的方式和其以前的展开和折叠设置。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-137">Whether or not its descendent nodes are expanded or collapsed depends on how the selected node was collapsed and their previous expand and collapse settings.</span></span>  
  
### <a name="collapse-a-node"></a><span data-ttu-id="dfd5c-138">折叠节点</span><span class="sxs-lookup"><span data-stu-id="dfd5c-138">Collapse a node</span></span>
  
-   <span data-ttu-id="dfd5c-139">单击要折叠的节点旁边的减号 (-) 图标。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-139">Click the minus (-) icon next to the node you want to collapse.</span></span>  
  
 <span data-ttu-id="dfd5c-140">所选的节点处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-140">The selected node is collapsed.</span></span>  
  
 <span data-ttu-id="dfd5c-141">此操作将记住单个展开和折叠的所选节点下的节点的设置。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-141">This operation will remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="dfd5c-142">通过使用加号 (+) 图标重新展开折叠的节点时，各个下级节点以前的设置不会丢失，该节点的下级架构树将恢复为以前的状态。</span><span class="sxs-lookup"><span data-stu-id="dfd5c-142">When you re-expand the collapsed node by using the plus (+) icon, the previous individual settings are not lost, and the schema tree below that point returns to its previous state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfd5c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dfd5c-143">See Also</span></span>  
 [<span data-ttu-id="dfd5c-144">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="dfd5c-144">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)