---
title: 如何管理 XSD 视图 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3245ebf0-6128-47b4-8e88-ea06ececbc15
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa052fffcb50854b43cd8b1df169c026e4c0320
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384611"
---
# <a name="how-to-manage-the-xsd-view"></a>如何管理 XSD 视图
与 XSD 视图有关的管理任务可以分为三个类别： 更改其大小、 更改其背景色和字体，以及更改其刷新特性。  
  
 有关刷新特性的后一种类别是最有用时使用的大型架构，其中使用自动刷新可能导致意外的延迟。 在这种情况下，可以禁用自动 （连续） 刷新，并改为根据需要手动刷新 XSD 视图。  
  
 本主题提供有关这些任务的分步说明。  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a>若要使 XSD 视图更高或更短  
  
1. 将鼠标指针移动到 Microsoft 的下边缘[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口，其中显示 XSD 视图的并行与架构树视图中，直到光标更改为标准的窗口垂直调整图标。  
  
2. 单击并按住鼠标左键并向上或向下拖动窗口边缘。  
  
    通过垂直调整整个主编辑窗口，您已垂直调整 XSD 视图。  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a>若要使 XSD 视图更宽或更窄  
  
1. 将鼠标指针移动到中的窗格分隔符[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口，将从架构树视图中，XSD 视图，直到光标更改为标准的窗口水平调整图标。  
  
2. 单击并按住鼠标按钮并拖动窗格边缘 （更宽） 左或向右 （更窄）。  
  
    通过更改主编辑窗口的量为 XSD 视图，相对于在架构树视图，您已水平调整 XSD 视图。  
  
    此外可以通过水平调整整个主编辑窗口更宽或窄的 XSD 视图。  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a>若要更改的背景色和/或使用 XSD 视图字体  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2. 在中**选项**对话框中，单击 BizTalk 编辑器文件夹，并如有必要，展开**架构显示**类别单击加号 （+） 图标。  
  
3. 通过使用下拉颜色选取器来更改背景色和/或字体和/或**字体**与关联的对话框中**XSD 视图背景色**并**XSD 视图字体**属性，分别。  
  
    访问**字体**对话框中，使用旁边的省略号 (**...**) 按钮位于右侧**XSD 视图字体**属性值框。  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a>若要打开和关闭自动刷新 XSD 视图  
  
-   在 BizTalk 编辑器中，下面**XSD**选项卡上，单击**关闭自动刷新**或**启用自动刷新**。  
  
     如果关闭了自动刷新，XSD 视图为空。  
  
    > [!IMPORTANT]
    >  默认情况下，自动刷新为上。 因为架构变得更大和更大，它变得日益重要，以便关闭自动刷新功能，并根据需要手动刷新您的架构。  
  
### <a name="to-manually-refresh-the-xsd-view"></a>若要手动刷新 XSD 视图  
  
-   上**BizTalk**菜单上，单击**刷新 XSD**。  
  
     XSD 视图进行更新以反映对架构树所做的任何更改。  
  
    > [!NOTE]
    >  通过单击可以手动刷新 XSD 视图**刷新 XSD**与在架构树中，或通过单击每个节点关联的快捷菜单上**刷新**下面的链接**XSD** XSD 视图中的选项卡。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)