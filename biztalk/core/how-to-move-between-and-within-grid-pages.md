---
title: "如何移动之间和在网格的页内 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.gridpreview
ms.assetid: 9553d9ad-1c57-4e73-bb77-0eaaa172090c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 928e9540c91e33b8e5027bd33757beeff62b145b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-between-and-within-grid-pages"></a>如何移动之间和在网格的页内
如果映射很复杂，很可能无法在单个网格页中同时看到所有链接和 functoid。 这意味着您需要能够在网格页内滚动。 如果您的映射需要多个网格页，则您需要能够在网格页之间移动。 本主题提供有关这些操作的分步说明。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-pan-within-a-grid-page"></a>在网格页内平移  
  
1.  在映射器实用程序功能区中，单击![滚动映射程序使用此按钮](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")图标。  
  
2.  按住鼠标左键，然后向您要滚动映射的方向拖动鼠标。  
  
    > [!NOTE]
    >  若要切换到正常模式下，单击![滚动映射程序使用此按钮](../core/media/mapper-pan-hand.gif "Mapper_Pan_Hand")图标。  
  
## <a name="to-scroll-within-a-grid-page-using-keyboard"></a>使用键盘在网格页内滚动  
 单击网格图面上的任意位置，使该网格页成为焦点。 然后，使用键盘上的向左、向右、向上、向下箭头向所需的方向滚动网格页。 一次只能移动一个网格单元格。  
  
 \-或者-  
  
 单击网格图面上的任意位置，使该网格页成为焦点。 然后，使用键盘上的 Page Up/Page Down 键滚动网格页。  
  
## <a name="to-scroll-within-a-grid-page-using-mouse"></a>使用鼠标在网格页内滚动  
 将鼠标指针移动到网格页上，滑动鼠标滚轮以将映射上下移动。  
  
> [!NOTE]
>  您不能使用鼠标在映射上向左或向右移动。  
  
 或者也可以将鼠标指针移动到网格页的边缘或一角，并朝向您要滚动的方向。 光标将变为箭头。 单击并按住鼠标左键可在网格页内导航。  
  
### <a name="to-scroll-within-a-grid-page-by-using-the-grid-preview"></a>使用网格预览在网格页内滚动  
  
1.  上**BizTalk**菜单上，单击**网格预览**。  
  
    > [!NOTE]
    >  你可以在网格页背景中，右键单击，然后单击**网格预览**从快捷菜单。 此外，还可以在键盘上按 Ctrl+M、Ctrl+G。 映射器的键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
2.  在**网格预览**对话框框中，将正方形的定位符拖动到新位置。 在移动定位块时，所显示的网格页也将相应滚动。  
  
    > [!NOTE]
    >  在具有分布在较大区域内的许多 functoid 和链接的大型网格页中导航时，网格预览十分有用。  
  
     ![网格预览](../core/media/gridpreview.gif "GridPreview")  
  
## <a name="to-zoom-the-grid-page"></a>放大网格页  
 拖动缩放滑块以缩小或放大所处理的网格页。 您可以缩小以查看它中容纳不下的足够小大小中的整个网格页。 相反，您可以放大以获取网格页面的一部分的特写视图。  
  
 ![拖动以放大或缩小](../core/media/zoom-gridpage.gif "Zoom_gridpage")  
  
### <a name="to-move-between-grid-pages"></a>在网格页之间移动  
  
1.  使用**移到左侧结尾**，**左移**，**右移**，和**移到右侧结尾**网格可以显示选项卡底部的箭头，显示您想要移动的网格页的名称。  
  
     ![映射中的网格页之间移动](../core/media/move-between-grid-pages.gif "Move_between_grid_pages")  
  
2.  单击要移动到的网格页的选项卡。  
  
    > [!TIP]
    >  或者，你可以右键单击任意位置的区域中其中**移到左侧结尾**，**左移**，**右移**，和**移到右侧结尾**箭头将显示。 从上下文菜单中单击您要移动到的页。  
  
## <a name="see-also"></a>另请参阅  
 [使用网格页](../core/working-with-grid-pages.md)