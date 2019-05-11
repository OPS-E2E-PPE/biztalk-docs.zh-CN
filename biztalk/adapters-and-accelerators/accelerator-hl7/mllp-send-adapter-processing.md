---
title: MLLP 发送适配器处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- send adapters
- MLLP adapters, send adapters
ms.assetid: b8e47c7f-4a69-4f0c-86b4-26ed9c70613c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 180e11f3f4c4c0406927614d4351eb19fef1fb95
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290397"
---
# <a name="mllp-send-adapter-processing"></a>MLLP 发送适配器处理
最小的较低层协议 (MLLP) 发送适配器支持单向和双向传输模式中的以下配置：  
  
-   双向要求-响应发送适配器  
  
-   单向发送适配器配置为接收确认 (Ack)  
  
-   配置用于没有返回消息的单向发送适配器  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>双向要求-响应发送 MLLP 适配器  
 在 true 的端到端同步方案中使用此适配器。 在这种情况下，仅可使用此适配器与一个目标参与方。 发送适配器将持续维护针对远程方 (URL) 打开的连接之前它将返回的消息路由到请求响应接收端口。 请参阅下的图以了解请求要求响应/响应处理体系结构。  
  
 当使用此适配器时，可以指示系统 ACK 或响应消息返回到业务线应用程序。 这样将确认路由到与到发送管道中的请求响应接收端口设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 选择此属性以返回确认，或取消选中它，返回响应会议。  
  
 一旦使用此适配器的发送端口已成功发送原始消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]中删除该消息。 与此发送端口相关联的接收管道将不会生成确认。 BizTalk 会将查询响应转发到源应用程序而不考虑值的 MSA2 字段的响应。  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>配置为接收确认的单向发送处的 MLLP 适配器  
 此适配器在同一套接字连接它发送原始消息，并将确认传递到接收位置上接收确认。 发送适配器持续维护针对远程方 (URL) 打开的连接，即使没有消息正在等待[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将其发送给它。 如果多个端口都指向同一远程参与方，发送适配器会保持每个发送端口的一个连接。  
  
 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序安装的默认接收位置，TwoWayAckReceiveLocation。 可以使用此用于接收 Ack 的接收位置处的 MLLP 发送适配器。 使用此适配器的发送端口的此配置要求你将接收位置与发送端口相关联。  
  
 如果接收的 MSA 字段，将响应消息或支持多个目标已设置，请使用此发送端口。 使用 MSA 字段或多个目标，不会不起双向要求-响应适配器。  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>确认收到的单向 MLLP 发送适配器  
 当配置对于确认的单向 MLLP 发送适配器接收一个，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 MessageBox 数据库中删除原始消息、 重试，或将它，具体取决于类型的确认。 挂起 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将确认分析两个阶段：  
  
- 第一阶段在发送适配器中完成其中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析字段 MSA1 来确定类型的确认。  
  
- 在第二个阶段，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]执行 ACK，完成分析，然后提交到 MessageBox 数据库的确认。  
  
  配置双向发送适配器需要确认[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
  下表显示在原始消息 MLLP 发送适配器可以接收的确认和采取的操作。  
  
|收到的 ACK|在原始消息的操作|  
|------------------|------------------------------------|  
|提交接受，或应用程序接受|从 MessageBox 数据库中删除|  
|提交/应用程序、 拒绝确认或无效的确认|挂起|  
|提交/应用程序错误|重试/移动到备份传输/挂起|  
|静态确认成功|从 MessageBox 数据库中删除|  
|静态确认失败|挂起|  
  
 下表显示了无效的确认条件。  
  
|实例|条件|  
|--------------|---------------|  
|HL7 （原始，增强的、 延迟）|1.不包含的 XML。<br />2.不具有结构，因此不能检索 MSA1 字段;或 MSA1 字段不包含其中一个 CA、 AA、 CR，AR，CE （AE） 允许的值。|  
|Static|不会与成功的允许值之一匹配或失败确认。|  
|包含的 XML|接受确认 （而不考虑内容） 作为处理并删除原始消息。|  
  
### <a name="error-conditions"></a>错误条件  
 当出现错误条件或处于非活动状态时，可以执行以下操作：  
  
- 如果传出消息中序列化失败，除非它是一批消息，发送适配器将不发送该邮件，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]流式处理。 如果这种情况下，并[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]检测到序列化失败中途消息，适配器将不会发送以来 EB/CR[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不发送完成消息。 管道记录错误，并且适配器尝试重新发送该批处理消息。  
  
- 如果发送操作失败，适配器将尝试再次，将消息发送到发送端口配置设置中指定的重试次数。 用完重试次数后, 该消息将移到备份传输，如果存在。 如果所有其他方法均失败，则挂起消息。 对挂起的消息将以原始 (XML) 格式。  
  
  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 可以生成要描述的错误条件的以下事件：  
  
|        Event        |  ID  |                                                                                                                                   错误条件                                                                                                                                   |
|---------------------|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ErrorSendingMessage | 8450 | 无法将消息发送到远程参与方。 最常见原因是网络失败或超时。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 如果发送管道失败序列化大型消息时，可能会报告此错误。 |
|  ErrorReceivingAck  | 8451 |                                                                                                       可能不会收到确认，由于网络故障或超时。                                                                                                       |
|   ErrorConnecting   | 8453 |                                                    无法建立 TCP 连接到远程方-无法解析，主机名或远程方未侦听端口，或拒绝连接。                                                     |
  
> [!NOTE]
>  （在原始消息的 MSH5) 的目标参与方的配置确定是否[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]需要 HL7 或静态的确认。 如果不匹配， [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK 视为无效。  
  
 MLLP 发送适配器进程确认后，确认将被发送到接收位置，作为其自身上的消息。 拆装器执行完全分析的确认，这可能导致分析错误报告的接收管道和/或被挂起的确认。  
  
## <a name="see-also"></a>请参阅  
 [处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [配置参数，以便进行发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [设置用于接收 ACK 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)