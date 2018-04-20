---
title: 演练： 从文档实例创建平面文件架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5e1453f-0380-4505-97a9-9d3526db0923
caps.latest.revision: 47
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9077e8c8b878b3e24319ef112eb391a3eaf4e0ef
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="walkthrough-creating-a-flat-file-schema-from-a-document-instance"></a>演练：从文档实例创建平面文件架构
此演练演示如何根据以下示例采购订单，使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。 BizTalk 平面文件架构向导的介绍，请参阅[如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md)。  
  
 ![示例采购订单](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")  
  
 该采购订单的每行都以一个用绿色标记的回车换行符 (CRLF) 结束。 采购订单以红色 PO 标记后跟日期开头。 两个重复的固定位置字段包含客户信息，以紫色显示。 注释字段中之后，没有重复的域从一个项标记，它包含多个由逗号 （，） 分隔的记录和由管道 (& #124;) 分隔的数据值显示为蓝色。  
  
## <a name="prerequisites"></a>先决条件  
 在进行此演练之前，请确保您的服务器上安装并配置了以下软件：  
  
-   Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  
  
-   Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与**开发人员工具**安装
  
 若要准备本演练的文档实例，将以下内容复制到文本编辑器，并将其保存为文本文件。 请确保将所有行都复制源和回车符。  
  
```
PO1999-10-20
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952
US        Robert Smith        8 Oak Avenue        Old Town       PA 95819
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric

```

  
## <a name="start-the-wizard"></a>启动向导  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  
  
2.  若要添加新的平面文件架构，右键单击项目，然后选择 **添加**。 单击 **新项**。  
  
3.  在 **添加新项** 窗口中，执行以下操作︰  
  
    1.  在 **类别** 部分中，选择 **架构文件**。  
  
    2.  在 **模板** 部分中，选择 **平面文件架构向导**。  
  
    3.  在 **名称** 字段中，输入 **PurchaseOrder.xsd** 新架构。  
  
    4.  单击 **“添加”**。  
  
4.  “BizTalk 平面文件架构向导”打开后，将显示“欢迎”页。   
    若要在将来运行向导时跳过此屏幕，选择 **不要再显示此简介页** 框。 单击 **“下一步”** 继续。  
  
## <a name="selecting-purchase-order-instance"></a>选择的采购订单实例  
  
-   上 **平面文件架构信息** 屏幕上，选择你的实例，输入以下信息。 完成后，单击 **下一步** 以继续。  
  
    -   **实例文件︰** 单击 **浏览** 按钮以查找要从中生成架构的平面文件。 浏览到包含演练先决条件部分中创建的文本文件的文件夹︰ 创建平面文件架构从文档实例。  
  
    -   **记录名称︰** 类型 **PO** 因为它将架构根名称。  
  
    -   **目标命名空间：**类型**http://Flat_File_Project.PurchaseOrder**架构目标命名空间。  
  
    -   **代码页︰** 选择 **utf-8 (65001)** 的下拉列表选择列表中。  
  
    -   **计数以字节为单位的位置︰** 选中此框，如果你想要按字节计数的位置的数据字段。 默认情况下，位置数据字段以字符为单位计算。 在本演练中，保留 **计数以字节为单位的位置** 未选中的复选框。  
  
## <a name="select-purchase-order-data"></a>选择采购订单数据  
  
-   上 **选择文档数据** 显示屏幕上，平面文件的内容。 选择用于创建架构，所需的数据，然后单击 **下一步**。  
  
    > [!NOTE]
    >  如果你想要使用的整个文档实例，你可以按 **Ctrl A** 可以选择所有。  
  
    > [!NOTE]
    >  检查 **折长行** 框中，如果你想要查看整个文档实例内容包装在整个向导的编辑框中。  
  
    > [!NOTE]
    >  如果从交换实例创建架构，请只选择表示单个文档结构的部分。  
  
## <a name="delimit-purchase-order-record"></a>分隔采购订单记录  
  
-   如采购订单的每一行结尾回车换行符 (CRLF) 中，选择 **按分隔符符号**, ，然后单击 **下一步** 上 **选择记录格式** 屏幕。  
  
## <a name="specify-purchase-order-record-property"></a>指定采购订单记录属性  
  
-   上 **分隔记录** 屏幕上，输入以下信息来定义架构的第一个级别，完成后，单击 **下一步**。  
  
    -   **子分隔符︰** 选择 **{CR} {LF}**。  
  
        > [!NOTE]
        >  **子分隔符**属性是一个可编辑带有下拉选择列表框包含一组默认值。 **子分隔符** 可以作为一个字符或十六进制值指定。 例如， **\\{** 或 **{0x0D0A}**。  
  
    -   **转义字符︰** 转义符是单个字符，用于屏蔽它后面的字符的任何特殊含义。 请参阅[转义字符](../core/escape-characters.md)有关详细信息。 将它保留为空，以用于演练。  
  
        > [!NOTE]
        >  使用时 **\\**, ，**{，** 和 **}** 为 **子分隔符** 或 **转义符**, ，必须使用反斜杠。 例如， **\\\\,，** 和 **\\{**。  
  
    -   检查 **记录带有标记标识符** 框，并键入 **PO** 中 **标记**。 在多个记录文件中， **PO** 将用于标识每个单独的记录。 单击 **“下一步”** 继续。  
  
     ![分隔的记录屏幕](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")  
  
## <a name="define-the-element-in-the-purchase-order-record"></a>将元素定义采购订单记录中  
  
1.  向导已标识了采购订单记录中的四个元素；您现在必须定义元素属性。 在第一行中，执行以下操作：  
  
    1.  类型 **日期** 为 **元素名称**。  
  
    2.  选择 **Field 元素** 为 **元素类型**。  
  
    3.  选择 **日期** 从下拉选择列表中为 **数据类型**。  
  
2.  对以下元素重复执行步骤 a 至 c。 完成后，单击 **下一步**。  
  
    |元素名称|元素类型|数据类型|  
    |------------------|------------------|---------------|  
    |**客户**|**重复记录**||  
    ||**忽略**||  
    |**项**|**记录**||  
  
     ![子元素屏幕](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")  
  
    > [!NOTE]
    >  您可以选择多个行，然后更改其 **元素类型** 为单个类型通过使用鼠标和 SHIFT 或 CTRL 键。  
  
    > [!NOTE]
    >  单击后 **下一步** 上 **子元素** 屏幕上，你将不能单击 **回** 重新定义样式或子元素对进行任何更改。 您需要关闭该向导，然后重新启动它来定义平面文件架构。  
  
3.  完成此过程的各个步骤后，将生成该架构的第一级，如以下屏幕快照所示。 现在已定义了三个唯一的元素，您还需要进一步定义采购订单记录中元素的子记录。 单击“下一步” 。  
  
     ![示例架构屏幕](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")  
  
## <a name="define-the-customer-record"></a>定义的客户记录  
  
1.  因为我们定义 **客户** 元素作为 **重复记录** 类型和 **项** 元素作为 **记录** 类型，BizTalk 平面文件架构向导现在继续进一步定义这两个元素。 上 **架构视图** 屏幕上，选择 **客户**, ，然后单击 **下一步** 以继续。  
  
2.  若要使用客户记录，您必须选择表示客户元素的数据。 由于客户记录是重复记录，因此客户记录的任何一行都可用于定义该记录。 选择客户数据的第一行，然后单击 **下一步** 以继续。  
  
3.  上 **选择记录格式** 页上，选择 **按相对位置**, ，然后单击 **下一步**。  
  
4.  该向导提供了一个用于显示和计算字段之间距离的可视化工具。 上 **位置记录** 页上，使用鼠标左键单击表示名称字段的开始处的位置标记 10。 单击要表示的数据字段的其余部分的以下位置标记︰  
  
    |字段名|位置标记|  
    |----------------|---------------------|  
    |街道|30|  
    |城市|50|  
    |state|65|  
    |邮政编码|68|  
  
     单击 **“下一步”** 继续。  
  
     ![位置记录屏幕](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")  
  
5.  上 **子元素** 页上，指定的子元素的属性。 选择第一个行，然后类型 **国家/地区** 作为 **元素名称**。 对于其他列，保留默认值。 键入以下值的其他属性 **元素名称**:  
  
    |元素名称|“值”|  
    |------------------|-----------|  
    |**customer_Child2**|**fullName**|  
    |**customer_Child3**|**街道**|  
    |**customer_Child4**|**城市**|  
    |**customer_Child5**|**状态**|  
    |**customer_Child6**|**邮政编码**|  
  
     单击 **“下一步”** 继续。  
  
     ![子元素屏幕](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")  
  
6.  客户记录的子元素随即创建，如以下屏幕快照所示。 单击 **下一步** 来定义 items 记录的子元素。  
  
     ![示例架构屏幕](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")  
  
#### <a name="define-the-items-record"></a>定义 items 记录  
  
1.  上 **架构视图** 页上，选择 **项**, ，然后单击 **下一步**。  
  
2.  上 **选择文档数据** 页上，选择整行开头的项目，然后单击 **下一步** 以定义其子元素。  
  
3.  上 **选择记录格式** 页上，选择 **按分隔符符号**, ，然后单击 **下一步**。  
  
4.  在“物品”记录中，逗号用于分隔各个物品。 因此，在 **分隔记录** 页上，输入以下项来定义 items 记录。 完成后，单击 **下一步**。  
  
    -   选择 **,，** 从 **子分隔符** 下拉选择列表。  
  
    -   保留 **转义符** 文本框保留为空白。  
  
    -   选择 **记录带有标记标识符** 和类型 **项** 中 **标记**。  
  
         在多个 items 记录， **项** 用于标识每个单独的记录。  
  
5.  使用中的值 **分隔记录** 页上，向导标识两个子元素。 由于其中一个是重复记录，选择第一个元素，并输入 **项** 作为元素的名称，然后选择 **重复记录** 的下拉列表选择列表中 **元素类型**。 列中保留其余默认值。 选择第二个行，然后选择 **忽略** 从 **元素类型** 列表。 当你单击 **下一步**, ，架构中创建 items 记录的下一个级别。 您还需要定义采购订单架构的最后一部分。  
  
6.  选择 **项** ，然后单击 **下一步** 来继续 **架构视图** 页。  
  
7.  上 **选择文档数据** 页上，选择 **ITEM872 AA & #124;Lawnmower & #124; 1 & #124; 148.95 & #124;确认这是 electric**。 单击 **“下一步”** 继续。  
  
8.  上 **选择记录格式** 页上，选择 **按分隔符符号** 选项，因为由管道 (& #124;) 分隔单个项。  
  
9. 上 **分隔记录** 页上，输入以下命令以定义 item 记录。 完成后，单击 **下一步**。  
  
    -   选择 **& #124;** 从 **子分隔符** 下拉选择列表。  
  
    -   保留 **转义符** 文本框保留为空白。  
  
10. 上 **子元素** 页上，向导已标识五个子元素。 选择第一个行并输入 **productCode** 为 **元素名称**。 对于其他列，请保留默认值。 中的其余 **元素名称属性**, ，键入以下命令︰  
  
    |元素名称|“值”|  
    |------------------|-----------|  
    |**item_Child2**|**说明**|  
    |**item_Child3**|**数量**|  
    |**item_Child4**|**单价**|  
    |**item_Child5**|**说明**|  
  
     单击 **“下一步”** 继续。  
  
11. 您现在已定义了采购订单架构的所有节点。 上 **架构视图** 页上，单击 **完成**。  
  
12. 您现在可以查看最终的采购订单架构了。 您还可以使用 BizTalk 架构编辑器优化该架构。 请参阅平面文件属性名称表以及中的属性表**架构节点属性**。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="summary"></a>“摘要”  
 在此演练中，您学习了如何使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。  
  
## <a name="next-steps"></a>后续步骤  
  
### <a name="validate-po-instance"></a>验证 PO 实例  
 为了确保 PurchaseOrder.xsd 架构能够正确解析 PO 实例，请执行以下操作：  
  
1.  在解决方案资源管理器，右键单击 **PurchaseOrder.xsd** ，然后选择 **属性**。  
  
2.  在 **属性页**, ，请确保 **输入实例 Filename** 字段指向演练先决条件部分中创建的 PO 实例的位置︰ 创建平面文件架构从文档实例。 单击 **确定** 关闭对话框。  
  
3.  在解决方案资源管理器，右键单击 **PurchaseOrder.xsd**, ，然后选择 **验证实例**。 验证组件随即打开。  
  
4.  验证完成后，将向您提供一个链接，使用该链接可以查看基于用 PurchaseOrder.xsd 架构解析 PO 实例所得结果的 XML 输出。 若要查看 XML 输出，请按住 Ctrl，然后单击该链接。  
  
### <a name="create-pipelines-for-the-schema"></a>为架构中创建管道  
 现在，您可以基于 PurchaseOrder.xsd 架构创建 BizTalk 应用程序使用的接收管道或发送管道。  
  
 若要创建新管道，请参阅[如何创建一条新管道](../core/how-to-create-a-new-pipeline.md)。 若要配置平面文件管道组件，请参阅[如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)和[如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md)   
 [使用“BizTalk 平面文件架构向导”创建架构](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)