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
# <a name="the-orchestration-design-surface"></a>业务流程设计图面
业务流程设计图面是一个可视化设计器可用于创建 BizTalk 业务流程，，和是业务流程设计器的主要组件。 它是一个画布，您可以从工具箱拖动到形状，然后配置形状。 作为 Visual Studio 编辑器窗口中，它占用所使用的其他 Visual Studio 编辑器窗口的主窗口区域。  
  
 ![业务流程设计器](../core/media/b96c16e5-58a2-4d8e-b66c-485864846cec.gif "b96c16e5-58a2-4d8e-b66c-485864846cec")  
业务流程设计图面  
  
 业务流程的名称显示在顶部的选项卡的业务流程设计图面窗口和 Visual Studio 窗口标题栏中。  
  
 在设计图面本身划分为三个区域： 在流程区域和两个端口图面。 中心流程区域包含描述的实际处理流程的业务流程的形状。 它两边是端口图面，其中包含仅端口和角色链接形状与之交互**发送**并**接收**流程区域中的形状。  
  
 **过程区域**  
  
 过程区域是业务流程设计图面上的业务流程设计器的主要部分，并在业务流程设计图面中始终水平居中。  
  
 在流程区域的任何一侧会看到端口图面。 **开始**形状放置在设计图面的顶部和业务流程添加形状的向下增长。  
  
 **端口图面**  
  
 两个端口图面会显示在业务流程设计图面上，一个过程区域的任意一侧。 端口图面可以包含两种类型的形状：**端口**并**角色链接**。 这些形状与之交互**发送**并**接收**流程区域中的形状。  
  
 它没有任何区别对形状; 使用的端口图面也就是说，形状相同函数的右侧或左侧的端口图面上。 具有两个要在其中放置新端口的端口图面，可以使用更少，所以很容易进行读取的 crisscrossing 连接器创建业务流程。  
  
 这两个端口图面可以折叠或展开通过双击，或者通过单击双箭头图标。  
  
> [!IMPORTANT]
>  许多业务流程设计器任务要求你选择架构或业务流程等各种项目。 如果这些项不是当前项目中，您必须记住你的项目中引用添加到包含你想要选择的项的程序集。 若要执行此操作，右键单击该项目并选择**添加引用**。  
  
 **支持缩放**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供的功能，以放大或缩小业务流程设计器图面。 您可以使用缩放支持，通过完成以下步骤之一：  
  
-   右键单击业务流程设计器图面，然后单击**缩放**菜单选项。 然后，可以选择你想要应用的缩放百分比。  
  
-   使用 CTRL + MWHEEL 进行组合，以放大或缩小。按住 CTRL 按钮并向上或向下同时旋转鼠标滚轮。 使用 CTRL + MWHEELUP 组合以缩小和 CTRL + MWHEELDOWN 组合来缩放。