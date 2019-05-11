---
title: 如何将选定的映射视图中的项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e287b22-5738-428a-aa35-cced877e51ea
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd4a932b00ac2d0a89eb9cfb8f343fd9ab0d4fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342621"
---
# <a name="how-to-bring-selected-map-items-in-view"></a>如何将视图中选择映射项
与早期版本的 BizTalk 映射器中，如果映射包含大型架构，则必须手动滚动源架构窗格、 网格页中和目标架构窗格才能将所有相关映射项目引入单个视图。 BizTalk 映射器与 BizTalk Server，可将所选的 functoid/链接的所有相关映射项目引入单个视图通过自动滚动网格页。 本主题提供有关如何执行该操作的信息。  
  
 根据你的选择 （源架构节点、 关系视图或目标架构节点中的元素），BizTalk 映射器自动滚动架构视图和关系视图，以同步方式，并显示整体的关系的视图选定的项。  
  
> [!NOTE]
>  BizTalk 映射器强调全部相关映射项目后自动滚动功能才会生效。 换而言之，首先将突出显示与所选内容相关的元素，，然后 BizTalk 映射器通过自动滚动将相关的元素引入视图。  
  
 BizTalk 映射器不会实际移动网格对象。 删除或修改所选内容时，网格对象返回到其各自的位置。  
  
## <a name="prerequisites"></a>先决条件  
 此操作需要 BizTalk 映射器正在运行。  
  
### <a name="to-bring-the-selected-map-items-in-view"></a>若要在视图中将所选的映射项目  
  
1.  在映射器实用工具功能区中，单击自动滚动图标![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其关闭。  
  
    > [!NOTE]
    >  ![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")图标处于打开状态默认情况下关闭。  
  
2.  单击 functoid 或链接;在关系中的相关映射项目将突出显示。  
  
     下图以蓝色显示所选的链接。 依次，BizTalk 映射器突出显示与所选内容，以绿色表示相关的其他映射项目。 从图中，可以看到当前视图中完全不是所选的关系，但是强调中的所有元素。  
  
     ![链接时自动&#45;关闭滚动](../core/media/autoscroll-switchoff.gif "AutoScroll_SwitchOff")  
  
3.  单击自动滚动图标![自动&#45;滚动图标](../core/media/mapper-intelliscroll.gif "Mapper_IntelliScroll")以将其打开。  
  
     BizTalk 映射器自动滚动到当前地图视图选定内容中将所有相关项。  
  
     ![查看打开自动滚动时](../core/media/autoscroll-switchon.gif "AutoScroll_SwitchOn")  
  
    > [!NOTE]
    >  或者，可以按 CTRL + M、 CTRL + U 键盘。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器中的增强功能](../core/using-enhanced-features-in-biztalk-mapper.md)