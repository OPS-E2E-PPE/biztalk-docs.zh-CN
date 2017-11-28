---
title: "键盘快捷方式所特有的过程区域 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba60b23c6c8719789e8de6903dbb538fa5088b08
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a><span data-ttu-id="e0b78-102">过程区域特有的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="e0b78-102">Keyboard Shortcuts Specific to the Process Area</span></span>
<span data-ttu-id="e0b78-103">下表对流程区域中可用的键盘导航进行了说明，该区域是用于定义业务流程处理流程的设计图面的中心区域：</span><span class="sxs-lookup"><span data-stu-id="e0b78-103">The following table describes the keyboard navigation available in the Process Area, the central area of the design surface used to define the process flow of the orchestration.</span></span>  
  
|<span data-ttu-id="e0b78-104">Key</span><span class="sxs-lookup"><span data-stu-id="e0b78-104">Key</span></span>|<span data-ttu-id="e0b78-105">效果</span><span class="sxs-lookup"><span data-stu-id="e0b78-105">Effect</span></span>|  
|---------|------------|  
|<span data-ttu-id="e0b78-106">向下键</span><span class="sxs-lookup"><span data-stu-id="e0b78-106">DOWN ARROW</span></span>|<span data-ttu-id="e0b78-107">将选择内容移至下方的下一条连接线或下一个形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-107">Moves the selection to the next connecting line or shape below.</span></span> <span data-ttu-id="e0b78-108">如果该形状连接到下方的多个分支（与判定形状的情况类似），则选择内容将移至最左侧分支中的第一个形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-108">If the shape is connected to several branches below (as in the case of a Decide shape), the selection moves to the first shape in the leftmost branch.</span></span><br /><br /> <span data-ttu-id="e0b78-109">如果选择内容位于业务流程的结束形状上，则按此键不起作用，因为其下方没有其他任何形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-109">If selection is on the End shape for the orchestration, pressing this key has no effect, because there are no more shapes below it.</span></span>|  
|<span data-ttu-id="e0b78-110">向上键</span><span class="sxs-lookup"><span data-stu-id="e0b78-110">UP ARROW</span></span>|<span data-ttu-id="e0b78-111">将选择内容移至上方的上一条连接线或上一个形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-111">Moves the selection to the next connecting line or shape above.</span></span> <span data-ttu-id="e0b78-112">如果该形状连接到上方的多个分支，则选择内容将移至最左侧分支上的最后一个形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-112">If the shape is connected to several branches above, selection moves to the last shape on the leftmost branch.</span></span><br /><br /> <span data-ttu-id="e0b78-113">按下此键没有时生效**启动**选择形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-113">Pressing this key has no effect when the **Start** shape is selected.</span></span>|  
|<span data-ttu-id="e0b78-114">向左键</span><span class="sxs-lookup"><span data-stu-id="e0b78-114">LEFT ARROW</span></span>|<span data-ttu-id="e0b78-115">如果选择内容位于发送形状或接收形状上，并且该形状连接到某端口：</span><span class="sxs-lookup"><span data-stu-id="e0b78-115">If the selection is on a Send or Receive shape and the shape is connected to a port:</span></span><br /><br /> <span data-ttu-id="e0b78-116">-如果形状具有通向左端口图面中的端口的端口连接器，焦点和所选内容将移动到形状的端口连接器中。</span><span class="sxs-lookup"><span data-stu-id="e0b78-116">-   If the shape has a port connector leading to a port in the Left Port Surface, focus and selection shift to the port connector of the shape.</span></span><br /><span data-ttu-id="e0b78-117">-如果形状具有通向右端口图面中的端口的端口连接器，按此密钥不起作用。</span><span class="sxs-lookup"><span data-stu-id="e0b78-117">-   If the shape has a port connector leading to a port in the Right Port Surface, pressing this key has no effect.</span></span><br /><span data-ttu-id="e0b78-118">-如果形状不具有的任何端口连接器，导航，则与任何其他形状相同。</span><span class="sxs-lookup"><span data-stu-id="e0b78-118">-   If the shape has no port connector, navigation is the same as with any other shape.</span></span><br /><br /> <span data-ttu-id="e0b78-119">对于其他形状（或未连接到端口的发送形状或接收形状）：</span><span class="sxs-lookup"><span data-stu-id="e0b78-119">For other shapes (or Send or Receive shapes not connected to a port):</span></span><br /><br /> <span data-ttu-id="e0b78-120">-如果分支存在形状在其上的当前分支左侧的分支中, 进行选择后，所选内容移到最接近的形状上向左分支。</span><span class="sxs-lookup"><span data-stu-id="e0b78-120">-   If the selection is in a branch, and a branch exists with shapes on it to the left of the current branch, the selection moves to the nearest shape on the branch to the left.</span></span><br /><span data-ttu-id="e0b78-121">-密钥不起作用业务流程中的其他任何位置。</span><span class="sxs-lookup"><span data-stu-id="e0b78-121">-   The key has no effect anywhere else in the orchestration.</span></span>|  
|<span data-ttu-id="e0b78-122">向右键</span><span class="sxs-lookup"><span data-stu-id="e0b78-122">RIGHT ARROW</span></span>|<span data-ttu-id="e0b78-123">与向左键相同，只是方向相反。</span><span class="sxs-lookup"><span data-stu-id="e0b78-123">Same as the LEFT ARROW key, but in the opposite direction.</span></span>|  
|<span data-ttu-id="e0b78-124">Home</span><span class="sxs-lookup"><span data-stu-id="e0b78-124">HOME</span></span>|<span data-ttu-id="e0b78-125">选择内容将移至从业务流程的开始形状引出的连接线。</span><span class="sxs-lookup"><span data-stu-id="e0b78-125">Selection changes to the connector that leads from the Start shape of the orchestration.</span></span>|  
|<span data-ttu-id="e0b78-126">END</span><span class="sxs-lookup"><span data-stu-id="e0b78-126">END</span></span>|<span data-ttu-id="e0b78-127">选择内容将移至通向业务流程的结束形状中的连接线。</span><span class="sxs-lookup"><span data-stu-id="e0b78-127">Selection changes to the connector that leads into the End shape of the orchestration.</span></span>|  
|<span data-ttu-id="e0b78-128">Num Lock + -</span><span class="sxs-lookup"><span data-stu-id="e0b78-128">NUM LOCK + -</span></span>|<span data-ttu-id="e0b78-129">折叠选定的复杂形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-129">Collapses the selected complex shape.</span></span>|  
|<span data-ttu-id="e0b78-130">Num Lock + +</span><span class="sxs-lookup"><span data-stu-id="e0b78-130">NUM LOCK + +</span></span>|<span data-ttu-id="e0b78-131">展开选定的复杂形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-131">Expands the selected complex shape.</span></span>|  
|<span data-ttu-id="e0b78-132">Num Lock + *</span><span class="sxs-lookup"><span data-stu-id="e0b78-132">NUM LOCK + *</span></span>|<span data-ttu-id="e0b78-133">展开选定的复杂形状，以及其包含的所有子复杂形状。</span><span class="sxs-lookup"><span data-stu-id="e0b78-133">Expands the selected complex shape, plus any child complex shapes it may have.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e0b78-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0b78-134">See Also</span></span>  
 [<span data-ttu-id="e0b78-135">业务流程设计器键盘快捷键</span><span class="sxs-lookup"><span data-stu-id="e0b78-135">Orchestration Designer Keyboard Shortcuts</span></span>](../core/orchestration-designer-keyboard-shortcuts.md)