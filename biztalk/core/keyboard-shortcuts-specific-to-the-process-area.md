---
title: 键盘快捷方式特定于流程区域 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- keyboard shortcuts, Orchestration Designer
- Orchestration Designer, keyboard shortcuts
ms.assetid: d993d341-99f2-4788-b1f3-6a8b911e5278
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc59da751ee8acb68ff4d38f42b08020ae94b66
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329464"
---
# <a name="keyboard-shortcuts-specific-to-the-process-area"></a><span data-ttu-id="5a268-102">过程区域专用的键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="5a268-102">Keyboard Shortcuts Specific to the Process Area</span></span>
<span data-ttu-id="5a268-103">下表描述了在流程区域，用于定义的处理流程的业务流程设计图面中心区域中可用的键盘导航。</span><span class="sxs-lookup"><span data-stu-id="5a268-103">The following table describes the keyboard navigation available in the Process Area, the central area of the design surface used to define the process flow of the orchestration.</span></span>  
  
|<span data-ttu-id="5a268-104">Key</span><span class="sxs-lookup"><span data-stu-id="5a268-104">Key</span></span>|<span data-ttu-id="5a268-105">效果</span><span class="sxs-lookup"><span data-stu-id="5a268-105">Effect</span></span>|  
|---------|------------|  
|<span data-ttu-id="5a268-106">向下键</span><span class="sxs-lookup"><span data-stu-id="5a268-106">DOWN ARROW</span></span>|<span data-ttu-id="5a268-107">将所选内容移动到一条连接线或形状下面。</span><span class="sxs-lookup"><span data-stu-id="5a268-107">Moves the selection to the next connecting line or shape below.</span></span> <span data-ttu-id="5a268-108">如果该形状连接到多个分支下 （如中所示的判定形状的情况下），所选内容移到最左边的分支中的第一个形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-108">If the shape is connected to several branches below (as in the case of a Decide shape), the selection moves to the first shape in the leftmost branch.</span></span><br /><br /> <span data-ttu-id="5a268-109">如果选择内容位于业务流程的结束形状上，按此键无效，因为其下方没有其他任何形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-109">If selection is on the End shape for the orchestration, pressing this key has no effect, because there are no more shapes below it.</span></span>|  
|<span data-ttu-id="5a268-110">向上键</span><span class="sxs-lookup"><span data-stu-id="5a268-110">UP ARROW</span></span>|<span data-ttu-id="5a268-111">将所选内容移动到一条连接线或形状更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a268-111">Moves the selection to the next connecting line or shape above.</span></span> <span data-ttu-id="5a268-112">如果该形状连接到更高版本的多个分支中，选择内容将移到最后一个形状上最左边的分支。</span><span class="sxs-lookup"><span data-stu-id="5a268-112">If the shape is connected to several branches above, selection moves to the last shape on the leftmost branch.</span></span><br /><br /> <span data-ttu-id="5a268-113">按此键没有时生效**启动**选择形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-113">Pressing this key has no effect when the **Start** shape is selected.</span></span>|  
|<span data-ttu-id="5a268-114">向左键</span><span class="sxs-lookup"><span data-stu-id="5a268-114">LEFT ARROW</span></span>|<span data-ttu-id="5a268-115">如果所选内容上发送或接收形状，并且该形状连接到端口：</span><span class="sxs-lookup"><span data-stu-id="5a268-115">If the selection is on a Send or Receive shape and the shape is connected to a port:</span></span><br /><br /> <span data-ttu-id="5a268-116">-如果该形状具有通向左侧端口图面中的端口的端口连接线，则焦点和选择内容移至端口连接线的形状中。</span><span class="sxs-lookup"><span data-stu-id="5a268-116">-   If the shape has a port connector leading to a port in the Left Port Surface, focus and selection shift to the port connector of the shape.</span></span><br /><span data-ttu-id="5a268-117">-如果该形状具有通向右侧端口图面中的端口的端口连接线，按此键无效。</span><span class="sxs-lookup"><span data-stu-id="5a268-117">-   If the shape has a port connector leading to a port in the Right Port Surface, pressing this key has no effect.</span></span><br /><span data-ttu-id="5a268-118">-如果该形状具有没有端口连接线，导航将是与使用其他任何形状相同。</span><span class="sxs-lookup"><span data-stu-id="5a268-118">-   If the shape has no port connector, navigation is the same as with any other shape.</span></span><br /><br /> <span data-ttu-id="5a268-119">对于其他形状 （或未连接到端口的发送或接收形状）：</span><span class="sxs-lookup"><span data-stu-id="5a268-119">For other shapes (or Send or Receive shapes not connected to a port):</span></span><br /><br /> <span data-ttu-id="5a268-120">-如果所选内容中一个分支，并且分支存在包含形状左侧的 current branch，所选内容移至左侧分支上最近的形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-120">-   If the selection is in a branch, and a branch exists with shapes on it to the left of the current branch, the selection moves to the nearest shape on the branch to the left.</span></span><br /><span data-ttu-id="5a268-121">-键没有任何影响业务流程中的其他任何位置。</span><span class="sxs-lookup"><span data-stu-id="5a268-121">-   The key has no effect anywhere else in the orchestration.</span></span>|  
|<span data-ttu-id="5a268-122">向右键</span><span class="sxs-lookup"><span data-stu-id="5a268-122">RIGHT ARROW</span></span>|<span data-ttu-id="5a268-123">相同向左箭头键，但在相反的方向。</span><span class="sxs-lookup"><span data-stu-id="5a268-123">Same as the LEFT ARROW key, but in the opposite direction.</span></span>|  
|<span data-ttu-id="5a268-124">Home</span><span class="sxs-lookup"><span data-stu-id="5a268-124">HOME</span></span>|<span data-ttu-id="5a268-125">选择更改会导致从业务流程的开始形状连接线。</span><span class="sxs-lookup"><span data-stu-id="5a268-125">Selection changes to the connector that leads from the Start shape of the orchestration.</span></span>|  
|<span data-ttu-id="5a268-126">END</span><span class="sxs-lookup"><span data-stu-id="5a268-126">END</span></span>|<span data-ttu-id="5a268-127">所选内容更改为通向业务流程的结束形状的连接器。</span><span class="sxs-lookup"><span data-stu-id="5a268-127">Selection changes to the connector that leads into the End shape of the orchestration.</span></span>|  
|<span data-ttu-id="5a268-128">NUM LOCK +-</span><span class="sxs-lookup"><span data-stu-id="5a268-128">NUM LOCK + -</span></span>|<span data-ttu-id="5a268-129">折叠选定的复杂形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-129">Collapses the selected complex shape.</span></span>|  
|<span data-ttu-id="5a268-130">NUM LOCK + +</span><span class="sxs-lookup"><span data-stu-id="5a268-130">NUM LOCK + +</span></span>|<span data-ttu-id="5a268-131">展开选定的复杂形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-131">Expands the selected complex shape.</span></span>|  
|<span data-ttu-id="5a268-132">NUM LOCK + \*</span><span class="sxs-lookup"><span data-stu-id="5a268-132">NUM LOCK + \*</span></span>|<span data-ttu-id="5a268-133">展开所选的复杂形状，以及可能具有的所有子复杂形状。</span><span class="sxs-lookup"><span data-stu-id="5a268-133">Expands the selected complex shape, plus any child complex shapes it may have.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a268-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a268-134">See Also</span></span>  
 [<span data-ttu-id="5a268-135">业务流程设计器键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="5a268-135">Orchestration Designer Keyboard Shortcuts</span></span>](../core/orchestration-designer-keyboard-shortcuts.md)