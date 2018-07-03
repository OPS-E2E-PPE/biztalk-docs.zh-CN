---
title: 如何导出 EDI-AS2 解决方案的绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 856ab630-66c4-4496-884a-fdbe641143c5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36bd9c265d28555c40f84f1728fd28846fbd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012326"
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a>如何导出 EDI-AS2 解决方案的绑定
本主题介绍如何从设置为 EDI 和/或 AS2 解决方案的计算机中导出配置。 这样，您可以以自动方式在其他计算机上设置相同配置。 您可以从应用程序、组或程序集导出绑定。  
  
 您可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中创建绑定文件。 此 .xml 绑定文件包含与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置相关的所有信息。 其中包括所有 EDI 和 AS2 配置属性，但某些安全信息除外。 有关绑定文件 （包括 EDI 和 AS2 节点） 中的节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。 有关 EDI/AS2 绑定的常规信息，请参阅下面的“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 绑定文件中的 EDI 和 AS2 节点”。  
  
 您还可以在使用 .msi 文件导出应用程序时导出绑定。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。 还可以用 BTSTask 命令导出和导入绑定。 有关 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
 **导出绑定**  
  
 导出配置时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将自动导出所有绑定参与方的 EDI 属性，以及其他参与方信息。 如果激活导出全局参与方信息，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 还将导出未绑定到业务流程的参与方的属性以及全局 EDI 属性。 您可以按如下三种方式导出全局参与方信息：  
  
- 通过选中“导出绑定”对话框中的“导出全局参与方信息”属性。  
  
- 通过选中导出 MSI 文件向导的“选择资源”窗格中的“全局参与方”复选框。  
  
- 通过使用 BTSTask 命令行工具中的 GlobalParties 开关，如下所示：  
  
  ```  
  BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
  ```  
  
  出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从 EDIFACT 属性和 X12 中的 ISA1 和 ISA2、 ISA3，和 ISA4 字段中删除 UNB6.1 和 UNB6.2 字段属性。  
  
  除使用导出绑定、导出应用程序或 BTSTask 命令之外，您还可以手动创建 XML 绑定文件。 这样，您可以从业务线应用程序导出参与方和 EDI 设置。 然后，您可以使用导入绑定命令或 BTSTask 命令导入绑定。  
  
## <a name="prerequisites"></a>必要條件  
 您必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员身份帐户登录。 有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文档中的“部署和管理 BizTalk 应用程序所需的权限”。  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a>将配置导出到绑定文件  
  
1. 在要从中导出配置的计算机上，打开“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台”。  
  
2. 右键单击 BizTalk 应用程序想要复制其配置，请指向**导出**，然后单击**绑定**。  
  
   > [!NOTE]
   >  您还可以使用 BTSTask 实用工具导出或导入配置。  
  
3. 选择导出选项，选择从当前应用程序或组导出，或者导出程序集的绑定。  
  
4. 如果你想要导出所有参与方，并且其非敏感属性，即使业务流程未绑定到它们，再单击**导出全局参与方信息**。  
  
   > [!NOTE]
   >  如果不单击**导出全局参与方信息**，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将导出所有参与方绑定到业务流程，到绑定文件的属性。 但是，它将不会导出所有参与方的未绑定到业务流程，除非您单击**导出全局参与方信息**。  
   > 
   > [!NOTE]
   >  生成的绑定文件时**导出全局参与方信息**选择属性，则将包括的计算机上定义的所有参与方的配置。 无法导出计算机上定义的完整参与方集合子集的配置。  
  
5. 单击**确定**导出绑定。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不会导出任何 EDI 保密字段，例如密码或安全/身份验证信息。 对于任何 EDI 保密字段，BizTalk Server 将导出一个空字符串。 将绑定导入到其他计算机中后，必须手动设置 EDI 保密字段的值。  
  
6. 手动记下所有 EDI 保密字段（如密码或安全/身份验证信息），以便稍后在要向其导入绑定的计算机上进行设置。  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a>BizTalk Server 绑定文件中的 EDI 和 AS2 节点  
 如果导出您的配置**导出全局参与方信息**属性处于选中状态，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将生成具有下列节点的绑定文件：  
  
```  
EdiData  
   PartyEDIProperties  
      PartnerAgreement  
         Contacts  
      PartnerEdifact  
         PartnerEdifactReceiverGroups  
         PartnerEdifactSenderGroups  
      PartnerAckValidation  
      PartnerX12  
      PartnerX12ReceiverGroups  
      PartnerX12SenderGroups  
      PartnerBatchUpdatable  
      PartnerAS2CommonUpdatable  
      PartnerAS2  
```  
  
 EDI 全局属性将在下列节点中添加到绑定文件中。  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 EDI 和 AS2 节点将被添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 绑定文件的末尾。 EdiData 节点将被添加到“参与方集合”节点下的“参与方”子节点；而 EdiGlobalProperties 节点将被添加到“参与方集合”节点之后，且其级别与“参与方集合”节点的级别相同。 有关 BizTalk 绑定文件中的 EDI 和 AS2 节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。  
  
 EdiData 节点是可选的。 但是，如果存在 EdiData 节点，则 EdiData 下的子节点是必需的。 同样，EdiGlobalProperties 节点也是可选的；但是，如果存在 EdiGlobalProperties 节点，则该节点下的子节点是必需的。  
  
 EDI 和 AS2 绑定文件节点不与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中的合作伙伴协议管理器的属性页直接对应。 某些 EDI 和 AS2 绑定文件节点包含适用于发送方角色和接收方角色的属性。 角色是由节点中的 IsSender 属性指示的。 对于不适用于发送方和接收方角色的节点（PartnerAgreement、PartnerBatchUpdatable、PartnerAS2Updatable 和 GlobalCommon），IsSender 始终为 False。  
  
 无论 IsSender 设置为 True 还是 False，PartnerEdifact 和 PartnerX12 节点都包含接收方和发送方角色的属性。 例如，即使 IsSender 为 True，PartnerEdifact 仍将包含 Una1 字段（适用于作为交换接收方的参与方）。 即使 IsSender 为 False，PartnerEdifact 仍将包含 Unb5CheckDup 字段（适用于作为交换发送方的参与方）。 但是，如果 IsSender 为 True，作为交换接收方的参与方的字段则不会在 UI 中或者由引擎使用，而是对该字段赋予默认值。 同样，如果 IsSender 为 False，作为交换发送方的参与方的字段则不会在 UI 中或者由引擎使用，而是向该字段赋予默认值。  
  
 如果属性的默认值为空，则不会将该字段包含在绑定文件中，除非向此字段赋予一个值。  
  
 绑定文件数据保存在 BizTalk 管理数据库 (BizTalkMgmtDb) 的表中。