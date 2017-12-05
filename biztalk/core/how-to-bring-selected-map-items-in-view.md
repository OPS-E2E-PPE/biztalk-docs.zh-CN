---
title: "如何将所选的地图视图中的项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1dff8e981b65b6b91c744ce26648a5f4e06adea
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-bring-selected-map-items-in-view"></a>如何在视图中移动所选的映射项
使用早期版本的 BizTalk 映射器时，如果映射包含大型架构，则必须手动滚动源架构窗格、网格页和目标架构窗格，以便将全部的相关映射项目引入单个视图中。 与 BizTalk Server BizTalk 映射程序，可将所选 functoid/链接的所有相关映射项引入的单一视图自动滚动的网格页。 本主题提供有关如何执行此操作的信息。  
  
 根据您的选择（源架构节点、关系视图中的元素或目标架构节点），BizTalk 映射器以同步方式自动滚动架构视图和关系视图，并显示选定项目的全部关系视图。  
  
> [!NOTE]
>  BizTalk 映射器强调全部相关的映射项目后，自动滚动功能才会生效。 换言之，将首先突出显示与所选内容相关的元素，然后 BizTalk 映射器通过自动滚动将相关元素引入视图中。  
  
 BizTalk 映射器不会实际移动网格对象。 当您删除或修改所选内容时，网格对象将返回其各自的位置。  
  
## <a name="prerequisites"></a>先决条件  
 此操作要求 BizTalk 映射器处于运行状态。  
  
### <a name="to-bring-the-selected-map-items-in-view"></a>将所选映射项目引入视图中  
  
1.  在映射器实用程序功能区，单击自动滚动图标![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其关闭。  
  
    > [!NOTE]
    >  ![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")切换图标默认情况下的关闭。  
  
2.  单击 functoid 或链接后，将突出显示关系中的相关映射项目。  
  
     下图以蓝色显示了所选链接。 依次，BizTalk 映射器以绿色突出显示与所选内容相关的其他映射项目。 从图中可以看到，尽管已经突出显示，但所选关系的全部元素并未完全出现在当前视图中。  
  
     ![链接时自动 &#45; 滚动处于关闭](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")  
  
3.  单击自动滚动图标![自动 &#45; 滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")若要切换到。  
  
     BizTalk 映射器将自动滚动，以将所选内容中的全部相关项目引入当前映射视图。  
  
     ![查看时自动滚动接通](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")  
  
    > [!NOTE]
    >  此外，还可以在键盘上按 Ctrl+M、Ctrl+U。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)