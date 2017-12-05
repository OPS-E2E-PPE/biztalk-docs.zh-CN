---
title: "设置发送端口用于接收确认 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df0988a9edc2af81970237aad363315a778f821b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>设置发送端口用于接收确认
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以在单向发送端口上接收确认 (ACK)。 如果你设置了新的单向发送端口用于同一连接上接收确认，你必须将关联该发送端口使用单向接收端口。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序创建单向接收端口 (调用**TwoWayAckReceivePort**) 和接收位置 (称为**TwoWayAckReceiveLocation**)。 接收位置使用的最小较低层协议 (MLLP) 传输类型、 具有 URI 的"127.0.0.1:65535"，并使用**BTAHL72XReceivePipeline**。 这些是用于接收所需的设置和处理针对一条消息接收的 ACK 由发送出去[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送适配器，在双向模式下。 此接收位置不应删除或任何其他用途。 永远不会将数据发送到此接收位置。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将默认的启用此 receive 按列出的位置。  
  
 **TwoWayAckReceiveLocation**，后者[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装向导创建，使用**BizTalkServerApplication**作为接收处理程序。 但是，如果你选择创建新的主机并将其用作接收处理程序 MLLP，则你必须执行以下操作来创建一个新**TwoWayAckReceiveLocation**:  
  
1.  创建单向接收端口。  
  
2.  创建单向 MLLP 接收位置。  
  
3.  指定 MLLP 传输属性的相应值。  
  
4.  指定相应接收处理程序。  
  
5.  启用接收位置。  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>若要创建启用接收同一套接字上的 ACK 发送端口  
  
1.  打开 BizTalk 管理控制台中，，然后展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk应用程序 1**。 右键单击**发送端口**，指向新建，然后单击**静态单向发送端口**。  
  
2.  在**名称**框中，键入发送端口的名称。  
  
3.  在**传输**部分中，为**类型**，选择**MLLP**。  
  
4.  单击**配置**。  
  
5.  在 MLLP 传输属性对话框中，键入连接名称和主机 (例如， **localhost**)。  
  
6.  有关**请求作出响应启用**，选择**是**。 保留**提交接收位置 (URI) ACK**为空，并依次**确定**。  
  
    > [!NOTE]
    >  当你退出**提交接收位置**保留为空，BTAHL7 输入 URI 默认**TwoWayAckReceiveLocation**。 你可以验证，之后单击**确定**第 6 步中，通过单击**配置**试。 Uri，该 URI **TwoWayAckReceiveLocation** (127.0.0.1:65535) 将被放入**提交接收位置 (URI) ACK**。  
  
    > [!NOTE]
    >  你必须创建订阅接收，ACK 发送端口或 ACK 将会被发现处于挂起状态，因为未找到的订阅。 若要订阅发送端口收到 ACK，使用筛选器，例如，  **BTS。MessageType = = \<* MessageType*\>* * 和 **BTS。ReceivePortName = = \<*接收端口*\>* *。 对于静态 Ack 消息类型是**StaticAck**。  
  
7.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [错误条件确认](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)