---
title: 如何在网格页之间移动关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da495b073df7f76ba60946f66a4a40b697c25793
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335978"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a><span data-ttu-id="80efc-102">如何在网格页之间移动关系</span><span class="sxs-lookup"><span data-stu-id="80efc-102">How to Move a Relationship Between Grid Pages</span></span>
<span data-ttu-id="80efc-103">大型映射包含许多组 functoid 和链接，可以使难以识别加入多个 functoid 的链接。</span><span class="sxs-lookup"><span data-stu-id="80efc-103">Large maps include many sets of functoids and links, which can make it difficult for you to identify the links joining multiple functoids.</span></span> <span data-ttu-id="80efc-104">在此类方案中，你可能想要将一组类似的 functoid 和链接移到其他网格页中以使映射更具可读性。</span><span class="sxs-lookup"><span data-stu-id="80efc-104">In such a scenario, you might want to move a similar set of functoids and links to a different grid page to make the map more readable.</span></span> <span data-ttu-id="80efc-105">本主题提供执行该操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="80efc-105">This topic provides step-by-step instructions to perform the operation.</span></span>  
  
 <span data-ttu-id="80efc-106">您可以将关系从一个网格页为另一种相同的映射，通过以下方式之一：</span><span class="sxs-lookup"><span data-stu-id="80efc-106">You can move a relationship from one grid page to another, in the same map only, in one of the following ways:</span></span>  
  
-   <span data-ttu-id="80efc-107">使用**移至页面**对话框</span><span class="sxs-lookup"><span data-stu-id="80efc-107">Using the **Move to Page** dialog box</span></span>  
  
-   <span data-ttu-id="80efc-108">使用拖放的功能区选择 functoid （和链接）</span><span class="sxs-lookup"><span data-stu-id="80efc-108">Using the drag-and-drop of the ribbon-selected functoid(s) (and links)</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="80efc-109">您可以移动一个或多个 functoid 及其链接。</span><span class="sxs-lookup"><span data-stu-id="80efc-109">You can move one or more functoids and their links.</span></span> <span data-ttu-id="80efc-110">移动关系、 标签、 注释和常数值 （以及正确的占位符） 时与关联的关系会保留。</span><span class="sxs-lookup"><span data-stu-id="80efc-110">When you move a relationship, the labels, comments, and the constant values (along with the correct place holders) associated with that relationship are retained.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="80efc-111">不能只将链接拖放到其他网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-111">You cannot drag-and-drop only links to another grid page.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="80efc-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="80efc-112">Prerequisites</span></span>  
 <span data-ttu-id="80efc-113">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="80efc-113">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a><span data-ttu-id="80efc-114">若要使用移至页面对话框移动关系</span><span class="sxs-lookup"><span data-stu-id="80efc-114">To move a relationship using Move To Page dialog box</span></span>  
  
1.  <span data-ttu-id="80efc-115">在映射中，选择你想要移动关系的网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-115">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="80efc-116">右键单击 functoid 或你想要移动，然后单击的关系中的链接**移至页面**。</span><span class="sxs-lookup"><span data-stu-id="80efc-116">Right-click a functoid or a link in the relationship you want to move and then click **Move to Page**.</span></span> <span data-ttu-id="80efc-117">显示一条消息指出将移动所有所选的映射项目 (s)，以及相关的链接和 functoid。</span><span class="sxs-lookup"><span data-stu-id="80efc-117">A message saying that all the selected map items(s), along with related links and functoids, will be moved is displayed.</span></span> <span data-ttu-id="80efc-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="80efc-118">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80efc-119">若要禁用消息弹出窗口中的，在 Visual Studio 菜单中，请转到**工具**，单击**选项**，单击**BizTalk 映射器**，单击**常规**，然后取消选中**移至页面**选项。</span><span class="sxs-lookup"><span data-stu-id="80efc-119">To disable the message popup, in the Visual Studio menu, go to **Tools**, click **Options**, click **BizTalk Mapper**, click **General**, and then uncheck the **Move to page** option.</span></span> <span data-ttu-id="80efc-120">有关常规选项的详细信息，请参阅[如何在 BizTalk 映射器中自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。</span><span class="sxs-lookup"><span data-stu-id="80efc-120">For more information about general options, see [How to Customize General Settings in BizTalk Mapper](../core/how-to-customize-general-settings-in-biztalk-mapper.md).</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="80efc-121">或者，可以按 CTRL + M、 CTRL + M 以打开**移至页面**对话框。</span><span class="sxs-lookup"><span data-stu-id="80efc-121">Alternatively, you can press CTRL+M, CTRL+M to open the **Move to Page** dialog box.</span></span> <span data-ttu-id="80efc-122">有关映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="80efc-122">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="80efc-123">![将所选的关系移动到新页面](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span><span class="sxs-lookup"><span data-stu-id="80efc-123">![Moving selected relationship to a new page](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")</span></span>  
  
3.  <span data-ttu-id="80efc-124">在中**移至页面**对话框框中，选择你想要将此关系，再单击目标网格页**确定**。</span><span class="sxs-lookup"><span data-stu-id="80efc-124">In the **Move to Page** dialog box, select the target grid page to which you want to move the relationship, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80efc-125">此外可以通过选择创建一个新页面 **\*（添加新的页）**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="80efc-125">You can also create a new page by selecting **\*(add new page)**, and then clicking **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="80efc-126">或者，可以按 CTRL + M、 CTRL + A 在映射中添加新的网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-126">Alternatively, you can press CTRL+M, CTRL+A to add a new grid page in a map.</span></span> <span data-ttu-id="80efc-127">有关映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。</span><span class="sxs-lookup"><span data-stu-id="80efc-127">For a list of Mapper shortcuts, see [BizTalk Mapper Keyboard Shortcuts](../core/biztalk-mapper-keyboard-shortcuts.md).</span></span>  
  
     <span data-ttu-id="80efc-128">![选择目标网格页](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span><span class="sxs-lookup"><span data-stu-id="80efc-128">![Selecting the target grid page](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")</span></span>  
  
     <span data-ttu-id="80efc-129">所选的 functoid/链接以及相关的 functoid 和链接，将移动到新的网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-129">The selected functoid/link, along with the related functoids and links, is moved to the new grid page.</span></span> <span data-ttu-id="80efc-130">下图显示了所选的关系 （这是在第 3 页） 移动到第 1 页。</span><span class="sxs-lookup"><span data-stu-id="80efc-130">The figure below shows the selected relationship (which was in Page 3) moved to Page 1.</span></span>  
  
     <span data-ttu-id="80efc-131">![所选的关系已经移动到新页面](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span><span class="sxs-lookup"><span data-stu-id="80efc-131">![Selected relationship is moved to a new page](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")</span></span>  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a><span data-ttu-id="80efc-132">若要使用拖放移动关系</span><span class="sxs-lookup"><span data-stu-id="80efc-132">To move a relationship using drag-and-drop</span></span>  
  
1.  <span data-ttu-id="80efc-133">在映射中，选择你想要移动关系的网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-133">On the map, select the grid page from which you want to move a relationship.</span></span>  
  
2.  <span data-ttu-id="80efc-134">选择 functoid （和 link(s)) 你想要移动到另一个网格页。</span><span class="sxs-lookup"><span data-stu-id="80efc-134">Select the functoid(s) (and link(s)) you want to move to another grid page.</span></span> <span data-ttu-id="80efc-135">此以递归方式选择连接到所选内容中的 functoid 的所有链接。</span><span class="sxs-lookup"><span data-stu-id="80efc-135">This recursively selects all links that connect to the functoids in the selection.</span></span>  
  
3.  <span data-ttu-id="80efc-136">将所选内容拖动到的页面 （在页选项卡） 想要移动的关系。</span><span class="sxs-lookup"><span data-stu-id="80efc-136">Drag the selection to the page (on the page tab) where you want to move the relationship.</span></span>  
  
    > [!WARNING]
    >  <span data-ttu-id="80efc-137">不释放鼠标，直到执行步骤 4。</span><span class="sxs-lookup"><span data-stu-id="80efc-137">Do not release the mouse till you perform step 4.</span></span>  
  
4.  <span data-ttu-id="80efc-138">当目标网格页进入焦点 （在上面的图中，第 1 页为焦点），所选内容放在网格页上的某个空单元格。</span><span class="sxs-lookup"><span data-stu-id="80efc-138">When the target grid page comes into focus (in the above figure, Page 1 is in focus), drop the selection on an empty cell on the grid page.</span></span> <span data-ttu-id="80efc-139">所选的关系已经移动到新的网格页中。</span><span class="sxs-lookup"><span data-stu-id="80efc-139">The selected relationship is moved to the new grid page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80efc-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="80efc-140">See Also</span></span>  
 [<span data-ttu-id="80efc-141">使用网格页</span><span class="sxs-lookup"><span data-stu-id="80efc-141">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)