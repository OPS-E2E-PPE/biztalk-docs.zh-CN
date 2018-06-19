---
title: 响应方私有过程 |Microsoft 文档
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
ms.openlocfilehash: f8ba5ca38eb64859182242c944d260c9db15c880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210893"
---
# <a name="responder-private-process"></a>响应方私有过程
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用响应方专用流程 (PrivateResponder.odx) 来处理在响应方计算机的服务内容。 其中包括：  
  
-   传入消息路由到的业务线 (LOB) 应用程序  
  
-   创建响应消息的服务内容和将消息路由到公共过程中，在到响应方计算机的路由  
  
 专用流程还设置元数据，并添加到响应消息的任何附件。 专用的过程将传出的消息路由到响应方公共进程，后者将 RosettaNet 实现框架 (RNIF) 标头添加并准备要传输的消息。 专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个响应方专用流程示例，可以对其进行自定义以实现特定业务流程。 第一个示例是 PrivateResponder 流程示例，它包含 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装的响应方专用流程的代码。 有关详细信息，请参阅[PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。  
  
 第二个示例是自动执行使用 3A2 和 3A4 合作伙伴接口过程 (Pip) 购买查询/采购订单流程的 PIP3A4PrivateResponder 专用流程示例。 它还可以处理任何其他 PIP 消息。 有关详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。  
  
## <a name="message-flow"></a>消息流  
 响应方专用流程通过邮件流未，如下所示：  
  
1.  响应方私有进程接收从响应方公共进程从发起程序计算机的路由中的原始的传入消息。  
  
2.  专用流程构造 LOB 应用程序消息。 这涉及获得 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。  
  
3.  专用的过程将消息路由到 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库，在后端 LOB 应用程序的路由。  
  
4.  如果原始消息具有附件，专用流程将调用 AttachmentHelper 组件处理附件。  
  
5.  专用的过程会向 LOB 应用程序发送通知，它 MessagesToLOB 表中保存响应消息。  
  
6.  如果消息是单操作消息，专用的过程已完成。  
  
7.  如果消息已双操作消息，专用流程侦听来自 LOB 应用程序的响应。  
  
8.  当专用流程从 LOB 应用程序收到响应时，它将构造响应消息，并将消息发送到公共的进程。  
  
9. 专用的进程将等待来自公用流程的信号。 如果它收到信号，它将构造 LOB 信号消息并将其发送到 LOB 应用程序。 如果 RNIF 版本 1.1，专用的进程将侦听的第二个确认信号，并在接收它，、 将构造 LOB 信号消息和将其发送到 LOB 应用程序。 专用流程通知后发送每个信号消息的 LOB 应用程序。  
  
10. 如果专用流程收到通知失败 （起） 消息从发起方，路由中的公共过程专用流程构造"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]异常"消息，并将其发送到 LOB 应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [私有进程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [发起方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)