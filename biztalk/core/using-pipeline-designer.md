---
title: 使用管道设计器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Pipeline Designer, how to
- pipelines, Pipeline Designer
ms.assetid: bdb2f5c7-f8a2-4bd6-a8d8-8b7a64f97bd0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d69860203103990c642f5da13cdc916e1185581
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396596"
---
# <a name="using-pipeline-designer"></a>使用管道设计器
管道设计器是图形编辑器，在 Microsoft 中托管[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，其中，您可以创建新的管道; 查看 Microsoft 中附带的管道模板[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]; 管道; 中移动管道组件和配置管道、阶段和管道组件。  
  
 管道设计器使用的三个主要工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]作为设计体验的一部分的 shell:  
  
- 属性窗口中，在其中查看和修改的大多数管道对象的特性。  
  
- 工具箱作为源用于在设计图面。  
  
- 设计图面上，其中组件从工具箱拖放。  
  
  下图显示了管道设计器环境。  
  
  ![管道设计器编辑环境](../core/media/ebiz-prog-usepipe.gif "ebiz_prog_usepipe")  
  描绘了管道设计器环境。  
  
  管道设计器与 BizTalk 项目模板，以增强您的开发体验集成。 在使用项目系统创建一个新的 BizTalk 项目之后, 可以使用**添加新项**命令**文件**菜单添加到你的解决方案的管道。 有关 BizTalk 项目模板的详细信息，请参阅[使用 BizTalk 项目系统](../core/using-the-biztalk-project-system.md)。  
  
> [!NOTE]
>  在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，管道的概念已封装在消息通道和端口，它定义了应用于文档的特定组件设置顺序。 在此版本中，管道非常灵活，因为您可以随意重排管道的每个阶段中的组件，可以轻松地将整个管道的多个自定义组件。  
  
 管道设计器设计图面可以绘制管道的图形表示形式。 在设计图面占据的主要部分[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]窗口并使您能够编辑属于 BizTalk 项目的管道。 您可以通过单击设计图面上的选项卡的管道之间进行导航。  
  
 每个管道由几个阶段，每个阶段包含一个或多个组件组成。 如果阶段中没有任何组件，用文本水印指示，可以从工具箱插入形状。 第一个形状插入到一个阶段，初始文本将消失。 在设计图面显示管道竖向，从顶部 （启动） 运行到下 （结束）。  
  
 一样与其他常用的 Microsoft Windows 程序，您可以执行多项任务，如**开放**并**保存**从**文件**菜单。  
  
## <a name="see-also"></a>请参阅  
 [使用管道设计器创建管道](../core/creating-pipelines-with-pipeline-designer.md)   
 [使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md)