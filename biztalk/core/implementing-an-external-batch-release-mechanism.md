---
title: 实现外部批处理释放机制 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5633a448-cc29-4931-a3ad-206ae25c989b
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e88b6962cc0c83ab0ac4971f481b9ac1f185ca02
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258133"
---
# <a name="implementing-an-external-batch-release-mechanism"></a>实现外部批处理发布机制
您可以使用外部发布触发器触发批处理的发布。 可以通过后端业务线应用程序在达到某一阀值时自动触发此发布。 此机制是除了自动触发的批次版本按计划或计数的事务集或字符，或手动触发批处理，通过单击**重写**按钮**批处理配置**单向协议选项卡页。  
  
 若要实现外部发布触发器，需要设置接收端口和位置，以便处理 OverrideControlMessage。 接收位置必须使用 `Edi.BatchControlMessageRecvPipeline` 接收管道。 这与 BatchControlMessageRecvLoc 接收位置所使用的是同一管道，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用该位置处理手动替代消息。 不过，BatchControlMessageRecvLoc 是 SQL 类型的接收位置，而为外部发布触发器设置的接收位置可以使用任何适配器类型。  
  
 外部批处理发布触发器由 XML 控制消息触发。 为触发批处理，后端应用程序会将控制消息路由到接收位置。 您可以修改控制消息，以便激活、替代或终止批处理。 请参阅以下有关创建控制消息的过程。  
  
 若要启用外部发布触发器，您必须选择**外部发布触发器**中的属性**批配置**页**协议属性**对话框X12 或 EDIFACT 框。 此属性指明批处理发布需要外部发布消息。 **重写**按钮，**停止**按钮，和**激活**范围的控件保持有效如果**外部发布触发器**属性已选择。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a>为外部批处理发布触发器消息创建接收位置  
  
1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个单向接收端口。 有关如何创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
2.  在接收端口中创建一个单向接收位置。  
  
3.  选择传输类型。 您可以为此接收位置选择任意类型。 通常是选择“FILE”类型，然后输入用于接收文件的文件夹。  
  
4.  对于“接收管道”，请选择 `BatchControlMessageRecvPipeline`。  
  
5.  单击 **“确定”**。  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a>创建外部批处理发布触发器消息  
  
1.  在记事本中新建一个文件，然后使用 .xml 扩展名对其进行命名。  
  
2.  向文件中添加以下内容：  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <ControlMessage xmlns="http://SQLControlMessage.IssueSelect">  
      <PAM_Control xmlns="http://SQLControlMessage.IssueSelect">  
        <DestinationParty>[Party ID]</DestinationParty>  
        <EdiMessageType>[0 for X12\HIPAA|1 for Edifact]</EdiMessageType>  
        <ActionType>EdiBatchOverride</ActionType>  
        <ActionDateTime>[yyyy-mm-ddThh:mm:ss.sss]</ActionDateTime>  
        <UsedOnce>0</UsedOnce>  
        <BatchId>[Batch ID]</BatchId>  
        <BatchName>[Batch Name]</BatchName>  
        <DestinationPartyName>[Destination Party/Partner name]</DestinationPartyName>  
        <SenderPartyName>[Sender Party/Partner name]</SenderPartyName>  
        <AgreementName>[Agreement Name]</AgreementName>  
        <ReceiverPartyNameType>[Receiver Party/Partner name]</ReceiverPartyNameType>  
        <ToBeBatched>1</ToBeBatched>  
      </PAM_Control>  
    </ControlMessage>  
    ```  
  
     替换以上摘录中的值，如下所示：  
  
    -   指定操作类型。 通常情况下， **ActionType**必须设置为**EdiBatchOverride**重写协议中进行的批处理设置。 你还可以将此设**EdiBatchTerminate**通过外部触发器批处理终止。  
  
        > [!NOTE]
        >  Microsoft 建议您不要使用外部发布触发器来激活批处理。 因此，不应指定**ActionType**作为**EdiBatchActivate**。  
  
    -   确定批次 ID 和批处理名称。 为此，请打开**协议属性**对话框框中，然后在单向协议选项卡上，单击**批配置**。 单击要重写并输入的值的批的选项卡**批名称**和**批次 ID**字段到**BatchName**和**BatchID**控制消息的节点。  
  
    -   指定目标参与方名称。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，获取将在批处理接收方/伙伴的名称交换。 输入中的名称**ReceiverPartyNameType**控制消息的节点。  
  
    -   指定发件人方名称。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，获取批处理的交换将要发送方/伙伴的名称. 输入中的名称**SenderPartyName**控制消息的节点。  
  
    -   指定协议名称。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，在**协议**部分中，右键单击具有批配置，需要到使用重写控制消息中，然后单击协议**属性**。 在**协议属性**对话框中，在**常规**选项卡上，在**常规属性**页上，复制的值从**名称**字段**协议参数**部分，并将其粘贴中**AgreementName**控制消息的节点。  
  
    > [!NOTE]
    >  无需指定目标方 ID。 控制消息中需要此元素只是为了实现向后兼容性。  
  
3.  保存该文件。  
  
### <a name="to-enable-the-external-release-trigger"></a>启用外部发布触发器  
  
1.  在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**方和业务配置文件**页上，在**协议**部分中，右键单击具有批配置，需要到使用重写控制消息中，然后单击协议**属性**。 在**协议属性**对话框中，在单向协议选项卡上，单击**批配置**。  
  
2.  在**批配置**页上，单击想要有一个外部发布触发器，然后在批处理的选项卡**释放**部分中，选择**外部发布触发器**.  
  
3.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [配置 EDI 批处理](../core/configuring-edi-batches.md)   
 [如何创建接收位置](../core/how-to-create-a-receive-location.md)