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
ms.openlocfilehash: 25c4981e083352bbba24a6579083dc4023605cba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338899"
---
# <a name="how-to-customize-colors-and-font-in-biztalk-mapper"></a>如何自定义的颜色和字体在 BizTalk 映射器
您可以更改与不同类型的链接和网格视图中的所选对象的颜色相关联的颜色。 此外可以更改用于显示架构树节点的字体。 本主题提供执行这些更改的分步说明。  
  
 您还可以选择自定义 BizTalk 映射器的常规设置。 有关如何选择的设置的信息，请参阅[如何在 BizTalk 映射器中自定义常规设置](../core/how-to-customize-general-settings-in-biztalk-mapper.md)。  
  
> [!NOTE]
>  这些说明需要 BizTalk 映射器处于运行状态。  
  
### <a name="to-change-the-colors-and-font-used-in-biztalk-mapper"></a>若要更改颜色和 BizTalk 映射器中使用的字体  
  
1. 在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]的 **“工具”** 菜单中，单击 **“选项”**。  
  
2. 在中**选项**对话框框中，展开**BizTalk 映射器**节点，，然后单击**颜色和字体**。  
  
    ![选择颜色和字体](../core/media/colorsfonts-options.gif "ColorsFonts_Options")  
  
3. 通过使用与每个颜色属性相关联的下拉颜色选取器更改为各种类型的链接、 编译器警告、 网格前景和网格背景的颜色。  
  
    可用以下颜色选项如下：  
  
   -   **子节点链接。** 用于绘制折叠的父级的子项的链接的颜色。  
  
   -   **编译器错误。** 用于绘制编译器错误的颜色。  
  
   -   **编译器链接。** 编译器链接的颜色，是指编译器指令链接。 它们是将链接从源架构树中的某个字段从设置到目标架构树中的字段时自动创建的链接。  
  
   -   **灰显的链接。** 用于绘制未选中或未突出显示的链接的颜色。  
  
   -   **弹性链接。** 弹性链接是从源架构树拖到目标架构树的简单的值复制链接的颜色。 链接之后进行，链接更改为固定链接的颜色的颜色。  
  
   -   **常规链接。** 用于绘制两端在视图中，当未选择任何内容的链接的颜色。  
  
   -   **网格背景。** 网格页中背景的颜色。  
  
   -   **网格线。** 用于绘制网格线的颜色。  
  
   -   **突出显示的链接。** 用于突出显示链接的颜色。  
  
   -   **指示匹配的链接。** 用于绘制指示匹配的颜色。  
  
   -   **部分所有作用域链接。** 用于绘制具有只有一端在视图中的链接的颜色。  
  
   -   **架构节点字体颜色。** 使用架构树节点的颜色。  
  
   -   **搜索结果。** 用于绘制架构树上的搜索匹配项的颜色。  
  
   -   **选定的网格对象。** 用于绘制网格图面中的所选内容的颜色。  
  
   -   **完全超出作用域的链接。** 用于绘制两端不在视图的链接的颜色。  
  
4. 单击省略号 (**...**) 按钮位于右侧**架构节点字体**属性值框。  
  
5. 在中**字体**对话框中，更改主编辑窗口中的视图中使用的字体。  
  
6. 单击“确定” 。 选择应用的设置。  
  
   > [!IMPORTANT]
   >  如果不想使用自定义的设置，请单击**还原为默认值**中**选项**对话框。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk 映射程序](../core/using-biztalk-mapper.md)