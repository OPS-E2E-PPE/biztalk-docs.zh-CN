---
title: 如何选择多个链接和 Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f9ae50cb-c212-48f3-9dfb-74df282645c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dbc88252719a59780f5971a4f68990057b130b4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383974"
---
# <a name="how-to-select-multiple-links-and-functoids"></a><span data-ttu-id="786cc-102">如何选择多个链接和 Functoid</span><span class="sxs-lookup"><span data-stu-id="786cc-102">How to Select Multiple Links and Functoids</span></span>
<span data-ttu-id="786cc-103">当你想要执行映射中 functoid 和/或链接的一组类似的操作时，可以全部在同一时间选择该组 functoid 和/或链接。</span><span class="sxs-lookup"><span data-stu-id="786cc-103">When you want to perform a similar operation on a group of functoids and/or links in a map, you can select that group of functoids and/or links all at the same time.</span></span> <span data-ttu-id="786cc-104">本主题提供有关如何执行此操作的信息。</span><span class="sxs-lookup"><span data-stu-id="786cc-104">This topic provides information about how to perform this operation.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="786cc-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="786cc-105">Prerequisites</span></span>  
 <span data-ttu-id="786cc-106">这些说明需要 BizTalk 映射器处于运行状态。</span><span class="sxs-lookup"><span data-stu-id="786cc-106">These instructions require that BizTalk Mapper is running.</span></span>  
  
## <a name="why-do-you-need-to-bulk-select-linksfunctoids"></a><span data-ttu-id="786cc-107">为什么需要批量选择链接 /functoid 到？</span><span class="sxs-lookup"><span data-stu-id="786cc-107">Why do you need to bulk-select links/functoids?</span></span>  
 <span data-ttu-id="786cc-108">您可以批量选择链接和/或 functoid 可以执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="786cc-108">You can bulk-select links and/or functoids to do any of the following:</span></span>  
  
-   <span data-ttu-id="786cc-109">复制/剪切并粘贴在同一网格页或同一映射中的另一个网格页中所选内容。</span><span class="sxs-lookup"><span data-stu-id="786cc-109">Copy/cut and paste the selection in the same grid page or another grid page in the same map.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="786cc-110">有关如何复制、 剪切和粘贴链接和 functoid 的信息，请参阅[如何复制、 剪切和粘贴链接和 Functoid](../core/how-to-copy-cut-and-paste-links-and-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="786cc-110">For information on how to copy, cut, and paste links and functoids, see [How to Copy, Cut, and Paste Links and Functoids](../core/how-to-copy-cut-and-paste-links-and-functoids.md).</span></span>  
  
-   <span data-ttu-id="786cc-111">网格页之间移动所选内容</span><span class="sxs-lookup"><span data-stu-id="786cc-111">Move the selection between grid pages</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="786cc-112">有关如何在一个网格页之间移动关系的信息，请参阅[如何移动网格页面之间的关系](../core/how-to-move-a-relationship-between-grid-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="786cc-112">For information on how to move a relationship from one grid page to another, see [How to Move a Relationship Between Grid Pages](../core/how-to-move-a-relationship-between-grid-pages.md).</span></span>  
  
-   <span data-ttu-id="786cc-113">编辑所选内容中 functoid 和链接的常见属性</span><span class="sxs-lookup"><span data-stu-id="786cc-113">Edit the common properties of functoids and links in the selection</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="786cc-114">有关如何设置注释和标签为 functoid 和链接的信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)或[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。</span><span class="sxs-lookup"><span data-stu-id="786cc-114">For information on how to set comments and labels for functoids and links, see [How to Label a Link](../core/how-to-label-a-link.md) or [How to Label and Comment a Functoid](../core/how-to-label-and-comment-a-functoid.md).</span></span>  
  
-   <span data-ttu-id="786cc-115">删除多个链接和/或在一个步骤中的 functoid</span><span class="sxs-lookup"><span data-stu-id="786cc-115">Deleting multiple link(s) and/or functoid(s) in one step</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="786cc-116">有关如何删除 functoid 的信息，请参阅[如何删除 Functoid](../core/how-to-delete-functoids.md)。</span><span class="sxs-lookup"><span data-stu-id="786cc-116">For information on how to delete functoids, see [How to Delete Functoids](../core/how-to-delete-functoids.md).</span></span>  
  
## <a name="to-select-multiple-links-and-functoids"></a><span data-ttu-id="786cc-117">若要选择多个链接和 functoid</span><span class="sxs-lookup"><span data-stu-id="786cc-117">To select multiple links and functoids</span></span>  
 <span data-ttu-id="786cc-118">您可以批量选择 functoid 和/或链接任何以下方法：</span><span class="sxs-lookup"><span data-stu-id="786cc-118">You can bulk-select functoids and/or links in any of the following ways:</span></span>  
  
-   <span data-ttu-id="786cc-119">单击该链接或 functoid。</span><span class="sxs-lookup"><span data-stu-id="786cc-119">Click the link or the functoid.</span></span> <span data-ttu-id="786cc-120">按住 CTRL 键，然后单击其他链接和/或你想要选择的 functoid。</span><span class="sxs-lookup"><span data-stu-id="786cc-120">Hold down the CTRL key, and then click the other links and/or functoids you want to select.</span></span>  
  
     <span data-ttu-id="786cc-121">下图显示了所选的 functoid 和链接被突出显示。</span><span class="sxs-lookup"><span data-stu-id="786cc-121">The following figure shows the selected functoids and links highlighted.</span></span>  
  
     <span data-ttu-id="786cc-122">![批量选择 functoid 和链接](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois 和链接")</span><span class="sxs-lookup"><span data-stu-id="786cc-122">![Bulk selecting functoids and links](../core/media/bulkselect-functois-links.gif "BulkSelect_Functois&Links")</span></span>  
  
-   <span data-ttu-id="786cc-123">在图面上拖动鼠标。</span><span class="sxs-lookup"><span data-stu-id="786cc-123">Drag the mouse on the map surface.</span></span> <span data-ttu-id="786cc-124">选择矩形下的 functoid 将突出显示。</span><span class="sxs-lookup"><span data-stu-id="786cc-124">The functoids under the selection rectangle are highlighted.</span></span>  
  
     <span data-ttu-id="786cc-125">![Functoid 的矩形选择](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span><span class="sxs-lookup"><span data-stu-id="786cc-125">![Rectangle selection of functoids](../core/media/bulkselect-selectionrectangle.gif "BulkSelect_SelectionRectangle")</span></span>  
  
-   <span data-ttu-id="786cc-126">您可以使用拖动的组合和 ctrl 键并单击。</span><span class="sxs-lookup"><span data-stu-id="786cc-126">You can use a combination of dragging and CTRL-click.</span></span> <span data-ttu-id="786cc-127">在映射图面上拖动鼠标和选择 functoid 和/或链接该范围内。</span><span class="sxs-lookup"><span data-stu-id="786cc-127">Drag the mouse on the map surface and select the functoids and/or links in that range.</span></span> <span data-ttu-id="786cc-128">按住 CTRL 键，然后单击 functoid 和/或选择范围外的链接。</span><span class="sxs-lookup"><span data-stu-id="786cc-128">Hold down the CTRL key, and then click the functoids and/or links outside the selection range.</span></span>  
  
## <a name="to-select-all-links-and-functoids-on-the-grid-page"></a><span data-ttu-id="786cc-129">若要选择所有链接和 functoid 的网格页</span><span class="sxs-lookup"><span data-stu-id="786cc-129">To select all links and functoids on the grid page</span></span>  
 <span data-ttu-id="786cc-130">可以在任何通过以下方式选择的所有 functoid 和链接在映射器网格页上：</span><span class="sxs-lookup"><span data-stu-id="786cc-130">You can select all the functoids and links on the Mapper grid page in any of the following ways:</span></span>  
  
-   <span data-ttu-id="786cc-131">右键单击网格页上的任意位置，然后单击**全**。</span><span class="sxs-lookup"><span data-stu-id="786cc-131">Right-click anywhere on the grid page and click **Select All**.</span></span>  
  
-   <span data-ttu-id="786cc-132">在网格页上的任意位置单击，然后单击在键盘中按 CTRL + A。</span><span class="sxs-lookup"><span data-stu-id="786cc-132">Click anywhere on the grid page and click press CTRL+A from the keyboard.</span></span>  
  
-   <span data-ttu-id="786cc-133">单击网格页上的任意位置。</span><span class="sxs-lookup"><span data-stu-id="786cc-133">Click anywhere on the grid page.</span></span> <span data-ttu-id="786cc-134">从 Visual Studio 菜单中，单击**编辑**，然后单击**全**。</span><span class="sxs-lookup"><span data-stu-id="786cc-134">From the Visual Studio menu, click **Edit**, and then click **Select All**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786cc-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="786cc-135">See Also</span></span>  
 [<span data-ttu-id="786cc-136">使用链接指定记录和字段映射</span><span class="sxs-lookup"><span data-stu-id="786cc-136">Using Links to Specify Record and Field Mappings</span></span>](../core/using-links-to-specify-record-and-field-mappings.md)