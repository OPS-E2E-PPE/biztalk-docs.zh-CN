---
title: "MLLP 发送适配器处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, send adapters
- send adapters
- MLLP adapters, send adapters
ms.assetid: b8e47c7f-4a69-4f0c-86b4-26ed9c70613c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1644d699014f23ce90568034c4bd90f6f0c7b099
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-send-adapter-processing"></a>MLLP 发送适配器处理
最小较低层协议 (MLLP) 发送适配器支持下列配置中的单向和双向传输模式：  
  
-   双向请求作出响应发送适配器  
  
-   单向发送适配器配置为接收确认 (Ack)  
  
-   针对任何返回的消息配置单向发送适配器  
  
## <a name="two-way-solicit-response-send-mllp-adapter"></a>双向请求作出响应发送 MLLP 适配器  
 在真正的端到端同步方案使用此适配器。 在这种情况下，仅可与一个目标方使用此适配器。 发送适配器将持续维护针对远程方 (URL) 打开的连接之前它将返回的消息路由到请求响应接收端口。 请参阅下图以了解请求的请求作出响应/响应处理体系结构。  
  
 当你使用此适配器时，你可以指示系统将 ACK 或响应消息返回到业务线应用程序。 您上执行此操作与路由 ACK 到发送管道中的请求响应接收端口设置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。 选择此属性以返回 ACK，或取消选中它，返回响应会议。  
  
 一旦使用此适配器发送端口已成功发送原始消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]删除该消息。 与此发送端口关联的接收管道将不会生成确认 BizTalk 将转发到源应用程序无论值如何该响应 MSA2 字段的查询响应。  
  
## <a name="one-way-send-mllp-adapter-configured-to-receive-acks"></a>单向发送 MLLP 适配器配置为接收确认  
 此适配器在它发送原始消息，并将确认传递到接收位置的同一套接字连接上接收确认。 发送适配器持续维护针对远程方 (URL) 打开的连接，即使没有邮件正在等待[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将其发送给它。 如果多个端口均指向同一个远程方，发送适配器维护每个发送端口的一个连接。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 安装程序安装的默认接收位置，TwoWayAckReceiveLocation。 你可以使用此用于接收确认接收与 MLLP 发送适配器的位置。 使用此适配器发送端口的这种配置要求你将接收位置与发送端口相关联。  
  
 如果你设置以接收响应消息具有 MSA 字段，或以支持多个目标，请使用此发送端口。 不工作的双向请求作出响应适配器不使用 MSA 字段或使用多个目标。  
  
### <a name="acknowledgments-received-by-the-one-way-mllp-send-adapter"></a>确认收到单向 MLLP 发送适配器  
 当配置的 Ack 的单向 MLLP 发送适配器收到一个，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]从 MessageBox 数据库中删除原始消息、 重试，或将它，具体取决于的确认类型挂起 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在两个阶段来分析 ACK:  
  
-   第一阶段完成发送适配器中其中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析字段 MSA1 来确定的确认类型  
  
-   在第二个阶段，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]执行 ACK，完成分析，然后提交到 MessageBox 数据库 ACK。  
  
 配置双向发送适配器要求在 ACK[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
 下表显示对原始消息接收 MLLP 发送适配器可以用于确认和产生的操作。  
  
|收到的确认|对原始消息的操作|  
|------------------|------------------------------------|  
|提交接受，或应用程序接受|从 MessageBox 数据库中删除|  
|提交/应用程序、 拒绝 ACK 或无效的 ACK|挂起|  
|提交/应用程序错误|重试/移动到备份传输/挂起|  
|静态 ACK 成功|从 MessageBox 数据库中删除|  
|静态 ACK 失败|挂起|  
  
 下表显示不是有效的 ACK 条件。  
  
|实例|条件|  
|--------------|---------------|  
|HL7 （原始，得到增强，延迟）|1.不包含 XML。<br />2.没有结构，因此无法检索 MSA1 字段;或 MSA1 字段不包含某个允许的值 （CA、 AA、 CR，AR、 CE、 遍历）。|  
|静态|不会与成功的允许值之一匹配或失败确认|  
|包含 XML|视为验收 ACK （无论内容） 和删除原始消息。|  
  
### <a name="error-conditions"></a>错误条件  
 出现错误条件或处于非活动状态时，可以执行以下操作：  
  
-   如果传出消息中序列化失败，除非它是一批消息，发送适配器将不发送消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]流式处理。 如果是这种情况，和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]检测到序列化故障中途消息，该适配器将不会发送 EB/CR 自[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]尚未发送完整的消息。 管道记录错误，并且适配器尝试重新发送批处理消息。  
  
-   如果发送操作失败，该适配器将尝试再次，将消息发送到发送端口配置设置中指定的重试次数。 耗尽重试次数后, 该消息将移到备份传输，如果存在。 如果所有其他方法均失败，则挂起消息。 挂起的消息将在原始 (XML) 窗体中。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以生成来描述的错误条件的以下事件：  
  
|事件|ID|错误条件|  
|-----------|--------|---------------------|  
|ErrorSendingMessage|8450|无法将消息发送给远程方。 最常见原因是网络失败或超时。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]如果发送管道失败序列化一个大的消息时，可能会报告此错误。|  
|ErrorReceivingAck|8451|无法接收确认时，由于网络故障或超时。|  
|ErrorConnecting|8453|无法建立 TCP 连接到远程方-无法解析主机名或远程方不侦听端口或拒绝连接。|  
  
> [!NOTE]
>  （在原始消息的 MSH5) 的目标方的配置确定是否[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]需要 HL7 或静态确认 如果不匹配， [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK 视为无效。  
  
 MLLP 发送适配器进程的 ACK 后，会将 ACK 传送到作为其自身上消息的接收位置。 反汇编程序执行完全分析的 ACK，这可能会导致分析报告的接收管道错误和/或挂起的确认。  
  
## <a name="see-also"></a>另请参阅  
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [配置参数发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 接收适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-receive-adapter-processing.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)