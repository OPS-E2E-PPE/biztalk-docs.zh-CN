---
title: 如何复制、 剪切和粘贴链接和 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80b4792a-5ff6-4603-96cd-b3d3d530c12f
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dcce057f4c3e04eb4974ccd7f8833e2dab8e580
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016036"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a><span data-ttu-id="e3652-102">如何复制、剪切和粘贴链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="e3652-102">How to Copy, Cut, and Paste Links and Functoids</span></span>
<span data-ttu-id="e3652-103">BizTalk 映射器中的复制/剪切/粘贴功能使关系可重复使用。</span><span class="sxs-lookup"><span data-stu-id="e3652-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of a relationship.</span></span> <span data-ttu-id="e3652-104">本主题提供了在映射中复制、剪切和粘贴 functoid 和/或链接的分步说明。</span><span class="sxs-lookup"><span data-stu-id="e3652-104">This topic provides step-by-step instructions to copy, cut, and paste functoids and/or links in a map.</span></span>  
  
 <span data-ttu-id="e3652-105">如果希望重复使用一组 functoid 和/或链接，可以使用复制/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="e3652-105">You can use the copy/paste feature when you want to reuse a set of functoids and/or links.</span></span> <span data-ttu-id="e3652-106">如果希望从现有位置删除所选内容并将其移动到新位置，也可以使用剪切/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="e3652-106">And, when you want to remove the selection from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3652-107">您是否觉得剪切/粘贴功能和移动功能很相似？</span><span class="sxs-lookup"><span data-stu-id="e3652-107">Do you feel cut/paste feature and the move feature are similar?</span></span> <span data-ttu-id="e3652-108">这两者之间只有一点区别。</span><span class="sxs-lookup"><span data-stu-id="e3652-108">There is a difference.</span></span> <span data-ttu-id="e3652-109">如果选择剪切，则所选内容中只有 functoid 和/或链接会从源网格页面中删除。</span><span class="sxs-lookup"><span data-stu-id="e3652-109">When you select cut, only the functoids and/or links in your selection are removed from the source grid page.</span></span> <span data-ttu-id="e3652-110">但如果选择移动，则关系（无论是否为所选内容）中的所有 functoid 和链接都会以递归方式从源网格页面中删除。</span><span class="sxs-lookup"><span data-stu-id="e3652-110">But, when you select move, all the functoids and links in the relationship (irrespective of the selection), recursively, are removed from the source grid page.</span></span> <span data-ttu-id="e3652-111">有关移动关系的详细信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-111">For more information about moving a relationship, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
 <span data-ttu-id="e3652-112">当你复制/剪切一组 functoid 和/或链接时，functoid、 标签、 注释和常数值 （以及正确的占位符） 与关联组会保留。</span><span class="sxs-lookup"><span data-stu-id="e3652-112">When you copy/cut a set of functoids and/or links, the functoids, labels, comments, and the constant values (along with the correct place holders) associated with that set are retained.</span></span>  
  
 <span data-ttu-id="e3652-113">您只能复制/剪切以下映射项：</span><span class="sxs-lookup"><span data-stu-id="e3652-113">You can copy/cut only these map items:</span></span>  
  
- <span data-ttu-id="e3652-114">从源到目标架构的链接。</span><span class="sxs-lookup"><span data-stu-id="e3652-114">Link from source to target schema.</span></span>  
  
- <span data-ttu-id="e3652-115">从 functoid 到架构节点的链接（仅在同时选择了“functoid”及链接的情况下）。</span><span class="sxs-lookup"><span data-stu-id="e3652-115">Link from functoid to schema node, if and only if the “functoid” is also selected along with the link.</span></span>  
  
- <span data-ttu-id="e3652-116">从 functoid 到 functoid 的链接（仅在同时选择了这两个 functoid 及链接的情况下）。</span><span class="sxs-lookup"><span data-stu-id="e3652-116">Link from functoid to functoid, if and only if both the functoids are selected along with the link.</span></span>  
  
  <span data-ttu-id="e3652-117">您可以从以下位置复制/剪切 functoid 和/或链接：</span><span class="sxs-lookup"><span data-stu-id="e3652-117">You can copy/cut functoids and/or links from:</span></span>  
  
- <span data-ttu-id="e3652-118">在映射的同一网格页面中</span><span class="sxs-lookup"><span data-stu-id="e3652-118">Within the same grid page of a map</span></span>  
  
- <span data-ttu-id="e3652-119">在同一映射中一个网格页面到另一个网格页面</span><span class="sxs-lookup"><span data-stu-id="e3652-119">One grid page to the other in the same map</span></span>  
  
- <span data-ttu-id="e3652-120">在同一 Visual Studio 实例中一个映射到另一个映射</span><span class="sxs-lookup"><span data-stu-id="e3652-120">One map to the other in the same instance of Visual Studio</span></span>  
  
- <span data-ttu-id="e3652-121">在 Visual Studio 的不同实例之间</span><span class="sxs-lookup"><span data-stu-id="e3652-121">Across different instances of Visual Studio</span></span>  
  
  <span data-ttu-id="e3652-122">可以撤消或重做剪切和粘贴操作。</span><span class="sxs-lookup"><span data-stu-id="e3652-122">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="e3652-123">有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-123">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
  <span data-ttu-id="e3652-124">此外，在粘贴链接时，您还必须考虑以下几点：</span><span class="sxs-lookup"><span data-stu-id="e3652-124">In addition to this, you must consider the following points while pasting links:</span></span>  
  
- <span data-ttu-id="e3652-125">仅当以下情况下才能粘贴源架构和目标架构之间的链接：正在粘贴链接的当前映射包含源节点和目标节点，其 XPath 与正在粘贴的链接的源节点和目标节点的 XPath 相同。</span><span class="sxs-lookup"><span data-stu-id="e3652-125">A link between the source and target schema can be pasted if and only if the current map, where the link is being pasted, contains a source node as well as a target node whose XPath is identical to the XPath of the source and target nodes for the link being pasted.</span></span>  
  
- <span data-ttu-id="e3652-126">仅当上述源节点和目标节点之间没有链接的情况下，才能粘贴源架构和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="e3652-126">A link between the source and target schema can be pasted if and only if there is no existing link between the aforesaid source and target nodes.</span></span>  
  
- <span data-ttu-id="e3652-127">仅当以下情况下才能将链接从 functoid 粘贴到目标架构：存在一个目标节点，其 XPath 与正在粘贴的链接的目标节点的 XPath 相同。</span><span class="sxs-lookup"><span data-stu-id="e3652-127">A link from a functoid to target schema can be pasted if and only if there exists a target node whose XPath is same as the XPath of the target node of the link being pasted.</span></span>  
  
- <span data-ttu-id="e3652-128">仅当以下情况下才能将链接从源架构粘贴到 functoid：存在一个源节点，其 XPath 与正在粘贴的链接的源节点的 XPath 相同。</span><span class="sxs-lookup"><span data-stu-id="e3652-128">A link from a source schema to a functoid can be pasted if and only if there exists a source node whose XPath is same as the XPath of the source node of the link being pasted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e3652-129">选择多个项目（链接和/或 functoid）时，如果其中某些项目无法剪切/复制，则在执行剪切/复制命令时，Visual Studio 中的状态栏将显示一条警告消息：“某些所选项目无法剪切/复制”。</span><span class="sxs-lookup"><span data-stu-id="e3652-129">When you select multiple items (links and/or functoids) such that some of them cannot be cut/copied, then on executing the cut/copy command, the status bar in Visual Studio displays a warning message “Some of the selected items could not be cut/copied.”</span></span> <span data-ttu-id="e3652-130">消息还将显示相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="e3652-130">The message also displays relevant details.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e3652-131">必要條件</span><span class="sxs-lookup"><span data-stu-id="e3652-131">Prerequisites</span></span>  
 <span data-ttu-id="e3652-132">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="e3652-132">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-relationship"></a><span data-ttu-id="e3652-133">复制和粘贴关系</span><span class="sxs-lookup"><span data-stu-id="e3652-133">To copy and paste a relationship</span></span>  
  
1.  <span data-ttu-id="e3652-134">在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。</span><span class="sxs-lookup"><span data-stu-id="e3652-134">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="e3652-135">选择您要复制的 functoid 和/或链接。</span><span class="sxs-lookup"><span data-stu-id="e3652-135">Select the functoids and/or links you want to copy.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e3652-136">可以通过以下方式进行选择：按下 Ctrl 键，然后选择所需的 functoid 和/或链接，或者拖放鼠标框住链接以形成一个矩形选区。</span><span class="sxs-lookup"><span data-stu-id="e3652-136">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3652-137">可以使用“功能区选择”操作选择多个链接和/或 functoid。</span><span class="sxs-lookup"><span data-stu-id="e3652-137">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="e3652-138">有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-138">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="e3652-139">右键单击所选内容。</span><span class="sxs-lookup"><span data-stu-id="e3652-139">Right-click the selection.</span></span> <span data-ttu-id="e3652-140">然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="e3652-140">and then click **Copy**.</span></span> <span data-ttu-id="e3652-141">也可以在键盘上按 Ctrl+C。</span><span class="sxs-lookup"><span data-stu-id="e3652-141">Alternatively, you can press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3652-142">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-142">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="e3652-143">将光标放在要粘贴所选内容的地方。</span><span class="sxs-lookup"><span data-stu-id="e3652-143">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="e3652-144">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="e3652-144">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="e3652-145">也可以选择并按键盘上的 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="e3652-145">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="e3652-146">所选内容的副本会显示在新位置。</span><span class="sxs-lookup"><span data-stu-id="e3652-146">A copy of the selection appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-relationship"></a><span data-ttu-id="e3652-147">剪切和粘贴关系</span><span class="sxs-lookup"><span data-stu-id="e3652-147">To cut and paste a relationship</span></span>  
  
1.  <span data-ttu-id="e3652-148">在解决方案资源管理器中，打开 BizTalk 项目，然后双击映射，将其在 BizTalk 映射器中打开。</span><span class="sxs-lookup"><span data-stu-id="e3652-148">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="e3652-149">选择您要剪切的 functoid 和/或链接。</span><span class="sxs-lookup"><span data-stu-id="e3652-149">Select the functoids and/or links you want to cut.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e3652-150">可以通过以下方式进行选择：按下 Ctrl 键，然后选择所需的 functoid 和/或链接，或者拖放鼠标框住链接以形成一个矩形选区。</span><span class="sxs-lookup"><span data-stu-id="e3652-150">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3652-151">可以使用“功能区选择”操作选择多个链接和/或 functoid。</span><span class="sxs-lookup"><span data-stu-id="e3652-151">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="e3652-152">有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-152">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="e3652-153">右键单击所选内容，然后依次**剪切**。</span><span class="sxs-lookup"><span data-stu-id="e3652-153">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="e3652-154">也可以在键盘上按 Ctrl+X。</span><span class="sxs-lookup"><span data-stu-id="e3652-154">Alternatively, you can press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e3652-155">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="e3652-155">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="e3652-156">将光标放在要粘贴所选内容的地方。</span><span class="sxs-lookup"><span data-stu-id="e3652-156">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="e3652-157">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="e3652-157">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="e3652-158">也可以选择并按键盘上的 Ctrl+V。</span><span class="sxs-lookup"><span data-stu-id="e3652-158">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="e3652-159">所选内容将从现有位置中删除，并显示在新位置中。</span><span class="sxs-lookup"><span data-stu-id="e3652-159">The selection is deleted from the existing location and appears at the new location.</span></span>