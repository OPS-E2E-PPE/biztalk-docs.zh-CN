---
title: 发起方专用流程 |Microsoft Docs
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
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c718921f14e69916f2b1691d57fc51121bb965a8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013870"
---
# <a name="initiator-private-process"></a>发起方专用流程
Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]发起方专用流程 (PrivateInitiator.odx) 用于处理在发起方计算机上的服务内容。 其中包括：  
  
- 创建原始消息的服务内容和将消息路由到公用流程，路由到贸易合作伙伴  
  
- 处理返回信号消息并将其路由到业务 (LOB) 应用程序  
  
- 对于双操作 PIP，处理响应返回消息并将其路由到 LOB 应用程序。  
  
  专用流程还设置元数据，并将所有附件。 专用流程将传出消息路由到公用流程，用于添加 RosettaNet 实现框架 (RNIF) 标头并准备要传输的消息。 专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。  
  
  此专用流程自动执行使用 3A2 和 3A4 合作伙伴接口流程 (Pip) 购买查询/采购订单流程。 它还处理任何其他 PIP 消息。 你可以为您的特定业务流程自定义专用流程。  
  
## <a name="message-flow"></a>消息流  
 通过发起方专用流程的消息流如下所示：  
  
1. 发起方专用流程接收 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesFromLOB 表中的原始消息。 后端 LOB 应用程序将消息路由到此表。  
  
2. 专用流程准备的初始消息的服务内容，并将其发送到公用流程。  
  
3. 然后，发起方专用流程进入等待状态，侦听的返回信号。  
  
4. 接收到公用流程的返回信号以后，专用流程便构造一条信号消息，然后先将该信号消息发送到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再将其路由到 LOB 应用程序。  
  
5. 专用流程将发送到 LOB 应用程序的通知，它将信号消息放在 MessagesToLOB 表中。  
  
6. 如果 RNIF 版本 1.1，专用流程将等待接受确认信号消息。 如果它收到信号，它构造信号消息，并将信号发送到 MessagesToLOB 表中，路由到 LOB 应用程序。  
  
7. 如果原始消息是单操作消息，专用流程已完成的信号消息返回到 LOB 应用程序后。 如果原始消息是双操作消息，专用流程将侦听响应消息。  
  
8. 如果专用流程从公用流程收到响应消息，它构造中的 LOB 应用程序格式的响应消息。 这涉及到获取 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。  
  
9. 专用流程将消息路由到 MessagesToLOB 表中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。  
  
10. 如果响应消息的附件，专用流程调用 AttachmentHelper 工具来处理附件。  
  
11. 专用流程将通知发送到 LOB 应用程序，它在 MessagesToLOB 表中，将响应消息，则已完成。  
  
## <a name="handling-of-incorrect-messages"></a>不正确的消息的处理  
 当发起方专用流程从 LOB 应用程序收到一条错误消息时，专用流程将一条异常消息发送回 LOB。 但是，专用流程不在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理控制台张贴该错误消息。 因此，您不能在 BizTalk 管理控制台中查看不正确的消息。 可以使用异常消息访问错误消息，以确定哪个消息是错误的，然后从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA 数据库的 MessagesFromLOB 表中访问此错误消息。 但是，此消息可能不能相同作为消息处理私有的因为存储的过程和用于处理该消息的适配器对其进行编辑。 它们向消息中添加根元素和命名空间。 存储的过程和适配器可能返回多个记录。  
  
## <a name="see-also"></a>请参阅  
 [专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [响应方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)