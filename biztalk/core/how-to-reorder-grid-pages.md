---
title: 如何重排网格页顺序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a8ea3a0f5eb08544862081d1495ce5413aaa6f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384271"
---
# <a name="how-to-reorder-grid-pages"></a>如何重排网格页顺序
如果映射很复杂，您可以包含多个网格页中，重命名并进行重新排序。 本主题包括执行这些操作的分步说明。  
  
 可以包含一个或多个网格页以简化您的映射视图，以及让其整齐和可读。 例如，您可以将所有链接和 functoid 与上一个页上，标头信息相关的然后都将所有链接和 functoid 与另一页上映射的正文。 然后可以重命名和重新排序已创建的网格页。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-add-and-rename-a-grid-page"></a>添加和重命名网格页  
  
1.  右键单击页选项卡面板，然后依次**添加页**。 您将看到在映射中插入一个新页。  
  
     ![添加和重命名网格页](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")  
  
2.  右键单击页选项卡面板，然后依次**重命名页**。  
  
    > [!TIP]
    >  或者，你可以双击现有页选项卡，或在键盘上按 F2。  
  
3.  键入网格页中的新名称，然后按 ENTER。  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a>重排网格页使用重排映射页对话框  
  
1.  右键单击页选项卡面板，然后依次**重排页顺序**。  
  
2.  在中**重排映射页顺序**对话框中，选择你想要移动的页选项卡，然后单击向上键或向下箭头更改网格页的相对位置，然后单击**确定**。  
  
     ![向上或向下重排网格页移动](../core/media/reorder-map-pages.gif "Reorder_map_pages")  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a>重排网格页使用页选项卡面板  
  
1.  选择你想要移动/重排顺序的页选项卡。  
  
2.  按住鼠标键并沿着页选项卡面板移动。  
  
3.  释放鼠标按钮时的页选项卡使到达页选项卡面板上的目标位置。  
  
    > [!TIP]
    >  页已移动/重新排序仅当鼠标光标更改为两个页选项卡之间的竖直线时。 垂直线指示要重新排序的页的位置。  
  
### <a name="to-delete-a-grid-page"></a>若要删除网格页  
  
1.  选择你想要删除的页的选项卡。  
  
2.  右键单击页选项卡，然后依次**删除页**。 以无提示方式删除页面。  
  
    > [!IMPORTANT]
    >  如果不希望删除网格页，按 CTRL + Z 撤消删除操作。 有关如何撤消或重做用户操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用网格页](../core/working-with-grid-pages.md)