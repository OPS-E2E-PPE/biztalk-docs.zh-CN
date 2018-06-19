---
title: 如何撤消或重做用户操作 |Microsoft 文档
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
ms.openlocfilehash: 8358fc1624346b90d98fd1f1707dd2bfb02446dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973395"
---
# <a name="how-to-undo-or-redo-user-operations"></a><span data-ttu-id="dd5d8-102">如何撤消或重做用户操作</span><span class="sxs-lookup"><span data-stu-id="dd5d8-102">How to Undo or Redo User Operations</span></span>
<span data-ttu-id="dd5d8-103">撤消/重做的支持，而另一个可用性帮助提供通过 BizTalk 映射程序。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-103">The support for undo/redo is yet another usability aid provided by the BizTalk Mapper.</span></span> <span data-ttu-id="dd5d8-104">如果您对所做的更改不满意或者执行了误操作，可以使用撤消功能来返回到之前的“未处理”状态，并从此处继续。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-104">If you are not satisfied with modifications you have made, or if you have made a change by mistake, you can use undo to gradually come back to an earlier "untouched" state, and resume from there.</span></span> <span data-ttu-id="dd5d8-105">重做，可重新应用已撤消的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-105">Redo allows you to reapply the editing actions that have been undone.</span></span> <span data-ttu-id="dd5d8-106">本主题提供有关操作的您可以撤消/重做的信息。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-106">This topic provides information about the operations that you can undo/redo.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dd5d8-107">只有当您执行完至少一个编辑代码图上的操作，则可以撤消操作。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-107">You can undo an operation only when you have performed at least one edit operation on the map.</span></span> <span data-ttu-id="dd5d8-108">重做是不可用，除非你已使用撤消命令。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-108">Redo is unavailable unless you have used the undo command.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd5d8-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="dd5d8-109">Prerequisites</span></span>  
 <span data-ttu-id="dd5d8-110">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-110">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="what-can-you-undoredo"></a><span data-ttu-id="dd5d8-111">新增功能可以你撤消/重做？</span><span class="sxs-lookup"><span data-stu-id="dd5d8-111">What can you undo/redo?</span></span>  
 <span data-ttu-id="dd5d8-112">你可以撤消/重做所有的编辑操作。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-112">You can undo/redo all editing operations.</span></span> <span data-ttu-id="dd5d8-113">可以撤消/重做的操作如下所示：</span><span class="sxs-lookup"><span data-stu-id="dd5d8-113">The operations that can be undone/redone are as follows:</span></span>  
  
-   <span data-ttu-id="dd5d8-114">剪切/复制/粘贴 functoid 和/或链接</span><span class="sxs-lookup"><span data-stu-id="dd5d8-114">Cutting/copying/pasting functoids and/or link</span></span>  
  
     <span data-ttu-id="dd5d8-115">您无法撤消操作或重做通过简单地选择并将其复制的任意数量的项 (链接/functoid)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-115">You cannot undo or redo any number of items (links/functoids) by simply selecting and copying them.</span></span> <span data-ttu-id="dd5d8-116">复制功能不会更改在地图上的任何内容。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-116">Copy function does not change anything on the map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-117">有关如何对剪切/复制/粘贴 functoid 的信息，请参阅[如何复制、 剪切和粘贴 Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-117">For information about how to cut/copy/paste a functoid, see [How to Copy, Cut, and Paste a Functoid](../core/how-to-copy-cut-and-paste-a-functoid.md).</span></span> <span data-ttu-id="dd5d8-118">有关如何剪切/复制/粘贴 functoid 和链接的详细信息，请参阅[如何复制、 剪切、 粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-118">For more information about how to cut/copy/paste functoid and link, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-119">将源节点链接到目标节点上或到 functoid、 与另一个 functoid functoid 或到目标节点 functoid 源节点</span><span class="sxs-lookup"><span data-stu-id="dd5d8-119">Linking a source node to a target node, or a source node to a functoid, a functoid to another functoid, or a functoid to a target node</span></span>  
  
-   <span data-ttu-id="dd5d8-120">删除 functoid 和/或链接</span><span class="sxs-lookup"><span data-stu-id="dd5d8-120">Deleting functoids and/or links</span></span>  
  
-   <span data-ttu-id="dd5d8-121">将所选的链接和 functoid 移动到另一个网格页</span><span class="sxs-lookup"><span data-stu-id="dd5d8-121">Moving selected links and functoids to another grid page</span></span>  
  
-   <span data-ttu-id="dd5d8-122">添加、 移动、 重新排序，或删除网格页</span><span class="sxs-lookup"><span data-stu-id="dd5d8-122">Adding, moving, reordering, or deleting grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-123">移动、 重新排序，或删除网格页将添加的信息，请参阅[如何重新排序网格页](../core/how-to-reorder-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-123">For information on adding, moving, reordering, or deleting grid pages, see [How to Reorder Grid Pages](../core/how-to-reorder-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-124">在创建地图时选择源和目标架构</span><span class="sxs-lookup"><span data-stu-id="dd5d8-124">Selecting source and destination schemas while creating a map</span></span>  
  
-   <span data-ttu-id="dd5d8-125">替换源/目标架构</span><span class="sxs-lookup"><span data-stu-id="dd5d8-125">Replacing source/destination schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-126">有关如何替换源/目标架构的信息，请参阅[如何替换架构](../core/how-to-replace-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-126">For information on how to replace source/destination schema, see [How to Replace Schemas](../core/how-to-replace-schemas.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-127">配置 functoid 的输入的参数</span><span class="sxs-lookup"><span data-stu-id="dd5d8-127">Configuring input parameters for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-128">有关详细信息，请参阅[如何配置 Functoid 输入参数](../core/how-to-configure-functoid-input-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-128">For more information, see [How to Configure Functoid Input Parameters](../core/how-to-configure-functoid-input-parameters.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-129">链接的/编辑设置的标签</span><span class="sxs-lookup"><span data-stu-id="dd5d8-129">Setting/editing labels for links</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-130">有关详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-130">For more information, see [How to Label a Link](../core/how-to-label-a-link.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-131">设置/编辑 functoid 的标签和/或注释</span><span class="sxs-lookup"><span data-stu-id="dd5d8-131">Setting/editing labels and/or comments for functoids</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-132">有关详细信息，请参阅[如何标记和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-132">For more information, see [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-133">忽略链接和脚本类型优先级映射器网格的属性的命名空间。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-133">Ignore Namespaces for Links and Script Type Precedence properties for Mapper grid.</span></span>  
  
-   <span data-ttu-id="dd5d8-134">通过将链接的一个终结点中的节点或 functoid 到另一种节点或 functoid 替换链接。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-134">Replacing a link by dragging one end point of a link from a node or functoid to anther node or functoid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-135">有关详细信息，请参阅[如何创建链接](../core/how-to-create-links.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-135">For more information, see [How to Create Links](../core/how-to-create-links.md).</span></span>  
  
-   <span data-ttu-id="dd5d8-136">执行中的多个修改**配置\<Functoid\> Functoid**对话框中，将被视为单个操作。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-136">Performing multiple modifications in the **Configure \<Functoid\> Functoid** dialog box, which is treated as a single operation.</span></span>  
  
-   <span data-ttu-id="dd5d8-137">拖动 functoid(s) 和/或映射器网格中的链接。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-137">Dragging functoid(s) and/or link(s) within the Mapper grid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dd5d8-138">有关详细信息，请参阅[如何移动关系网格页面之间](../core/how-to-move-a-relationship-between-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-138">For more information, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
## <a name="how-can-you-undoredo-any-operation"></a><span data-ttu-id="dd5d8-139">如何可以你撤消/重做的任何操作？</span><span class="sxs-lookup"><span data-stu-id="dd5d8-139">How can you undo/redo any operation?</span></span>  
 <span data-ttu-id="dd5d8-140">你可以撤消/重做操作通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="dd5d8-140">You can undo/redo an operation in one of the following ways:</span></span>  
  
-   <span data-ttu-id="dd5d8-141">从 Visual Studio**编辑**菜单。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-141">From the Visual Studio’s **Edit** menu.</span></span>  
  
-   <span data-ttu-id="dd5d8-142">单击工具栏上的撤消和重做图标。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-142">Clicking the undo and redo icons on the toolbar.</span></span>  
  
-   <span data-ttu-id="dd5d8-143">按 CTRL + Z 表示撤消和 CTRL + Y 重做的。</span><span class="sxs-lookup"><span data-stu-id="dd5d8-143">Pressing CTRL+Z for undo and CTRL+Y for redo.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd5d8-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd5d8-144">See Also</span></span>  
 [<span data-ttu-id="dd5d8-145">使用网格页</span><span class="sxs-lookup"><span data-stu-id="dd5d8-145">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)