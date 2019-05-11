---
title: 如何移动之间和网格页内 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.gridpreview
ms.assetid: 9553d9ad-1c57-4e73-bb77-0eaaa172090c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cedbf885b9e017a50d0e2dd68fc693bf5b54491a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335913"
---
# <a name="how-to-move-between-and-within-grid-pages"></a>如何移动之间和网格页内
如果映射很复杂，则很有可能，并非所有链接和 functoid 都是在单个网格页内可见在同一时间。 这意味着您需要能够在网格页内滚动。 并且，如果您的映射需要多个网格页，将需要能够在网格页之间移动。 本主题提供有关这些操作的分步说明。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-pan-within-a-grid-page"></a>若要在网格页内平移  
  
1.  在映射器实用工具功能区中，单击![滚动映射器使用此按钮](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")图标。  
  
2.  按住鼠标左键，然后在你想要滚动映射的方向拖动鼠标。  
  
    > [!NOTE]
    >  若要切换到正常模式，请单击![滚动映射器使用此按钮](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")图标。  
  
## <a name="to-scroll-within-a-grid-page-using-keyboard"></a>若要在使用键盘的网格页内滚动  
 使网格页成为焦点在网格图面上任意位置单击。 然后，使用键盘上向右、 向上或向下箭头向左滚动网格页中为所需的方向。 可以一次移动一个网格单元格。  
  
 \- 或 -  
  
 使网格页成为焦点在网格图面上任意位置单击。 然后，使用 Page Up/Page Down 键滚动网格页在键盘上。  
  
## <a name="to-scroll-within-a-grid-page-using-mouse"></a>若要在使用鼠标网格页内滚动  
 将鼠标指针移动到网格页上，并旋转鼠标滚轮以向上或向下移动该映射。  
  
> [!NOTE]
>  不能在代码图上使用鼠标向右移动或向左。  
  
 或者，可以将鼠标指针移动到的边缘或一角的网格页中您要滚动的方向。 光标更改为一个箭头。 单击并按住鼠标左键以在网格页中导航。  
  
### <a name="to-scroll-within-a-grid-page-by-using-the-grid-preview"></a>使用网格预览在网格页内滚动  
  
1.  上**BizTalk**菜单上，单击**网格预览**。  
  
    > [!NOTE]
    >  您可以在网格页背景，右键单击，然后单击**网格预览**从快捷菜单。 或者，您还可以按 CTRL + M、 CTRL + G 从键盘。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
2.  在中**网格预览**对话框框中，将定位块拖至新位置。 在移动定位块时，显示的网格页也将相应滚动。  
  
    > [!NOTE]
    >  网格预览可用于导航与许多 functoid 和链接跨越较大区域的大型网格页。  
  
     ![网格预览](../core/media/gridpreview.gif "GridPreview")  
  
## <a name="to-zoom-the-grid-page"></a>若要放大网格页  
 拖动缩放滑块以缩小或放大网格页正在努力。 您可以缩小以查看完整网格页以其合适的足够小的尺寸。 相反，您可以放大以获得的网格页的一部分的特写视图。  
  
 ![拖动以放大或缩小](../core/media/zoom-gridpage.gif "Zoom_gridpage")  
  
### <a name="to-move-between-grid-pages"></a>网格页之间移动  
  
1.  使用**移到左侧结尾**，**左移**，**右移**，并**移至最右端**网格以显示选项卡底部的箭头，显示你想要移动的网格页的名称。  
  
     ![在映射中的网格页间移动](../core/media/move-between-grid-pages.gif "Move_between_grid_pages")  
  
2.  单击你想要移动的网格页的选项卡。  
  
    > [!TIP]
    >  或者，您可以右键单击任意位置的区域中位置**移到左侧结尾**，**左移**，**右移**，和**移至最右端**显示箭头。 从上下文菜单中，单击想要将移动到的网页。  
  
## <a name="see-also"></a>请参阅  
 [使用网格页](../core/working-with-grid-pages.md)