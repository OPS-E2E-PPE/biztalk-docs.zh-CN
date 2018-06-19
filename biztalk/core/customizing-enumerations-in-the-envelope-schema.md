---
title: 自定义信封架构中的枚举 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2b053d82-753f-4a05-9922-fa5dbd073ba9
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b33458d3a7fbc71ea5e2df7603390f10b928113
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241853"
---
# <a name="customizing-enumerations-in-the-envelope-schema"></a>信封架构中的自定义枚举
使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您可以在服务（信封）架构中自定义 ID 字段枚举。 这样，您可以接收或发送在信封的发送方或接收方 ID 字段中具有非标准值（在 X12 标准正文定义的值集以外）的交换。 您还可以更改在协议属性定义的标头值下拉列表中可用的限定符。  
  
> [!IMPORTANT]
>  对架构的修改会应用于上述标准中的所有事务。 为单个方，不能在信封架构进行修改。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从产品随附的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 的静态服务架构中请求允许的值列表。 若要扩展基本的值集，您需要开发并部署服务架构扩展。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供服务 （信封） 可用于修改中的枚举的架构模板。 这些服务架构是 X12_ServiceSchemaExtension.xsd 和 EDIFACT_ServiceSchemaExtension.xsd。 每个自定义架构都将根据标准拥有下列命名空间中的一个。 此命名空间不能更改。  
  
|Standard|命名空间|  
|--------------|---------------|  
|X12 和 HIPAA|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`|  
|EDIFACT|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`|  
  
 可以在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的 BizTalk 编辑器中更改架构（请参阅下面的过程）。 进行所需更改之后，必须部署架构。  
  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 验证信封段（对于 X12 为 ISA 和 GS，或者对于 EDIFACT 为 UNB 和 UNG）时，在接收端和发送端都将检查是否存在基于其命名空间的自定义服务架构。 如果已部署自定义架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将该架构与常规服务架构合并在一起，并将在指定之处同时使用自定义枚举值和标准枚举值。 可以自定义架构以扩展枚举列表，但不能从该列表中删除值。 如果未部署自定义架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将使用标准服务架构。  
  
 部署自定义架构之后，[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)] 管理控制台中的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用户界面将使用自定义枚举中的值填充 [!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)] 属性页中的相应下拉列表。 如果尚未部署自定义架构，[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)] 将在标准服务架构中使用枚举中的值。 另外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时将使用自定义枚举来验证消息。  
  
 如果使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供的 XML 工具验证带有信封的实例，并且已自定义了服务架构，则在 BizTalk 项目中除文档（事务集）架构之外还必须包括自定义服务架构，并且必要时还要包括批处理架构。 如果验证的是不带信封的事务集实例，则不必包括此架构。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
##  <a name="BKMK_Env_Can"></a>可以修改的信封字段  
 只能修改以下信封字段。 只有这些字段包括在扩展架构中。 在服务扩展架构中添加其他字段对处理没有任何影响。  
  
|Standard|字段|  
|--------------|-----------|  
|X12 和 HIPAA|ISA01 – 授权限定符<br /><br /> ISA03 – 安全限定符<br /><br /> ISA05 – 发送方 ID 限定符<br /><br /> ISA07 - 接收方 ID 限定符<br /><br /> GS01 - 功能代码<br /><br /> GS07 - 责任代理|  
|EDIFACT|UNB2.2 - 发送方代码限定符<br /><br /> UNB3.2 - 接收方代码限定符|  
  
## <a name="envelope-fields-that-should-not-be-modified"></a>不应修改的信封字段  
 信封中的某些字段控制引擎中的行为。 因此，不应向任何这些字段的现有枚举列表添加值。 这些字段如下所示：  
  
|Standard|字段|  
|--------------|-----------|  
|X12 和 HIPAA|ISA11 – 交换控制标准标识符<br /><br /> ISA12 – 交换控制版本号<br /><br /> ISA14 – 请求确认|  
|EDIFACT|UNB1.1 – 语法标识符<br /><br /> UNB1.2 – 语法版本号<br /><br /> UNB9 – 确认请求|  
  
### <a name="to-customize-an-enumeration-in-the-envelope-schema"></a>在信封架构中自定义枚举  
  
1.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，创建一个新项目。  
  
2.  在 BizTalk 编辑器中，将 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 中的 X12_ServiceSchemaExtension.xsd 架构（以修改 X12 或 HIPAA 枚举）或 EDIFACT_ServiceSchemaExtension.xsd 架构添加到 BizTalk 项目。 打开架构。  
  
3.  若要更改枚举中的值，选择中的枚举**属性**窗格中，然后单击省略号以打开**枚举编辑器**。 根据需要确保在每一行上一个值的值，列表添加**值**窗格。 单击 **“确定”**。  
  
    > [!IMPORTANT]
    >  不能更改服务架构的命名空间。 架构应与随产品一起安装的原始扩展架构具有相同的命名空间和根节点名称。  
  
    > [!NOTE]
    >  如果要向架构添加新字段，该字段将被忽略。 仅列出中的字段[信封字段，可以修改](../core/customizing-enumerations-in-the-envelope-schema.md#BKMK_Env_Can)可以更改上面一节。  
  
4.  保存该架构。  
  
5.  右键单击架构，然后单击**部署**。  
  
    > [!NOTE]
    >  架构必须部署在当前 BizTalk 组中。  
  
## <a name="see-also"></a>另请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)   
 [修改 EDI 架构](../core/modifying-edi-schemas.md)