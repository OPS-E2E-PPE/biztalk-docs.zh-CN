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
ms.openlocfilehash: 1a8600ed52a70d1e8cf47641b7aade20272c9287
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337745"
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a>如何导出 EDI-AS2 解决方案的绑定
本主题介绍如何从设置为 EDI 和/或 AS2 解决方案的计算机导出配置。 这使你能够设置以自动方式的另一台计算机上的相同配置。 可以从应用程序、 组或程序集导出绑定。  
  
 在创建绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 此.xml 绑定文件包含到相关的所有信息在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置。 这包括所有 EDI 和 AS2 配置属性，但某些安全信息除外。 有关绑定文件 （包括 EDI 和 AS2 节点） 中的节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。 有关 edi/as2 绑定的常规信息，请参阅"EDI 和 AS2 节点中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]绑定文件"下面。  
  
 此外可以导出使用某一.msi 文件的应用程序的一部分导出绑定。 有关详细信息，请参阅[如何导出 BizTalk 应用程序](../core/how-to-export-a-biztalk-application.md)。 或者，可以使用 BTSTask 命令导出和导入绑定。 有关 BTSTask 的详细信息，请参阅[BTSTask 命令行参考](../core/btstask-command-line-reference.md)。  
  
 **导出绑定**  
  
 当您导出配置，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将会自动将导出的 EDI 属性，以及其他参与方信息，所有绑定参与方。 如果激活导出全局参与方信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还将导出未绑定到业务流程的参与方属性以及全局 EDI 属性。 可以导出全局参与方信息三种方式：  
  
- 通过选中导出绑定对话框中的导出全局参与方信息属性。  
  
- 通过选中导出 MSI 文件向导的选择资源窗格中的全局参与方复选框。  
  
- 通过使用中的 GlobalParties 开关 BTSTask 命令行工具，按如下所示：  
  
  ```  
  BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
  ```  
  
  出于安全原因，当您导出绑定文件，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会从文件删除绑定的密码。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 从 EDIFACT 属性和 X12 中的 ISA1 和 ISA2、 ISA3，和 ISA4 字段中删除 UNB6.1 和 UNB6.2 字段属性。  
  
  除了使用导出绑定，导出应用程序或 BTSTask 命令，可以手动创建 XML 绑定文件。 通过此操作，可以从业务线应用程序导出参与方和 EDI 设置。 然后可以导入使用导入绑定命令或 BTSTask 命令的绑定。  
  
## <a name="prerequisites"></a>先决条件  
 您必须是的成员的帐户登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。 详细信息，请参阅"所需部署和管理 BizTalk 应用程序的权限"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文档。  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a>导出到绑定文件的配置  
  
1. 在你想要从中导出配置计算机，打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2. 右键单击 BizTalk 应用程序想要复制其配置，请指向**导出**，然后单击**绑定**。  
  
   > [!NOTE]
   >  您还可以使用 BTSTask 实用工具导出或导入配置。  
  
3. 选择导出选项，选择要导出当前应用程序或组，或者导出程序集的绑定。  
  
4. 如果你想要导出所有参与方，并且其非敏感属性，即使业务流程未绑定到它们，再单击**导出全局参与方信息**。  
  
   > [!NOTE]
   >  如果不单击**导出全局参与方信息**，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将导出所有参与方绑定到业务流程，到绑定文件的属性。 但是，它将不会导出所有参与方的未绑定到业务流程，除非您单击**导出全局参与方信息**。  
   > 
   > [!NOTE]
   >  生成的绑定文件时**导出全局参与方信息**选择属性，则将包括的计算机上定义的所有参与方的配置。 不能导出的完整的计算机上定义的参与方集合子集的配置。  
  
5. 单击**确定**导出绑定。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将不会导出任何 EDI 保密字段，如密码或安全/身份验证信息。 它会导出任何 EDI 保密字段保留为空字符串。 在导入到另一台计算机上的绑定之后, 必须手动设置 EDI 敏感字段的值。  
  
6. 手动记下任何 EDI 保密字段，如密码或安全/身份验证信息，用于在您导入到绑定的计算机上更高版本设置。  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a>EDI 和 AS2 绑定文件的 BizTalk Server 中的节点  
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
  
 EDI 全局属性将添加到以下节点中的绑定文件。  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 EDI 和 AS2 节点添加到末尾[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]绑定文件。 EdiData 节点添加到参与方相应的子节点下的参与方集合节点中，并且 EdiGlobalProperties 节点添加后，并在与参与方集合节点相同的级别。 有关 BizTalk 绑定文件中的 EDI 和 AS2 节点的详细信息，请参阅[绑定文件的结构](../core/structure-of-a-binding-file.md)。  
  
 EdiData 节点是可选的。 但是，如果存在 EdiData 节点，则 EdiData 下的子节点是必需的。 同样，EdiGlobalProperties 节点是可选的;但是，如果存在 EdiGlobalProperties 节点，则其下的子节点是必需的。  
  
 EDI 和 AS2 绑定文件节点不对应于在合作伙伴协议管理器中的属性页直接[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。 某些 EDI 和 AS2 绑定文件节点包括用于发件人角色的属性和接收方角色的属性。 由节点中的 IsSender 属性指示该角色。 对于这些节点不用于发送方和接收方角色 （PartnerAgreement、 PartnerBatchUpdatable、 PartnerAS2Updatable 和 GlobalCommon），IsSender 始终为 False。  
  
 PartnerEdifact 和 PartnerX12 节点包含接收方和发件人角色的属性，无论 IsSender 设置为 True 或 False。 例如，partneredifact 仍将包含 Una1 字段 （用于作为交换接收方的参与方），甚至当 IsSender 为 True。 PartnerEdifact 还将包含 Unb5CheckDup 字段 （用于作为交换发送方的参与方），即使 IsSender 为 False。 但是，当 IsSender 为 True，作为交换接收方的参与方不能在 UI 中或者由引擎使用，而字段赋予默认值。 同样，当 IsSender 为 False 时，作为交换发送方的参与方不能在 UI 中或者由引擎使用，而字段赋予默认值。  
  
 如果属性的默认值为 null，该字段将不会包含在绑定文件中除非该字段提供值。  
  
 绑定文件数据保存在 BizTalk 管理数据库 (BizTalkMgmtDb) 的表中。