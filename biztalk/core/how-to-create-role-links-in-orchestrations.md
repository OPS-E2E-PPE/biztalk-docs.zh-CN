---
title: 如何在业务流程中创建角色链接 |Microsoft 文档
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
ms.openlocfilehash: e40a77392af9e97791cd9afbacc8f0b533f60288
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250421"
---
# <a name="how-to-create-role-links-in-orchestrations"></a>如何在业务流程中创建角色链接
必须完成以下基本任务才能在业务流程中使用角色链接：  
  
-   创建参与方和发送端口，并将它们相互关联。  
  
-   使用下面的过程可创建角色链接类型并添加端口类型。  
  
    |创建角色链接类型|  
    |--------------------------------|  
    |1.在业务流程视图窗口中，展开**类型**，右键单击**角色链接类型**，然后单击**新角色的链接类型**。<br />2.单击您刚刚创建的角色链接类型。 在属性窗口中，在**标识符**字段中，键入`Provider_Consumer_RoleLinkType`。<br />3.展开**Provider_Consumer_RoleLinkType**，然后单击**Role_1**。 在属性窗口中，在**标识符**字段中，键入`ConsumerRole`。<br />4.右键单击**ConsumerRole**，然后单击**添加端口类型**。 这将启动端口类型向导。<br />5.上**欢迎使用端口类型向导**页上，单击**下一步**。<br />6.上**选择端口类型或创建新的端口类型**页上，选择**创建新的端口类型**，，然后为**端口类型名称**，类型`ConsumerPortType`。<br />7.有关**通信模式**，选择**单向**，和**访问限制**，选择**公有-无限制**。 单击 **“下一步”**。<br />8.上**完成端口向导**页上，单击**完成**。<br />9.右键单击**Provider_Consumer_RoleLinkType**，然后单击**新角色**。<br />10.单击**Role_1**，然后在属性窗口中，在**标识符**字段中，键入`ProviderRole`。<br />11.右键单击**ProviderRole**，然后单击**添加端口类型**。 这将启动端口类型向导。<br />12.上**欢迎使用端口类型向导**页上，单击**下一步**。<br />13.上**选择端口类型或创建新的端口类型**页上，选择**创建新的端口类型**，，然后为**端口类型名称**，类型`ProviderPortType`。<br />14.有关**通信模式**，选择**单向**，和**访问限制**，选择**公有-无限制**。 单击 **“下一步”**。<br />15.上**完成端口向导**页上，单击**完成**。 **注意：** 置于角色链接内的已配置端口不保留其关联的绑定信息。|  
  
     在前面的过程中，创建包含两个角色的角色链接类型-ProviderRole 将接收和处理来自使用者和 ConsumerRole 的消息，您的业务流程将使用提供的发送端口与该角色将消息发送到使用者。  
  
> [!NOTE]
>  角色链接类型可以包含提供者角色和使用者角色，它可以包括这两者之一，或各包含一个，具体视业务流程需要而定。  
  
-   使用以下过程可以向业务流程添加角色链接。  
  
    |使用角色链接向导创建角色链接|  
    |---------------------------------------------------------|  
    |1.业务流程工具箱，在将拖动**角色链接**到设计图面上的形状。 这将启动角色链接向导。<br />2.上**欢迎角色链接向导**页上，单击**下一步**。<br />3.上**角色链接名称**页上，在**名称**字段中，键入`Provider_Consumer`。 单击 **“下一步”**。<br />4.上**角色链接类型**页上，选择**使用现有角色链接类型**。 在**角色链接类型名称**下拉列表中，选择**Provider_Consumer_RoleLinkType**。 单击 **“下一步”**。<br />5.上**角色标识**页上，选择**ProviderRole**从**此业务流程将实现哪个角色接收和处理来自合作伙伴的消息？** 下拉列表。 向导会自动选择**ConsumerRole**为**此业务流程将使用以下角色将消息发送到该角色内的端口上的合作伙伴**。 单击 **“下一步”**。<br />6.上**角色链接用法**页上，选择**我将将第一条消息发送到我的合作伙伴角色**。 单击 **“完成”**。|  
  
     在前面的过程中，您将 ConsumerRole 进一步定义为初始化角色。 这意味着，业务流程将通过 ConsumerRole 提供的端口向使用者发送第一条消息，然后 ProviderRole 将从使用者接收发送回来的消息，以进一步处理。  
  
    > [!NOTE]
    >  如果角色链接类型中只有一个角色，你需要在业务流程中定义你的角色，通过选择**提供程序角色： 我接收第一条消息**或**使用者角色： 我将要发送第一个消息**而无需执行步骤 5 中前面的过程。  
  
-   设计业务流程。 您可以利用相关集来确保传入消息与业务流程的相应实例相匹配。  
  
-   将使用的端口相关联**发送**和**接收**形状。 此外，执行以下操作：  
  
    -   如果启动的角色是用于发送消息的使用者，显式设置**DestinationParty**业务流程中的属性 （一次，并且一次）。 为此，请设置的值**DestinationParty**中**表达式**形状，如下面的示例，其中 ConfirmOrder 是相应角色的名称，使用省略号和单位名称是参数中所示当事方：  
  
        ```  
        ConfirmOrder(Microsoft.XLANGs.BaseTypes.DestinationParty) = new Microsoft.XLANGs.BaseTypes.Party("PartnerName", "OrganizationName");  
        ```  
  
    -   如果启动角色是提供用于接收消息， **DestinationParty**接收方自动初始化属性。 **DestinationParty**设置为提供程序本身。 **SourceParty**属性是只读的并且要为基于或与方相关联的证书上的安全标识符 (SID) 发件人的方名称解析的受信任的管道组件通过提供。 运行管道组件的主机必须标记为**受信任的身份验证**。 你可以获取的值**SourceParty**中**表达式**通过使用下面的示例代码的形状：  
  
        ```  
        PartyName = Buyer_Supplier(Microsoft.XLANGs.BaseTypes.SourceParty);  
        ```  
  
## <a name="examples-of-using-role-links"></a>使用角色链接示例  
  
-   [PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)  
  
-   在提供的 BizTalk Server 代码示例从下载"使用角色链接"中的 SDK 示例[http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703)。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用角色链接](../core/using-role-links-in-orchestrations.md)   
 [如何使用角色链接形状](../core/how-to-use-the-role-link-shape.md)   
 [如何使用角色链接向导](../core/how-to-use-the-role-link-wizard.md)