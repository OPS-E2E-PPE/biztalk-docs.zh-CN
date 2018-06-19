---
title: 如何管理 XSD 视图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3245ebf0-6128-47b4-8e88-ea06ececbc15
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 945f3fc4d8eac3b09279ea774209a9f43a0f6bd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254429"
---
# <a name="how-to-manage-the-xsd-view"></a><span data-ttu-id="f9090-102">如何管理 XSD 视图</span><span class="sxs-lookup"><span data-stu-id="f9090-102">How to Manage the XSD View</span></span>
<span data-ttu-id="f9090-103">与 XSD 视图有关的管理任务可划分为三个类别： 更改其大小、 更改其背景色和字体，以及更改其刷新特征。</span><span class="sxs-lookup"><span data-stu-id="f9090-103">Management tasks with respect to the XSD view can be divided into three categories: changing its size, changing its background color and font, and changing its refresh characteristics.</span></span>  
  
 <span data-ttu-id="f9090-104">有关刷新特征，后一种类别是最有用时使用大型架构，其中使用自动刷新可能会导致意外的延迟。</span><span class="sxs-lookup"><span data-stu-id="f9090-104">The latter category, concerning refresh characteristics, is most useful when working with large schemas, for which using automatic refresh might cause undesirable delays.</span></span> <span data-ttu-id="f9090-105">在这种情况下，可以禁用自动 （连续） 刷新，并改为根据需要手动刷新 XSD 视图。</span><span class="sxs-lookup"><span data-stu-id="f9090-105">In such cases, you can disable automatic (continuous) refresh, and instead refresh the XSD view manually as needed.</span></span>  
  
 <span data-ttu-id="f9090-106">本主题提供有关这些任务的分步说明。</span><span class="sxs-lookup"><span data-stu-id="f9090-106">This topic provides step-by-step instructions for these tasks.</span></span>  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a><span data-ttu-id="f9090-107">若要使 XSD 视图更高或更短</span><span class="sxs-lookup"><span data-stu-id="f9090-107">To make the XSD view taller or shorter</span></span>  
  
1.  <span data-ttu-id="f9090-108">将鼠标指针移动到 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 主编辑窗口（该窗口将 XSD 视图与架构树视图并列显示）的下边缘，直到光标更改为标准的窗口垂直调整图标。</span><span class="sxs-lookup"><span data-stu-id="f9090-108">Move the mouse pointer to the bottom edge of the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which displays the XSD view side-by-side with the schema tree view, until the cursor changes to the standard window vertical resizing icon.</span></span>  
  
2.  <span data-ttu-id="f9090-109">单击并按住鼠标左键，向上或向下拖动窗口边缘。</span><span class="sxs-lookup"><span data-stu-id="f9090-109">Click and hold the left mouse button and drag the window edge either up or down.</span></span>  
  
     <span data-ttu-id="f9090-110">垂直已调整 XSD 视图大小垂直调整整个主编辑窗口中。</span><span class="sxs-lookup"><span data-stu-id="f9090-110">You have vertically resized the XSD view by vertically resizing the entire main editing window.</span></span>  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a><span data-ttu-id="f9090-111">若要使 XSD 视图更宽或更窄的搜索</span><span class="sxs-lookup"><span data-stu-id="f9090-111">To make the XSD view wider or more narrow</span></span>  
  
1.  <span data-ttu-id="f9090-112">将鼠标指针移到中的窗格中分隔线[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口中，该值可划分将 XSD 视图从架构树视图中，直到光标更改为标准的窗口水平调整大小的图标。</span><span class="sxs-lookup"><span data-stu-id="f9090-112">Move the mouse pointer to the pane divider in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] main editing window, which divides the XSD view from the schema tree view, until the cursor changes to the standard window horizontal resizing icon.</span></span>  
  
2.  <span data-ttu-id="f9090-113">单击并按住鼠标按钮并拖动窗格边缘 （更广泛的） 左或向右 （窄）。</span><span class="sxs-lookup"><span data-stu-id="f9090-113">Click and hold the left mouse button and drag the pane edge either left (wider) or right (narrower).</span></span>  
  
     <span data-ttu-id="f9090-114">通过更改主编辑窗口专用的量为 XSD 视图中的相对于架构树视图，，具有水平调整 XSD 视图。</span><span class="sxs-lookup"><span data-stu-id="f9090-114">You have horizontally resized the XSD view by changing the amount of the main editing window dedicated to the XSD view, relative to the schema tree view.</span></span>  
  
     <span data-ttu-id="f9090-115">你还可以水平调整整个主编辑窗口中进行更宽或窄的 XSD 视图。</span><span class="sxs-lookup"><span data-stu-id="f9090-115">You can also make the XSD view wider or narrower by horizontally resizing the entire main editing window.</span></span>  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a><span data-ttu-id="f9090-116">若要更改的背景色和/或 XSD 视图所用字体</span><span class="sxs-lookup"><span data-stu-id="f9090-116">To change the background color and/or font used by the XSD view</span></span>  
  
1.  <span data-ttu-id="f9090-117">在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。</span><span class="sxs-lookup"><span data-stu-id="f9090-117">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="f9090-118">在**选项**对话框中，单击 BizTalk 编辑器文件夹中，并如有必要，展开**架构显示**类别方法是单击加号 （+） 图标。</span><span class="sxs-lookup"><span data-stu-id="f9090-118">In the **Options** dialog box, click the BizTalk Editor folder, and if necessary, expand the **Schema Display** category by clicking the plus (+) icon.</span></span>  
  
3.  <span data-ttu-id="f9090-119">使用下拉列表颜色选取器中更改的背景色和/或字体和/或**字体**与关联的对话框**XSD 视图背景色**和**XSD 视图字体**属性，分别。</span><span class="sxs-lookup"><span data-stu-id="f9090-119">Change the background color and/or font by using the drop-down color picker and/or **Font** dialog box associated with the **XSD View Background Color** and **XSD View Font** properties, respectively.</span></span>  
  
     <span data-ttu-id="f9090-120">访问**字体**对话框中使用的省略号 (**...**) 按钮位于右侧**XSD 视图字体**属性值框。</span><span class="sxs-lookup"><span data-stu-id="f9090-120">Access the **Font** dialog box by using the ellipsis (**…**) button located at the right end of the **XSD View Font** property value box.</span></span>  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a><span data-ttu-id="f9090-121">若要打开和关闭打开的 XSD 视图自动刷新</span><span class="sxs-lookup"><span data-stu-id="f9090-121">To turn automatic refresh of the XSD view on and off</span></span>  
  
-   <span data-ttu-id="f9090-122">在 BizTalk 编辑器中，下面**XSD**选项卡上，单击**关闭自动刷新**或**启用自动刷新**。</span><span class="sxs-lookup"><span data-stu-id="f9090-122">In BizTalk Editor, below the **XSD** tab, click **Turn off auto refresh** or **Turn on auto refresh**.</span></span>  
  
     <span data-ttu-id="f9090-123">如果关闭了自动刷新，XSD 视图为空。</span><span class="sxs-lookup"><span data-stu-id="f9090-123">When auto-refresh is off, the XSD view is blank.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="f9090-124">默认情况下，自动刷新是上。</span><span class="sxs-lookup"><span data-stu-id="f9090-124">By default, auto-refresh is on.</span></span> <span data-ttu-id="f9090-125">如你的架构会变得更大和更大、 它变得日益重要为你关闭自动刷新功能，并根据需要手动刷新您的架构。</span><span class="sxs-lookup"><span data-stu-id="f9090-125">As your schemas become bigger and bigger, it becomes increasingly important for you to turn off the automatic refresh feature and refresh your schema manually as needed.</span></span>  
  
### <a name="to-manually-refresh-the-xsd-view"></a><span data-ttu-id="f9090-126">要手动刷新 XSD 视图</span><span class="sxs-lookup"><span data-stu-id="f9090-126">To manually refresh the XSD view</span></span>  
  
-   <span data-ttu-id="f9090-127">上**BizTalk**菜单上，单击**刷新 XSD**。</span><span class="sxs-lookup"><span data-stu-id="f9090-127">On the **BizTalk** menu, click **Refresh XSD**.</span></span>  
  
     <span data-ttu-id="f9090-128">XSD 查看更新以反映对架构树所做任何更改。</span><span class="sxs-lookup"><span data-stu-id="f9090-128">The XSD view updates to reflect any changes you have made to the schema tree.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f9090-129">你还可以手动刷新 XSD 视图通过单击**刷新 XSD**与在架构树中，或通过单击每个节点关联的快捷菜单上**刷新**下面链接**XSD** XSD 视图中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="f9090-129">You can also manually refresh the XSD view by clicking **Refresh XSD** on the shortcut menu associated with every node in the schema tree, or by clicking the **Refresh** link below the **XSD** tab in the XSD view.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9090-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9090-130">See Also</span></span>  
 [<span data-ttu-id="f9090-131">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="f9090-131">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)