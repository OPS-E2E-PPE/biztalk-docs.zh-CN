---
title: 如何复制、 剪切和粘贴 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825847e4-87db-4b40-8e5d-5b5b1c79c6de
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53fbd0d8c5a4a72263b6abf0eb3918d130cf53fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340139"
---
# <a name="how-to-copy-cut-and-paste-a-functoid"></a><span data-ttu-id="33bc0-102">如何复制、 剪切和粘贴 Functoid</span><span class="sxs-lookup"><span data-stu-id="33bc0-102">How to Copy, Cut, and Paste a Functoid</span></span>
<span data-ttu-id="33bc0-103">在 BizTalk 映射器中的复制/剪切/粘贴功能使 functoid 可重复使用。</span><span class="sxs-lookup"><span data-stu-id="33bc0-103">The copy/cut/paste feature in the BizTalk Mapper enables the reusability of functoids.</span></span> <span data-ttu-id="33bc0-104">在映射中，可以复制、 剪切和粘贴一个或多个 functoid 从一个网格页到另一个。</span><span class="sxs-lookup"><span data-stu-id="33bc0-104">In a map, you can copy, cut, and paste one or more functoids from one grid page to another.</span></span> <span data-ttu-id="33bc0-105">本主题提供执行这些操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="33bc0-105">This topic provides step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="33bc0-106">当你想要重复使用 functoid 时，可以使用复制/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="33bc0-106">You can use the copy/paste feature when you want to reuse functoids.</span></span> <span data-ttu-id="33bc0-107">并且，当你想要从现有位置删除 functoid 并将其移到新位置，可以使用剪切/粘贴功能。</span><span class="sxs-lookup"><span data-stu-id="33bc0-107">And, when you want to remove a functoid from the existing location and move it to a new location, you can use the cut/paste feature.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="33bc0-108">如果您选择复制 functoid、 functoid、 其标签、 注释和输入的常数，以及占位符索引会复制。</span><span class="sxs-lookup"><span data-stu-id="33bc0-108">When you choose to copy a functoid, the functoid, its label, comments, and the constant-inputs, along with the placeholder indices, are copied.</span></span> <span data-ttu-id="33bc0-109">同样，当您选择剪切 functoid、 functoid、 其标签、 注释，常量输入，以及占位符索引都会被剪切。</span><span class="sxs-lookup"><span data-stu-id="33bc0-109">Similarly, when you choose to cut a functoid, the functoid, its label, comments, constant-inputs, along with the placeholder indices, are cut.</span></span> <span data-ttu-id="33bc0-110">但是，当您粘贴 （在选择剪切） 之后所选内容，只有该 functoid 保留和删除孤立的链接。</span><span class="sxs-lookup"><span data-stu-id="33bc0-110">But, when you paste (after choosing to cut) the selection, only the functoid is retained and the orphaned links are deleted.</span></span> <span data-ttu-id="33bc0-111">标签、 注释、 输入的常数和占位符索引不会保留。</span><span class="sxs-lookup"><span data-stu-id="33bc0-111">The label, comments, constant inputs, and placeholder indices are not retained.</span></span>  
  
 <span data-ttu-id="33bc0-112">如果您只选择 functoid，或者链接到另一个 functoid 或架构节点，只有该 functoid 将剪切或复制，不包括这些链接。</span><span class="sxs-lookup"><span data-stu-id="33bc0-112">If you select only a functoid, which is either linked to another functoid or a schema node, only the functoid will be cut or copied, without the links.</span></span> <span data-ttu-id="33bc0-113">如果剪切 functoid 链接到其他映射中 functoid 或架构节点，会删除指向这个剪切的 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-113">If you cut a functoid that is linked to other functoids in the map or to the schema nodes, the links to the functoid that is cut are deleted.</span></span>  
  
 <span data-ttu-id="33bc0-114">您可以复制/剪切 functoid 从：</span><span class="sxs-lookup"><span data-stu-id="33bc0-114">You can copy/cut functoids from:</span></span>  
  
- <span data-ttu-id="33bc0-115">映射的同一网格页中</span><span class="sxs-lookup"><span data-stu-id="33bc0-115">Within the same grid page of a map</span></span>  
  
- <span data-ttu-id="33bc0-116">到相同的映射中另一个网格页</span><span class="sxs-lookup"><span data-stu-id="33bc0-116">One grid page to the other in the same map</span></span>  
  
- <span data-ttu-id="33bc0-117">到另一个 Visual Studio 的一个实例</span><span class="sxs-lookup"><span data-stu-id="33bc0-117">One instance of Visual Studio to another</span></span>  
  
  <span data-ttu-id="33bc0-118">可以撤消或重做剪切和粘贴操作。</span><span class="sxs-lookup"><span data-stu-id="33bc0-118">You can undo or redo the cut and paste operations.</span></span> <span data-ttu-id="33bc0-119">有关详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="33bc0-119">For more information, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33bc0-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="33bc0-120">Prerequisites</span></span>  
 <span data-ttu-id="33bc0-121">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="33bc0-121">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-copy-and-paste-a-functoid"></a><span data-ttu-id="33bc0-122">若要复制和粘贴 functoid</span><span class="sxs-lookup"><span data-stu-id="33bc0-122">To copy and paste a functoid</span></span>  
  
1.  <span data-ttu-id="33bc0-123">在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。</span><span class="sxs-lookup"><span data-stu-id="33bc0-123">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="33bc0-124">选择你想要复制的 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-124">Select the functoid you want to copy.</span></span> <span data-ttu-id="33bc0-125">若要选择多个 functoid，单击一个 functoid，按住 CTRL 键，再单击其他 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-125">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33bc0-126">"功能区选择"操作可用于选择多个链接和/或 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-126">You can use the “ribbon select” operation to select multiple link(s) and/or functoid(s).</span></span> <span data-ttu-id="33bc0-127">有关详细信息，请参阅[如何选择多个链接和 Functoid](../core/how-to-select-multiple-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="33bc0-127">For more information, see [How to Select Multiple Links and Functoids](../core/how-to-select-multiple-links-and-functoids.md).</span></span>  
  
3.  <span data-ttu-id="33bc0-128">右键单击所选内容，然后依次**复制**。</span><span class="sxs-lookup"><span data-stu-id="33bc0-128">Right-click the selection, and then click **Copy**.</span></span> <span data-ttu-id="33bc0-129">或者，您可以单击**副本**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + C。</span><span class="sxs-lookup"><span data-stu-id="33bc0-129">Alternatively, you can either click **Copy** from the Visual Studio’s **Edit** menu or press CTRL+C on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33bc0-130">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="33bc0-130">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="33bc0-131">将光标置于想要粘贴 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-131">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="33bc0-132">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="33bc0-132">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="33bc0-133">或者，您可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。</span><span class="sxs-lookup"><span data-stu-id="33bc0-133">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="33bc0-134">所选的 functoid 或 functoid 组的副本会显示在新位置。</span><span class="sxs-lookup"><span data-stu-id="33bc0-134">A copy of the selected functoid or group of functoids appears at the new location.</span></span>  
  
### <a name="to-cut-and-paste-a-functoid"></a><span data-ttu-id="33bc0-135">若要剪切和粘贴 functoid</span><span class="sxs-lookup"><span data-stu-id="33bc0-135">To cut and paste a functoid</span></span>  
  
1.  <span data-ttu-id="33bc0-136">在解决方案资源管理器，打开 BizTalk 项目中，，然后双击要打开 BizTalk 映射器中的映射。</span><span class="sxs-lookup"><span data-stu-id="33bc0-136">In Solution Explorer, open the BizTalk project, and then double-click the map to open it in BizTalk Mapper.</span></span>  
  
2.  <span data-ttu-id="33bc0-137">选择你想要剪切的 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-137">Select the functoid you want to cut.</span></span> <span data-ttu-id="33bc0-138">若要选择多个 functoid，单击一个 functoid，按住 CTRL 键，再单击其他 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-138">To select multiple functoids, click one functoid, hold down the CTRL key, and then click the other functoids.</span></span>  
  
3.  <span data-ttu-id="33bc0-139">右键单击所选内容，然后依次**剪切**。</span><span class="sxs-lookup"><span data-stu-id="33bc0-139">Right-click the selection, and then click **Cut**.</span></span> <span data-ttu-id="33bc0-140">或者，您可以单击**剪切**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + X。</span><span class="sxs-lookup"><span data-stu-id="33bc0-140">Alternatively, you can either click **Cut** from the Visual Studio’s **Edit** menu or press CTRL+X on the keyboard.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33bc0-141">键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="33bc0-141">For a list of keyboard shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
4.  <span data-ttu-id="33bc0-142">将光标置于想要粘贴 functoid。</span><span class="sxs-lookup"><span data-stu-id="33bc0-142">Place the cursor where you wish to paste the functoid.</span></span>  
  
5.  <span data-ttu-id="33bc0-143">在网格页上，右键单击，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="33bc0-143">Right-click on the grid page, and then click **Paste**.</span></span> <span data-ttu-id="33bc0-144">或者，您可以单击**粘贴**从 Visual Studio**编辑**菜单或键盘上的按 CTRL + V。</span><span class="sxs-lookup"><span data-stu-id="33bc0-144">Alternatively, you can either click **Paste** from the Visual Studio’s **Edit** menu or press CTRL+V on the keyboard.</span></span> <span data-ttu-id="33bc0-145">所选的 functoid 组从现有位置删除，并出现在新位置。</span><span class="sxs-lookup"><span data-stu-id="33bc0-145">The selected functoid or group of functoids are deleted from the existing location and appear at the new location.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33bc0-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="33bc0-146">See Also</span></span>  
 [<span data-ttu-id="33bc0-147">使用 Functoid 创建更复杂的映射</span><span class="sxs-lookup"><span data-stu-id="33bc0-147">Using Functoids to Create More Complex Mappings</span></span>](../core/using-functoids-to-create-more-complex-mappings.md)