---
title: 如何使用 BizTalk 平面文件架构向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7cb8b18-266d-422e-bdb8-1efefb6b4c8e
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28e0c95087c3471e29d0d487171ce30ff92d46eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383581"
---
# <a name="how-to-use-biztalk-flat-file-schema-wizard"></a>如何使用 BizTalk 平面文件架构向导
在以前版本的 BizTalk Server 中，您必须手动将批注添加到 XML 架构定义语言 (XSD) 架构在 BizTalk 架构编辑器中以使这些架构可以理解的平面文件管道组件，例如平面文件拆装器和平面文件组装器。 您仍然可以这样做使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]架构编辑器。 若要减少的手动步骤和创建解决方案所需的时间，您可以使用 BizTalk 平面文件架构向导，它提供以下功能：  
  
-   使用真实的平面文件实例作为输入。  
  
-   包括用于处理分隔和位置平面文件架构的可视化设计图面。  
  
-   向架构添加元素和定义平面文件相关的批注，以交互方式使用可重入的基于向导的过程。  
  
-   支持标记标识符、 字符分隔符和十六进制分隔符。  
  
-   自动确定标记标识符的偏移量以及子级的分隔顺序。  
  
-   为文件格式提供预览功能。  
  
-   使您可以选择交换实例要用于定义平面文件架构中的首选子数据。  
  
## <a name="how-to-start-the-biztalk-flat-file-schema-wizard"></a>如何启动 BizTalk 平面文件架构向导  
 您可以从任一 Microsoft Visual Studio 解决方案资源管理器或从 BizTalk 架构编辑器启动向导。  
  
#### <a name="to-start-the-wizard-from-solution-explorer"></a>若要从解决方案资源管理器启动向导  
  
1. 在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  
  
2. 若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。  
  
3. 单击**新项。**  
  
    ![解决方案资源管理器菜单](../core/media/flatfileschemawizard-01.gif "FlatFileSchemaWizard_01")  
  
4. 在中**添加新项**窗口中，执行以下操作：  
  
   1.  在中**类别**部分中，选择**架构文件**。  
  
   2.  在中**模板**部分中，选择**平面文件架构向导**。  
  
   3.  在中**名称**文本框中，键入的新架构的名称。  
  
   4.  单击 **“添加”**。  
  
        BizTalk 平面文件架构向导将打开。  
  
#### <a name="to-start-the-wizard-from-the-schema-editor"></a>从架构编辑器中启动向导  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开**解决方案资源管理器**。  
  
2. 若要添加新的平面文件架构，右键单击 BizTalk 项目，然后选择**添加**。 选择**新项**然后单击**新项**。  
  
3. 在中**添加新项**窗口中，执行以下操作：  
  
   1.  在中**类别**部分中，选择**架构文件**。  
  
   2.  在中**模板**部分中，选择**平面文件架构**。  
  
   3.  在中**名称**文本框中，键入的新架构的名称。  
  
   4.  单击 **“添加”**。  
  
   5.  右键单击**根**，然后选择**平面文件实例中定义的记录**。  
  
        BizTalk 平面文件架构向导现在开始。  
  
> [!NOTE]
>  如果必须在架构编辑器中打开一个工作架构，您需要做是右键单击所选的节点，然后选择**平面文件实例中定义的记录**。  
  
> [!NOTE]
>  **平面文件实例中定义的记录**选项启用所选的节点是否不包含子元素的记录。 如果所选的节点具有子元素，该向导将删除所有当前的子元素，并生成新的。 向导将提示您确认删除现有的子元素之前。  
  
## <a name="considerations-for-using-the-flat-file-schema-wizard"></a>使用平面文件架构向导的注意事项  
 本部分介绍使用 BizTalk 平面文件架构向导时应考虑的问题。  
  
### <a name="working-with-multibyte-character-set-mbcs"></a>使用多字节字符集 (MBCS)  
 默认情况下**单位计算位置以字节为单位**复选框处于未选中状态，在平面文件架构信息屏幕上。 该向导来计算位置数的字符;这意味着，如果你的位置平面文件实例中有 MBCS 字符，位置不正确计算位置数。 通过选择**单位计算位置以字节为单位**复选框，向导将显示 MBCS 字符，并指示其位置长度。 字符占据一个位置上显示和圆点符号"•"填充剩余的长度。 填充的圆点符号的数将取决于在双字节字符中保存的文件设置 (DBCS)、 Unicode 或 utf-8 格式。  
  
### <a name="code-pages-supported-in-the-flat-file-schema-wizard"></a>支持在平面文件架构向导中的代码页  
 下面是在向导的受支持的代码页的列表：  
  
-   阿拉伯语 (1256)  
  
-   ASCII (20127)  
  
-   波罗的语 (1257)  
  
-   大 Endian UTF16 (1201)  
  
-   中部语 (1250)  
  
-   西里尔语 (1251)  
  
-   希腊语 (1253)  
  
-   希伯来语 (1255)  
  
-   日语 Shift JIS (932)  
  
-   朝鲜语 (949)  
  
-   小 Endian UTF16 (1200)  
  
-   简化的中文-GBK (936)  
  
-   简体中文 GB18030 (54936)  
  
-   泰语 (874)  
  
-   传统-Chinese-BIG5 (950)  
  
-   土耳其语 (1254)  
  
-   UTF-7 (65000)  
  
-   UTF-8 (65001)  
  
-   越南语 (1258)  
  
-   西欧 (1252)  
  
### <a name="record-types-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的记录类型  
 平面文件不能包含在位置记录内的分隔的记录。 该向导是基于重入，因为中的定义的类型的单选按钮**按分隔符符号**并**按相对位置**启用或禁用的父记录的格式在向导中所定义子级。 例如，  
  
-   如果针对分隔记录的子级运行该向导，将选择这两个单选按钮。  
  
-   如果针对位置记录的子级运行该向导**按分隔符符号**单选按钮被清除。  
  
### <a name="delimiter-symbols-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的分隔符符号  
 子分隔符属性下拉列表包含具有以下常见的分隔符：  
  
- {CR}{LF}  
  
- {CR}  
  
- {LF}  
  
- {TAB}  
  
- {SPACE}  
  
- {0x1A}  
  
- &#124;  
  
- 、  
  
- ;  
  
  此属性的默认值为 {CR} {LF}。 属性也是一个可编辑的文本框，以便可以将子分隔符指定为一系列字符或字符的十六进制值。 使用子分隔符的字符的一个示例是"a"或"street"。 使用以下格式指定十六进制分隔符：  
  
- {0xnnnn}。 例如，{0x0D} {0x0A}、 {0x09} 或 {0x20}。  
  
  使用十六进制值序列的示例是 {0x0D} {0x0A}、 {0x09} {0x20}。  
  
  如果使用的符号\\，{，或} 用作分隔符，您还必须放置分隔符符号前面一个反斜杠符号，否则将收到一条错误消息。 例如，  
  
- \\\\\\{，或\\}。  
  
### <a name="relative-positions-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的相对位置  
  
#### <a name="setting-position-markers"></a>设置位置标记  
 用鼠标左键单击位置选择框中，若要设置新的位置标记线的位置标记。 位置标记表示为一条实线。 默认情况下，位置标记线位于位置 0 处的记录的开头。 若要删除现有的位置标记线，用鼠标左键单击它。  
  
### <a name="escape-characters-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的字符进行转义  
 转义符是字符的取消其后的任何特殊含义的单个字符。 有关详细信息，请参阅[转义符](../core/escape-characters.md)下的主题[方式解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。 使用向导中的转义符属性，以指定要分析的平面文件实例时使用的转义字符。 默认值为 null，表示使用默认的转义符在架构级别定义。  
  
 为字符或十六进制值，可以指定转义符。 使用以下格式指定十六进制值：  
  
- {0xnnnn}。 例如，{0x0D} {0x0A}、 {0x09} 或 {0x20}。  
  
  如果使用的符号\\，{，或} 用作转义字符，您必须放置分隔符符号前面一个反斜杠符号，否则将收到一条错误消息等  
  
- \\\\, \\{, \\}.  
  
### <a name="child-elements-in-the-flat-file-schema-wizard"></a>平面文件架构向导中的子元素  
 每个子元素包含**元素名称**，**元素类型**，**数据类型**并**内容**。 您使用**元素名称**文本框中键入有意义的名称的节点。 **元素类型**是以下值的下拉列表：  
  
- **字段元素**:指定将在架构中作为元素创建此节点。  
  
- **字段属性**:指定将在架构中作为属性创建此节点。  
  
- **记录**:指定将在架构中创建无子级的记录。  
  
- **重复记录**:指定将在架构中创建无子级的记录和其最大出现次数设置为**Unbounded**。  
  
- **忽略**:执行任何操作将为此节点在架构中创建。  
  
  默认情况下的所有元素都属于类型**Field 元素**是其数据类型**字符串**。  
  
> [!NOTE]
>  子元素可以声明为**字段属性**仅在没有任何子级之前它声明为**字段元素**，**记录**或**重复记录**。  
  
> [!NOTE]
>  您将看到的前面一个感叹号**子节点**如下例所示：  
  
-   **字段属性**定义后**Field 元素**，**记录，** 或者**重复记录**。  
  
-   子元素不具有一个名称。  
  
-   子元素具有重复的名称。  
  
-   子元素的所选的数据类型不适合的内容。  
  
## <a name="see-also"></a>请参阅  
 [“BizTalk 平面文件架构向导”演练](../core/biztalk-flat-file-schema-wizard-walkthrough.md)