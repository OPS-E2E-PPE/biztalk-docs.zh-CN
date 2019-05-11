---
title: 实现外部批处理发布机制 |Microsoft Docs
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
ms.openlocfilehash: e278fff5f04566f8c6b01777f1523e60373e1457
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382680"
---
# <a name="implementing-an-external-batch-release-mechanism"></a>实现外部批处理发布机制
可以触发使用外部发布触发器批处理的发布。 可以通过一个后端业务线应用程序，一旦达到特定阈值自动触发发布。 此机制是自动触发批处理发布通过计划或事务集或字符的计数或手动触发通过单击的补充**重写**按钮在**批处理配置**页的单向协议选项卡。  
  
 若要实现外部发布触发器，需要设置接收端口和位置以便处理 OverrideControlMessage。 接收位置必须使用`Edi.BatchControlMessageRecvPipeline`接收管道。 这是同一管道，由 BatchControlMessageRecvLoc 接收位置的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于处理手动替代消息。 不过，BatchControlMessageRecvLoc 是 SQL 类型的接收位置，而为外部发布触发器设置的接收位置可以使用任何适配器类型。  
  
 由 XML 控制消息触发外部批处理发布。 若要触发批处理后, 端应用程序控制将消息路由到接收位置。 可以修改控制消息，以便激活、 替代或终止批处理。 请参阅下面有关创建控制消息的过程。  
  
 若要启用外部发布触发器，必须选择**外部发布触发器**属性中的**批配置**页**协议属性**对话框对于 X12 或 EDIFACT 的框。 此属性指示批处理发布需要外部发布消息。 **重写**按钮，**停止**按钮，并**激活**范围控件仍将有效如果**外部发布触发器**属性已选择。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-create-a-receive-location-for-the-external-batch-release-trigger-message"></a>若要创建外部批处理发布触发器消息的接收位置  
  
1. 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建一个单向接收端口。 有关如何创建接收端口的说明，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
2. 在接收端口中创建一个单向接收位置。  
  
3. 选择传输类型。 为此接收位置，可以选择任何类型。 常见的解决方案是选择文件类型，并输入用于接收文件的文件夹。  
  
4. 对于接收管道中，选择`BatchControlMessageRecvPipeline`。  
  
5. 单击“确定” 。  
  
### <a name="to-create-the-external-batch-release-trigger-message"></a>若要创建外部批处理发布触发器消息  
  
1. 在记事本中，创建一个新文件并将其命名扩展名为.xml。  
  
2. 以下代码添加到该文件：  
  
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
  
    按如下所示替换以上摘录中的值：  
  
   - 指定操作类型。 通常情况下， **ActionType**必须设置为**EdiBatchOverride**替代协议中完成的批处理设置。 此外可以将此设置为**EdiBatchTerminate**通过外部触发器批处理终止。  
  
     > [!NOTE]
     >  Microsoft 建议您不要使用外部发布触发器来激活批处理。 因此，不应指定**ActionType**作为**EdiBatchActivate**。  
  
   - 确定批 ID 和批处理名称。 若要执行此操作，打开**协议属性**对话框框中，然后在单向协议选项卡上，单击**批配置**。 单击要重写和输入的值的批的选项卡**批名称**并**批处理 ID**到字段**BatchName**和**BatchID**控制消息的节点。  
  
   - 指定目标参与方名称。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**参与方和业务配置文件**页上，获取将接收批的参与方/合作伙伴的名称交换。 输入中的名称**ReceiverPartyNameType**节点的控制消息。  
  
   - 指定发送方的参与方名称。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**参与方和业务配置文件**页上，获取将发送批处理的交换的参与方/合作伙伴的名称. 输入中的名称**SenderPartyName**节点的控制消息。  
  
   - 指定协议名称。 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**参与方和业务配置文件**页上，在**协议**部分中，右键单击，需要为使用重写控制消息，然后单击其批处理配置的协议**属性**。 在中**协议属性**对话框中**常规**选项卡中，**常规属性**页上，复制从值**名称**字段中**协议参数**部分，并将其粘贴**AgreementName**节点的控制消息。  
  
   > [!NOTE]
   >  不需要指定目标参与方 id。 元素必须为仅对向后兼容性的控制消息中。  
  
3. 保存该文件。  
  
### <a name="to-enable-the-external-release-trigger"></a>若要启用外部发布触发器  
  
1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点，并从**参与方和业务配置文件**页上，在**协议**部分中，右键单击，需要为使用重写控制消息，然后单击其批处理配置的协议**属性**。 在中**协议属性**对话框中，在单向协议选项卡上，单击**批配置**。  
  
2. 在中**批配置**页上，单击想要有一个外部发布触发器，然后在批的选项卡**发行**部分中，选择**外部发布触发器**.  
  
3. 单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [配置 EDI 批](../core/configuring-edi-batches.md)   
 [如何创建接收位置](../core/how-to-create-a-receive-location.md)