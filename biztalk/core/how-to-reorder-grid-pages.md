---
title: "如何重新排列网格页 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.reorderpages
ms.assetid: bbf45501-109f-4333-8d1f-1ad47b010db0
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 622ee8346855e41c722898a59de6dbe3da90c8a3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-reorder-grid-pages"></a>如何重排网格页
如果映射复杂，则可以包含多个网格页，然后将其重命名和重新排序。 本主题为这些操作提供了分步说明。  
  
 您可以包含一个或多个网格页以简化您的映射视图，让其整齐和可读。 例如，可以将与标头信息相关的所有链接和 functoid 放到一页中，然后将与映射主体相关的全部链接和 functoid 放到另一页中。 然后，可以重命名和重新排列您创建的网格页。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-add-and-rename-a-grid-page"></a>添加和重命名网格页  
  
1.  右键单击页面选项卡面板，并依次**添加页**。 您将看到在您的映射中插入一个新页。  
  
     ![添加和重命名网格页](../core/media/adding-and-renaming-grid-page.gif "Adding_and_renaming_grid_page")  
  
2.  右键单击页面选项卡面板，并依次**重命名此页**。  
  
    > [!TIP]
    >  或者，您可以双击现有的页面选项卡或在键盘上按 F2。  
  
3.  键入网格页的新名称，然后按 Enter。  
  
### <a name="to-reorder-grid-pages-using-reorder-map-pages-dialog-box"></a>使用“重排映射页顺序”对话框重排网格页顺序的步骤  
  
1.  右键单击页面选项卡面板，并依次**重新排序页**。  
  
2.  在**重新排序地图页**对话框中，选择您想要移动，页选项卡，然后单击向上箭头或向下箭头可更改网格页的相对位置，然后单击**确定**。  
  
     ![移动向上或向下重新排序网格页](../core/media/reorder-map-pages.gif "Reorder_map_pages")  
  
### <a name="to-reorder-grid-pages-using-the-page-tabs-panel"></a>使用页选项卡面板重排网格页顺序的步骤  
  
1.  选择要移动/重排顺序的页选项卡。  
  
2.  按住鼠标键并沿着页选项卡面板移动该页选项卡。  
  
3.  将该页选项卡移动到页选项卡面板上所需位置后松开鼠标。  
  
    > [!TIP]
    >  只有鼠标光标更改为两个页选项卡之间的竖直线时，才能对页进行移动/重排顺序。 垂直线指示要重排顺序的页的位置。  
  
### <a name="to-delete-a-grid-page"></a>若要删除的网格页  
  
1.  选择要删除的页的选项卡。  
  
2.  页选项卡上，右键单击，然后单击**删除页**。 该页将以静默方式删除。  
  
    > [!IMPORTANT]
    >  如果不想删除网格页，可按 Ctrl + Z 撤消删除操作。 有关如何撤消或重做用户操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用网格页](../core/working-with-grid-pages.md)