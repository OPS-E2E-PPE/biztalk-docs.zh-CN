---
title: FRR 处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- FRR, processing
- FRR, components
- FRR, process flow
ms.assetid: 8b064d18-5ee7-44fd-95d1-9a0d66f1ad1a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c343d214a97895e90bae2bc3a041180c0cc8e3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987006"
---
# <a name="frr-processing"></a>FRR 处理
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] FIN 响应对帐 (FRR) 功能将与来自原始消息相关联 FIN 消息从 SWIFT 联盟访问 (SAA) [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] SAA 消息响应。 每当[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]发送原始消息时，FRR 缓存的和 SWIFT 绑定任何消息的副本不具有故障处理。 然后，它监视的响应消息返回到 SAA MessageBox [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，接收对应于缓存的消息复制任何 ACK/NAK 消息。  

 FRR 通过比较相关 ID 属性来建立传出消息和传入消息之间的相关性。 FRR 设置升级的属性的特性的响应，根据原始消息的副本，并随后将原始消息路由到 MessageBox 中以便进一步处理。  

## <a name="frr-components"></a>FRR 组件  
 FRR 包括一个持续的过程 （业务流程），用于监视传出和传入消息，并对于每个传出或传入消息，升级将用来比较标识属性。 一系列[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]组件一起使用 FRR 业务流程、 路由中的 FRR 组件之间的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]，和介于[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]和 SAA。 下面列出了这些组件：  

- FRR 接收位置从后端应用程序接收原始消息。  

- FRR 业务流程，用于监视传出和传入消息，并建立它们之间的相关性。  

- FRR 发送端口发送原始消息从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]SAA 到。  

- 用于使之间的数据传输的 MQSeries 的 BizTalk 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和 SAA （它使用 MQSeries 队列）。  

- FRR 接收位置用于接收来自 SAA FIN 响应消息。  

- FRR 发送端口，其中每个发送相关的消息中的特定类型的一组[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到后端应用程序进行自定义处理。  

  到更高版本的组件，可以添加后端自定义处理程序，用于处理原始消息的 FRR 已设置的升级的属性。  

## <a name="frr-process-flow"></a>FRR 处理流程  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 以下过程中执行对帐：  

1. 后端应用程序将路由到原始消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  

2. 接收的 FRR 接收位置接收消息、 在关联的接收管道中，对其进行处理，并将其路由到 BizTalk MessageBox。  

   > [!NOTE]
   >  可以结合使用 FRR[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]消息修复和新提交功能，或单独。 如果已安装消息修复和新提交，您可以在步骤 2 后配置消息修复的系统。 消息修复业务流程将修复/验证/批准消息路由回 BizTalk MessageBox 中以便后续 FRR 处理。  

3. 如果 MessageBox 中的消息的 SWIFT 绑定，并且已通过验证，[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]激活 FRR 业务流程实例。 业务流程将传出消息的副本。 然后，它处于激活状态等待来自 SAA，因此它可以与匹配任何传入的响应的传出消息的响应。 业务流程的此实例只处理该特定的传出消息和任何相关的响应该消息。 任何其他的消息的相同的类型，甚至是由业务流程的另一个实例进行处理。  

4. 在同一时间[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]FRR 业务流程实例，将激活[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]将消息路由到发送端口将消息发送到 SAA。 发送管道会升级消息标识属性和所需的处理通过 MQSeries 属性。 然后将该消息对 BizTalk 适配器发送的 MQSeries。  

5. 用于 MQSeries 的 BizTalk 适配器会将传输到位于 SAA 相应的 MQSeries 队列的消息。  

6. SAA 生成即时响应直接路由回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 SAA 然后将该消息路由到 SWIFT 网络。 SWIFT 网络生成其他响应，将其发送到 SAA 路由回[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。 SAA 将 FIN 响应消息的相关令牌属性设置为原始消息的消息的标识值。  

7. 通过用于 MQSeries 的 BizTalk 适配器 FIN 响应发回到 SAA 传输[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]。  

8. 接收的 FRR 接收位置接收的响应，并将路由该消息的 FRR 接收管道处理响应的相关标记。 它然后将响应放置到 BizTalk MessageBox 中。  

9. FRR 业务流程实例从 MessageBox 具有一个等于原始消息的副本的消息 ID 属性的相关标记提取的任何消息。  

10. 如果该响应指示原始消息已成功处理通过 SAA/SWIFT，FRR 业务流程实例将原始消息的副本将提升 A4SWIFT_Failed 属性设置为 False，并设置 BTS。操作属性设置为适当的值。  

11. 如果通过 SAA/SWIFT 原始消息未成功处理，FRR 业务流程实例设置 BTS。操作属性设置为适当的值，并将修复该消息然后指定通过 A4SWIFT_Failed 设置为 True 并提升 A4SWIFT_FRRFailedReason 属性设置为失败的原因。  

12. FRR 业务流程实例将丢弃的响应消息，并随后将原始消息的副本 （与升级的属性，该值指示响应） 路由到 MessageBox。  

13. 其中一个的 FRR 发送端口设置以将答复转到一个或多个自定义处理程序从其中提取已升级的属性的原始消息的副本。  

14. 自定义处理程序或处理程序订阅、 检索，并处理原始消息所需的后端应用程序的副本。
