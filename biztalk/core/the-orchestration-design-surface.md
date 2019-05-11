---
title: 业务流程设计图面 |Microsoft Docs
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
ms.openlocfilehash: 649187d2b0003ec2c784d5d628d841600ef9ea9b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394110"
---
# <a name="the-orchestration-design-surface"></a><span data-ttu-id="e6a07-102">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="e6a07-102">The Orchestration Design Surface</span></span>
<span data-ttu-id="e6a07-103">业务流程设计图面是一个可视化设计器可用于创建 BizTalk 业务流程，，和是业务流程设计器的主要组件。</span><span class="sxs-lookup"><span data-stu-id="e6a07-103">The Orchestration Design Surface is a visual designer that you can use to create a BizTalk Orchestration, and is the central component of Orchestration Designer.</span></span> <span data-ttu-id="e6a07-104">它是一个画布，您可以从工具箱拖动到形状，然后配置形状。</span><span class="sxs-lookup"><span data-stu-id="e6a07-104">It is a canvas that you can drag shapes onto from the Toolbox, and then configure the shapes.</span></span> <span data-ttu-id="e6a07-105">作为 Visual Studio 编辑器窗口中，它占用所使用的其他 Visual Studio 编辑器窗口的主窗口区域。</span><span class="sxs-lookup"><span data-stu-id="e6a07-105">As a Visual Studio editor window, it occupies the main window area used by other Visual Studio editor windows.</span></span>  
  
 <span data-ttu-id="e6a07-106">![业务流程设计器](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span><span class="sxs-lookup"><span data-stu-id="e6a07-106">![Orchestration Designers](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")</span></span>  
<span data-ttu-id="e6a07-107">业务流程设计图面</span><span class="sxs-lookup"><span data-stu-id="e6a07-107">Orchestration Design Surface</span></span>  
  
 <span data-ttu-id="e6a07-108">业务流程的名称显示在顶部的选项卡的业务流程设计图面窗口和 Visual Studio 窗口标题栏中。</span><span class="sxs-lookup"><span data-stu-id="e6a07-108">The name of the orchestration is displayed on the top tab of the Orchestration Design Surface window and in the Visual Studio window title bar.</span></span>  
  
 <span data-ttu-id="e6a07-109">在设计图面本身划分为三个区域： 在流程区域和两个端口图面。</span><span class="sxs-lookup"><span data-stu-id="e6a07-109">The design surface itself is divided into three areas: the Process Area and two Port Surfaces.</span></span> <span data-ttu-id="e6a07-110">中心流程区域包含描述的实际处理流程的业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="e6a07-110">The central Process Area contains shapes that describe the actual process flow of the orchestration.</span></span> <span data-ttu-id="e6a07-111">它两边是端口图面，其中包含仅端口和角色链接形状与之交互**发送**并**接收**流程区域中的形状。</span><span class="sxs-lookup"><span data-stu-id="e6a07-111">It is flanked on both sides by Port Surfaces, which contain only Port and Role Link shapes that interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="e6a07-112">**过程区域**</span><span class="sxs-lookup"><span data-stu-id="e6a07-112">**Process Area**</span></span>  
  
 <span data-ttu-id="e6a07-113">过程区域是业务流程设计图面上的业务流程设计器的主要部分，并在业务流程设计图面中始终水平居中。</span><span class="sxs-lookup"><span data-stu-id="e6a07-113">The Process Area is the main part of the Orchestration Design Surface of Orchestration Designer, and is always horizontally centered in the Orchestration Design Surface.</span></span>  
  
 <span data-ttu-id="e6a07-114">在流程区域的任何一侧会看到端口图面。</span><span class="sxs-lookup"><span data-stu-id="e6a07-114">On either side of the Process Area you see Port Surfaces.</span></span> <span data-ttu-id="e6a07-115">**开始**形状放置在设计图面的顶部和业务流程添加形状的向下增长。</span><span class="sxs-lookup"><span data-stu-id="e6a07-115">The **Begin** shape is placed at the top of the design surface and the orchestration grows downward as you add shapes.</span></span>  
  
 <span data-ttu-id="e6a07-116">**端口图面**</span><span class="sxs-lookup"><span data-stu-id="e6a07-116">**Port Surfaces**</span></span>  
  
 <span data-ttu-id="e6a07-117">两个端口图面会显示在业务流程设计图面上，一个过程区域的任意一侧。</span><span class="sxs-lookup"><span data-stu-id="e6a07-117">Two Port Surfaces are displayed in the Orchestration Design Surface, one on either side of the Process Area.</span></span> <span data-ttu-id="e6a07-118">端口图面可以包含两种类型的形状：**端口**并**角色链接**。</span><span class="sxs-lookup"><span data-stu-id="e6a07-118">Port Surfaces can contain two kinds of shapes: **Ports** and **Role Links**.</span></span> <span data-ttu-id="e6a07-119">这些形状与之交互**发送**并**接收**流程区域中的形状。</span><span class="sxs-lookup"><span data-stu-id="e6a07-119">These shapes interact with the **Send** and **Receive** shapes in the Process Area.</span></span>  
  
 <span data-ttu-id="e6a07-120">它没有任何区别对形状; 使用的端口图面也就是说，形状相同函数的右侧或左侧的端口图面上。</span><span class="sxs-lookup"><span data-stu-id="e6a07-120">It makes no difference which Port Surface you use for a shape; that is, the shape functions identically on either the right or the left Port Surface.</span></span> <span data-ttu-id="e6a07-121">具有两个要在其中放置新端口的端口图面，可以使用更少，所以很容易进行读取的 crisscrossing 连接器创建业务流程。</span><span class="sxs-lookup"><span data-stu-id="e6a07-121">Having two Port Surfaces on which to place new ports lets you create orchestrations with fewer crisscrossing connectors that therefore are easier to read.</span></span>  
  
 <span data-ttu-id="e6a07-122">这两个端口图面可以折叠或展开通过双击，或者通过单击双箭头图标。</span><span class="sxs-lookup"><span data-stu-id="e6a07-122">Both Port Surfaces can be collapsed or expanded by double-clicking on them or by clicking on the double arrow icon.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e6a07-123">许多业务流程设计器任务要求你选择架构或业务流程等各种项目。</span><span class="sxs-lookup"><span data-stu-id="e6a07-123">Many Orchestration Designer tasks require you to select various items such as schemas or orchestrations.</span></span> <span data-ttu-id="e6a07-124">如果这些项不是当前项目中，您必须记住你的项目中引用添加到包含你想要选择的项的程序集。</span><span class="sxs-lookup"><span data-stu-id="e6a07-124">If these items are not in the current project, you must remember to add a reference in your project to the assembly that contains the item that you want to select.</span></span> <span data-ttu-id="e6a07-125">若要执行此操作，右键单击该项目并选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="e6a07-125">To do this, right-click the project and select **Add Reference**.</span></span>  
  
 <span data-ttu-id="e6a07-126">**支持缩放**</span><span class="sxs-lookup"><span data-stu-id="e6a07-126">**Zoom Support**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e6a07-127">提供的功能，以放大或缩小业务流程设计器图面。</span><span class="sxs-lookup"><span data-stu-id="e6a07-127">provides the ability to zoom in or zoom out of the Orchestration designer surface.</span></span> <span data-ttu-id="e6a07-128">您可以使用缩放支持，通过完成以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="e6a07-128">You can use zoom support by completing one of the following steps:</span></span>  
  
-   <span data-ttu-id="e6a07-129">右键单击业务流程设计器图面，然后单击**缩放**菜单选项。</span><span class="sxs-lookup"><span data-stu-id="e6a07-129">Right-click the Orchestration designer surface and click the **Zoom** menu option.</span></span> <span data-ttu-id="e6a07-130">然后，可以选择你想要应用的缩放百分比。</span><span class="sxs-lookup"><span data-stu-id="e6a07-130">You can then select the percentage of magnification that you would like to apply.</span></span>  
  
-   <span data-ttu-id="e6a07-131">使用 CTRL + MWHEEL 进行组合，以放大或缩小。按住 CTRL 按钮并向上或向下同时旋转鼠标滚轮。</span><span class="sxs-lookup"><span data-stu-id="e6a07-131">Use the CTRL + MWHEEL combination to zoom in or zoom out. Hold down the CTRL button and simultaneously rotate the mouse wheel up or down.</span></span> <span data-ttu-id="e6a07-132">使用 CTRL + MWHEELUP 组合以缩小和 CTRL + MWHEELDOWN 组合来缩放。</span><span class="sxs-lookup"><span data-stu-id="e6a07-132">Use the CTRL+MWHEELUP combination to zoom out and the CTRL+MWHEELDOWN combination to zoom in.</span></span>