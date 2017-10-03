---
title: "如何使用 BizTalk 平面文件架构向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff7d87959bd39b9040a495022c2b7bf352954848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a>如何使用“BizTalk 平面文件架构向导”
在以前的 BizTalk Server 版本中，您必须在 BizTalk 架构编辑器中手动向 XML 架构定义 (XSD) 语言架构添加批注，才能使平面文件管道组件（例如，平面文件拆装器和平面文件组装器）理解这些架构。 你仍然可以这样做使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构编辑器。 为了减少创建解决方案的手动步骤和所需时间，您可以使用“BizTalk 平面文件架构向导”，该向导提供以下功能：  
  
-   将真实的平面文件实例用作输入内容。  
  
-   包括一个用于处理分隔平面文件架构和位置平面文件架构的可视化设计图面。  
  
-   使用基于向导的重入过程以交互方式向架构添加元素和定义与平面文件相关的批注。  
  
-   支持标记标识符、字符分隔符和十六进制分隔符。  
  
-   自动确定标记标识符的偏移量以及子级的分隔顺序。  
  
-   提供文件格式的预览功能。  
  
-   可用于选择交换实例中的首选子数据，以用于定义平面文件架构。  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a>如何启动“BizTalk 平面文件架构向导”  
 您可以从 Microsoft Visual Studio 解决方案资源管理器或 BizTalk 架构编辑器启动该向导。  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a>从解决方案资源管理器启动向导  
  
1.  在 Microsoft 中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  
  
2.  若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。  
  
3.  单击**新项。**  
  
     ![解决方案资源管理器菜单](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")  
  
4.  在**添加新项**窗口中，执行以下操作：  
  
    1.  在**类别**部分中，选择**架构文件**。  
  
    2.  在**模板**部分中，选择**平面文件架构向导**。  
  
    3.  在**名称**文本框中，键入一个新的架构的名称。  
  
    4.  单击 **“添加”**。  
  
         “BizTalk 平面文件架构向导”随即打开。  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a>从架构编辑器启动向导  
  
1.  在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  
  
2.  若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。 选择**新项**单击**新项**。  
  
3.  在**添加新项**窗口中，执行以下操作：  
  
    1.  在**类别**部分中，选择**架构文件**。  
  
    2.  在**模板**部分中，选择**平面文件架构**。  
  
    3.  在**名称**文本框中，键入一个新的架构的名称。  
  
    4.  单击 **“添加”**。  
  
    5.  右键单击**根**和选择**从平面文件实例定义记录**。  
  
         此时“BizTalk 平面文件架构向导”启动。  
  
> [!NOTE]
>  如果你具有在架构编辑器中打开的工作架构，你需要做是用鼠标右键单击所选的节点，然后选择**从平面文件实例定义记录**。  
  
> [!NOTE]
>  **从平面文件实例定义记录**如果所选的节点没有子元素记录启用选项。 如果所选节点有子元素，该向导会删除所有当前子元素，然后生成新的子元素。 在删除现有子元素之前，向导会提示您进行确认。  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a>使用平面文件架构向导的注意事项  
 本部分介绍您在使用“BizTalk 平面文件架构向导”时应注意的问题。  
  
### <a name="working-with-multibyte-character-set-mbcs"></a>使用多字节字符集 (MBCS)  
 默认情况下，**计数以字节为单位的位置**复选框未选中平面文件架构信息屏幕上。 该向导按字符来计算位置数，这意味着如果您的位置平面文件实例中有 MBCS 字符，则将无法正确计算位置数。 通过选择**计数以字节为单位的位置**复选框，向导显示 MBCS 字符替换其位置的长度的其他指示。 字符占据屏幕的一个位置 ， 而剩下的长度将用圆点符号“•” 填充 。 具体填充多少圆点符号取决于文件是以双字节字符集 (DBCS)、Unicode，还是 UTF-8 格式保存的。  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a>平面文件架构向导中支持的代码页  
 以下是该向导支持的代码页的列表：  
  
-   阿拉伯语 (1256)  
  
-   ASCII (20127)  
  
-   波罗的语 (1257)  
  
-   Big-Endian-UTF16 (1201)  
  
-   中部欧洲 (1250)  
  
-   西里尔语 (1251)  
  
-   希腊语 (1253)  
  
-   希伯来语 (1255)  
  
-   日语 Shift JIS (932)  
  
-   韩语 (949)  
  
-   Little-Endian-UTF16 (1200)  
  
-   简体中文 GBK (936)  
  
-   简体中文 GB18030 (54936)  
  
-   泰语 (874)  
  
-   繁体中文 BIG5 (950)  
  
-   土耳其语 (1254)  
  
-   UTF-7 (65000)  
  
-   UTF-8 (65001)  
  
-   越南语 (1258)  
  
-   西欧语 (1252)  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的记录类型  
 平面文件不能将分隔记录包含在位置记录中。 由于该向导后可重入基于中的定义的类型的单选按钮**按分隔符符号**和**按相对位置**启用或禁用的父记录的格式在向导中定义子级。 例如：  
  
-   如果针对分隔记录的子级运行该向导，则两个单选按钮都是选中的。  
  
-   如果子级的位置的记录，运行该向导**按分隔符符号**单选按钮处于未选中状态。  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的分隔符符号  
 子分隔符属性的下拉列表包含以下常见的分隔符：  
  
-   {CR}{LF}  
  
-   {CR}  
  
-   {LF}  
  
-   {TAB}  
  
-   {SPACE}  
  
-   {0x1A}  
  
-   &#124;  
  
-   、  
  
-   ;  
  
 此属性的默认值为 {CR}{LF}。 该属性还有一个可编辑的文本框，这样您就可以将子分隔符指定为字符序列或字符的十六进制值。 例如，将字符“a”或“street”用作子分隔符。 十六进制分隔符用以下格式指定：  
  
-   {0xnnnn}。 例如，{0x0D} {0x0A}，{为 0x09} 或 {0x20}。  
  
 例如，使用十六进制值序列 {0x0D}{0x0A}, {0x09}{0x20}。  
  
 如果使用符号\\，{，或} 作为分隔符，则必须将放置分隔符符号的前面附加的反斜杠符号，否则您将收到一条错误消息。 例如：  
  
-   \\\\\\{，或\\}。  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的相对位置  
  
#### <a name="setting-position-markers"></a>设置位置标记  
 用鼠标左键单击位置选择框中的某个位置标记来设置新的位置标记线。 位置标记用实线表示。 默认情况下，位置标记线位于记录开头的位置 0 处。 若要删除某一现有位置标记行，用鼠标右键单击它。  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的转义符  
 ：转义符是取消其后紧跟字符的任何特殊意义的单个字符。 有关详细信息，请参阅[转义字符](../core/escape-characters.md)下的主题[如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。 您可以在向导中使用转义符属性指定在解析平面文件实例时使用的转义符。 默认值为空，这表示将使用在架构级别定义的默认转义符。  
  
 转义符可指定为字符或十六进制值。 十六进制值用以下格式指定：  
  
-   {0xnnnn}。 例如，{0x0D}{0x0A}、{0x09} 或 {0x20}。  
  
 如果使用符号\\，{，或} 用作转义字符，则必须将放置分隔符符号的前面附加的反斜杠符号，否则将收到一条错误消息例如，  
  
-   \\\\, \\{, \\}.  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的子元素  
 每个子元素包含**元素名称**，**元素类型**，**数据类型**和**内容**。 你使用**元素名称**文本框中键入有意义的名称的节点。 **元素类型**是使用以下值的下拉列表：  
  
-   **字段元素**： 指定将一个元素的架构中创建此节点。  
  
-   **字段特性**： 指定将属性的架构中创建此节点。  
  
-   **记录**： 指定将在架构中创建包含无子级的记录。  
  
-   **重复记录**： 指定将在架构中创建包含无子级的记录，并且其最大值的匹配项设置为**Unbounded**。  
  
-   **忽略**： 执行任何操作将在此节点的架构中创建。  
  
 默认情况下所有元素的类型都是**Field 元素**和它们的数据类型是**字符串**。  
  
> [!NOTE]
>  子元素可以声明为**字段特性**仅在没有任何子级才将其声明为**字段元素**，**记录**或**重复记录**。  
  
> [!NOTE]
>  你将看到前端中的叹号**子节点**如下例所示：  
  
-   **字段特性**后定义**Field 元素**，**记录，**或**重复记录**。  
  
-   子元素没有名称。  
  
-   子元素有重复的名称。  
  
-   子元素的选定数据类型对内容不合适。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 平面文件架构向导演练](../core/biztalk-flat-file-schema-wizard-walkthrough.md)