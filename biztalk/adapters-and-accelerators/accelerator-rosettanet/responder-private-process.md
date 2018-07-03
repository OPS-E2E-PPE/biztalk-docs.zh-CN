---
title: 响应方专用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 045559ad13492055e0e63a0cb19c4e7e780d5252
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989614"
---
# <a name="responder-private-process"></a>响应方专用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用响应方专用流程 (PrivateResponder.odx) 处理响应方计算机上的服务内容。 其中包括：  
  
- 传入消息路由到业务 (LOB) 应用程序  
  
- 创建响应消息的服务内容和将消息路由到公用流程，在响应方计算机的路由  
  
  专用流程还设置元数据，并将响应消息的任何附件。 专用流程将传出消息路由到响应方公用流程，用于添加 RosettaNet 实现框架 (RNIF) 标头并准备要传输的消息。 专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。  
  
  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个响应方专用流程示例，可以对其进行自定义以实现特定业务流程。 第一个示例是 PrivateResponder 流程示例，它包含 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装的响应方专用流程的代码。 有关详细信息，请参阅[PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。  
  
  第二个示例是自动执行使用 3A2 和 3A4 合作伙伴接口流程 (Pip) 购买查询/采购订单流程 PIP3A4PrivateResponder 专用流程示例。 它还处理任何其他 PIP 消息。 有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
## <a name="message-flow"></a>消息流  
 通过响应方专用流程的消息流如下所示：  
  
1. 响应方专用流程从响应方公用流程从发起方计算机的路由中接收的原始的传入消息。  
  
2. 专用流程构造 LOB 应用程序消息。 这涉及到获取 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。  
  
3. 专用流程将消息路由到 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中路由到后端 LOB 应用程序数据库。  
  
4. 如果原始邮件的附件，专用流程将调用 AttachmentHelper 组件来处理附件。  
  
5. 专用流程将通知发送到 LOB 应用程序它保存在 MessagesToLOB 表中的响应消息。  
  
6. 如果消息是单操作消息，专用流程已完成。  
  
7. 如果消息是双操作消息，专用流程将侦听来自 LOB 应用程序的响应。  
  
8. 当专用流程从 LOB 应用程序收到响应时，它构造响应消息，并将消息发送到公用流程。  
  
9. 专用流程将等待来自公用流程的信号。 如果它收到信号，它构造 LOB 信号消息，并将其发送到 LOB 应用程序。 如果 RNIF 版本 1.1，专用流程将侦听的第二个确认信号，并在收到它时将构造 LOB 信号消息，将其发送到 LOB 应用程序。 专用流程通知后将每个信号消息发送的 LOB 应用程序。  
  
10. 如果专用流程从公用流程，在路由中来自发起方，接收失败通知 (NoF) 消息的专用流程将构造"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]异常"消息，并将其发送到 LOB 应用程序。  
  
## <a name="see-also"></a>请参阅  
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)