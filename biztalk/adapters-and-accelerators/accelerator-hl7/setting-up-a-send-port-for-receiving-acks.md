---
title: 设置发送端口用于接收 Ack |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, acknowledgements
- creating, send ports
- acknowledgements, send ports
- send ports, creating
ms.assetid: bb683e72-36e2-4a8f-acc2-8b37ed23746f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2489a8c26d418782e661629afd65f3bafd3b03ff
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289589"
---
# <a name="setting-up-a-send-port-for-receiving-acks"></a>设置用于接收 Ack 的发送端口
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以在一个单向发送端口上接收确认 (ACK)。 如果设置了新的单向发送端口用于接收 Ack 的同一连接上时，必须将关联该发送端口使用一个单向接收端口。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 安装程序将创建一个单向接收端口 (称为**TwoWayAckReceivePort**) 和接收位置 (称为**TwoWayAckReceiveLocation**)。 接收位置使用的最小的较低层协议 (MLLP) 传输类型、 uri 为"127.0.0.1:65535"，并使用**BTAHL72XReceivePipeline**。 这些是用于接收所需的设置和处理对消息接收到 ACK 发送的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送适配器，在双向模式下。 此接收位置不应删除或任何其他用途。 永远不会将数据发送到此接收位置。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 允许此接收位置的默认值。  
  
 **TwoWayAckReceiveLocation**，后者[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]安装程序向导创建，使用**BizTalkServerApplication**为接收处理程序。 但是，如果您选择创建新的主机，并为 MLLP 的接收处理程序使用它，然后你必须执行以下操作来创建一个新**TwoWayAckReceiveLocation**:  
  
1.  创建一个单向接收端口。  
  
2.  创建一个单向 MLLP 接收位置。  
  
3.  指定为 MLLP 传输属性的相应值。  
  
4.  指定相应的接收处理程序。  
  
5.  启用接收位置。  
  
### <a name="to-create-a-send-port-enabled-to-receive-an-ack-on-the-same-socket"></a>若要创建启用了接收相同的套接字上的 ACK 的发送端口  
  
1.  打开 BizTalk 管理控制台，然后展开**BizTalk Server 管理**， **BizTalk 组**，**应用程序**，和**BizTalk应用程序 1**。 右键单击**发送端口**，指向新建，，然后单击**静态单向发送端口**。  
  
2.  在中**名称**框中，键入发送端口的名称。  
  
3.  在中**传输**部分中，对于**类型**，选择**MLLP**。  
  
4.  单击**配置**。  
  
5.  在处的 MLLP 传输属性对话框中，键入连接名称和主机 (例如， **localhost**)。  
  
6.  有关**要求响应启用**，选择**是**。 将保留**提交接收位置 (URI) ACK**保留为空，然后依次**确定**。  
  
    > [!NOTE]
    >  当你退出**提交接收位置**保留为空，BTAHL7 进入 URI 默认**TwoWayAckReceiveLocation**。 你可以验证该后单击**确定**第 6 步中，通过单击**配置**试。 URI **TwoWayAckReceiveLocation** (127.0.0.1:65535) 将被放入**提交接收位置 (URI) 确认**。  
  
    > [!NOTE]
    >  必须创建用于订阅接收确认的发送端口或确认将会看到处于挂起状态，因为未找到订阅。 若要订阅发送端口接收的确认，请使用筛选器，例如， **BTS。MessageType = = \< *MessageType* \>** 和**BTS。ReceivePortName = = \< *ReceivePort*\>**。 对于静态确认消息类型是**StaticAck**。  
  
7.  单击“确定” 。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [错误条件确认](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)