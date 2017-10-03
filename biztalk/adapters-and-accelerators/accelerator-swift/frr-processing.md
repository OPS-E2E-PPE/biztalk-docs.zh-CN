---
title: "FRR 处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- FRR, processing
- FRR, components
- FRR, process flow
ms.assetid: 8b064d18-5ee7-44fd-95d1-9a0d66f1ad1a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2b0d34ccffd2bf09148bcfc5544b38ea5d0033d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="frr-processing"></a>FRR 处理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐 (FRR) 功能包含来自的原始消息关联 FIN 消息从 SWIFT 联盟访问 (SAA) [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SAA 消息响应。 每当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发送原始消息，FRR 缓存绑定 SWIFT 和的任何消息的副本不失败处理。 然后，它监视的响应消息返回到 SAA MessageBox [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，接收对应于缓存的消息副本的任何 ACK/否认消息。  
  
 FRR 通过比较相关性 ID 属性建立传出消息和传入消息之间的相关性。 FRR 设置的副本的原始消息的性质的响应，根据提升的属性，并随后将原始消息路由到 MessageBox 进行进一步处理。  
  
## <a name="frr-components"></a>FRR 组件  
 FRR 包括一个持续的过程 （业务流程），用于监视传出和传入消息，并为每个传出或传入消息，将提升将用于比较的标识属性。 一系列[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]组件结合起来，FRR 业务流程中的 FRR 组件之间路由消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，和之间[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]和 SAA。 下面列出了这些组件：  
  
-   FRR 接收从后端应用程序接收原始消息的位置。  
  
-   FRR 业务流程，用于监视传出和传入消息，并建立它们之间的相关性。  
  
-   FRR 发送端口发送原始消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]到 SAA。  
  
-   使之间的数据传输的 MQSeries BizTalk 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SAA （它使用 MQSeries 队列）。  
  
-   FRR 接收从 SAA 接收 FIN 响应消息的位置。  
  
-   一组的 FRR 发送端口，其中每个发送中特定类型的相关的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到的后端应用程序自定义处理。  
  
 上面的组件，你可以将添加到的后端自定义处理程序处理原始消息已由 FRR 设置种提升的属性。  
  
## <a name="frr-process-flow"></a>FRR 流程  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]在以下过程中执行对帐：  
  
1.  后端应用程序将路由到原始消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  
  
2.  FRR 接收位置接收消息，在关联的接收管道中对其进行处理并将它路由到 BizTalk MessageBox。  
  
    > [!NOTE]
    >  你可以结合使用 FRR[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交功能，或单独。 如果你已安装消息修复和新的提交，可以在步骤 2 后配置消息修复的系统。 消息修复业务流程将修复/验证/批准消息路由回到后续 FRR 处理 BizTalk MessageBox。  
  
3.  如果消息框中的消息被绑定到 SWIFT 和已通过验证，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]激活 FRR 业务流程的实例。 业务流程将在传出消息的副本。 然后，它处于激活状态等待来自 SAA，因此它可以匹配任何传入的响应的传出消息的响应。 业务流程的此实例仅处理该特定的传出消息和对该邮件的任何相关的响应。 任何其他消息，甚至优先于相同的类型，由业务流程的另一个实例处理。  
  
4.  在同一时间[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]激活 FRR orchestration 实例时，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息路由到将消息发送到 SAA 发送端口。 发送管道促进消息标识属性和所需的处理由 MQSeries 属性。 它然后将消息发送到 BizTalk 适配器为 MQSeries。  
  
5.  MQSeries BizTalk 适配器传输到 SAA 上的相应 MQSeries 队列消息。  
  
6.  SAA 生成用于直接路由回即时响应[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 SAA 然后将消息路由到 SWIFT 网络。 SWIFT 网络生成其他响应，它会将发送给 SAA 路由回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 SAA 将 FIN 响应消息的相关令牌属性设置为原始消息的消息标识值。  
  
7.  通过 MQSeries BizTalk 适配器 FIN 响应发回到 SAA 传输[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  
  
8.  FRR 接收位置接收响应，并将通过 FRR 条消息路由接收处理响应的相关标记的管道。 然后，它将响应放置在 BizTalk 消息框中。  
  
9. FRR 业务流程实例从那里获取的任何消息具有相关令牌等于原始消息的副本的消息 ID 属性 MessageBox。  
  
10. 如果该响应指示 SAA/SWIFT 成功处理原始消息，FRR 业务流程实例的副本的原始消息的 A4SWIFT_Failed 提升属性设置为 False，并设置 BTS。操作属性设置为适当的值。  
  
11. 如果未通过 SAA/SWIFT 成功处理原始消息，FRR 业务流程实例设置 BTS。为适当的值的操作属性，然后通过将 A4SWIFT_Failed 设置为 True 和 A4SWIFT_FRRFailedReason 提升属性设置为失败的原因指定修复的消息。  
  
12. FRR 业务流程实例放弃响应消息，并随后将原始消息的副本 （使用提升的属性，该值指示响应） 路由到 MessageBox。  
  
13. FRR 发送端口之一设置以便将路由到一个或多个自定义处理程序选取提升的属性的原始消息的副本的响应。  
  
14. 自定义处理程序或处理程序订阅中, 检索，并处理所需的后端应用程序的原始消息的副本。