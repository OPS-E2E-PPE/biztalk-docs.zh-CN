---
title: 修改 EDI 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6fa33c5e-17ca-4aaf-a1ca-1972a9bb45ac
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3330ca9bf2b630ef71fde35b6be25386f68fd011
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394403"
---
# <a name="modifying-edi-schemas"></a>修改 EDI 架构
您可以修改现有 EDI 架构中附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在您和您的贸易合作伙伴有对标准架构的修改达成一致，并且可能已更改相关的消息实现指南 (MIG) 文件，你可以修改架构的 BizTalk 编辑器中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]。  
  
> [!NOTE]
>  一些架构修改 （跨字段验证和 HIPAA 子文档拆分） 涉及对 EDI 架构中批注的更改。 这些更改不能成为在 BizTalk 编辑器中，但可以在诸如记事本之类的文本编辑器中进行。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
## <a name="schema-naming-convention"></a>架构命名约定  
 EDI 架构由其根名称和命名空间标识。 不能部署具有相同的根名称和命名空间相同的 BizTalk 组中的两个架构。 不能修改任何 EDI 架构的根名称或将添加到的根名称，因为根名称必须包含的版本和文档中的标准命名约定的类型。 因此，如果你想要部署具有相同的根名称相同的 BizTalk 组中的两个架构，则必须为每个使用不同的命名空间。  
  
 不常见的部署在同一个 BizTalk 组中的不同版本相同的架构为两个或多个不同的贸易合作伙伴公司。 在这种情况下，两个架构将具有相同的版本和文档类型相同。 若要部署这两个架构，必须具有不同的命名空间为每个架构。  
  
## <a name="edi-schema-changes"></a>EDI 架构更改  
 可以对 EDI 架构中进行以下更改[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]:  
  
|执行的操作|操作|  
|----------------|-------------|  
|更改枚举<br /><br /> （例如代码列表中的值列表）|在属性元素中，打开**枚举编辑器**和添加值，或从枚举列表中删除一个值。|  
|更改数据元素的可选性|更改**最小出现次数**属性。 将其更改为 0，以使字段成为可选或为 1，以使它所必需。|  
|更改数据元素可以出现在文件最大次数|更改**Max Occurs**属性。|  
|更改数据元素中的字符数|更改**长度**属性。|  
|更改数据元素的数据类型|更改**Base Data Type**或**日期类型**属性。|  
|添加自定义字段|将插入一个子字段元素架构节点并设置其属性。 **注意：** 不允许将子字段属性添加到 EDI 架构中的记录，因为将无法保证元素的顺序。 尝试添加子字段属性将导致无效架构。 仅可以将子字段元素添加到 EDI 架构中的记录。|  
|添加自定义记录|插入子记录架构节点、 设置其属性，以及如何将子字段元素。|  
|删除自定义字段或记录|删除自定义字段或自定义记录及其子字段元素。|  
|启用跨字段验证|在架构的 appinfo 部分批注中设置的跨字段验证标志**是**。 此标志为**X12ConditionDesignator_Check** （对于 X12 或 HIPAA 架构） 或**EdifactDependencyRule_Check** （针对 EDIFACT 架构）。<br /><br /> 通过指定关系条件 （x12 和 HIPAA） 或依赖规则 (EDIFACT) 中启用跨字段验证特定元素。 有关详细信息，请参阅[配置跨字段验证](../core/configuring-cross-field-validation.md)。<br /><br /> 此外需要设置**Edi 类型验证**属性设置为**是**。<br /><br /> 默认情况下，对于 HIPAA 架构启用跨字段验证。|  
|启用 HIPAA 子文档拆分|在其中一个可以设置子文档拆分的 HIPAA 架构中，设置**subdocument_break**并**Split_Without_Sibling_Data**到该架构属性**是**并**subdocument_creation_break**到架构中的特定元素的属性**是**。<br /><br /> 此外需要设置**入站批处理选项**协议属性设置为**交换拆分为事务集**。<br /><br /> 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。|  
|向 HIPAA 文档添加触发器字段|您可以允许 EDI 拆装器以便创建段的 HIPAA 文档中，根据限定元素称为触发器字段的唯一 XML 记录。 必须指定描述段和触发器值，以便为该段创建唯一 XML 记录的属性。 有关详细信息，请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md)。|  
|将一个段添加到 X12 事务集|当将一个新段添加到 X12 事务集段名称的前三个字符用作段标识符。 因此，我们建议您命名分段，从而使前三个字符都唯一。|  
|向 HIPAA 事务集添加循环|在向 HIPAA 事务集添加一个新的循环，我们建议命名循环在名称中包括"Loop"。 循环的示例格式为"TS837_2010AB_Loop"。 **注意：** 在循环中的第一个段是必需的 （段的 minOccurs 必须等于 1） 以避免混乱。|  
|向 HIPAA 事务集添加任何顺序循环|当事务集具有不同语义的等效分段时，您必须在 SubLoop 中定义它们。 使用 XML 批注的 SubLoop \<xs: all\>允许等效分段以任何顺序出现。<br /><br /> 我们建议您命名任何顺序循环在循环名称中包含"SubLoop"。 示例格式为"TS837Q1_2010A_SubLoop"**注意：** 任何顺序循环的元素在循环中必须仅出现一次。 同级 SubLoop 必须设置为 1，以避免混乱的 maxOccurs。|  
  
### <a name="to-modify-an-existing-edi-schema-in-biztalk-editor"></a>若要修改现有 EDI 架构在 BizTalk 编辑器中  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，添加你想要修改为一个项目并在 BizTalk 编辑器中打开该架构的架构。  
  
   > [!NOTE]
   >  可以以图形方式显示该架构，通过单击**EDI**架构编辑器屏幕底部的选项卡。 它是架构的更轻松地导航使用此表格格式的节点。  
  
2. 若要更改数据元素或记录的属性，单击左窗格中的 BizTalk 编辑器中的相应节点和属性窗口中更改其属性。  
  
3. 若要更改枚举中的值，请选择中的枚举**属性**窗格中，然后单击省略号以打开**枚举编辑器**。 将添加到或根据需要确保在每行一个值，从列表中的值，删除**值**窗格。 单击“确定” 。  
  
4. 若要将自定义字段添加到架构中，右键单击 BizTalk 编辑器的控制台树中的记录节点，指向**插入 Schema 节点**，然后单击**子字段元素**。 命名该数据元素，并将数据元素应用到记录中的相应位置。 根据需要设置自定义字段属性的属性。  
  
   > [!NOTE]
   >  不允许将子字段属性添加到 EDI 架构中的记录，因为将无法保证元素的顺序。 尝试添加子字段属性将导致无效架构。  
  
5. 若要将自定义记录添加到架构中，右键单击控制台树中的架构编辑器中的记录节点，指向**插入 Schema 节点**，然后单击**子记录**。 命名该记录，然后将该记录拖至架构中的相应位置。 将至少一个数据元素添加到该记录。 根据需要设置自定义记录的属性。  
  
6. 对架构进行所需的更改之后, 你可以单击根节点适用于架构属性的目标命名空间 (\<架构\>)，然后更改**Target Namespace**属性。  
  
7. 保存该架构。  
  
8. 通过右键单击解决方案资源管理器中的架构，并单击验证架构**验证架构**。  
  
   > [!NOTE]
   >  **验证架构**命令将验证 EDI 架构，因为**架构编辑器扩展**属性的根节点 (\<架构\>) 设置为**EDI架构编辑器扩展**。  
  
### <a name="to-modify-annotation-properties-in-an-existing-edi-schema"></a>若要修改现有 EDI 架构中的批注属性  
  
1.  在诸如记事本之类的文本编辑器中打开该架构。  
  
2.  若要启用跨字段验证，继续执行，如下所示。 有关详细信息，请参阅[配置跨字段验证](../core/configuring-cross-field-validation.md)。  
  
    1.  在架构顶部的 appinfo 批注中，将设置跨字段验证标志 (任一**X12ConditionDesignator_Check**针对 X12 或 HIPAA 架构或**EdifactDependencyRule_Check**对于 EDIFACT架构） 到**是**。  
  
        > [!NOTE]
        >  跨字段验证标志**是**默认情况下为 BizTalk Server HIPAA 架构。  
  
    2.  在特定元素的批注，指定关系条件 (X 12 或 HIPAA） 或依赖规则 (EDIFACT) 的元素。 有关这些设置的详细信息，请参阅[跨字段-段验证](../core/cross-field-segment-validation.md)。  
  
        > [!NOTE]
        >  在中**验证**页 (下**事务集设置**部分) 的单向协议选项卡**协议属性**相关协议的对话框请确保**EDI 类型验证**选择属性。  
  
3.  若要启用 HIPAA 子文档拆分，继续执行，如下所示。 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。  
  
    1.  在架构顶部的 appinfo 批注中，设置**subdocument_break**并**Split_Without_Sibling_Data**到标志**是**。  
  
    2.  中的特定元素的 appinfo 批注，请参阅**subdocument_creation_break**标记，用于**是**。  
  
        > [!NOTE]
        >  在中**本地主机设置**页 (下**交换设置**部分) 的单向协议选项卡**协议属性**为相关的对话框协议，请确保**入站批处理选项**属性设置为**交换拆分为事务集**。  
  
## <a name="see-also"></a>请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)