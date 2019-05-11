---
title: 如何配置 Functoid 输入参数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- bts10.mapper.functoid.inputs
ms.assetid: 2c8f773a-932c-423d-b3fe-724265304b0a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75c2d7997f76df6e1b4983a896d409a93c628872
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341511"
---
# <a name="how-to-configure-functoid-input-parameters"></a>如何配置 Functoid 输入参数
正确配置映射中 functoid 的输入的参数是使用 functoid 的最重要的是，和潜在易出错的方面之一。 可以按如下所示配置 functoid 输入的参数：  
  
- 创建通过连接 schema 节点及各自的 functoid （拖放到 functoid 鼠标从 schema 节点） 的可见输入的链接。  
  
- 直接编辑输入参数使用的列表**配置\<Functoid\> Functoid**对话框。  
  
  本主题提供有关配置为使用这些方法的 functoid 的输入的参数的分步说明。  
  
  拖放方法建立 functoid 输入的参数提供了方便地指定在源架构中的 XPath 规范所涉及的输入的参数。 有关创建 schema 节点和 functoid 输入的参数的信息，请参阅[如何向映射添加基本 Functoid](../core/how-to-add-basic-functoids-to-a-map.md)。 但是，**配置\<Functoid\> Functoid**对话框是可靠的机制对于查看 functoid 的输入的参数，用于创建和修改任何常数参数，以及为重新排列输入参数在必要时的顺序。  
  
  当你配置 functoid 的输入的参数直接在网格页上 （通过绘制线条、 使用鼠标拖放，来自源架构节点并将其链接到该 functoid），如果输入数量达到最大值，光标将更改为无状态。 此外，状态栏显示的原因。 下图显示了 functoid 接受一个输入的链接。  
  
  ![用于配置 functoid 输入的参数没有状态](../core/media/configure-input-parameters-no-state.gif "Configure_input_parameters_NO_state")  
  
  你可以配置使用的脚本编写和表循环 functoid**配置\<Functoid\> Functoid**对话框。 有关如何配置 functoid 的信息，请参阅[如何配置脚本 Functoid](../core/how-to-configure-the-scripting-functoid.md)并[如何配置表循环和表提取程序 Functoid](../core/how-to-configure-the-table-looping-and-table-extractor-functoids.md)。  
  
## <a name="prerequisites"></a>先决条件  
 这些说明需要 BizTalk 映射器处于运行状态。  
  
## <a name="what-is-an-input-parameter"></a>什么是输入的参数？  
 输入的参数可以是以下任一项：  
  
-   来自源架构节点到 functoid 的链接  
  
-   从 functoid 到另一个有效 functoid 的链接  
  
-   常量值  
  
> [!NOTE]
>  有几个 functoid，如**日期**，**时间**，**日期和时间**，以及**Nil**，不需要任何输入的参数。  
  
 下图显示了 functoid （以红色突出显示） 使用两个输入参数 （Input [0] 和 Input[1]) 和常数参数 （input[2]）。  
  
 ![显示 functoid 的输入的参数](../core/media/identifying-input-parameters.gif "Identifying_input_parameters")  
  
## <a name="to-open-the-configure-functoid-functoid-dialog-box"></a>若要打开配置\<Functoid\> Functoid 对话框  
 您可以打开**配置\<Functoid\> Functoid**对话框中的以下方法之一：  
  
-   在相关网格页中，右键单击 functoid，然后依次**配置 Functoid 输入**。  
  
-   双击你想要配置的输入的参数的 functoid。  
  
-   选择 functoid，然后单击省略号 (**...**) 在 Visual Studio**属性**窗口。  
  
-   选择 functoid，然后按 ENTER 键盘。  
  
-   选择 functoid，然后按 CTRL + M、 CTRL + I 键盘。 有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
### <a name="to-insert-constant-input-parameters"></a>插入常数输入的参数  
  
1.  在中**配置\<Functoid\> Functoid**对话框中，选择**Functoid 输入**选项卡。  
  
    > [!NOTE]
    >  **Functoid 输入**默认情况下选择选项卡。  
  
2.  单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮。 将添加一个新行。  
  
3.  键入新的输入参数的值，然后单击**确定**。  
  
    > [!NOTE]
    >  如果未启用添加按钮，该 functoid 不接受或不需要输入的参数，或者可能已具有的最大数目允许输入。  
  
### <a name="to-edit-existing-constant-input-parameters"></a>若要编辑现有常数输入的参数  
  
1.  在中**配置\<Functoid\> Functoid**对话框中，单击现有常数输入你想要编辑的参数。 选择的当前值。  
  
    > [!IMPORTANT]
    >  可以编辑常数输入参数。 不能编辑所有其他类型的输入的参数。 它们只能重新排列或删除。  
  
2.  单击![编辑常数输入的参数](../core/media/edit-input-parameters.gif "Edit_input_parameters")按钮。 对常数值进行适当的更改，然后单击**确定**。  
  
     或者，可以双击常数输入的参数进行编辑，或按键盘上 F2。  
  
## <a name="to-select-multiple-input-parameters"></a>若要选择多个输入的参数  
 您可以通过按住 CTRL 键并单击所需的行，选择多个输入的参数，然后执行任何以下操作。 您可以从键盘来选择所有的行按 CTRL + A。  
  
-   将选择向上/向下的移动。  
  
    > [!NOTE]
    >  如果批量选择包含最顶层或其他行中的最底层的行，则不能移动所选内容向上/向下分别。  
  
-   重新排列所选内容。  
  
-   删除所选内容。  
  
### <a name="to-change-the-order-of-existing-input-parameters"></a>若要更改现有输入参数的顺序  
  
1.  在中**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要移动到其他位置有序列表中的输入参数的参数。  
  
2.  单击![在列表中上移](../core/media/move-up-button.gif "Move_up_button")按钮在参数列表中向上移动参数。 根据需要重复执行，直到所选的输入的参数为所需的位置。 此外，您可以按键盘向上键。 有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
     -或-  
  
     单击![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮在参数列表中向下移动参数。 根据需要重复执行，直到所选的输入的参数为所需的位置。 此外，您可以按键盘向下箭头键。 有关映射器键盘快捷方式的列表，请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
    > [!IMPORTANT]
    >  您可以重新排列输入只能从顺序**配置\<Functoid\> Functoid**对话框。 如果你选择最顶层或最底层的行![在列表中上移](../core/media/move-up-button.gif "Move_up_button")或![列表中向下移动](../core/media/move-down-button.gif "Move_down_button")按钮，将禁用，分别。  
  
### <a name="to-delete-an-input-parameter-by-deleting-the-input-link"></a>若要通过删除输入的链接来删除输入的参数  
  
1.  在相关网格页中，单击与你想要删除的输入参数对应的输入的链接。  
  
2.  上**编辑**菜单上，单击**删除**。  
  
    > [!NOTE]
    >  或者，可以按 DELETE 键，或右键单击该链接在相关网格页中，并单击**删除**从快捷菜单。  
  
    > [!IMPORTANT]
    >  将自行删除输入的链接。 如果您不能确定有关它，可以始终撤消删除。 有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
### <a name="to-delete-existing-input-parameters-within-the-configure-functoid-functoid-dialog-box"></a>若要删除现有输入的参数中配置\<Functoid\> Functoid 对话框  
  
1.  在中**配置\<Functoid\> Functoid**对话框中，单击现有输入你想要删除的参数。  
  
    > [!NOTE]
    >  您可以删除使用此技术，甚至与输入链接相对应的任何输入的参数。  
  
2.  单击![删除所选内容](../core/media/delete-button.gif "Delete_button")按钮。 从参数列表中删除所选现有输入的参数。 单击“确定” 。  
  
     或者，可以选择你想要删除的行并按 DELETE 键键盘。  
  
    > [!IMPORTANT]
    >  将自行删除输入的参数。 如果您不能确定有关它，可以始终撤消删除。 有关撤消/重做操作的详细信息，请参阅[如何撤消或重做用户操作](../core/how-to-undo-or-redo-user-operations.md)。  
  
    > [!NOTE]
    >  在参数列表中没有任何输入的参数时，不启用删除按钮。  
  
## <a name="to-set-labels-and-comments-for-functoids"></a>若要为 functoid 设置标签和注释  
 您可以设置标签和注释 functoid 使用的**配置\<Functoid\> Functoid**对话框。  
  
1.  在中**配置\<Functoid\> Functoid**对话框中，单击**标签和注释**选项卡。  
  
2.  类型**标签**并**注释**，然后单击**确定**。  
  
    > [!IMPORTANT]
    >  有关如何对标签和注释 functoid 和/或链接的详细信息，请参阅[如何标记链接](../core/how-to-label-a-link.md)并[如何标签和注释 Functoid](../core/how-to-label-and-comment-a-functoid.md)。  
  
## <a name="see-also"></a>请参阅  
 [编辑 Functoid 属性和输入参数](../core/editing-functoid-properties-and-input-parameters.md)