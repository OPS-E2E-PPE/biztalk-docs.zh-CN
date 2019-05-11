---
title: FRR 业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, promoted properties
- orchestrations, message subscriptions
- promoted properties, messages
- FRR, orchestrations
- subscriptions, messages
- orchestrations, reconciliation time-out
- messages, message/response correlation
- message/response correlation
- promoted properties, FIN Response Reconciliation
- orchestrations, FRR
- outbound messages
- FIN Response Reconciliation, promoted properties
- direct bindings
- reconciliation time-out
- bindings, direct
- messages, subscriptions
- subscriptions, orchestrations
- messages, outbound
- MessageBox database
ms.assetid: ea8d31c2-ac3b-44ac-8064-d008da4f7f72
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c5cd411773555e87cb3395291b6b6f900e83a94
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377603"
---
# <a name="frr-orchestration"></a>FRR 业务流程
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 实现 FRR 通过 FRR 业务流程。 业务流程可确定的 FIN 响应的令牌相关的匹配原始消息的消息 ID。 与执行向 SAA，发送消息的发送端口的发送功能和执行的从 SAA 接收消息的接收位置的接收函数，它处理并行中的消息。  
  
 最高级别的业务流程实例将执行以下处理操作：  
  
1. 缓存原始出站消息的副本绑定 SAA 通过 MessageBox 上进行侦听。  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 创建业务流程的实例时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将原始消息路由到 MessageBox。  
  
2. 等待[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发布到 MessageBox SAA FIN 响应。  
  
3. 集的已提升属性的具体的性质 FIN 响应取决于原始消息的副本。  
  
4. 将原始消息的副本发布回 MessageBox。 自定义处理程序然后可以订阅以，检索，并处理所需的消息。  
  
## <a name="subscription-to-outbound-messages"></a>出站消息的订阅  
 FRR 业务流程直接绑定到 MessageBox 中。 FRR 业务流程订阅的所有出站消息绑定的 SWIFT 网络不包含验证错误，通过订阅到以下属性：  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed （所设置的 SWIFT 反汇编程序验证过程） = = false  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Swiftbound （所设置的 SWIFT 反汇编程序配置过程） = = true  
  
## <a name="messageresponse-correlation"></a>消息/响应相关  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 关联到入站 FIN 响应消息原始的出站 FIN 消息通过比较以下属性：  
  
- FIN 响应 MQMD_CorrelID 上下文属性  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 出站的 MTXYY 消息属性。 接收管道的参与方解析阶段升级此属性。  
  
  这些属性的值必须相同。 SWIFT 将传出消息的 MQMD_MsgID 属性设置为的值绑定的消息的发送管道的编码器阶段[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 属性。 SAA 将响应消息的 MQMD_CorrelID 属性设置为的 MQMD_MsgID 值。  
  
## <a name="setting-of-promoted-properties"></a>设置的已提升属性  
 在接收 FIN 响应和关联到原始消息的副本之后, FRR 业务流程将根据响应的性质，原始消息的副本的以下升级的属性：  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 true; 如果响应是 ACK 或 False，如果响应已发送 NAK _FRRFailed  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为以下值，如果响应已发送 NAK _FRRFailedReason:  
  
  -   *\<ErrorCode\>*  （从 MTS21_FIN_ACKNAK 否定确认消息的 405 字段）  
  
  -   TransportError （从 MQ 系列平移/NAN 消息）  
  
  -   DelayedNAK （从 MT015 (DNK) 消息）  
  
  -   AbortReceived (从 MT019 （中止通知） 消息)  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 TimedOut _FRRFailedReason 如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]超时期限内未收到响应。 有关 FRR 延迟超时的详细信息，请参阅下面的"对帐超时"部分或[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 _SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
- BTS。消息响应的类型相对应的值的操作。 有关详细信息，请参阅[为发送到自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendTransport MQ 系列平移/NAN 消息 (MQ Series 传输级 ACK/NAK)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend010NDW MT010 消息 （非传递警告）  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend011Delivered MT011 消息 （送达通知）  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend012SenderACK MT012 消息 （发件人通知）  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend015DNK MT015 消息 （DNK 或延迟 NAK）  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend019Abort MT019 消息 （中止通知）  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21ACK MTS21_FIN_ACKNAK 确认消息 (ACK 的发送 T 的 FIN 消息)  
  
  - [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21NAK MTS21_FIN_ACKNAK 否定确认消息 (NAK LT 发送 FIN 消息)  
  
## <a name="direct-binding"></a>直接绑定  
 接收输入的业务流程定义的业务流程利用到 MessageBox 的订阅。 上下文属性和值提升业务流程定义业务流程将发布到 MessageBox 的消息的发送输出。 由于此直接绑定到 MessageBox 中，就会从以下分离业务流程：  
  
- 物理接收位置接收来自后端应用程序路由到 SAA 的出站消息  
  
- 发送端口发送出站 FIN 消息从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 联盟访问 (SAA)  
  
- 从 SAA 接收传入 FIN 响应消息的接收位置  
  
- FIN 响应通过 SAA 的存入其中物理 MQSeries 队列  
  
## <a name="reconciliation-time-out"></a>对帐超时  
 当[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建 FRR 业务流程，该业务流程启动时将等待 FIN 响应的新实例。 在运行时，必须配置某些时间段后超时的业务流程，以便它将不响应无限期等待。 FRR 业务流程时超时持续时间到期，将升级[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason 属性并将其设置为 TimedOut。 然后，将发出消息发布到 MessageBox，并终止。 如果超时，相关性 ID 是消失了。  
  
 可以创建一个自定义处理程序来处理超时消息 （原始出站消息的副本）。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 实现此任务使用侦听形状在业务流程中。 有关详细信息，请参阅[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。