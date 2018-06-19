---
title: 如何添加表循环和表为地图的提取程序 Functoid |Microsoft 文档
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
ms.openlocfilehash: e4b7844260b7ac5ab29f204a538e61cb99b0d017
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249789"
---
# <a name="how-to-add-table-looping-and-table-extractor-functoids-to-a-map"></a>如何向映射添加“表循环”和“表提取程序”Functoid
**表循环**和**表提取程序**functoid 一起使用。 **表循环**functoid 具有你配置的内部表。 为每个输入字段或记录**表循环**functoid 输出的表，一次一个地行。 **表提取程序**functoid 从行提取所需的项目，并将其传递到输出实例消息。  
  
 有关概念性信息**表循环**和**表提取程序**functoid，请参阅[表循环和表提取程序 Functoid](../core/table-looping-and-table-extractor-functoids.md)。  
  
### <a name="to-add-the-table-looping-and-table-extractor-functoids-to-a-map-and-configure-them"></a>向映射添加“表循环”和“表提取程序”functoid 并对其进行配置  
  
1.  与[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]工具箱处于活动状态，单击**高级 Functoid**选项卡以选择 functoid 该类别。  
  
     此时，将显示所选类别的高级 functoid 列表。  
  
2.  拖动**表循环**functoid (![](../core/media/advtablelooping.gif "advtablelooping")) 从工具箱拖到网格页上的适当位置。  
  
    > [!NOTE]
    >  该 functoid 将放置到显示的网格页上。 如果你想要将 functoid 放到不同的网格页面上，你需要首先显示该网格页。  
  
    > [!NOTE]
    >  因为的输出**表循环**functoid 用作一个或多个关联的输入**表提取程序**functoid，请确保你的右侧留出空间**表循环**为 functoid**表提取程序**functoid。  
  
3.  将记录或字段从源架构拖至新添加**表循环**functoid。 作为将第一个输入参数与**表循环**functoid、 此记录或实例消息中的字段的匹配项的数量将控制的此 functoid 产生的输出的次数。 例如，如果循环记录拖动到 functoid，和具有 10 次此记录的实例消息处理，并已配置了一个行的列数据源的表的网格**表循环**将循环 functoid 10 次，生成由提取的 10 个输出行**表提取程序**functoid 和允许 10 目标记录轻松构造。  
  
    > [!NOTE]
    >  如果你在表的网格中配置多个行，每个这样的行将每个迭代的输出**表循环**functoid。 因此，输入记录出现的次数乘以表网格中所配置的行数将得出可用于进行数据提取的输出表行数。  
  
4.  将记录或字段拖到目标架构从**表循环**functoid。 此链接可确保在目标架构中创建节点。  
  
5.  选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮其**输入参数**属性。  
  
    > [!NOTE]
    >  此外，还可以选择 functoid，然后在键盘上按 Ctrl+M、Ctrl+T。 列表映射器的键盘快捷方式请参阅[BizTalk 映射器键盘快捷键](../core/biztalk-mapper-keyboard-shortcuts.md)。  
  
6.  在**配置表循环 Functoid**对话框中，单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。 键入一个数字，表示将可创建此表中的列数**表循环**functoid。  
  
    > [!NOTE]
    >  表的最大列数为 228 列。  
  
7.  在**配置表循环 Functoid**对话框中，单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以输入任何常量在你配置的表的网格中显示的值。 只要第一个和第二个参数值、行数和列数分别位于输入参数列表的开始位置，这些常数在此对话框中的创建顺序并不重要。 完成后，单击**确定**。  
  
     **配置表循环 Functoid**对话框关闭。  
  
8.  将零个或多个记录或字段节点拖到源架构从**表循环**你最近添加的 functoid。 这些记录和字段节点的每一个记录或字段节点都将添加到输入参数列表的末尾，因此在后面的步骤中配置表网格时将可以使用这些记录和字段节点。 与前面添加的表数据常数（不是行数和列数常数）一样，这些记录和字段节点的添加顺序并不重要。  
  
9. 若要为链接加标签，请执行以下步骤：  
  
    -   在显示的网格页中选择链接。  
  
    -   在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，提供的描述性名称**标签**属性。 例如，对于来自名为“第二作者”的字段的链接，可以将其命名为“link2ndAuthor”。  
  
10. 选择新添加**表循环**functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮**表循环网格**与该 functoid 关联的属性。  
  
     **配置表循环 Functoid**对话框中将显示**表循环网格**选定选项卡。  
  
    > [!NOTE]
    >  或者，你可以右键单击提取 functoid，，然后单击**配置表循环网格**上下文菜单中。 **配置表循环 Functoid**对话框中将显示**表循环网格**选定选项卡。  
  
11. 使用与每个表单元格关联的下拉列表至少配置网格中的一个（可能多个）行。 在下拉列表中提供的选择是常量以及已在步骤 6-8 中配置的作为输入参数 3 并且速度最多的链接**表循环**functoid。 （输入参数 1 和 2 不显示在这些下拉列表中。）完成后，单击**确定**。  
  
     **配置表循环 Functoid**对话框关闭。  
  
    > [!NOTE]
    >  每个行构成的输出结构，与结合使用的出现次数的记录或指定为的第一个输入参数的字段的一次迭代**表循环**functoid。 有关详细信息，请参阅步骤 3。  
  
    > [!NOTE]
    >  必须选择你想要使用访问每个列的值**表提取程序**functoid。 如果未使用列**表提取程序**functoid，应考虑删除，而不是维护，该列。  
  
    > [!NOTE]
    >  表网格的填充顺序并不重要。  
  
12. 尽可能多拖动**表提取程序**functoid (![](../core/media/advtableextractor.gif "advtableextractor")) 从工具箱拖到显示的网格页上根据需要。  
  
    > [!NOTE]
    >  因为这些输入**表提取程序**functoid 来自**表循环**functoid 添加在上一步骤中，请确保你将放置**表提取程序**右侧的 functoid**表循环**functoid 显示的网格页中。  
  
13. 若要创建的第一个输入的参数之一**表提取程序**functoid 添加在步骤 9，将其拖到相关**表循环**functoid 其左侧。  
  
14. 若要创建第二个输入的参数为同一**表提取程序**functoid，选择提取 functoid，然后在**属性**窗口中，单击省略号 (**...**) 与关联的按钮其**输入参数**属性。  
  
     **配置表提取程序 Functoid**对话框随即出现。  
  
15. 单击![将常量的输入的参数添加到 functoid](../core/media/add-input-parameters.gif "Add_input_parameters")按钮以创建第二个输入的参数。 相应的表网格中键入的列号**表循环**functoid 要从中提取数据。 单击 **“确定”**。  
  
     **配置表提取程序 Functoid**对话框关闭。  
  
    > [!NOTE]
    >  列数从 1 开始。  
  
16. 若要使用的输出**表提取程序**functoid，拖动**表提取程序**functoid 到目标架构或到拖动目标架构中的记录或字段节点中的记录或字段节点**表提取程序**functoid。 目标实例消息中与目标架构中的这一记录或字段节点相对应的元素或属性值将使用表网格中指定的单元格的值（如果为常熟）或该单元格所表示的值（如果为链接）填充。  
  
17. 为每个重复步骤 12、 13、 14 中和 15**表提取程序**functoid 步骤 11 中添加。  
  
## <a name="see-also"></a>另请参阅  
 [向地图添加高级的 Functoid](../core/adding-advanced-functoids-to-a-map.md)