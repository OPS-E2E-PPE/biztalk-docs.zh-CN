---
title: 自定义信封架构中的枚举 |Microsoft Docs
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
ms.openlocfilehash: 4c5ee34c80b2bcdc0d0abfe085e174bf5ee6b599
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353280"
---
# <a name="customizing-enumerations-in-the-envelope-schema"></a>信封架构中自定义枚举
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 允许你自定义服务 （信封） 架构中的 ID 字段枚举。 这使您可以接收或发送具有非标准值的交换 (之外的一组值定义的 X12 标准正文) 信封中的发送方或接收方 ID 字段中。 它还可以更改在协议属性定义的标头值下拉列表中可用的限定符。  
  
> [!IMPORTANT]
>  当您修改架构的修改会应用于上述标准中的所有事务。 为某一参与方，不能在信封架构中进行修改。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将拉取的产品随附的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 的静态服务架构中的允许值列表。 若要扩展基本的值集，您需要开发和部署服务架构扩展。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供服务 （信封） 架构模板。 可用于修改中的枚举。 这些服务架构为 X12_ServiceSchemaExtension.xsd 和 EDIFACT_ServiceSchemaExtension.xsd。 每个自定义架构将具有以下命名空间，根据标准之一。 不能更改此命名空间。  
  
|标准|命名空间|  
|--------------|---------------|  
|X12 和 HIPAA|`http://schemas.microsoft.com/BizTalk/EDI/X12/2006`|  
|EDIFACT|`http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`|  
  
 对架构在 BizTalk 编辑器中进行更改[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]（请参阅下面的过程）。 进行所需的更改后，必须部署架构。  
  
 端接收和发送端，当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证信封段 （ISA 和 GS，对于 X12 或 UNB 和 UNG edifact），它将检查是否存在基于其命名空间的自定义服务架构。 如果已部署自定义架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将该架构与常规服务架构合并，并且将自定义和标准枚举值中指定。 你可以自定义架构以扩展枚举列表中，但无法从中删除值。 如果未部署自定义架构，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用标准服务架构。  
  
 部署自定义架构后[!INCLUDE[firstref_TPM](../includes/firstref-tpm-md.md)]中的用户界面[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台将使用的值中的自定义枚举来填充中的相应下拉列表[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)]属性页。 如果尚未部署自定义架构，[!INCLUDE[TPM_abbrev](../includes/tpm-abbrev-md.md)]将使用标准服务架构中的枚举中的值。 此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时将使用自定义枚举来验证消息。  
  
 如果你使用随提供的 XML 工具[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]验证与实例信封，并且您已自定义服务架构，必须将包含自定义服务架构在 BizTalk 项目中，此外到文档 （事务集）架构和如有必要，批架构。 这不是必需的如果您要验证没有信封的事务集实例。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
##  <a name="BKMK_Env_Can"></a> 可以修改的信封字段  
 可以修改仅以下信封字段。 仅这些字段包括在扩展架构。 添加服务扩展架构中的其他字段不会处理任何影响。  
  
|标准|字段|  
|--------------|-----------|  
|X12 和 HIPAA|ISA01 – 授权限定符<br /><br /> ISA03 – 安全限定符<br /><br /> ISA05 – Sender ID Qualifier<br /><br /> ISA07-接收方 ID 限定符<br /><br /> GS01-功能代码<br /><br /> GS07-责任代理|  
|EDIFACT|UNB2.2-发送方代码限定符<br /><br /> UNB3.2-接收方代码限定符|  
  
## <a name="envelope-fields-that-should-not-be-modified"></a>不应修改的信封字段  
 引擎中的信封驱动器行为中的某些字段。 因此，不应将值添加到其中的任何字段的现有枚举列表。 这些字段如下所示：  
  
|标准|字段|  
|--------------|-----------|  
|X12 和 HIPAA|ISA11 – 交换控制标准标识符<br /><br /> ISA12 – 交换控制版本号<br /><br /> ISA14 – 请求确认|  
|EDIFACT|UNB1.1 – 语法标识符<br /><br /> UNB1.2 – 语法版本号<br /><br /> UNB9 – 确认请求|  
  
### <a name="to-customize-an-enumeration-in-the-envelope-schema"></a>若要自定义信封架构中的枚举  
  
1. 在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，创建一个新项目。  
  
2. 添加的 X12_ServiceSchemaExtension.xsd 架构 （以修改 X12 或 HIPAA 枚举） 或 EDIFACT_ServiceSchemaExtension.xsd 架构中的[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 向 BizTalk 项目在 BizTalk 编辑器中。 打开该架构。  
  
3. 若要更改枚举中的值，请选择中的枚举**属性**窗格中，然后单击省略号以打开**枚举编辑器**。 根据需要确保在每行一个值添加到值列表**值**窗格。 单击“确定” 。  
  
   > [!IMPORTANT]
   >  不能更改服务架构的命名空间。 架构应具有形式随产品一起安装的原始扩展架构的相同命名空间和根节点名称。  
  
   > [!NOTE]
   >  如果您打算向架构添加新字段，该字段将被忽略。 仅中列出的字段[信封字段，可以修改](../core/customizing-enumerations-in-the-envelope-schema.md#BKMK_Env_Can)上面部分可以进行更改。  
  
4. 保存该架构。  
  
5. 右键单击架构，然后单击**部署**。  
  
   > [!NOTE]
   >  架构必须部署在当前 BizTalk 组中。  
  
## <a name="see-also"></a>请参阅  
 [开发 EDI 架构](../core/developing-edi-schemas.md)   
 [修改 EDI 架构](../core/modifying-edi-schemas.md)