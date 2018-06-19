---
title: FRR 业务流程 |Microsoft 文档
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
ms.openlocfilehash: f56b16f59b967ccd9e57d03d38f86e64795da477
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967870"
---
# <a name="frr-orchestration"></a>FRR 业务流程
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]实现 FRR 通过 FRR 业务流程。 业务流程确定的 FIN 响应的令牌相关的匹配原始消息的消息 ID。 与执行向 SAA，发送消息的发送端口的发送功能和执行从 SAA 接收消息的接收位置接收函数，它将处理并行中的消息。  
  
 在最高级别中，业务流程的实例执行以下处理操作：  
  
1.  缓存的原始的出站消息的副本绑定 SAA 通过侦听 MessageBox。  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建业务流程的实例时[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将原始消息路由到 MessageBox。  
  
2.  等待[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发布到 MessageBox SAA FIN 响应。  
  
3.  集提升的副本的具体 FIN 响应的性质取决于原始消息的属性。  
  
4.  返回到 MessageBox 发布原始消息的副本。 自定义处理程序然后可以订阅，检索，并处理所需的消息。  
  
## <a name="subscription-to-outbound-messages"></a>向出站消息的订阅  
 FRR 业务流程直接绑定到 MessageBox。 所有通过订阅到以下属性不包含验证错误的出站消息 SWIFT 网络发往订阅 FRR 业务流程：  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Failed （如由 SWIFT 反汇编程序验证流程的组） = = false  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Swiftbound （如由 SWIFT 反汇编程序配置进程的组） = = true  
  
## <a name="messageresponse-correlation"></a>消息/响应相关  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]关联到入站 FIN 响应消息原始的出站 FIN 消息通过比较以下属性：  
  
-   FIN 响应 MQMD_CorrelID 上下文属性  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 属性的出站 MTXYY 消息。 此属性将由接收管道的参与方解析阶段提升。  
  
 这些属性的值必须完全相同。 消息发送管道的编码器阶段运往 SWIFT 设置的值的传出消息的 MQMD_MsgID 属性[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRCorrelationToken 属性。 SAA 将响应消息的 MQMD_CorrelID 属性设置为 MQMD_MsgID 的值。  
  
## <a name="setting-of-promoted-properties"></a>设置的已提升属性  
 在接收 FIN 响应并关联到原始消息的副本之后, FRR 业务流程将设置以下提升的属性的副本的原始消息根据响应的性质：  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 True，如果的响应为 ACK 或 False，如果此响应否认 _FRRFailed  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]下面的值，如果此响应否认于 _FRRFailedReason:  
  
    -   *\<ErrorCode\>*  （从 MTS21_FIN_ACKNAK 负确认消息的 405 字段）  
  
    -   TransportError （从 MQ 系列平移/NAN 消息）  
  
    -   DelayedNAK （从 MT015 (DNK) 消息）  
  
    -   AbortReceived (从 MT019 （中止的通知） 消息)  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 TimedOut _FRRFailedReason 如果[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]未在超时期限内收到响应。 有关 FRR 延迟超时的详细信息，请参阅下面的"对帐超时"一节或[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 _SendingServiceType [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrService  
  
-   BTS。对消息响应的类型与对应的值的操作。 有关详细信息，请参阅[为发送到的自定义处理程序创建 FRR 发送端口](../../adapters-and-accelerators/accelerator-swift/creating-the-frr-send-ports-for-sending-to-the-custom-handlers.md)。  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendTransport MQ 系列平移/NAN 消息 （MQ 系列传输级 ACK/否认）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend010NDW MT010 消息 （未送达警告）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend011Delivered MT011 消息 （传递通知）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend012SenderACK MT012 消息 （发件人通知）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend015DNK MT015 消息 （DNK 或延迟否认）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSend019Abort MT019 消息 （中止的通知）  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21ACK MTS21_FIN_ACKNAK 确认消息 (通过 LT 发送的 FIN 消息的 ACK)  
  
    -   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FrrSendS21NAK MTS21_FIN_ACKNAK 负确认消息 （否认的发送 LT 的 FIN 消息）  
  
## <a name="direct-binding"></a>直接绑定  
 业务流程定义由业务流程对 MessageBox 的订阅，则接收输入。 上下文属性和提升的业务流程的值定义业务流程将发布到 MessageBox 一条消息的发送输出。 由于此直接绑定到消息框中，业务流程的相互脱耦下表中：  
  
-   物理接收从路由到 SAA 的后端应用程序接收出站消息的位置  
  
-   发送出站发送端口鳍来自消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到 SWIFT 联盟访问 (SAA)  
  
-   从 SAA 接收传入 FIN 响应消息接收位置  
  
-   FIN 响应通过 SAA 的存储位置中的物理 MQSeries 队列  
  
## <a name="reconciliation-time-out"></a>对帐超时  
 当[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]创建 FRR 业务流程，则业务流程将启动该等待 FIN 响应的新实例。 在运行时，必须配置超时后某些持续时间，业务流程，以便它将不响应无限期等待。 时超时持续时间已满，FRR 业务流程会将提升[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_FRRFailedReason 属性并将其设置超时。 然后，将发出消息发布到 MessageBox，并终止。 如果超时，相关 ID 是消失。  
  
 你可以创建自定义处理程序能够处理超时消息 （原始的出站消息的副本）。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将可实现此目的使用侦听形状中业务流程。 有关详细信息，请参阅[设置 FRR 延迟超时](../../adapters-and-accelerators/accelerator-swift/setting-the-frr-delay-time-out.md)。