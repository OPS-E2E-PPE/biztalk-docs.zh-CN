---
title: 发起方公用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, initiator
- CIDX, 0A1 messages
- messages, 0A1 messages
- messages, message flow
- messages, public processes
- 0A1 messages
- public processes, message flow
ms.assetid: 371d0792-d346-405b-a8f4-2dfa64dd1566
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50506911108d21247f5da9cadc76cd505417a8d9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283503"
---
# <a name="initiator-public-process"></a>发起方公用流程
此过程将启动 RosettaNet 实现框架 (RNIF) 消息传送在发起方系统通过创建并发送初始的 RNIF 业务消息。  
  
## <a name="message-flow-in-the-initiator-public-process"></a>发起方公用流程中的消息流  
 通过发起方公用流程的消息流如下所示：  
  
1. 发起方公用流程的专用流程通过服务内容端口从接收服务内容和附件。  
  
2. 公用流程向专用流程发送响应，并不会无需进一步处理。  
  
3. 如果公用流程接收通知，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未成功发送消息，则公用流程将该状态发送回发起方专用流程，然后结束。  
  
4. 如果公用流程接收通知的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]成功发送消息，流程进入等待状态 （等待由响应方操作）。  
  
5. 以下操作可以结束等待状态：  
  
   1.  公用流程从响应方接收的确认信号。  
  
        如果信号的不可否认 （按照流程配置设置中），所需进程读取摘要、 关联信号中的摘要与原始操作消息中的摘要，然后持久保留该信号。  
  
        公用流程向专用流程发送标头和服务内容的信号。  
  
   2.  公用流程从响应方接收双操作响应消息。  
  
        该过程从响应消息中提取的服务内容和标头，并将其发送到专用流程。  
  
        如果活动是同步的该过程通过将服务内容消息部分使用前导头、 服务头和传递头包装 （对于 RNIF 2.01) 构造 RNIF 信号消息。 进程创建的前导码和标头使用源和目标参与方和参与方之间的贸易合作伙伴协议中存储的 PIP 变量的配置信息。 然后，过程将信号消息发送到响应方。  
  
        如果活动是异步的则在进程结束。  
  
   3.  公用流程从响应方接收失败通知 (NoF) 消息。 公用流程将相应的状态消息发送到发起方专用流程。 专用流程然后处理该错误并结束这两个进程。  
  
   4.  公用流程未收到的确认信号响应方的时间内到确认期 （按照流程配置设置中设置）。 如果是这样，会发生下列情况之一：  
  
        如果重试的次数 （按照流程配置设置中） 还没有到零，并且活动是异步，则公用流程将再次发送消息。  
  
        如果重试的次数 （按照流程配置设置中） 还没有到零，并且活动是同步，则公用流程将启动一个 0A1 消息。  
  
       > [!NOTE]
       >  CIDX 不支持 0A1 消息。  
  
        如果重试次数达到零，而无需成功发送，则公用流程将发布错误消息，并且如果这不是 CIDX，则公用流程将发送 0A1 消息。  
  
        如果活动是同步的并且不是 CIDX，则公用流程将启动一个 0A1 消息。  
  
   5.  如果与执行持续时间的时间内发生任何操作并不是 CIDX，则公用流程将发送 0A1 消息。  
  
## <a name="see-also"></a>请参阅  
 [公用流程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [响应方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)