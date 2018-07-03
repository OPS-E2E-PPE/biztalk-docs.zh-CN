---
title: 如何自定义的颜色和字体在 BizTalk 映射器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.options.colors
ms.assetid: 494e4d70-8159-4721-9378-85bfc3c3d6f2
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d4a7126c8a1ffe7d710b880712d3fecd5f02021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989726"
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a>如何自定义 BizTalk 映射器中的颜色和字体
您可以更改与不同类型的链接关联的颜色，以及网格视图中选定对象的颜色。 还可以更改用于显示架构树节点的字体。 本主题提供了执行这些更改的分步说明。  
  
 还可以选择为 BizTalk 映射器自定义常规设置。 有关如何选择的设置的信息，请参阅[如何在 BizTalk 映射器中自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。  
  
> [!NOTE]
>  这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a>更改 BizTalk 映射器中使用的颜色和字体  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2. 在中**选项**对话框框中，展开**BizTalk 映射器**节点，，然后单击**颜色和字体**。  
  
    ![选择颜色和字体](../core/media/colorsfonts-options.gif "ColorsFonts_Options")  
  
3. 通过使用与各个颜色属性关联的下拉颜色选取器，更改不同类型的链接、编译器警告、网格前景和网格背景的颜色。  
  
    有以下颜色选项：  
  
   -   **子节点链接。** 。用于绘制折叠父级的子项的链接的颜色。  
  
   -   **编译器错误。** 。用于绘制编译器错误的颜色。  
  
   -   **编译器链接。** 。编译器链接的颜色，编译器链接是编译器指令链接。 如果设置了从源架构树中的字段指向目标架构树中的字段的链接，则会自动创建编译器指令链接。  
  
   -   **灰显的链接。** 用于绘制未选中或未突出显示的链接的颜色。  
  
   -   **弹性链接。** 。弹性链接的颜色，弹性链接是指从源架构树拖至目标架构树的简单的值复制链接。 在建立链接后，该链接的颜色将改为固定链接的颜色。  
  
   -   **常规链接。** 用于绘制两端在视图中，当未选择任何内容的链接的颜色。  
  
   -   **网格背景。** 。网格页中背景的颜色。  
  
   -   **网格线。** 。用于绘制网格线的颜色。  
  
   -   **突出显示的链接。** 。用于突出显示链接的颜色。  
  
   -   **指示匹配的链接。** 用于绘制指示匹配的颜色。  
  
   -   **部分所有作用域链接。** 用于绘制只有一端在视图中的链接的颜色。  
  
   -   **架构节点字体颜色。** 用于架构树节点的颜色。  
  
   -   **搜索结果。** 。用于绘制架构树中的搜索匹配项的颜色。  
  
   -   **选定的网格对象。** 。用于绘制网格图面中的所选内容的颜色。  
  
   -   **完全超出作用域的链接。** 用于绘制两端都不在视图中的链接的颜色。  
  
4. 单击省略号 (**...**) 按钮位于右侧**架构节点字体**属性值框。  
  
5. 在中**字体**对话框中，更改主编辑窗口中的视图中使用的字体。  
  
6. 单击“确定” 。 根据所作选择应用这些设置。  
  
   > [!IMPORTANT]
   >  如果不想使用自定义的设置，请单击**还原为默认值**中**选项**对话框。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射器](../core/using-biztalk-mapper.md)