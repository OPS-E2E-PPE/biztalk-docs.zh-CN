---
title: 如何在网格页之间移动关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.movetopage
ms.assetid: 185add4d-c876-44b6-b6e0-71c15a9b7c26
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da495b073df7f76ba60946f66a4a40b697c25793
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335978"
---
# <a name="how-to-move-a-relationship-between-grid-pages"></a>如何在网格页之间移动关系
大型映射包含许多组 functoid 和链接，可以使难以识别加入多个 functoid 的链接。 在此类方案中，你可能想要将一组类似的 functoid 和链接移到其他网格页中以使映射更具可读性。 本主题提供执行该操作的分步说明。  
  
 您可以将关系从一个网格页为另一种相同的映射，通过以下方式之一：  
  
-   使用**移至页面**对话框  
  
-   使用拖放的功能区选择 functoid （和链接）  
  
> [!IMPORTANT]
>  您可以移动一个或多个 functoid 及其链接。 移动关系、 标签、 注释和常数值 （以及正确的占位符） 时与关联的关系会保留。  
  
> [!IMPORTANT]
>  不能只将链接拖放到其他网格页。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-move-a-relationship-using-move-to-page-dialog-box"></a>若要使用移至页面对话框移动关系  
  
1.  在映射中，选择你想要移动关系的网格页。  
  
2.  右键单击 functoid 或你想要移动，然后单击的关系中的链接**移至页面**。 显示一条消息指出将移动所有所选的映射项目 (s)，以及相关的链接和 functoid。 单击“确定” 。  
  
    > [!NOTE]
    >  若要禁用消息弹出窗口中的，在 Visual Studio 菜单中，请转到**工具**，单击**选项**，单击**BizTalk 映射器**，单击**常规**，然后取消选中**移至页面**选项。 有关常规选项的详细信息，请参阅[如何在 BizTalk 映射器中自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。  
  
    > [!TIP]
    >  或者，可以按 CTRL + M、 CTRL + M 以打开**移至页面**对话框。 有关映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     ![将所选的关系移动到新页面](../core/media/moving-a-functoid-new.gif "Moving_a_functoid_new")  
  
3.  在中**移至页面**对话框框中，选择你想要将此关系，再单击目标网格页**确定**。  
  
    > [!NOTE]
    >  此外可以通过选择创建一个新页面 **\*（添加新的页）**，然后单击**确定**。  
  
    > [!NOTE]
    >  或者，可以按 CTRL + M、 CTRL + A 在映射中添加新的网格页。 有关映射器快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     ![选择目标网格页](../core/media/moving-a-functoid-step4.gif "Moving_a_functoid_Step4")  
  
     所选的 functoid/链接以及相关的 functoid 和链接，将移动到新的网格页。 下图显示了所选的关系 （这是在第 3 页） 移动到第 1 页。  
  
     ![所选的关系已经移动到新页面](../core/media/moving-a-functoid-new2.gif "Moving_a_functoid_new2")  
  
### <a name="to-move-a-relationship-using-drag-and-drop"></a>若要使用拖放移动关系  
  
1.  在映射中，选择你想要移动关系的网格页。  
  
2.  选择 functoid （和 link(s)) 你想要移动到另一个网格页。 此以递归方式选择连接到所选内容中的 functoid 的所有链接。  
  
3.  将所选内容拖动到的页面 （在页选项卡） 想要移动的关系。  
  
    > [!WARNING]
    >  不释放鼠标，直到执行步骤 4。  
  
4.  当目标网格页进入焦点 （在上面的图中，第 1 页为焦点），所选内容放在网格页上的某个空单元格。 所选的关系已经移动到新的网格页中。  
  
## <a name="see-also"></a>请参阅  
 [使用网格页](../core/working-with-grid-pages.md)