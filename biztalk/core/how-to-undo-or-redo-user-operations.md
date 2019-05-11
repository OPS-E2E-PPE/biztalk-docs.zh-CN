---
title: 如何撤消或重做用户操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1cb3708e-a9c2-4795-aba0-9c6d9635e08c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ef4122e31bae1c3bd0e107b5a5bb8a4c7405e42
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383684"
---
# <a name="how-to-undo-or-redo-user-operations"></a><span data-ttu-id="b27ed-102">如何撤消或重做用户操作</span><span class="sxs-lookup"><span data-stu-id="b27ed-102">How to Undo or Redo User Operations</span></span>
<span data-ttu-id="b27ed-103">有关撤消/重做支持但另一个可用性辅助工具提供的 BizTalk 映射器。</span><span class="sxs-lookup"><span data-stu-id="b27ed-103">The support for undo/redo is yet another usability aid provided by the BizTalk Mapper.</span></span> <span data-ttu-id="b27ed-104">如果您感到不满意的修改进行，或如果您错误地进行更改，可以使用撤消来逐渐回到前面"未处理"状态，并从此处继续。</span><span class="sxs-lookup"><span data-stu-id="b27ed-104">If you are not satisfied with modifications you have made, or if you have made a change by mistake, you can use undo to gradually come back to an earlier "untouched" state, and resume from there.</span></span> <span data-ttu-id="b27ed-105">重做，可重新应用已撤销的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="b27ed-105">Redo allows you to reapply the editing actions that have been undone.</span></span> <span data-ttu-id="b27ed-106">本主题提供有关，您可以撤消/重做操作的信息。</span><span class="sxs-lookup"><span data-stu-id="b27ed-106">This topic provides information about the operations that you can undo/redo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b27ed-107">只有当您已执行至少一个编辑代码图上的操作，您可以撤消操作。</span><span class="sxs-lookup"><span data-stu-id="b27ed-107">You can undo an operation only when you have performed at least one edit operation on the map.</span></span> <span data-ttu-id="b27ed-108">重做是不可用，除非已使用撤消命令。</span><span class="sxs-lookup"><span data-stu-id="b27ed-108">Redo is unavailable unless you have used the undo command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b27ed-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="b27ed-109">Prerequisites</span></span>  
 <span data-ttu-id="b27ed-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="b27ed-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-can-you-undoredo"></a><span data-ttu-id="b27ed-111">什么可以你撤消/重做？</span><span class="sxs-lookup"><span data-stu-id="b27ed-111">What can you undo/redo?</span></span>  
 <span data-ttu-id="b27ed-112">您可以撤消/重做所有编辑操作。</span><span class="sxs-lookup"><span data-stu-id="b27ed-112">You can undo/redo all editing operations.</span></span> <span data-ttu-id="b27ed-113">可以是撤消/重做的操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="b27ed-113">The operations that can be undone/redone are as follows:</span></span>  
  
-   <span data-ttu-id="b27ed-114">剪切/复制/粘贴 functoid 和/或链接</span><span class="sxs-lookup"><span data-stu-id="b27ed-114">Cutting/copying/pasting functoids and/or link</span></span>  
  
     <span data-ttu-id="b27ed-115">无法撤消或重做只是选择并将其复制任意数量的项 (链接 /functoid)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-115">You cannot undo or redo any number of items (links/functoids) by simply selecting and copying them.</span></span> <span data-ttu-id="b27ed-116">复制函数不会更改代码图上的任何内容。</span><span class="sxs-lookup"><span data-stu-id="b27ed-116">Copy function does not change anything on the map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-117">有关如何剪切/复制/粘贴 functoid 的信息，请参阅[如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-117">For information about how to cut/copy/paste a functoid, see [How to Copy, Cut, and Paste a Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span></span> <span data-ttu-id="b27ed-118">有关如何剪切/复制/粘贴 functoid 和链接的详细信息，请参阅[如何复制、 剪切和粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-118">For more information about how to cut/copy/paste functoid and link, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="b27ed-119">将源节点链接到目标节点或从源节点到 functoid、 functoid 到另一个 functoid 或 functoid 到目标节点</span><span class="sxs-lookup"><span data-stu-id="b27ed-119">Linking a source node to a target node, or a source node to a functoid, a functoid to another functoid, or a functoid to a target node</span></span>  
  
-   <span data-ttu-id="b27ed-120">删除 functoid 和/或链接</span><span class="sxs-lookup"><span data-stu-id="b27ed-120">Deleting functoids and/or links</span></span>  
  
-   <span data-ttu-id="b27ed-121">将所选的链接和 functoid 移动到另一个网格页</span><span class="sxs-lookup"><span data-stu-id="b27ed-121">Moving selected links and functoids to another grid page</span></span>  
  
-   <span data-ttu-id="b27ed-122">添加、 移动、 重新排序，或删除网格页</span><span class="sxs-lookup"><span data-stu-id="b27ed-122">Adding, moving, reordering, or deleting grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-123">有关添加的信息，移动、 重新排序，或删除网格页，请参阅[如何重排网格页顺序](../core/how-to-reorder-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-123">For information on adding, moving, reordering, or deleting grid pages, see [How to Reorder Grid Pages](../core/how-to-reorder-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="b27ed-124">创建映射时选择源和目标架构</span><span class="sxs-lookup"><span data-stu-id="b27ed-124">Selecting source and destination schemas while creating a map</span></span>  
  
-   <span data-ttu-id="b27ed-125">替换源/目标架构</span><span class="sxs-lookup"><span data-stu-id="b27ed-125">Replacing source/destination schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-126">有关如何替换源/目标架构的信息，请参阅[如何替换架构](../core/how-to-replace-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-126">For information on how to replace source/destination schema, see [How to Replace Schemas](../core/how-to-replace-schemas.md).</span></span>  
  
-   <span data-ttu-id="b27ed-127">配置输入的参数的 functoid</span><span class="sxs-lookup"><span data-stu-id="b27ed-127">Configuring input parameters for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-128">有关详细信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-128">For more information, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
-   <span data-ttu-id="b27ed-129">设置/编辑链接的标签</span><span class="sxs-lookup"><span data-stu-id="b27ed-129">Setting/editing labels for links</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-130">有关详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-130">For more information, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
-   <span data-ttu-id="b27ed-131">设置/编辑标签和/或 functoid 的注释</span><span class="sxs-lookup"><span data-stu-id="b27ed-131">Setting/editing labels and/or comments for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-132">有关详细信息，请参阅[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-132">For more information, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="b27ed-133">忽略的映射器网格的链接和脚本类型优先级属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="b27ed-133">Ignore Namespaces for Links and Script Type Precedence properties for Mapper grid.</span></span>  
  
-   <span data-ttu-id="b27ed-134">通过从一个节点或 functoid 对其他节点或 functoid 拖动一个链接的终结点替换链接。</span><span class="sxs-lookup"><span data-stu-id="b27ed-134">Replacing a link by dragging one end point of a link from a node or functoid to anther node or functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-135">有关详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-135">For more information, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
-   <span data-ttu-id="b27ed-136">执行在多个修改**配置\<Functoid\> Functoid**对话框中，将被视为单个操作。</span><span class="sxs-lookup"><span data-stu-id="b27ed-136">Performing multiple modifications in the **Configure \<Functoid\> Functoid** dialog box, which is treated as a single operation.</span></span>  
  
-   <span data-ttu-id="b27ed-137">拖动 functoid 和/或映射器网格中的链接。</span><span class="sxs-lookup"><span data-stu-id="b27ed-137">Dragging functoid(s) and/or link(s) within the Mapper grid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b27ed-138">有关详细信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="b27ed-138">For more information, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
## <a name="how-can-you-undoredo-any-operation"></a><span data-ttu-id="b27ed-139">如何可以你撤消/重做的任何操作？</span><span class="sxs-lookup"><span data-stu-id="b27ed-139">How can you undo/redo any operation?</span></span>  
 <span data-ttu-id="b27ed-140">您可以撤消/重做操作中的以下方法之一：</span><span class="sxs-lookup"><span data-stu-id="b27ed-140">You can undo/redo an operation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="b27ed-141">从 Visual Studio**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="b27ed-141">From the Visual Studio’s **Edit** menu.</span></span>  
  
-   <span data-ttu-id="b27ed-142">单击工具栏上的撤消和重做图标。</span><span class="sxs-lookup"><span data-stu-id="b27ed-142">Clicking the undo and redo icons on the toolbar.</span></span>  
  
-   <span data-ttu-id="b27ed-143">按 CTRL + Z 进行撤消，CTRL + Y 进行重做。</span><span class="sxs-lookup"><span data-stu-id="b27ed-143">Pressing CTRL+Z for undo and CTRL+Y for redo.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b27ed-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="b27ed-144">See Also</span></span>  
 [<span data-ttu-id="b27ed-145">使用网格页</span><span class="sxs-lookup"><span data-stu-id="b27ed-145">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)