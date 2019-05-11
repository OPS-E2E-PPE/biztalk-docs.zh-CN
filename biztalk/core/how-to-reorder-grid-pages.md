---
title: 如何重排网格页顺序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a8ea3a0f5eb08544862081d1495ce5413aaa6f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384271"
---
# <a name="how-to-reorder-grid-pages"></a><span data-ttu-id="b947f-102">如何重排网格页顺序</span><span class="sxs-lookup"><span data-stu-id="b947f-102">How to Reorder Grid Pages</span></span>
<span data-ttu-id="b947f-103">如果映射很复杂，您可以包含多个网格页中，重命名并进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="b947f-103">If your map is complex, you can include multiple grid pages, and then rename and reorder them.</span></span> <span data-ttu-id="b947f-104">本主题包括执行这些操作的分步说明。</span><span class="sxs-lookup"><span data-stu-id="b947f-104">This topic includes step-by-step instructions to perform these operations.</span></span>  
  
 <span data-ttu-id="b947f-105">可以包含一个或多个网格页以简化您的映射视图，以及让其整齐和可读。</span><span class="sxs-lookup"><span data-stu-id="b947f-105">You can include one or more grid pages to simplify the view of your map, and also to keep it organized and readable.</span></span> <span data-ttu-id="b947f-106">例如，您可以将所有链接和 functoid 与上一个页上，标头信息相关的然后都将所有链接和 functoid 与另一页上映射的正文。</span><span class="sxs-lookup"><span data-stu-id="b947f-106">For example, you can put all the links and functoids that relate to header information on one page, and then put all the links and functoids that relate to the body of your map on another page.</span></span> <span data-ttu-id="b947f-107">然后可以重命名和重新排序已创建的网格页。</span><span class="sxs-lookup"><span data-stu-id="b947f-107">You can then rename and reorder the grid pages that you have created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b947f-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="b947f-108">Prerequisites</span></span>  
 <span data-ttu-id="b947f-109">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="b947f-109">These instructions require that BizTalk Mapper is running.</span></span>  
  
### <a name="to-add-and-rename-a-grid-page"></a><span data-ttu-id="b947f-110">添加和重命名网格页</span><span class="sxs-lookup"><span data-stu-id="b947f-110">To add and rename a grid page</span></span>  
  
1.  <span data-ttu-id="b947f-111">右键单击页选项卡面板，然后依次**添加页**。</span><span class="sxs-lookup"><span data-stu-id="b947f-111">Right-click the page tabs panel, and then click **Add Page**.</span></span> <span data-ttu-id="b947f-112">您将看到在映射中插入一个新页。</span><span class="sxs-lookup"><span data-stu-id="b947f-112">You will see a new page inserted in your map.</span></span>  
  
     <span data-ttu-id="b947f-113">![添加和重命名网格页](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span><span class="sxs-lookup"><span data-stu-id="b947f-113">![Adding and renaming grid pages](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")</span></span>  
  
2.  <span data-ttu-id="b947f-114">右键单击页选项卡面板，然后依次**重命名页**。</span><span class="sxs-lookup"><span data-stu-id="b947f-114">Right-click the page tabs panel, and then click **Rename Page**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b947f-115">或者，你可以双击现有页选项卡，或在键盘上按 F2。</span><span class="sxs-lookup"><span data-stu-id="b947f-115">Alternatively, you can either double-click the existing page tab or press F2 on the keyboard.</span></span>  
  
3.  <span data-ttu-id="b947f-116">键入网格页中的新名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="b947f-116">Type the new name for the grid page, and then press ENTER.</span></span>  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a><span data-ttu-id="b947f-117">重排网格页使用重排映射页对话框</span><span class="sxs-lookup"><span data-stu-id="b947f-117">To reorder grid pages using Reorder map pages dialog box</span></span>  
  
1.  <span data-ttu-id="b947f-118">右键单击页选项卡面板，然后依次**重排页顺序**。</span><span class="sxs-lookup"><span data-stu-id="b947f-118">Right-click the page tabs panel, and then click **Reorder Pages**.</span></span>  
  
2.  <span data-ttu-id="b947f-119">在中**重排映射页顺序**对话框中，选择你想要移动的页选项卡，然后单击向上键或向下箭头更改网格页的相对位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b947f-119">In the **Reorder map pages** dialog box, select the page tab you want to move, and click the UP arrow or the DOWN arrow to change the relative position of the grid page, and then click **OK**.</span></span>  
  
     <span data-ttu-id="b947f-120">![向上或向下重排网格页移动](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span><span class="sxs-lookup"><span data-stu-id="b947f-120">![Move up or down to reorder grid pages](../core/media/reorder-map-pages.gif "Reorder_map_pages")</span></span>  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a><span data-ttu-id="b947f-121">重排网格页使用页选项卡面板</span><span class="sxs-lookup"><span data-stu-id="b947f-121">To reorder grid pages using the page tabs panel</span></span>  
  
1.  <span data-ttu-id="b947f-122">选择你想要移动/重排顺序的页选项卡。</span><span class="sxs-lookup"><span data-stu-id="b947f-122">Select the page tab you want to move/reorder.</span></span>  
  
2.  <span data-ttu-id="b947f-123">按住鼠标键并沿着页选项卡面板移动。</span><span class="sxs-lookup"><span data-stu-id="b947f-123">Hold down the mouse key and move it along the page tabs panel.</span></span>  
  
3.  <span data-ttu-id="b947f-124">释放鼠标按钮时的页选项卡使到达页选项卡面板上的目标位置。</span><span class="sxs-lookup"><span data-stu-id="b947f-124">Release the mouse when you have brought the page tab to the desired location on the page tab panel.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="b947f-125">页已移动/重新排序仅当鼠标光标更改为两个页选项卡之间的竖直线时。</span><span class="sxs-lookup"><span data-stu-id="b947f-125">The page is moved/reordered only when the mouse cursor changes into a vertical line between two page tabs.</span></span> <span data-ttu-id="b947f-126">垂直线指示要重新排序的页的位置。</span><span class="sxs-lookup"><span data-stu-id="b947f-126">The vertical line indicates the position of the page to be reordered.</span></span>  
  
### <a name="to-delete-a-grid-page"></a><span data-ttu-id="b947f-127">若要删除网格页</span><span class="sxs-lookup"><span data-stu-id="b947f-127">To delete a grid page</span></span>  
  
1.  <span data-ttu-id="b947f-128">选择你想要删除的页的选项卡。</span><span class="sxs-lookup"><span data-stu-id="b947f-128">Select the tab of the page you want to delete.</span></span>  
  
2.  <span data-ttu-id="b947f-129">右键单击页选项卡，然后依次**删除页**。</span><span class="sxs-lookup"><span data-stu-id="b947f-129">Right-click on the page tab, and then click **Delete Page**.</span></span> <span data-ttu-id="b947f-130">以无提示方式删除页面。</span><span class="sxs-lookup"><span data-stu-id="b947f-130">The page is deleted silently.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="b947f-131">如果不希望删除网格页，按 CTRL + Z 撤消删除操作。</span><span class="sxs-lookup"><span data-stu-id="b947f-131">If you do not want to delete the grid page, press CTRL + Z to undo the deletion operation.</span></span> <span data-ttu-id="b947f-132">有关如何撤消或重做用户操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="b947f-132">For more information on how to undo or redo user operations, see [How to Undo or Redo User Operations](../core/how-to-undo-or-redo-user-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b947f-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b947f-133">See Also</span></span>  
 [<span data-ttu-id="b947f-134">使用网格页</span><span class="sxs-lookup"><span data-stu-id="b947f-134">Working with Grid Pages</span></span>](../core/working-with-grid-pages.md)