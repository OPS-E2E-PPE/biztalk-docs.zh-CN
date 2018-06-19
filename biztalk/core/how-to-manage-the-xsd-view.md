---
title: 如何管理 XSD 视图 |Microsoft 文档
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
ms.openlocfilehash: 945f3fc4d8eac3b09279ea774209a9f43a0f6bd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254429"
---
# <a name="how-to-manage-the-xsd-view"></a>如何管理 XSD 视图
与 XSD 视图有关的管理任务可划分为三个类别： 更改其大小、 更改其背景色和字体，以及更改其刷新特征。  
  
 有关刷新特征，后一种类别是最有用时使用大型架构，其中使用自动刷新可能会导致意外的延迟。 在这种情况下，可以禁用自动 （连续） 刷新，并改为根据需要手动刷新 XSD 视图。  
  
 本主题提供有关这些任务的分步说明。  
  
### <a name="to-make-the-xsd-view-taller-or-shorter"></a>若要使 XSD 视图更高或更短  
  
1.  将鼠标指针移动到 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 主编辑窗口（该窗口将 XSD 视图与架构树视图并列显示）的下边缘，直到光标更改为标准的窗口垂直调整图标。  
  
2.  单击并按住鼠标左键，向上或向下拖动窗口边缘。  
  
     垂直已调整 XSD 视图大小垂直调整整个主编辑窗口中。  
  
### <a name="to-make-the-xsd-view-wider-or-more-narrow"></a>若要使 XSD 视图更宽或更窄的搜索  
  
1.  将鼠标指针移到中的窗格中分隔线[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]主编辑窗口中，该值可划分将 XSD 视图从架构树视图中，直到光标更改为标准的窗口水平调整大小的图标。  
  
2.  单击并按住鼠标按钮并拖动窗格边缘 （更广泛的） 左或向右 （窄）。  
  
     通过更改主编辑窗口专用的量为 XSD 视图中的相对于架构树视图，，具有水平调整 XSD 视图。  
  
     你还可以水平调整整个主编辑窗口中进行更宽或窄的 XSD 视图。  
  
### <a name="to-change-the-background-color-andor-font-used-by-the-xsd-view"></a>若要更改的背景色和/或 XSD 视图所用字体  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2.  在**选项**对话框中，单击 BizTalk 编辑器文件夹中，并如有必要，展开**架构显示**类别方法是单击加号 （+） 图标。  
  
3.  使用下拉列表颜色选取器中更改的背景色和/或字体和/或**字体**与关联的对话框**XSD 视图背景色**和**XSD 视图字体**属性，分别。  
  
     访问**字体**对话框中使用的省略号 (**...**) 按钮位于右侧**XSD 视图字体**属性值框。  
  
### <a name="to-turn-automatic-refresh-of-the-xsd-view-on-and-off"></a>若要打开和关闭打开的 XSD 视图自动刷新  
  
-   在 BizTalk 编辑器中，下面**XSD**选项卡上，单击**关闭自动刷新**或**启用自动刷新**。  
  
     如果关闭了自动刷新，XSD 视图为空。  
  
    > [!IMPORTANT]
    >  默认情况下，自动刷新是上。 如你的架构会变得更大和更大、 它变得日益重要为你关闭自动刷新功能，并根据需要手动刷新您的架构。  
  
### <a name="to-manually-refresh-the-xsd-view"></a>要手动刷新 XSD 视图  
  
-   上**BizTalk**菜单上，单击**刷新 XSD**。  
  
     XSD 查看更新以反映对架构树所做任何更改。  
  
    > [!NOTE]
    >  你还可以手动刷新 XSD 视图通过单击**刷新 XSD**与在架构树中，或通过单击每个节点关联的快捷菜单上**刷新**下面链接**XSD** XSD 视图中的选项卡。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk 编辑器](../core/using-biztalk-editor.md)