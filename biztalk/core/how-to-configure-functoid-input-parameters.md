---
title: "如何配置 Functoid 输入参数 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cd9843c46967c7d70a59b4917034e6a3795bb6d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-functoid-input-parameters"></a>如何配置 Functoid 输入参数
正确配置映射中 functoid 的输入参数是使用 functoid 最重要的一个方面，也是最可能出错的一个环节。 可以配置 functoid 输入的参数，如下所示：  
  
-   创建可见的输入的链接，通过连接架构节点和相应 functoid （拖放到 functoid 从架构节点鼠标）。  
  
-   直接编辑的使用的输入参数的列表**配置\<Functoid > Functoid**对话框。  
  
 本主题提供了使用这些方法配置 functoid 的输入参数的分步说明。  
  
 用拖放方法建立 functoid 输入参数可以很方便地指定在源架构中使用 XPath 规范所涉及的输入参数。 有关创建节点和 functoid 的输入的参数的架构的信息，请参阅[如何向地图添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。 但是，**配置\<Functoid > Functoid**对话框是用于查看所有 functoid 的输入的参数、 创建和修改任何常量参数，以及用于重新排列的权威机制在必要时输入的参数的顺序。  
  
 当您直接在网格页上为 functoid 配置输入参数时（通过使用鼠标从源 schema 节点执行拖放操作并将该节点链接到 functoid 来绘制线条），如果输入数量达到最大值，则光标将更改为 NO 状态。 此外，状态栏将显示原因。 下图显示仅接受一个输入链接的 functoid。  
  
 ![用于配置 functoid 输入的参数没有状态](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")  
  
 你可以配置使用的脚本和表循环 functoid**配置\<Functoid > Functoid**对话框。 有关如何配置 functoid 的信息，请参阅[如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)和[如何配置表循环和表提取程序 Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="what-is-an-input-parameter"></a>什么是输入参数？  
 输入参数可以是以下任何形式：  
  
-   从源 schema 节点到 functoid 的链接  
  
-   从 functoid 到另一个有效 functoid 的链接  
  
-   常量值  
  
> [!NOTE]
>  如有几个 functoid**日期**，**时间**，**日期和时间**，和**Nil**，哪些不需要任何输入的参数。  
  
 下图显示了具有两个输入参数（Input[0] 和 Input[1]）和一个常数参数 (Input[2]) 的 functoid（以红色突出显示）。  
  
 ![向 functoid 显示输入的参数](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a>若要打开配置\<Functoid > Functoid 对话框  
 你可以打开**配置\<Functoid > Functoid**对话框中，通过以下方式之一：  
  
-   在相关的网格页中，右键单击提取 functoid，，然后单击**配置 Functoid 输入**。  
  
-   双击要为其配置输入参数的 functoid。  
  
-   选择提取 functoid，然后单击省略号 (**...**) 在 Visual Studio 的**属性**窗口。  
  
-   选择 functoid，然后按键盘上的 Enter。  
  
-   选择 functoid，然后按键盘上的 Ctrl+M、Ctrl+I。 映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
### <a name="to-insert-constant-input-parameters"></a>插入常数输入参数  
  
1.  在**配置\<Functoid > Functoid**对话框中，选择**Functoid 输入**选项卡。  
  
    > [!NOTE]
    >  **Functoid 输入**选项卡在默认情况下处于选中状态。  
  
2.  单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。 将添加一个新行。  
  
3.  键入新的输入参数的值，然后单击**确定**。  
  
    > [!NOTE]
    >  如果添加按钮未启用，则说明该 functoid 不接受或不需要输入参数，或者已经具有允许的最大输入数。  
  
### <a name="to-edit-existing-constant-input-parameters"></a>编辑现有常数输入参数  
  
1.  在**配置\<Functoid > Functoid**对话框中，单击现有常量输入你想要编辑的参数。 当前值已被选中。  
  
    > [!IMPORTANT]
    >  只能编辑常数输入的参数。 不能编辑所有其他类型的输入参数。 只能重新排列或删除这些参数。  
  
2.  单击![编辑常量的输入的参数](../core/media/edit-input-parameters.gif "Edit_input_parameters")按钮。 常量的值中，进行适当的更改，然后单击**确定**。  
  
     此外，还可以双击常数输入参数来对其进行编辑，或按键盘上的 F2。  
  
## <a name="to-select-multiple-input-parameters"></a>选择多个输入参数  
 通过按住 Ctrl 键并单击所需的行，可以选择多个输入参数，然后执行以下任何操作。 您可以按键盘上的 Ctrl+A 选择所有行。  
  
-   上移/下移所选内容。  
  
    > [!NOTE]
    >  如果大容量选择包括最顶层或其他行中的最底部的行，则无法移动所选内容上移/下移分别。  
  
-   重新排列所选内容。  
  
-   删除所选内容。  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a>更改现有输入参数的顺序  
  
1.  在**配置\<Functoid > Functoid**对话框中，单击现有输入你想要将移动到的有序列表中的输入参数的不同位置的参数。  
  
2.  单击![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")按钮在参数列表中向上移动参数。 根据需要重复此步骤，直到所选输入参数位于期望位置。 或者，你可以按向上箭头键从键盘。 映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     -或者-  
  
     单击![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮以在参数列表中向下移动参数。 根据需要重复此步骤，直到所选输入参数位于期望位置。 此外，还可以按键盘上的向下键。 映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
    > [!IMPORTANT]
    >  你可以重新排列的只能从输入序列**配置\<Functoid > Functoid**对话框。 如果你选择最顶层或最底部的行，![在列表中向上移动](../core/media/move-up-button.gif "Move_up_button")或![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮将处于禁用状态，分别。  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a>通过删除输入链接来删除输入参数  
  
1.  在相关网格页中，单击与要删除的输入参数对应的输入链接。  
  
2.  上**编辑**菜单上，单击**删除**。  
  
    > [!NOTE]
    >  或者，可以按 DELETE 键，或右键单击相关的网格页中的链接，单击**删除**从快捷菜单。  
  
    > [!IMPORTANT]
    >  将自行删除输入链接。 如果不确定，可以始终撤消删除。 有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a>若要删除现有输入的参数中配置\<Functoid > Functoid 对话框  
  
1.  在**配置\<Functoid > Functoid**对话框中，单击现有输入你想要删除的参数。  
  
    > [!NOTE]
    >  您可以使用此方法删除任何输入参数，甚至是与输入链接相对应的输入参数。  
  
2.  单击![删除所选内容](../core/media/delete-button.gif "Delete_button")按钮。 将从参数列表中删除所选现有输入参数。 单击 **“确定”**。  
  
     或者，您可以选择要删除的行，然后按键盘上的 Delete 键。   
  
    > [!IMPORTANT]
    >  将自行删除输入参数。 如果不确定，可以始终撤消删除。 有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
    > [!NOTE]
    >  如果参数列表中没有输入参数，则不启用删除按钮。  
  
## <a name="to-set-labels-and-comments-for-functoids"></a>为 functoid 设置标签和注释  
 你可以设置标签和注释 functoid 使用**配置\<Functoid > Functoid**对话框。  
  
1.  在**配置\<Functoid > Functoid**对话框中，单击**标签和注释**选项卡。  
  
2.  类型**标签**和**注释**，然后单击**确定**。  
  
    > [!IMPORTANT]
    >  有关如何对标签和注释 functoid 和/或链接的详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)和[如何标记和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。  
  
## <a name="see-also"></a>另请参阅  
 [编辑 Functoid 属性和输入的参数](../core/editing-functoid-properties-and-input-parameters.md)