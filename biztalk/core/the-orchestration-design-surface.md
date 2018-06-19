---
title: 业务流程设计图面 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5fb190b-60d7-45e4-9883-7b3d2ed6b0c0
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f943c1543cf50e4ecb1f25627cbccd7b4d72eab5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279805"
---
# <a name="the-orchestration-design-surface"></a><span data-ttu-id="2bbd5-102">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="2bbd5-102">The Orchestration Design Surface</span></span>
<span data-ttu-id="2bbd5-103">业务流程设计图面是可视化设计器，你可以使用创建 BizTalk 业务流程中，并且是业务流程设计器的中心组件。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-103">The Orchestration Design Surface is a visual designer that you can use to create a BizTalk Orchestration, and is the central component of Orchestration Designer.</span></span> <span data-ttu-id="2bbd5-104">它是一个画布，你可以从工具箱中，拖动形状拖到，然后配置形状。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-104">It is a canvas that you can drag shapes onto from the Toolbox, and then configure the shapes.</span></span> <span data-ttu-id="2bbd5-105">为 Visual Studio 编辑器窗口，它占用所使用的其他 Visual Studio 编辑器窗口的主窗口区域。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-105">As a Visual Studio editor window, it occupies the main window area used by other Visual Studio editor windows.</span></span>  
  
 <span data-ttu-id="2bbd5-106">![业务流程设计器](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span><span class="sxs-lookup"><span data-stu-id="2bbd5-106">![Orchestration Designers](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span></span>  
<span data-ttu-id="2bbd5-107">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="2bbd5-107">Orchestration Design Surface</span></span>  
  
 <span data-ttu-id="2bbd5-108">业务流程的名称显示在顶级选项卡上的业务流程设计图面窗口和 Visual Studio 窗口标题栏中。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-108">The name of the orchestration is displayed on the top tab of the Orchestration Design Surface window and in the Visual Studio window title bar.</span></span>  
  
 <span data-ttu-id="2bbd5-109">将设计图面自身划分为三个方面： 过程区域和两个端口图面。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-109">The design surface itself is divided into three areas: the Process Area and two Port Surfaces.</span></span> <span data-ttu-id="2bbd5-110">中央过程区域包含描述业务流程的实际的处理流程的形状。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-110">The central Process Area contains shapes that describe the actual process flow of the orchestration.</span></span> <span data-ttu-id="2bbd5-111">它由包含仅端口和角色链接形状与之交互的端口曲面 flanked 两端**发送**和**接收**过程区域中的形状。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-111">It is flanked on both sides by Port Surfaces, which contain only Port and Role Link shapes that interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="2bbd5-112">**过程区域**</span><span class="sxs-lookup"><span data-stu-id="2bbd5-112">**Process Area**</span></span>  
  
 <span data-ttu-id="2bbd5-113">过程区域是业务流程设计图面的业务流程设计器中的主要部分，并始终水平居中的业务流程设计图面中。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-113">The Process Area is the main part of the Orchestration Design Surface of Orchestration Designer, and is always horizontally centered in the Orchestration Design Surface.</span></span>  
  
 <span data-ttu-id="2bbd5-114">在任意一侧的过程区域中，你将看到端口图面。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-114">On either side of the Process Area you see Port Surfaces.</span></span> <span data-ttu-id="2bbd5-115">**开始**形状放置在设计图面的顶部和业务流程将随着向下添加形状。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-115">The **Begin** shape is placed at the top of the design surface and the orchestration grows downward as you add shapes.</span></span>  
  
 <span data-ttu-id="2bbd5-116">**端口图面**</span><span class="sxs-lookup"><span data-stu-id="2bbd5-116">**Port Surfaces**</span></span>  
  
 <span data-ttu-id="2bbd5-117">两个端口图面会显示在业务流程设计图面，其中一个过程区域的任何一侧。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-117">Two Port Surfaces are displayed in the Orchestration Design Surface, one on either side of the Process Area.</span></span> <span data-ttu-id="2bbd5-118">端口图面可以包含两种类型的形状：**端口**和**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-118">Port Surfaces can contain two kinds of shapes: **Ports** and **Role Links**.</span></span> <span data-ttu-id="2bbd5-119">与这些形状进行交互**发送**和**接收**过程区域中的形状。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-119">These shapes interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="2bbd5-120">它没有任何区别形状; 使用哪些端口图面也就是说，形状相同函数的右或者左的端口图面。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-120">It makes no difference which Port Surface you use for a shape; that is, the shape functions identically on either the right or the left Port Surface.</span></span> <span data-ttu-id="2bbd5-121">具有要在其中放置新端口的两个端口图面，可以使用更少的 crisscrossing 连接器，因此更易于读取创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-121">Having two Port Surfaces on which to place new ports lets you create orchestrations with fewer crisscrossing connectors that therefore are easier to read.</span></span>  
  
 <span data-ttu-id="2bbd5-122">可以折叠或展开通过双击在其上或通过单击双箭头图标这两个端口图面。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-122">Both Port Surfaces can be collapsed or expanded by double-clicking on them or by clicking on the double arrow icon.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2bbd5-123">许多业务流程设计器任务要求你选择各种项，例如架构或业务流程。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-123">Many Orchestration Designer tasks require you to select various items such as schemas or orchestrations.</span></span> <span data-ttu-id="2bbd5-124">如果这些项不在当前项目中，你必须记得你项目中的引用添加到包含想要选择的项的程序集。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-124">If these items are not in the current project, you must remember to add a reference in your project to the assembly that contains the item that you want to select.</span></span> <span data-ttu-id="2bbd5-125">若要执行此操作，右键单击该项目并选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-125">To do this, right-click the project and select **Add Reference**.</span></span>  
  
 <span data-ttu-id="2bbd5-126">**缩放支持**</span><span class="sxs-lookup"><span data-stu-id="2bbd5-126">**Zoom Support**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="2bbd5-127">提供的功能，以放大或缩小业务流程的设计器图面。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-127"> provides the ability to zoom in or zoom out of the Orchestration designer surface.</span></span> <span data-ttu-id="2bbd5-128">通过完成以下步骤之一，可以使用缩放支持：</span><span class="sxs-lookup"><span data-stu-id="2bbd5-128">You can use zoom support by completing one of the following steps:</span></span>  
  
-   <span data-ttu-id="2bbd5-129">右键单击业务流程的设计器图面，然后单击**缩放**菜单选项。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-129">Right-click the Orchestration designer surface and click the **Zoom** menu option.</span></span> <span data-ttu-id="2bbd5-130">然后可以选择你想要应用的缩放百分比。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-130">You can then select the percentage of magnification that you would like to apply.</span></span>  
  
-   <span data-ttu-id="2bbd5-131">使用 CTRL + MWHEEL 进行组合，以放大或缩小。按住 CTRL 键并同时向上或向下滚动鼠标滚轮。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-131">Use the CTRL + MWHEEL combination to zoom in or zoom out. Hold down the CTRL button and simultaneously rotate the mouse wheel up or down.</span></span> <span data-ttu-id="2bbd5-132">使用 CTRL + MWHEELUP 组合，可以缩小和放大的 CTRL + MWHEELDOWN 组合。</span><span class="sxs-lookup"><span data-stu-id="2bbd5-132">Use the CTRL+MWHEELUP combination to zoom out and the CTRL+MWHEELDOWN combination to zoom in.</span></span>