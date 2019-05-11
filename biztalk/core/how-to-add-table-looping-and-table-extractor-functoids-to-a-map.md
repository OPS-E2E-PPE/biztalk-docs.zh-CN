---
title: 如何添加表循环和表提取程序 Functoid 映射到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c837ab8-55db-471a-af26-9fbd0497d7d4
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 171f9d637504dfe41445368e71f68256d6035685
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343047"
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a>如何添加表循环和表提取程序 Functoid 映射
**表循环**并**表提取程序**functoid 一起使用。 **表循环**functoid 已配置的内部表。 对于每个输入记录或字段中，**表循环**functoid 会输出表，一次一个的行。 **表提取程序**functoid 从行提取所需的项，并将其传递到输出实例消息。  
  
 有关概念性信息**表循环**并**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a>向映射添加表循环和表提取程序 functoid 并将其配置  
  
1. 与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择该类别的 functoid。  
  
    将显示所选类别的高级 functoid 列表。  
  
2. 拖动**表循环**functoid (![](../core/media/advtablelooping.gif "advtablelooping")) 从工具箱拖到网格页上的适当位置。  
  
   > [!NOTE]
   >  该 functoid 将放置上显示的网格页。 如果你想要将该 functoid 放置到其他网格页上，您需要首先显示该网格页。  
  
   > [!NOTE]
   >  因为的输出**表循环**functoid 将作为输入到一个或多个关联**表提取程序**functoid，请确保右侧留出空间**表循环**用于 functoid**表提取程序**functoid。  
  
3. 将记录或字段从源架构拖到新添加**表循环**functoid。 作为第一个输入参数**表循环**functoid，此记录或字段的实例消息中的出现次数将控制此 functoid 生成输出的次数。 例如，如果循环记录拖至该 functoid，并处理具有 10 次的此记录的实例消息时，并且已具有一行的列数据源配置表网格**表循环**functoid 将迭代 10 次，生成 10 个输出行，用于通过提取**表提取程序**要可以轻松地构建的 functoid，并允许 10 个目标记录。  
  
   > [!NOTE]
   >  如果在表网格中配置多个行，会输出每个迭代的每个此类行**表循环**functoid。 因此的出现次数的配置表网格中的行数生成的数字输入的记录次数输出可用于提取数据的表行。  
  
4. 将记录或字段拖到目标架构中**表循环**functoid。 此链接可确保在目标架构中节点的创建。  
  
5. 选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮及其**输入参数**属性。  
  
   > [!NOTE]
   >  或者，您可以选择 functoid，然后按 CTRL + M、 CTRL + T 键盘。 列表映射器的键盘快捷方式请参阅[BizTalk 映射器键盘快捷方式](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
6. 在中**配置表循环 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。 键入一个数字来表示将可创建此表中的列数**表循环**functoid。  
  
   > [!NOTE]
   >  最大表中的列数为 228 列。  
  
7. 在中**配置表循环 Functoid**对话框中，单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以输入的任何常量在配置的表网格中显示的值。 只要第一个和第二个参数值、 数量的行和列，分别保留其开始处的输入的参数列表的位置，并不重要此对话框中创建这些常量的顺序。 完成后，单击**确定**。  
  
    **配置表循环 Functoid**对话框将关闭。  
  
8. 将零个或多个记录或字段节点从源架构拖**表循环**最近添加的 functoid。 每个记录和字段节点添加到输入的参数列表的末尾，并因此时可以使用表网格配置在下一步。 类似的表数据常数前面添加 （不行和列数常数），在其中添加这些记录和字段节点的顺序不重要。  
  
9. 若要标记链接，请执行以下步骤：  
  
   - 在显示的网格页中选择一个链接。  
  
   - 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供的描述性名称**标签**属性。 例如，您可能来自一个名为"第二作者"字段的链接为"link2ndauthor"。  
  
10. 选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 按钮与相关联**表循环网格**与该 functoid 关联的属性。  
  
     **配置表循环 Functoid**对话框中显示有**表循环网格**选定的选项卡。  
  
    > [!NOTE]
    >  或者，您可以右键单击 functoid，然后单击**配置表循环网格**的上下文菜单中。 **配置表循环 Functoid**对话框中显示有**表循环网格**选定的选项卡。  
  
11. 使用与每个表单元格关联的下拉列表来配置至少一个，并可能是多个、 行网格中。 在下拉列表中可用选项包括的常数和链接已在步骤 6-8 中配置的作为输入参数 3 并且速度最多**表循环**functoid。 （输入的参数 1 和 2 不显示在这些下拉列表中。）完成后，单击**确定**。  
  
     **配置表循环 Functoid**对话框将关闭。  
  
    > [!NOTE]
    >  每个行构成的输出结构，与结合使用的出现次数的记录或字段的第一个输入参数指定的一次迭代**表循环**functoid。 有关详细信息，请参阅步骤 3。  
  
    > [!NOTE]
    >  必须选择想要访问使用每个列的值**表提取程序**functoid。 如果未使用列**表提取程序**functoid，则应考虑删除，而不是维护，此列。  
  
    > [!NOTE]
    >  填写表网格的顺序并不重要。  
  
12. 将所需数量**表提取程序**functoid (![](../core/media/advtableextractor.gif "advtableextractor")) 从工具箱拖到显示的网格页根据需要。  
  
    > [!NOTE]
    >  因为这些输入**表提取程序**functoid 来自**表循环**functoid 添加在上一步骤中，请确保您放置**表提取程序**functoid 的右侧**表循环**显示的网格页中的 functoid。  
  
13. 若要创建第一个输入的参数之一**表提取程序**functoid 添加在步骤 9 中，将其拖到相关**表循环**至其左侧的 functoid。  
  
14. 若要创建第二个输入的参数的相同**表提取程序**functoid，选中该 functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮及其**输入参数**属性。  
  
     **配置表提取程序 Functoid**对话框随即出现。  
  
15. 单击![将常数输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。 相应的表网格中键入列数**表循环**functoid 要从中提取数据。 单击“确定” 。  
  
     **配置表提取程序 Functoid**对话框将关闭。  
  
    > [!NOTE]
    >  列号从 1 开始。  
  
16. 若要使用的输出**表提取程序**functoid，拖动**表提取程序**到目标架构中的记录或字段节点拖或目标架构中的记录或字段节点到functoid**表提取程序**functoid。 将值 （如果常量），使用填充与目标架构中的此记录或字段节点相对应的目标实例消息中的元素或属性值或所表示的值 （在链接的情况下） 中的指定单元格表网格中。  
  
17. 为每个重复步骤 12、 13、 14 和 15**表提取程序**步骤 11 中添加 functoid。  
  
## <a name="see-also"></a>请参阅  
 [向映射添加高级 Functoid](../core/adding-advanced-functoids-to-a-map.md)