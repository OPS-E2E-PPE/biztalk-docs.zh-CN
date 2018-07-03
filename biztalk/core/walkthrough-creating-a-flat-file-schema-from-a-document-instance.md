---
title: 演练： 从文档实例创建平面文件架构 |Microsoft Docs
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
ms.openlocfilehash: faa79ea6784df39bb2f06b32b289837093a04919
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983422"
---
# <a name="walkthrough-creating-a-flat-file-schema-from-a-document-instance"></a>演练：从文档实例创建平面文件架构
此演练演示如何根据以下示例采购订单，使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。 BizTalk 平面文件架构向导的介绍，请参阅[如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md)。  

 ![示例采购订单](../core/media/flatfileschema-samplepurchaseorder.gif "FlatFileSchema_SamplePurchaseOrder")  

 该采购订单的每行都以一个用绿色标记的回车换行符 (CRLF) 结束。 采购订单以红色 PO 标记后跟日期开头。 两个重复的固定位置字段包含客户信息，以紫色显示。 注释字段中之后，没有重复的域开头包含多个由逗号 （，） 分隔的记录和数据值之间用竖线分隔的项标记 (&#124;)，其中显示为蓝色。  

## <a name="prerequisites"></a>必要條件  
 在进行此演练之前，请确保您的服务器上安装并配置了以下软件：  

- Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  

- Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与**开发人员工具**安装

  若要为本演练准备文档实例，将以下内容复制到文本编辑器，并将其保存为文本文件。 请确保将所有行都复制源的步骤，并返回回车符。  

```
PO1999-10-20
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952
US        Robert Smith        8 Oak Avenue        Old Town       PA 95819
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Confirm this is electric,ITEM926-AA|Baby Monitor|1|39.98|Confirm this is electric
```


## <a name="start-the-wizard"></a>启动向导  

1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  

2. 若要添加新的平面文件架构，请右键单击项目，并选择**添加**。 单击**新项**。  

3. 在中**添加新项**窗口中，执行以下操作：  

   1.  在中**类别**部分中，选择**架构文件**。  

   2.  在中**模板**部分中，选择**平面文件架构向导**。  

   3.  在中**名称**字段中，输入**PurchaseOrder.xsd**新架构。  

   4.  单击 **“添加”**。  

4. “BizTalk 平面文件架构向导”打开后，将显示“欢迎”页。   
   若要在以后运行该向导时跳过此屏幕，请选择**不再显示此简介页面**框。 单击 **“下一步”** 继续。  

## <a name="selecting-purchase-order-instance"></a>选择采购订单实例  

-   上**平面文件架构信息**屏幕上，选择你的实例并输入以下信息。 完成后，单击**下一步**以继续。  

    -   **实例文件：** 单击**浏览**按钮以查找将从其生成架构的平面文件。 浏览到包含演练先决条件部分中创建的文本文件的文件夹： 平面文件架构从文档实例创建。  

    -   **记录名称：** 类型**PO**一点，这是架构根名称。  

    -   **目标命名空间：** 类型**http://Flat_File_Project.PurchaseOrder**架构目标命名空间。  

    -   **代码页：** 选择**utf-8 (65001)** 的下拉列表选择列表中。  

    -   **计算以字节为单位的位置：** 选中此框，如果你想要通过字节来计算位置数据字段。 默认情况下，位置数据字段以字符为单位计算。 在本演练中，保留**单位计算位置以字节为单位**复选框未选中状态。  

## <a name="select-purchase-order-data"></a>选择采购订单数据  

-   上**选择文档数据**显示屏幕中，平面文件的内容。 选择用于创建架构，所需的数据，然后单击**下一步**。  

    > [!NOTE]
    >  如果你想要使用整个文档实例，可以按**CTRL-A**全。  

    > [!NOTE]
    >  检查**折长行**框如果想要查看整个文档实例内容在整个向导的编辑框中换行。  

    > [!NOTE]
    >  如果从交换实例创建架构，请只选择表示单个文档结构的部分。  

## <a name="delimit-purchase-order-record"></a>分隔采购订单记录  

-   如采购订单的每一行结尾回车换行符 (CRLF) 中，选择**按分隔符符号**，然后单击**下一步**上**选择记录格式**屏幕。  

## <a name="specify-purchase-order-record-property"></a>指定采购订单记录属性  

- 上**分隔记录**屏幕中，输入以下命令以定义架构的第一级，完成后，单击**下一步**。  

  - **子分隔符：** 选择 **{CR} {LF}**。  

    > [!NOTE]
    >  **子分隔符**属性是一个可编辑具有下拉选择列表框包含一组默认值。 **子分隔符**可以指定为字符或十六进制值。 例如，  **\\{** 或 **{0x0D0A}**。  

  - **转义符：** 转义符是取消其后的字符的任何特殊含义的单个字符。 请参阅[转义符](../core/escape-characters.md)有关详细信息。 将它保留为空，以用于演练。  

    > [!NOTE]
    >  使用时**\\**， **{，** 并 **}** 对于**子分隔符**或**转义符**、必须使用反斜杠。 例如，  **\\ \\，** 并 **\\{**。  

  - 检查**记录带有标记标识符**框，然后输入**PO**中**标记**。 在多个记录文件中， **PO**将用于标识各个记录。 单击 **“下一步”** 继续。  

    ![分隔的记录屏幕](../core/media/flatfileschemawizard-delimitedrecord1.gif "FlatFileSchemaWizard_DelimitedRecord1")  

## <a name="define-the-element-in-the-purchase-order-record"></a>定义采购订单记录中的元素  

1.  向导已标识了采购订单记录中的四个元素；您现在必须定义元素属性。 在第一行中，执行以下操作：  

    1.  类型**日期**有关**元素名称**。  

    2.  选择**Field 元素**有关**元素类型**。  

    3.  选择**日期**从下拉选择列表中为**数据类型**。  

2.  对以下元素重复执行步骤 a 至 c。 完成后，单击**下一步**。  

    |元素名称|元素类型|数据类型|  
    |------------------|------------------|---------------|  
    |**客户**|**重复记录**||  
    ||**忽略**||  
    |**项**|**记录**||  

     ![子元素屏幕](../core/media/flatfileschemawizard-childelements.gif "FlatFileSchemaWizard_ChildElements")  

    > [!NOTE]
    >  您可以选择多个行，然后更改其**元素类型**为单个类型通过使用鼠标和 SHIFT 或 CTRL 键。  

    > [!NOTE]
    >  单击后**下一步**上**子元素**屏幕中，您将无法再单击**回**重新定义或更改的子元素。 您需要关闭该向导，然后重新启动它来定义平面文件架构。  

3.  完成此过程的各个步骤后，将生成该架构的第一级，如以下屏幕快照所示。 现在已定义了三个唯一的元素，您还需要进一步定义采购订单记录中元素的子记录。 单击“下一步” 。  

     ![示例架构屏幕](../core/media/flatfileschemawizard-schema1.gif "FlatFileSchemaWizard_Schema1")  

## <a name="define-the-customer-record"></a>定义客户记录  

1.  因为我们定义**客户**元素作为**重复记录**类型并**项**元素作为**记录**键入 BizTalk平面文件架构向导现在将进一步定义这两个元素。 上**架构视图**屏幕上，选择**客户**，然后单击**下一步**以继续。  

2.  若要使用客户记录，您必须选择表示客户元素的数据。 由于客户记录是重复记录，因此客户记录的任何一行都可用于定义该记录。 选择客户数据的第一行，然后单击**下一步**以继续。  

3.  上**选择记录格式**页上，选择**按相对位置**，然后单击**下一步**。  

4.  该向导提供了一个用于显示和计算字段之间距离的可视化工具。 上**位置记录**页上，使用鼠标左键单击位置标记 10 来表示，名称字段的开始。 单击要表示其余数据字段的以下位置标记：  

    |字段名|位置标记|  
    |----------------|---------------------|  
    |street|30|  
    |城市|50|  
    |state|65|  
    |邮政编码|68|  

     单击 **“下一步”** 继续。  

     ![位置记录屏幕](../core/media/flatfileschemawizard-positionalrecord.gif "FlatFileSchemaWizard_PositionalRecord")  

5.  上**子元素**页上，指定的子元素的属性。 选择第一个行并键入**国家/地区**作为**元素名称**。 对于其他列，保留默认值。 键入以下值的其他属性**元素名称**:  

    |元素名称|ReplTest1|  
    |------------------|-----------|  
    |**customer_Child2**|**fullName**|  
    |**customer_Child3**|**街道**|  
    |**customer_Child4**|**城市**|  
    |**customer_Child5**|State|  
    |**customer_Child6**|**邮政编码**|  

     单击 **“下一步”** 继续。  

     ![子元素屏幕](../core/media/flatfileschemawizard-childelements2.gif "FlatFileSchemaWizard_ChildElements2")  

6.  客户记录的子元素随即创建，如以下屏幕快照所示。 单击**下一步**定义物品记录的子元素。  

     ![示例架构屏幕](../core/media/flatfileschemawizard-schema2.gif "FlatFileSchemaWizard_Schema2")  

#### <a name="define-the-items-record"></a>定义物品记录  

1. 上**架构视图**页上，选择**项**，然后单击**下一步**。  

2. 上**选择文档数据**页上，选择整行开头的项，然后单击**下一步**以定义其子元素。  

3. 上**选择记录格式**页上，选择**按分隔符符号**，然后单击**下一步**。  

4. 在“物品”记录中，逗号用于分隔各个物品。 因此，在**分隔记录**页上，输入以下内容定义物品记录。 完成后，单击**下一步**。  

   -   选择 **，** 从**子分隔符**下拉选择列表。  

   -   将保留**转义符**文本框保留为空。  

   -   选择**记录带有标记标识符**并键入**项**中**标记**。  

        在多个项记录中，**项**用于标识各个记录。  

5. 使用中的值**分隔记录**页上，向导标识两个子元素。 由于其中一个是重复记录，选择第一个元素，并输入**项**作为元素名称，然后选择**重复记录**从下拉列表选择列表**元素类型**. 列中保留其余默认值。 选择第二行，然后选择**忽略**从**元素类型**列表。 当您单击**下一步**，在架构中创建项记录的下一级别。 您还需要定义采购订单架构的最后一部分。  

6. 选择**项**，然后单击**下一步**继续**架构视图**页。  

7. 上**选择文档数据**页上，选择**ITEM872 AA&#124;Lawnmower&#124;1&#124;148.95&#124;确认这是电力**。 单击 **“下一步”** 继续。  

8. 上**选择记录格式**页上，选择**按分隔符符号**选项，因为由竖线分隔单个项 (&#124;)。  

9. 上**分隔记录**页上，输入以下内容定义物品记录。 完成后，单击**下一步**。  

    -   选择 **&#124;** 从**子分隔符**下拉选择列表。  

    -   将保留**转义符**文本框保留为空。  

10. 上**子元素**页上，向导已标识五个子元素。 选择第一行，并输入**productCode**有关**元素名称**。 对于其他列，请保留默认值。 为其余**元素名称属性**，键入以下内容：  

    |元素名称|ReplTest1|  
    |------------------|-----------|  
    |**item_Child2**|**description**|  
    |**item_Child3**|**数量**|  
    |**item_Child4**|**单价**|  
    |**item_Child5**|**说明**|  

     单击 **“下一步”** 继续。  

11. 您现在已定义了采购订单架构的所有节点。 上**架构视图**页上，单击**完成**。  

12. 您现在可以查看最终的采购订单架构了。 您还可以使用 BizTalk 架构编辑器优化该架构。 请参阅平面文件属性名表和属性表中的**Schema 节点属性**。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="summary"></a>“摘要”  
 在此演练中，您学习了如何使用“BizTalk 平面文件架构向导”从文档实例创建平面文件架构。  

## <a name="next-steps"></a>后续步骤  

### <a name="validate-po-instance"></a>验证 PO 实例  
 为了确保 PurchaseOrder.xsd 架构能够正确解析 PO 实例，请执行以下操作：  

1.  在解决方案资源管理器中右键单击**PurchaseOrder.xsd** ，然后选择**属性**。  

2.  在中**属性页**，请确保**输入实例文件名**字段指向演练先决条件部分中创建的 PO 实例的位置： 创建平面文件从文档实例的架构。 单击**确定**关闭对话框。  

3.  在解决方案资源管理器中右键单击**PurchaseOrder.xsd**，然后选择**验证实例**。 验证组件随即打开。  

4.  验证完成后，将向您提供一个链接，使用该链接可以查看基于用 PurchaseOrder.xsd 架构解析 PO 实例所得结果的 XML 输出。 若要查看 XML 输出，请按住 Ctrl，然后单击该链接。  

### <a name="create-pipelines-for-the-schema"></a>为架构创建管道  
 现在，您可以基于 PurchaseOrder.xsd 架构创建 BizTalk 应用程序使用的接收管道或发送管道。  

 若要创建新的管道，请参阅[如何创建新的管道](../core/how-to-create-a-new-pipeline.md)。 若要配置平面文件管道组件，请参阅[如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)并[如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)。  

## <a name="see-also"></a>请参阅  
 [如何使用 BizTalk 平面文件架构向导](../core/how-to-use-biztalk-flat-file-schema-wizard.md)   
 [使用“BizTalk 平面文件架构向导”创建架构](../core/creating-schemas-using-biztalk-flat-file-schema-wizard.md)