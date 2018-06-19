---
title: 如何查看信息提示和工具提示 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5621bd0a-7028-43fc-b6e8-74a528129285
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06aba645f94b87e0a7951d9c8264056262a12a13
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257277"
---
# <a name="how-to-view-infotip-and-tooltip"></a><span data-ttu-id="477a7-102">如何查看提示和工具提示</span><span class="sxs-lookup"><span data-stu-id="477a7-102">How to View Infotip and Tooltip</span></span>
<span data-ttu-id="477a7-103">当您将光标移动到映射项上而不单击该项时，将出现一个屏幕提示，提供有关该项的有用信息。</span><span class="sxs-lookup"><span data-stu-id="477a7-103">When you move the cursor over a map item without clicking it, a screen tip appears with useful information about that item.</span></span>  
  
 <span data-ttu-id="477a7-104">BizTalk 映射器使用两种类型的屏幕提示 – 信息提示和工具提示。</span><span class="sxs-lookup"><span data-stu-id="477a7-104">The BizTalk Mapper uses two types of screen tips – infotip and tooltip.</span></span>  
  
-   <span data-ttu-id="477a7-105">**Infotips** functoid 或链接都显示出来。</span><span class="sxs-lookup"><span data-stu-id="477a7-105">**Infotips** are displayed for functoids or links.</span></span> <span data-ttu-id="477a7-106">当您为 functoid 或链接配置标签或注释时，将在网格页上看到信息提示。</span><span class="sxs-lookup"><span data-stu-id="477a7-106">When you configure labels or comments for functoids or links, you see them as infotip on the grid page.</span></span> <span data-ttu-id="477a7-107">此外，超过时属性的文本值的显示**属性网格**，显示信息提示。</span><span class="sxs-lookup"><span data-stu-id="477a7-107">Also, when the text value for properties exceeds the display of the **Properties Grid**, the infotip is displayed.</span></span>  
  
-   <span data-ttu-id="477a7-108">**工具提示**显示在网格视图中的当前对齐方式从部分/完全隐藏这些架构节点。</span><span class="sxs-lookup"><span data-stu-id="477a7-108">**Tooltips** are displayed for those schema nodes that are hidden partially/completely from the current alignment in the grid view.</span></span>  
  
 <span data-ttu-id="477a7-109">对于链接标签，仅会保留前 256 个字符，而工具提示将显示全部标签。</span><span class="sxs-lookup"><span data-stu-id="477a7-109">For link labels, only the first 256 characters are retained, and the tooltip displays the complete label.</span></span> <span data-ttu-id="477a7-110">对于 functoid，标签最多可包含 256 个字符，注释限制在 1024 个字符。</span><span class="sxs-lookup"><span data-stu-id="477a7-110">For functoids, the label can contain a maximum of 256 characters and comments have a limit of 1024 characters.</span></span> <span data-ttu-id="477a7-111">注释的文本将相应地截断，以仅显示注释前 256 个字符。</span><span class="sxs-lookup"><span data-stu-id="477a7-111">Text of comment gets truncated accordingly to display only first 256 characters of comment.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="477a7-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="477a7-112">Prerequisites</span></span>  
 <span data-ttu-id="477a7-113">若要查看工具提示，请确保 BizTalk 映射器正在运行。</span><span class="sxs-lookup"><span data-stu-id="477a7-113">To view the tooltips, ensure BizTalk Mapper is running.</span></span>  
  
## <a name="to-view-the-infotip"></a><span data-ttu-id="477a7-114">若要查看的信息提示</span><span class="sxs-lookup"><span data-stu-id="477a7-114">To view the infotip</span></span>  
 <span data-ttu-id="477a7-115">将您将鼠标移动到 functoid 上，信息提示即会显示关于 functoid 名称、functoid 标签、functoid 注释和输入参数（如果存在）的信息。</span><span class="sxs-lookup"><span data-stu-id="477a7-115">When you move the mouse on a functoid, the infotip displays information about the functoid name, the functoid label, the functoid comment, and the input parameters (if existing).</span></span> <span data-ttu-id="477a7-116">有关**脚本**functoid，信息提示显示代码的前几行。</span><span class="sxs-lookup"><span data-stu-id="477a7-116">For a **Scripting** functoid, the infotip displays the first few lines of code.</span></span>  
  
 <span data-ttu-id="477a7-117">链接的信息提示将显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="477a7-117">The infotip to a link displays the following information:</span></span>  
  
-   <span data-ttu-id="477a7-118">如果链接标签，设置。</span><span class="sxs-lookup"><span data-stu-id="477a7-118">Link label, if set.</span></span>  
  
-   <span data-ttu-id="477a7-119">**从： 源连接**。</span><span class="sxs-lookup"><span data-stu-id="477a7-119">**From: source connection**.</span></span> <span data-ttu-id="477a7-120">如果源连接是架构元素，它将显示该元素的名称。</span><span class="sxs-lookup"><span data-stu-id="477a7-120">If the source connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="477a7-121">如果源连接是 functoid，则它将显示 functoid 名称。</span><span class="sxs-lookup"><span data-stu-id="477a7-121">If the source connection is a functoid, it shows the functoid name.</span></span>  
  
-   <span data-ttu-id="477a7-122">**目标机构： 目标连接**。</span><span class="sxs-lookup"><span data-stu-id="477a7-122">**To: destination connection**.</span></span> <span data-ttu-id="477a7-123">如果目标连接是架构元素，它将显示该元素的名称。</span><span class="sxs-lookup"><span data-stu-id="477a7-123">If the destination connection is a schema element, it shows the element name.</span></span> <span data-ttu-id="477a7-124">如果目标连接是 functoid，则它将显示 functoid 名称。</span><span class="sxs-lookup"><span data-stu-id="477a7-124">If the destination connection is a functoid, it shows the functoid name.</span></span>  
  
 <span data-ttu-id="477a7-125">如果中的字段**属性网格**具有超过显示中，文本的字段上移动鼠标。</span><span class="sxs-lookup"><span data-stu-id="477a7-125">If the fields in the **Properties Grid** have text that exceeds the display, move the mouse on the field.</span></span> <span data-ttu-id="477a7-126">信息提示将显示完整文本。</span><span class="sxs-lookup"><span data-stu-id="477a7-126">The infotip will show the full text.</span></span>  
  
 <span data-ttu-id="477a7-127">下图说明了与 functoid infotips 链接，与**属性网格**。</span><span class="sxs-lookup"><span data-stu-id="477a7-127">The following figure illustrates infotips to a functoid, link, and the **Properties Grid**.</span></span>  
  
 <span data-ttu-id="477a7-128">![有关 functoid、 链接和标签 Infotips](../core/media/viewing-infotips.gif "Viewing_infotips")</span><span class="sxs-lookup"><span data-stu-id="477a7-128">![Infotips for functoid, link, and label](../core/media/viewing-infotips.gif "Viewing_infotips")</span></span>  
  
## <a name="to-view-the-tooltip"></a><span data-ttu-id="477a7-129">查看工具提示</span><span class="sxs-lookup"><span data-stu-id="477a7-129">To view the tooltip</span></span>  
 <span data-ttu-id="477a7-130">如果源和/或目标架构非常大，则映射可能会纵向延伸，因此可能只能看到部分架构节点。</span><span class="sxs-lookup"><span data-stu-id="477a7-130">When your source and/or destination schemas are big, your map can span vertically; hence the schema nodes may be partially visible.</span></span> <span data-ttu-id="477a7-131">在这种情况下，当您将鼠标移动到这些源节点上时，可以看到工具提示。</span><span class="sxs-lookup"><span data-stu-id="477a7-131">In such a scenario, you can see tooltips when you move the mouse on those source nodes.</span></span>  
  
 <span data-ttu-id="477a7-132">下图显示了部分隐藏的目标架构节点的工具提示。</span><span class="sxs-lookup"><span data-stu-id="477a7-132">The following figure shows a tooltip to a partially hidden target schema node.</span></span>  
  
 <span data-ttu-id="477a7-133">![到架构节点的工具提示](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span><span class="sxs-lookup"><span data-stu-id="477a7-133">![Tooltip to a schema node](../core/media/viewing-tooltips.gif "Viewing_tooltips")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477a7-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="477a7-134">See Also</span></span>  
 [<span data-ttu-id="477a7-135">使用 BizTalk 映射程序</span><span class="sxs-lookup"><span data-stu-id="477a7-135">Using BizTalk Mapper</span></span>](../core/using-biztalk-mapper.md)