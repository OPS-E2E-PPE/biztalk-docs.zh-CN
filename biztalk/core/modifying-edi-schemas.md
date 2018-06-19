---
title: 修改 EDI 架构 |Microsoft 文档
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
ms.openlocfilehash: de196288f3f1d4475e6859e2440e4b03b1e521dc
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009590"
---
# <a name="modifying-edi-schemas"></a>修改 EDI 架构
您可以修改 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 附带的现有 EDI 架构。 如果您和您的贸易合作伙伴对标准架构的修改达成一致，并且可能已更改相关的消息实现指南 (MIG) 文件，则可在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的 BizTalk 编辑器中修改架构。  
  
> [!NOTE]
>  一些架构修改（跨字段验证和 HIPAA 子文档拆分）包含对 EDI 架构中批注的更改。 这些更改无法在 BizTalk 编辑器中完成，但可以在文本编辑器（例如记事本）中完成。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
## <a name="schema-naming-convention"></a>架构命名约定  
 EDI 架构通过其根名称和命名空间进行标识。 您不能使用相同的根名称和命名空间将两个架构部署在同一个 BizTalk 组中。 您不能修改任何 EDI 架构的根名称或向根名称添加内容，因为根名称必须包含符合标准命名约定的版本和文档类型。 因此，如果您希望使用相同的根名称将两个架构部署在同一个 BizTalk 组中，则必须为每个架构使用不同的命名空间。  
  
 对于公司而言，为两个或更多个不同的贸易合作伙伴将同一架构的不同版本部署在同一个 BizTalk 组中的情况并不少见。 在这种情况下，两个架构将具有相同的版本和相同的文档类型。 若要部署这两个架构，每个架构必须具有不同的命名空间。  
  
## <a name="edi-schema-changes"></a>EDI 架构更改  
 您可以在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中对 EDI 架构进行以下更改：  
  
|执行的操作|操作|  
|----------------|-------------|  
|更改枚举<br /><br /> （例如，代码列表中的值列表）|中的元素的属性中，打开**枚举编辑器**并添加一个值，或从枚举列表中删除值。|  
|更改数据元素的可选性|更改**最小出现次数**属性。 将其更改为 0 可使字段成为可选字段；将其更改为 1 可使字段成为必需字段。|  
|更改数据元素可以在文件中出现的最大次数|更改**Max Occurs**属性。|  
|更改数据元素中的字符数|更改**长度**属性。|  
|更改数据元素的数据类型|更改**基数据类型**或**日期类型**属性。|  
|添加自定义字段|插入一个子字段元素架构节点并设置其属性。 **注意：** 将子字段特性添加到 EDI 架构中的记录不允许的因为将不能保证元素的序列。 尝试添加子字段属性将导致无效架构。 只能将子字段元素添加到 EDI 架构的记录中。|  
|添加自定义记录|插入一个子记录架构节点并设置其属性，然后添加子字段元素。|  
|删除自定义字段或记录|删除自定义字段或自定义记录及其子字段元素。|  
|启用跨字段验证|批注中的架构的 appinfo 部分中设置跨字段验证标志**是**。 此标志是**X12ConditionDesignator_Check** （对于 X12 或 HIPAA 架构） 或**EdifactDependencyRule_Check** （对于 EDIFACT 架构）。<br /><br /> 通过指定关系条件（X12 和 HIPAA）或依赖规则 (EDIFACT) 为特定元素启用跨字段验证。 有关详细信息，请参阅[配置跨字段验证](../core/configuring-cross-field-validation.md)。<br /><br /> 你还需要设置**Edi 类型验证**属性**是**。<br /><br /> 默认情况下，对 HIPAA 架构启用跨字段验证。|  
|启用 HIPAA 子文档拆分|在其中一个可以设置子文档拆分中的 HIPAA 架构，设置**subdocument_break**和**Split_Without_Sibling_Data**到架构的属性**是**与**subdocument_creation_break**到架构中的特定元素的属性**是**。<br /><br /> 你还需要设置**入站批处理选项**协议属性**将交换拆分为事务集**。<br /><br /> 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。|  
|向 HIPAA 文档添加触发器字段|您可以让 EDI 拆装器根据限定元素（称为触发器字段）为 HIPAA 文档中的一段内容创建唯一的 XML 记录。 必须指定描述段的属性和触发器值，从而为该段创建唯一的 XML 记录。 有关详细信息，请参阅[HIPAA 架构触发器字段批注](../core/hipaa-schema-trigger-field-annotations.md)。|  
|向 X12 事务集添加分段|在向 X12 事务集添加新分段时，分段名称的前三个字符用作分段标识符。 因此，建议您命名分段时，前三个字符是唯一的。|  
|向 HIPAA 事务集添加循环|在向 HIPAA 事务集添加新循环时，建议命名循环时名称中包括“Loop”。 循环的示例格式为“TS837_2010AB_Loop”。 **注意：** 在循环中的第一个段是必需的 （段的 minOccurs 必须等于 1） 以避免多义性。|  
|向 HIPAA 事务集添加“任何顺序循环”|当事务集包含具有不同语义的等效分段时，必须在 SubLoop 中字义这些分段。 与 XML 批注的 SubLoop \<xs:all\>允许等效线段以任意顺序出现。<br /><br /> 建议您在命名“任意顺序循环”时，在循环名称中包含“SubLoop”。 示例格式是"TS837Q1_2010A_SubLoop"**注意：** 任何顺序循环的元素必须只出现一次在循环内。 同级 SubLoop 必须将最大出现次数设置为 1 以避免混乱。|  
  
### <a name="to-modify-an-existing-edi-schema-in-biztalk-editor"></a>在 BizTalk 编辑器中修改现有 EDI 架构  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，将您希望修改的架构添加到项目中，并在 BizTalk 编辑器中打开该架构。  
  
    > [!NOTE]
    >  可以通过单击以图形方式显示架构**EDI**在架构编辑器屏幕底部的选项卡。 使用此表格格式可更轻松地导航架构节点。  
  
2.  若要更改数据元素或记录的属性，请单击 BizTalk 编辑器左窗格中的相应节点，然后在“属性”窗口中更改其属性。  
  
3.  若要更改枚举中的值，选择中的枚举**属性**窗格中，然后单击省略号以打开**枚举编辑器**。 添加或删除从列表中的值，根据需要确保在每一行上一个值**值**窗格。 单击 **“确定”**。  
  
4.  若要将自定义字段添加到架构中，右键单击 BizTalk 编辑器的控制台树中的记录节点，指向**插入架构节点**，然后单击**子字段元素**。 命名该数据元素，然后将该数据元素拖至该记录中的相应位置。 根据需要设置自定义字段的属性。  
  
    > [!NOTE]
    >  不允许将子字段属性添加到 EDI 架构中的记录，因为元素顺序将无法保证。 尝试添加子字段属性将导致无效架构。  
  
5.  若要将自定义记录添加到架构中，右键单击控制台树中的架构编辑器中的记录节点，指向**插入架构节点**，然后单击**子记录**。 命名该记录，然后将该记录拖至该架构中的相应位置。 至少将一个数据元素添加到记录。 根据需要设置自定义记录的属性。  
  
6.  对架构进行所需的更改后, 可以更改通过单击根节点适用于架构属性的目标命名空间 (\<架构\>)，然后将更改**目标 Namespace**属性。  
  
7.  保存该架构。  
  
8.  通过右键单击解决方案资源管理器中的架构，并单击验证的架构**验证架构**。  
  
    > [!NOTE]
    >  **验证架构**命令将验证 EDI 架构，因为**架构编辑器扩展**的根节点的属性 (\<架构\>) 设置为**EDI架构编辑器扩展**。  
  
### <a name="to-modify-annotation-properties-in-an-existing-edi-schema"></a>修改现有 EDI 架构中的批注属性  
  
1.  在文本编辑器（如记事本）中打开该架构。  
  
2.  若要启用跨字段验证，请按如下所示继续操作。 有关详细信息，请参阅[配置跨字段验证](../core/configuring-cross-field-validation.md)。  
  
    1.  在顶部的架构的 appinfo 批注，设置跨字段验证标志 (任一**X12ConditionDesignator_Check** X12 或 HIPAA 架构或**EdifactDependencyRule_Check**对于 EDIFACT架构） 到**是**。  
  
        > [!NOTE]
        >  跨字段验证标志**是**默认情况下，BizTalk Server HIPAA 架构。  
  
    2.  在特定元素的批注中，为元素指定关系条件（X12 或 HIPAA）或依赖规则 (EDIFACT)。 有关这些设置的详细信息，请参阅[交叉字段段验证](../core/cross-field-segment-validation.md)。  
  
        > [!NOTE]
        >  在**验证**页 (下**事务设置设置**部分) 的单向协议选项卡**协议属性**相关协议的对话框中请确保**EDI 类型验证**选择属性。  
  
3.  若要启用 HIPAA 子文档拆分，请按如下所示继续操作。 有关详细信息，请参阅[拆分 HIPAA 子文档](../core/splitting-hipaa-subdocuments.md)。  
  
    1.  在顶部的架构的 appinfo 批注，设置**subdocument_break**和**Split_Without_Sibling_Data**标志到**是**。  
  
    2.  中的特定元素的 appinfo 批注，请参阅**subdocument_creation_break**标志切换为**是**。  
  
        > [!NOTE]
        >  在**本地主机设置**页 (下**交换设置**部分) 的单向协议选项卡**协议属性**为相关的对话框协议，请确保**入站批处理选项**属性设置为**将交换拆分为事务集**。  
  
## <a name="see-also"></a>另请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)