---
title: 如何管理视图 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4a865d7-b319-4264-a085-15f2155bdb2d
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 553e471826cf4744638e7498fd2bb7d52b2e326a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254637"
---
# <a name="how-to-manage-views"></a>如何管理视图
在开发 BizTalk 映射的过程中，您可能需要更改源或目标架构树视图的大小，或网格视图的大小。 有时，您可能需要用之前关闭的同一视图打开您的映射。 本主题提供有关这些任务的分步说明。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-taller-or-shorter"></a>增大或减小架构树视图或网格视图的高度  
  
1.  将鼠标指针移动到主编辑窗口（该窗口在网格视图的左右两侧显示架构树视图）的下边缘，直到光标更改为标准的窗口垂直调整图标。  
  
2.  单击并按住鼠标左键，然后向上或向下拖动窗口边缘。  
  
     通过垂直调整整个主编辑窗口，您已垂直调整了架构树视图和网格视图的大小。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-wider-or-more-narrow"></a>增大或减小架构树视图或网格视图的宽度  
  
1.  将鼠标指针移动到主编辑窗口中两个窗格分隔符（该分隔符将架构树视图与中间的网格视图分隔开来）中的任一分隔符处，直到光标变为标准的窗口水平调整图标。  
  
2.  单击并按住鼠标左键，然后向左（更窄）或向右（更宽）拖动窗格边缘。  
  
     通过更改主编辑窗口为每个视图分配的宽度，您已水平调整了其中一个架构树视图，以及网格视图的大小。  
  
     此外，通过水平调整整个主编辑窗口，您还可以同时增大或减小架构树视图和网格视图的宽度。  
  
## <a name="remembering-the-current-view-of-mapper"></a>记住映射器的当前视图  
 BizTalk 映射器会记住所有设置，如缩放级别、实用工具功能区选项的切换状态，以及当前链接/functoid 的对齐。  
  
> [!NOTE]
>  如果在 BizTalk 项目或解决方案中有多个映射，则分别记住每个映射的单独详细信息。  
  
> [!CAUTION]
>  上一个视图的设置存储在 **\*.suo**文件。 请确保不要从 Visual Studio 中的项目文件夹删除此文件。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 映射程序命令](../core/using-biztalk-mapper-commands.md)   
 [BizTalk 映射程序键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)   
 [如何将视图中选择映射项](../core/how-to-bring-selected-map-items-in-view.md)   
 [如何优化架构树视图](../core/how-to-optimize-the-schema-tree-view.md)