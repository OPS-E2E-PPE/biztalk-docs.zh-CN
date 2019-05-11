---
title: 如何调整架构选取器，并展开和折叠架构树 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 267ea17d-54fe-4031-a044-719606489f24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5027933c7ea34b1f886746d0f1ddb313a5752f9f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384200"
---
# <a name="how-to-resize-the-schema-picker-and-expand-and-collapse-the-schema-trees"></a><span data-ttu-id="7a100-102">如何调整架构选取器，并展开和折叠架构树</span><span class="sxs-lookup"><span data-stu-id="7a100-102">How to resize the schema picker, and expand and collapse the schema trees</span></span>
<span data-ttu-id="7a100-103">在开发 BizTalk 映射时，您很可能需要展开和折叠源和目标架构树以显示或隐藏各 schema 节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-103">When developing BizTalk maps, you are likely to need to expand and collapse the source and destination schema trees to expose or to hide the various schema nodes.</span></span> <span data-ttu-id="7a100-104">本主题提供分步说明来调整架构选取器，并可展开和折叠架构树。</span><span class="sxs-lookup"><span data-stu-id="7a100-104">This topic provides step-by-step instructions to resize the schema picker, and to expand and collapse the schema tree.</span></span>  

## <a name="resize-the-schema-picker"></a><span data-ttu-id="7a100-105">调整架构选取器大小</span><span class="sxs-lookup"><span data-stu-id="7a100-105">Resize the schema picker</span></span>

<span data-ttu-id="7a100-106">在创建映射时，添加源架构和目标架构。</span><span class="sxs-lookup"><span data-stu-id="7a100-106">When you create a map, you add a source schema, and a destination schema.</span></span> <span data-ttu-id="7a100-107">当添加或替换架构时，此时会打开 BizTalk 类型选取器窗口中，并选择您的架构。</span><span class="sxs-lookup"><span data-stu-id="7a100-107">When you add or replace a schema, the BizTalk Type Picker window opens, and you select your schema.</span></span> 

<span data-ttu-id="7a100-108">**从开始[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]** ，可以调整此类型选择器窗口的大小。</span><span class="sxs-lookup"><span data-stu-id="7a100-108">**Starting with [!INCLUDE[bts2016_md](../includes/bts2016-md.md)]**, you can resize this Type Picker window.</span></span> <span data-ttu-id="7a100-109">此功能，可查看您的架构的完整名称。</span><span class="sxs-lookup"><span data-stu-id="7a100-109">This feature allows you to see the full name of your schema.</span></span>

1. <span data-ttu-id="7a100-110">在映射中，选择**打开目标架构**，或**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="7a100-110">In your map, select **Open Destination Schema**, or **Open Source Schema**.</span></span>
2. <span data-ttu-id="7a100-111">在中**BizTalk 类型选取器**窗口中，拖动右下角以增加或减少的窗口大小。</span><span class="sxs-lookup"><span data-stu-id="7a100-111">In the **BizTalk Type Picker** window, drag the bottom-right corner to increase or decrease the window size.</span></span>
  
## <a name="expand-all-or-part-of-a-schema-tree"></a><span data-ttu-id="7a100-112">展开所有或部分架构树</span><span class="sxs-lookup"><span data-stu-id="7a100-112">Expand all or part of a schema tree</span></span>  
  
1.  <span data-ttu-id="7a100-113">选择要在其下以完全展开架构树的节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-113">Select the node under which you want to completely expand the schema tree.</span></span>  
  
     <span data-ttu-id="7a100-114">所选的节点必须是节点带有加号 （+） 或减号 （-） 图标旁边。</span><span class="sxs-lookup"><span data-stu-id="7a100-114">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2.  <span data-ttu-id="7a100-115">上**BizTalk**菜单中，或在该节点的快捷菜单，单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="7a100-115">On the **BizTalk** menu, or on the shortcut menu for that node, click **Expand Tree Node**.</span></span> <span data-ttu-id="7a100-116">下面所选节点的所有节点均将完全都展开。</span><span class="sxs-lookup"><span data-stu-id="7a100-116">All nodes below the selected node are completely expanded.</span></span>  
  
     <span data-ttu-id="7a100-117">如果所选节点的下级架构树已经完全展开，**展开树节点**菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="7a100-117">If the schema tree below the selected node is already completely expanded, the **Expand Tree Node** menu item is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a100-118">或者，也可以按 CTRL + M、 E 来展开架构树节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-118">Alternatively you can press CTRL+M, E to expand the schema tree nodes.</span></span> <span data-ttu-id="7a100-119">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="7a100-119">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7a100-120">在大型和复杂架构中，单击时**展开树节点**上包含复杂类型的节点，该架构中的某些节点可能仍会保持折叠状态。</span><span class="sxs-lookup"><span data-stu-id="7a100-120">In a large and complex schema, when you click **Expand Tree Node** on a node that contains complex types, some nodes in the schema may remain in the collapsed state.</span></span> <span data-ttu-id="7a100-121">这是因为递归过程扩展仅一个给定复杂类型的第一个匹配项。</span><span class="sxs-lookup"><span data-stu-id="7a100-121">This is because the recursive process expands only the first occurrence of a given complex type.</span></span> <span data-ttu-id="7a100-122">您必须手动展开之后出现相同的类型。</span><span class="sxs-lookup"><span data-stu-id="7a100-122">You must manually expand later occurrences of the same type.</span></span> <span data-ttu-id="7a100-123">此行为用于大型和复杂的架构中展开节点时优化性能。</span><span class="sxs-lookup"><span data-stu-id="7a100-123">This behavior is designed to optimize performance when expanding nodes in large and complex schemas.</span></span>  
  
## <a name="collapse-all-or-part-of-a-schema-tree"></a><span data-ttu-id="7a100-124">折叠所有或部分架构树</span><span class="sxs-lookup"><span data-stu-id="7a100-124">Collapse all or part of a schema tree</span></span>  
  
1. <span data-ttu-id="7a100-125">选择要在其下完全折叠架构树的节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-125">Select the node under which you want to completely collapse the schema tree.</span></span>  
  
    <span data-ttu-id="7a100-126">所选的节点必须是节点带有加号 （+） 或减号 （-） 图标旁边。</span><span class="sxs-lookup"><span data-stu-id="7a100-126">The selected node must be a node with a plus (+) or minus (-) icon next to it.</span></span>  
  
2. <span data-ttu-id="7a100-127">上**BizTalk**菜单中，或在该节点的快捷菜单，单击**折叠树节点**。</span><span class="sxs-lookup"><span data-stu-id="7a100-127">On the **BizTalk** menu, or on the shortcut menu for that node, click **Collapse Tree Node**.</span></span>  
  
    <span data-ttu-id="7a100-128">下面所选节点的所有节点均将完全都折叠。</span><span class="sxs-lookup"><span data-stu-id="7a100-128">All nodes below the selected node are completely collapsed.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="7a100-129">或者，也可以按 CTRL + M、 C 来折叠架构树节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-129">Alternatively you can press CTRL+M, C to collapse the schema tree nodes.</span></span> <span data-ttu-id="7a100-130">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="7a100-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
    <span data-ttu-id="7a100-131">如果所选节点的下级架构树已经完全折叠，**折叠树节点**菜单项被禁用。</span><span class="sxs-lookup"><span data-stu-id="7a100-131">If the schema tree below the selected node is already collapsed, the **Collapse Tree Node** menu item is disabled.</span></span>  
  
   <span data-ttu-id="7a100-132">此操作不会记住单个展开和折叠所选节点的下级节点的设置。</span><span class="sxs-lookup"><span data-stu-id="7a100-132">This operation will not remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="7a100-133">重新展开折叠的节点，以前的设置都将丢失，且必须扩展的下级架构树时点节点的节点或其完全展开。</span><span class="sxs-lookup"><span data-stu-id="7a100-133">When you re-expand the collapsed node, previous settings are lost, and you must expand the schema tree below that point node-by-node, or expand it entirely.</span></span>  
  
### <a name="expand-a-node"></a><span data-ttu-id="7a100-134">展开某一节点</span><span class="sxs-lookup"><span data-stu-id="7a100-134">Expand a node</span></span>
  
- <span data-ttu-id="7a100-135">单击加号 （+） 您想要扩展的节点旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="7a100-135">Click the plus (+) icon next to the node you want to expand.</span></span>  
  
  <span data-ttu-id="7a100-136">展开所选的节点。</span><span class="sxs-lookup"><span data-stu-id="7a100-136">The selected node is expanded.</span></span> <span data-ttu-id="7a100-137">及其子代节点是展开还是折叠取决于所选的节点的折叠方式以及其以前的展开和折叠设置。</span><span class="sxs-lookup"><span data-stu-id="7a100-137">Whether or not its descendent nodes are expanded or collapsed depends on how the selected node was collapsed and their previous expand and collapse settings.</span></span>  
  
### <a name="collapse-a-node"></a><span data-ttu-id="7a100-138">折叠节点</span><span class="sxs-lookup"><span data-stu-id="7a100-138">Collapse a node</span></span>
  
- <span data-ttu-id="7a100-139">单击减号 （-） 想要折叠的节点旁边的图标。</span><span class="sxs-lookup"><span data-stu-id="7a100-139">Click the minus (-) icon next to the node you want to collapse.</span></span>  
  
  <span data-ttu-id="7a100-140">所选的节点处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="7a100-140">The selected node is collapsed.</span></span>  
  
  <span data-ttu-id="7a100-141">此操作将记住单个展开和折叠所选节点的下级节点的设置。</span><span class="sxs-lookup"><span data-stu-id="7a100-141">This operation will remember the individual expand and collapse settings of the nodes below the selected node.</span></span> <span data-ttu-id="7a100-142">当您重新展开折叠的节点通过使用加号 （+） 图标，以前的各个设置不会丢失，和下级架构树将恢复为以前的状态。</span><span class="sxs-lookup"><span data-stu-id="7a100-142">When you re-expand the collapsed node by using the plus (+) icon, the previous individual settings are not lost, and the schema tree below that point returns to its previous state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a100-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="7a100-143">See Also</span></span>  
 [<span data-ttu-id="7a100-144">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="7a100-144">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)