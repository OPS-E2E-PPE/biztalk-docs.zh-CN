---
title: "业务流程设计图面 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5fb190b-60d7-45e4-9883-7b3d2ed6b0c0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f943c1543cf50e4ecb1f25627cbccd7b4d72eab5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-orchestration-design-surface"></a>业务流程设计图面
业务流程设计图面是可视化设计器，你可以使用创建 BizTalk 业务流程中，并且是业务流程设计器的中心组件。 它是一个画布，你可以从工具箱中，拖动形状拖到，然后配置形状。 为 Visual Studio 编辑器窗口，它占用所使用的其他 Visual Studio 编辑器窗口的主窗口区域。  
  
 ![业务流程设计器](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")  
业务流程设计图面  
  
 业务流程的名称显示在顶级选项卡上的业务流程设计图面窗口和 Visual Studio 窗口标题栏中。  
  
 将设计图面自身划分为三个方面： 过程区域和两个端口图面。 中央过程区域包含描述业务流程的实际的处理流程的形状。 它由包含仅端口和角色链接形状与之交互的端口曲面 flanked 两端**发送**和**接收**过程区域中的形状。  
  
 **过程区域**  
  
 过程区域是业务流程设计图面的业务流程设计器中的主要部分，并始终水平居中的业务流程设计图面中。  
  
 在任意一侧的过程区域中，你将看到端口图面。 **开始**形状放置在设计图面的顶部和业务流程将随着向下添加形状。  
  
 **端口图面**  
  
 两个端口图面会显示在业务流程设计图面，其中一个过程区域的任何一侧。 端口图面可以包含两种类型的形状：**端口**和**角色链接**。 与这些形状进行交互**发送**和**接收**过程区域中的形状。  
  
 它没有任何区别形状; 使用哪些端口图面也就是说，形状相同函数的右或者左的端口图面。 具有要在其中放置新端口的两个端口图面，可以使用更少的 crisscrossing 连接器，因此更易于读取创建业务流程。  
  
 可以折叠或展开通过双击在其上或通过单击双箭头图标这两个端口图面。  
  
> [!IMPORTANT]
>  许多业务流程设计器任务要求你选择各种项，例如架构或业务流程。 如果这些项不在当前项目中，你必须记得你项目中的引用添加到包含想要选择的项的程序集。 若要执行此操作，右键单击该项目并选择**添加引用**。  
  
 **缩放支持**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供的功能，以放大或缩小业务流程的设计器图面。 通过完成以下步骤之一，可以使用缩放支持：  
  
-   右键单击业务流程的设计器图面，然后单击**缩放**菜单选项。 然后可以选择你想要应用的缩放百分比。  
  
-   使用 CTRL + MWHEEL 进行组合，以放大或缩小。按住 CTRL 键并同时向上或向下滚动鼠标滚轮。 使用 CTRL + MWHEELUP 组合，可以缩小和放大的 CTRL + MWHEELDOWN 组合。