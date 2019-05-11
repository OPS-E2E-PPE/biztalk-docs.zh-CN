---
title: 如何在业务流程中创建角色链接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc386ac2-a851-4342-9ceb-0b6faddf4ece
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf9dd0026fd0da3a83e847639cbbd130400ccd9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385447"
---
# <a name="how-to-create-role-links-in-orchestrations"></a>如何在业务流程中创建角色链接
以下是你将需要完成在您的业务流程中使用角色链接的基本任务：  
  
-   创建参与方和发送端口并将其与相互关联。  
  
-   使用以下过程创建角色链接类型并添加端口类型。  
  
    |若要创建角色链接类型|  
    |--------------------------------|  
    |1.在业务流程视图窗口中，展开**类型**，右键单击**角色链接类型**，然后单击**新建角色链接类型**。<br />2.单击刚刚创建的角色链接类型。 在属性窗口中**标识符**字段中，键入`Provider_Consumer_RoleLinkType`。<br />3.展开**Provider_Consumer_RoleLinkType**，然后单击**Role_1**。 在属性窗口中**标识符**字段中，键入`ConsumerRole`。<br />4.右键单击**ConsumerRole**，然后单击**添加端口类型**。 这将启动端口类型向导。<br />5.上**欢迎使用端口类型向导**页上，单击**下一步**。<br />6.上**选择端口类型或创建新的端口类型**页上，选择**创建新的端口类型**，然后**端口类型名称**，类型`ConsumerPortType`。<br />7.有关**通信模式**，选择**单向**，并为**访问限制**，选择**公有-无限制**。 单击“下一步” 。<br />8.上**完成端口向导**页上，单击**完成**。<br />9.右键单击**Provider_Consumer_RoleLinkType**，然后单击**新角色**。<br />10.单击**Role_1**，然后在属性窗口中**标识符**字段中，键入`ProviderRole`。<br />11.右键单击**ProviderRole**，然后单击**添加端口类型**。 这将启动端口类型向导。<br />12.上**欢迎使用端口类型向导**页上，单击**下一步**。<br />13.上**选择端口类型或创建新的端口类型**页上，选择**创建新的端口类型**，然后**端口类型名称**，类型`ProviderPortType`。<br />14.有关**通信模式**，选择**单向**，并为**访问限制**，选择**公有-无限制**。 单击“下一步” 。<br />15.上**完成端口向导**页上，单击**完成**。 **注意：**     置于角色链接内配置的端口不会保留其关联的绑定信息。|  
  
     在前面的过程中，创建包含两个角色的角色链接类型 — ProviderRole 将接收和处理消息从使用者和 ConsumerRole，您的业务流程将使用提供的发送端口与该角色将消息发送到使用者。  
  
> [!NOTE]
>  角色链接类型可以包含一个提供者角色和使用者角色，并且它可以包含其中任何一个或之一，具体取决于您的业务流程的每个需要。  
  
-   使用以下过程将角色链接添加到您的业务流程。  
  
    |若要使用角色链接向导创建角色链接|  
    |---------------------------------------------------------|  
    |1.在业务流程工具箱中拖动**角色链接**形状添加到设计图面。 这将启动角色链接向导。<br />2.上**欢迎使用角色链接向导**页上，单击**下一步**。<br />3.上**角色链接名称**页上，在**名称**字段中，键入`Provider_Consumer`。 单击“下一步” 。<br />4.上**角色链接类型**页上，选择**使用现有角色链接类型**。 在中**角色链接类型名称**下拉列表中，选择**Provider_Consumer_RoleLinkType**。 单击“下一步” 。<br />5.上**角色标识**页上，选择**ProviderRole**从**此业务流程将实现哪个角色来接收和处理来自合作伙伴的消息？** 下拉列表。 向导会自动选择**ConsumerRole**有关**此业务流程将使用下面的角色将消息发送到该角色内端口上的合作伙伴**。 单击“下一步” 。<br />6.上**角色链接用法**页上，选择**我会将第一条消息发送到我的合作伙伴的角色**。 单击 **“完成”**。|  
  
     在前面的过程中，您将 ConsumerRole 进一步定义为初始化角色。 这意味着，您的业务流程会向通过 ConsumerRole 提供的端口使用者发送第一条消息，然后 ProviderRole 将接收从使用者进行进一步处理发送的消息。  
  
    > [!NOTE]
    >  如果角色链接类型中只有一个角色，需要通过选择业务流程中定义你的角色**提供者角色：我将接收第一条消息**或**使用者角色：我将发送第一条消息**而不是执行步骤 5 中前面的过程。  
  
-   设计业务流程。 您可以利用相关集来确保传入消息与业务流程的相应实例相匹配。  
  
-   将与端口相关联**发送**并**接收**形状。 此外，请执行以下操作：  
  
    -   如果初始化角色是发送消息的使用者，显式设置**DestinationParty**属性 （仅一次） 在业务流程中的。 若要执行此操作，设置的值**DestinationParty**中**表达式**形状，如下面的示例，其中，ConfirmOrder 是角色链接的名称，PartnerName 和 OrganizationName 是参数中所示参与方：  
  
        ```  
        ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
        ```  
  
    -   如果初始化角色是用于接收消息，提供商**DestinationParty**接收方会自动初始化属性。 **DestinationParty**设置为提供程序本身。 **SourceParty**属性是只读的并且提供通过受信任的管道组件以解析参与方名称基于安全标识符 (SID) 发件人或与该参与方相关联的证书。 运行该管道组件的主机必须标记为**受信任验证**。 你可以获取的值**SourceParty**中**表达式**形状使用下面的示例代码：  
  
        ```  
        PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);  
        ```  
  
## <a name="examples-of-using-role-links"></a>使用角色链接的示例  
  
-   [PartyResolution（BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)  
  
-   从 BizTalk Server 代码示例可在下载 SDK 示例"使用角色链接" [ http://go.microsoft.com/fwlink/?LinkId=73703 ](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)   
 [如何使用角色链接形状](../core/how-to-use-the-role-link-shape.md)   
 [如何使用角色链接向导](../core/how-to-use-the-role-link-wizard.md)