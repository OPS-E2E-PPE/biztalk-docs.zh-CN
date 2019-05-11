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
ms.openlocfilehash: b7af51d8bf1f2e7686647ccdf286402179d19a0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385651"
---
# <a name="how-to-copy-cut-and-paste-links-and-functoids"></a><span data-ttu-id="f9bb7-102">如何复制、 剪切和粘贴链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="f9bb7-102">How to Copy, Cut, and Paste Links and Functoids</span></span>
<span data-ttu-id="f9bb7-103">在 BizTalk 映射器中的复制/剪切/粘贴功能使关系的可重用性。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of a relationship.</span></span> <span data-ttu-id="f9bb7-104">本主题提供复制、 剪切和粘贴 functoid 和/或链接在映射中的分步说明。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-104">This topic provides step-by-step instructions to copy, cut, and paste functoids and/or links in a map.</span></span>  
  
 <span data-ttu-id="f9bb7-105">当你想要重复使用一组 functoid 和/或链接时，可以使用复制/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-105">You can use the copy/paste feature when you want to reuse a set of functoids and/or links.</span></span> <span data-ttu-id="f9bb7-106">并且，当你想要从现有位置删除所选内容并将其移到新位置，可以使用剪切/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-106">And, when you want to remove the selection from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f9bb7-107">您是否觉得剪切/粘贴功能和移动功能很相似？</span><span class="sxs-lookup"><span data-stu-id="f9bb7-107">Do you feel cut/paste feature and the move feature are similar?</span></span> <span data-ttu-id="f9bb7-108">没有区别。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-108">There is a difference.</span></span> <span data-ttu-id="f9bb7-109">如果选择剪切，只有 functoid 和/或所选内容中的链接是从从源网格页面中删除。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-109">When you select cut, only the functoids and/or links in your selection are removed from the source grid page.</span></span> <span data-ttu-id="f9bb7-110">但是，当你选择移动，所有 functoid 和链接中的关系 （无论所选内容的），以递归方式，从从源网格页面中删除。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-110">But, when you select move, all the functoids and links in the relationship (irrespective of the selection), recursively, are removed from the source grid page.</span></span> <span data-ttu-id="f9bb7-111">有关移动关系的详细信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-111">For more information about moving a relationship, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
 <span data-ttu-id="f9bb7-112">当你复制/剪切一组 functoid 和/或链接时，functoid、 标签、 注释和常数值 （以及正确的占位符） 与关联组会保留。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-112">When you copy/cut a set of functoids and/or links, the functoids, labels, comments, and the constant values (along with the correct place holders) associated with that set are retained.</span></span>  
  
 <span data-ttu-id="f9bb7-113">您可以复制/剪切以下映射项：</span><span class="sxs-lookup"><span data-stu-id="f9bb7-113">You can copy/cut only these map items:</span></span>  
  
- <span data-ttu-id="f9bb7-114">将链接从源到目标架构。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-114">Link from source to target schema.</span></span>  
  
- <span data-ttu-id="f9bb7-115">链接从 functoid 到架构节点，当且仅当及链接还选择了"functoid"。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-115">Link from functoid to schema node, if and only if the “functoid” is also selected along with the link.</span></span>  
  
- <span data-ttu-id="f9bb7-116">链接从 functoid 到 functoid，当且仅当选择这两个 functoid 及链接。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-116">Link from functoid to functoid, if and only if both the functoids are selected along with the link.</span></span>  
  
  <span data-ttu-id="f9bb7-117">您可以复制/剪切 functoid 和/或中的链接：</span><span class="sxs-lookup"><span data-stu-id="f9bb7-117">You can copy/cut functoids and/or links from:</span></span>  
  
- <span data-ttu-id="f9bb7-118">映射的同一网格页中</span><span class="sxs-lookup"><span data-stu-id="f9bb7-118">Within the same grid page of a map</span></span>  
  
- <span data-ttu-id="f9bb7-119">到相同的映射中另一个网格页</span><span class="sxs-lookup"><span data-stu-id="f9bb7-119">One grid page to the other in the same map</span></span>  
  
- <span data-ttu-id="f9bb7-120">一个映射到其他 Visual Studio 的同一实例中</span><span class="sxs-lookup"><span data-stu-id="f9bb7-120">One map to the other in the same instance of Visual Studio</span></span>  
  
- <span data-ttu-id="f9bb7-121">Visual Studio 的不同实例中</span><span class="sxs-lookup"><span data-stu-id="f9bb7-121">Across different instances of Visual Studio</span></span>  
  
  <span data-ttu-id="f9bb7-122">可以撤消或重做剪切和粘贴操作。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-122">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="f9bb7-123">有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-123">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
  <span data-ttu-id="f9bb7-124">除此之外，粘贴链接时必须考虑以下几点：</span><span class="sxs-lookup"><span data-stu-id="f9bb7-124">In addition to this, you must consider the following points while pasting links:</span></span>  
  
- <span data-ttu-id="f9bb7-125">当且仅当当前映射，其中正在粘贴链接，包含源节点，以及其 XPath 与正在粘贴的链接的源和目标节点的 XPath 相同的目标节点才能粘贴源和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-125">A link between the source and target schema can be pasted if and only if the current map, where the link is being pasted, contains a source node as well as a target node whose XPath is identical to the XPath of the source and target nodes for the link being pasted.</span></span>  
  
- <span data-ttu-id="f9bb7-126">当且仅当上述源和目标节点之间没有现有链接，才能粘贴源和目标架构之间的链接。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-126">A link between the source and target schema can be pasted if and only if there is no existing link between the aforesaid source and target nodes.</span></span>  
  
- <span data-ttu-id="f9bb7-127">可以粘贴链接从 functoid 到目标架构，当且仅当存在目标节点，其 XPath 与正在粘贴的链接的目标节点的 XPath 相同。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-127">A link from a functoid to target schema can be pasted if and only if there exists a target node whose XPath is same as the XPath of the target node of the link being pasted.</span></span>  
  
- <span data-ttu-id="f9bb7-128">可以粘贴 functoid 的链接源架构中，当且仅当存在源节点，其 XPath 与正在粘贴的链接的源节点的 XPath 相同。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-128">A link from a source schema to a functoid can be pasted if and only if there exists a source node whose XPath is same as the XPath of the source node of the link being pasted.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f9bb7-129">时，其中一些无法剪切/复制选择多个项 （链接和/或 functoid），然后在执行剪切/复制命令中，Visual Studio 中的状态栏显示一条警告消息"某些所选项目无法剪切/复制。"</span><span class="sxs-lookup"><span data-stu-id="f9bb7-129">When you select multiple items (links and/or functoids) such that some of them cannot be cut/copied, then on executing the cut/copy command, the status bar in Visual Studio displays a warning message “Some of the selected items could not be cut/copied.”</span></span> <span data-ttu-id="f9bb7-130">消息还将显示相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-130">The message also displays relevant details.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f9bb7-131">先决条件</span><span class="sxs-lookup"><span data-stu-id="f9bb7-131">Prerequisites</span></span>  
 <span data-ttu-id="f9bb7-132">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-132">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-relationship"></a><span data-ttu-id="f9bb7-133">若要复制和粘贴关系</span><span class="sxs-lookup"><span data-stu-id="f9bb7-133">To copy and paste a relationship</span></span>  
  
1.  <span data-ttu-id="f9bb7-134">在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-134">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="f9bb7-135">选择 functoid 和/或你想要复制的链接。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-135">Select the functoids and/or links you want to copy.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f9bb7-136">您可以选择通过按住 CTRL 键，然后选择所需的 functoid 和/或链接或通过拖放鼠标链接以形成一个矩形选区。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-136">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9bb7-137">"功能区选择"操作可用于选择多个链接和/或 functoid。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-137">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="f9bb7-138">有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-138">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="f9bb7-139">右键单击所选内容。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-139">Right-click the selection.</span></span> <span data-ttu-id="f9bb7-140">然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-140">and then click **Copy**.</span></span> <span data-ttu-id="f9bb7-141">或者，也可以在键盘上按 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-141">Alternatively, you can press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9bb7-142">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-142">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="f9bb7-143">将光标置于想要粘贴所选内容。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-143">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="f9bb7-144">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-144">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="f9bb7-145">或者，可以选择，并在键盘上按 CTRL + V。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-145">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="f9bb7-146">所选内容的副本会显示在新位置。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-146">A copy of the selection appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-relationship"></a><span data-ttu-id="f9bb7-147">若要剪切和粘贴关系</span><span class="sxs-lookup"><span data-stu-id="f9bb7-147">To cut and paste a relationship</span></span>  
  
1.  <span data-ttu-id="f9bb7-148">在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-148">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="f9bb7-149">选择 functoid 和/或你想要剪切的链接。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-149">Select the functoids and/or links you want to cut.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="f9bb7-150">您可以选择通过按住 CTRL 键，然后选择所需的 functoid 和/或链接或通过拖放鼠标链接以形成一个矩形选区。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-150">You can select either by holding down the CTRL key, and then selecting the desired functoids and/or links or by dragging and dropping the mouse across the links to form a rectangular selection.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9bb7-151">"功能区选择"操作可用于选择多个链接和/或 functoid。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-151">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="f9bb7-152">有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-152">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="f9bb7-153">右键单击所选内容，然后依次**剪切**。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-153">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="f9bb7-154">此外，您可以在键盘上按 CTRL + X。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-154">Alternatively, you can press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9bb7-155">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-155">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="f9bb7-156">将光标置于想要粘贴所选内容。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-156">Place the cursor where you wish to paste the selection.</span></span>  
  
5.  <span data-ttu-id="f9bb7-157">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-157">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="f9bb7-158">或者，可以选择，并在键盘上按 CTRL + V。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-158">Alternatively, you can select and press CTRL+V on the keyboard.</span></span> <span data-ttu-id="f9bb7-159">所选内容从现有位置删除并显示在新位置。</span><span class="sxs-lookup"><span data-stu-id="f9bb7-159">The selection is deleted from the existing location and appears at the new location.</span></span>