---
title: 如何管理视图 |Microsoft Docs
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
ms.openlocfilehash: 7d68fcb7518a73d18974b15cb9328baa2c74f83a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384616"
---
# <a name="how-to-manage-views"></a>如何管理视图
在开发 BizTalk 映射，过程中您可能想要更改源或目标架构树视图的大小或网格视图的大小。 有时，你可能想要在之前关闭的同一视图中打开您的映射。 本主题提供有关这些任务的分步说明。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-taller-or-shorter"></a>若要使架构树视图或更高或较短的网格视图  
  
1.  将鼠标指针移动到主编辑窗口 （显示在网格视图的任何一侧上的架构树视图） 的下边缘中，直到光标更改为标准的窗口垂直调整图标。  
  
2.  单击并按住鼠标左键，然后向上或向下拖动窗口边缘。  
  
     您已通过垂直调整整个主编辑窗口垂直调整架构树视图和网格视图。  
  
### <a name="to-make-the-schema-tree-views-or-the-grid-view-wider-or-more-narrow"></a>若要在架构树视图或网格视图更宽或更窄的  
  
1.  将鼠标指针移动到主编辑窗口 （该分隔符将架构树视图与它们之间的网格视图） 中的两个窗格分隔条之一中，直到光标更改为标准的窗口水平调整图标。  
  
2.  单击并按住鼠标左键，然后拖动窗格边缘向左 （更窄） 或向右 （更宽）。  
  
     通过您已水平调整架构树视图和网格视图的一个更改的专用主编辑窗口为每个视图。  
  
     或者，您还可以在架构树视图和网格视图更宽或窄通过水平调整整个主编辑窗口。  
  
## <a name="remembering-the-current-view-of-mapper"></a>记住映射器的当前视图  
 BizTalk 映射器会记住所有设置的缩放级别，如都切换状态的实用工具功能区选项和当前链接 /functoid 的对齐。  
  
> [!NOTE]
>  如果有多个映射的 BizTalk 项目或解决方案中，分别记住每个映射的详细信息。  
  
> [!CAUTION]
>  上一个视图的设置存储在 **\*.suo**文件。 请确保从 Visual Studio 中的项目文件夹不删除此文件。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器命令](../core/using-biztalk-mapper-commands.md)   
 [BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)   
 [如何将视图中选择映射项](../core/how-to-bring-selected-map-items-in-view.md)   
 [如何优化架构树视图](../core/how-to-optimize-the-schema-tree-view.md)