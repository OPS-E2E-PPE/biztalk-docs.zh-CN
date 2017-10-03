---
title: "如何网格页之间移动关系 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5737adcb9159568bfea7c7cdde9dff8015b19706
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a>如何在网格页之间移动关系
大型映射包含许多 functoid 和链接集合，这会使您难以识别加入多个 functoid 的链接。 在这种情况下，您可能需要将类似的 functoid 和链接集合移到其他网格页中以使映射更容易辨认。  本主题提供执行该操作的逐步说明。  
  
 通过以下某种方式，只需将关系从一个网格页移到同一个映射中的另一个网格页：  
  
-   使用**移到页**对话框  
  
-   使用功能区选择的 functoid（和链接） 的拖放功能  
  
> [!IMPORTANT]
>  您可以移动一个或多个 functoid 及其链接。 在您移动关系时，与该关系相关联的标签、注释和常数值（以及正确的占位符）均会保留。  
  
> [!IMPORTANT]
>  您不能只将链接拖放到其他网格页中。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a>使用“移至页面”对话框移动关系  
  
1.  在映射中，选择要从中移动关系的源网格页。  
  
2.  右键单击 functoid 或你想要移动，然后单击的关系中的链接**移到页**。 此时将显示一条消息，指出将移动选择的所有映射项目，以及相关链接和 functoid。 单击 **“确定”**。  
  
    > [!NOTE]
    >  若要禁用消息弹出窗口上的，在 Visual Studio 菜单中，请转到**工具**，单击**选项**，单击**BizTalk 映射程序**，单击**常规**，然后再取消选中**移动到页**选项。 有关常规选项的详细信息，请参阅[如何在 BizTalk 映射程序自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。  
  
    > [!TIP]
    >  或者，可以按 CTRL + M、 CTRL + M 以打开**移到页**对话框。 映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     ![将所选的关系移动到新页](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")  
  
3.  在**移到页**对话框框中，选择你想要移动关系，，然后单击目标网格页**确定**。  
  
    > [!NOTE]
    >  此外可以通过选择创建一个新页 **\*（添加新的页）**，然后单击**确定**。  
  
    > [!NOTE]
    >  此外，还可以按 Ctrl+M、Ctrl+A 在映射中添加新网格页。 映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     ![选择目标网格页](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")  
  
     此时，选定的 functoid/链接以及相关的 functoid 和链接将移动到新网格页中。 下图显示了移动到页面 1 中的选定关系（位于页面 3 中）。  
  
     ![所选的关系移到新页](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a>使用拖放功能移动关系  
  
1.  在映射中，选择要从中移动关系的源网格页。  
  
2.  选择要移动到其他网格页中的 functoid（和链接）。 这样会以递归方式选择连接到所选内容中的 functoid 的所有链接。  
  
3.  将所选内容拖动到要移动关系的页面（在页面选项卡上）中。  
  
    > [!WARNING]
    >  在执行步骤 4 之前不要松开鼠标。  
  
4.  当突出显示目标网格页（在上图中，突出显示第 1 页）时，将所选内容放到该网格页上的空白单元格中。 此时，选定关系将移动到新的网格页。  
  
## <a name="see-also"></a>另请参阅  
 [使用网格页](../core/working-with-grid-pages.md)