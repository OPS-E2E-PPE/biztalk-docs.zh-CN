---
title: "发起方私有过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d176a15ba5236d5f44d87406d9bbc0a19fca9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="initiator-private-process"></a>发起方私有过程
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]发起方私有流程 (PrivateInitiator.odx) 用于处理服务发起程序计算机上的内容。 其中包括：  
  
-   创建原始消息的服务内容和将消息路由到贸易合作伙伴的路由中的公共过程  
  
-   处理返回的信号消息并将其路由到的业务线 (LOB) 应用程序  
  
-   对于双操作 PIP，处理响应返回消息并将其路由到 LOB 应用程序。  
  
 专用流程还设置元数据，并添加任何附件。 专用的过程将传出的消息路由到公共的进程，后者将 RosettaNet 实现框架 (RNIF) 标头添加并准备要传输的消息。 专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。  
  
 此专用的过程会自动进行使用 3A2 和 3A4 合作伙伴接口过程 (Pip) 的购买查询/采购订单进程。 它还可以处理任何其他 PIP 消息。 你可以为特定的业务流程自定义专用的流程。  
  
## <a name="message-flow"></a>消息流  
 消息流通过发起方私有流程如下所示：  
  
1.  发起方专用流程接收 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesFromLOB 表中的原始消息。 后端 LOB 应用程序将消息路由到此表中。  
  
2.  专用流程准备一条启动消息的服务内容，并将其发送到公用的流程。  
  
3.  在发起方私有进程然后进入等待状态，侦听返回信号。  
  
4.  接收到公用流程的返回信号以后，专用流程便构造一条信号消息，然后先将该信号消息发送到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再将其路由到 LOB 应用程序。  
  
5.  专用的过程将发送到 LOB 应用程序的通知，它将信号消息放入 MessagesToLOB 表。  
  
6.  如果 RNIF 版本 1.1，专用的进程在等待接受确认信号消息。 如果它收到信号，它将构造信号消息，并将信号发送到 MessagesToLOB 表中，在 LOB 应用程序的路由。  
  
7.  如果原始消息是单操作消息，专用的过程已完成的它具有 LOB 应用程序返回信号消息之后。 如果原始消息已双操作消息，专用流程侦听的响应消息。  
  
8.  如果专用流程从公共过程接收响应消息，它会构造的 LOB 应用程序格式的响应消息。 这涉及获得 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。  
  
9. 专用的过程将消息路由到 MessagesToLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。  
  
10. 如果响应消息具有附件，专用流程将调用该 AttachmentHelper 工具处理附件。  
  
11. 它将响应消息放入 MessagesToLOB 表，并则已完成，专用流程 LOB 应用程序发送通知。  
  
## <a name="handling-of-incorrect-messages"></a>不正确的消息的处理  
 当发起程序专用流程从 LOB 应用程序收到不正确的消息时，专用的过程会将一条异常消息发送回 LOB。 但是，专用流程不在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理控制台张贴该错误消息。 因此，你不能在 BizTalk 管理控制台中查看不正确的消息。 可以使用异常消息访问错误消息，以确定哪个消息是错误的，然后从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA 数据库的 MessagesFromLOB 表中访问此错误消息。 但是，此消息可能不是使用，专用处理的消息相同因为的存储的过程和用来处理该消息适配器对其进行编辑。 它们可以将根元素和命名空间添加到消息。 存储的过程和适配器可能返回多个记录。  
  
## <a name="see-also"></a>另请参阅  
 [私有进程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md)   
 [响应方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md)   
 [业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)   
 [PrivateInitiator 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)