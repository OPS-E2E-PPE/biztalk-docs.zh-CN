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
ms.openlocfilehash: 5fa1cd2fc73e37590e25fb381f509c2ad74cd9e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968438"
---
# <a name="initiator-public-process"></a>发起方公用流程
本流程通过创建并发送初始的 RNIF 业务消息，在发起方系统中启动 RosettaNet 实现框架 (RNIF) 消息传送。  
  
## <a name="message-flow-in-the-initiator-public-process"></a>发起方公用流程中的消息流  
 通过发起方公用流程的消息流如下：  
  
1. 发起方公用流程通过服务内容端口从专用流程接收服务内容和附件。  
  
2. 然后，该公用流程向专用流程发送响应，而不进行进一步的处理。  
  
3. 如果公用流程接收通知，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未成功发送消息，则公用流程将该状态发送回发起方专用流程，然后结束。  
  
4. 如果公用流程接收到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 成功发送消息的通知，则公用流程进入等待状态（等待响应方的操作）。  
  
5. 以下操作可以结束等待状态：  
  
   1.  公用流程收到响应方的确认信号。  
  
        如果要求信号的不可否认性（按照流程配置中的设置），则该流程将读取摘要，使信号中的摘要与原始操作消息中的摘要相关联，然后持久保留该信号。  
  
        公用流程将信号的头和服务内容发送到专用流程。  
  
   2.  公用流程从响应方接收双操作响应消息。  
  
        该流程提取响应消息中的服务内容和头，然后将其发送到专用流程。  
  
        如果活动是同步的，则该流程将使用前导头、服务头和（限于 RNIF 2.01）传递头对服务内容消息部分进行包装，从而构造 RNIF 信号消息。 该流程使用参与方之间的贸易合作伙伴协议中存储的以下信息来创建前导头和头：一是源参与方和目标参与方的配置信息，二是 PIP 变量； 然后，将信号消息发送到响应方。  
  
        如果活动是异步的，则该流程结束。  
  
   3.  公用流程从响应方接收失败通知 (NoF) 消息， 并将相应的状态消息发送到发起方专用流程。 然后，发起方专用流程对错误进行处理，并结束公用和专用流程。  
  
   4.  在确认时间期（按照在流程配置中的设置）内，公用流程未收到响应方的确认信号。 如果这样的话，会出现下列情况之一：  
  
        如果重试次数（按照流程配置中的设置）还没有到零，并且活动是异步的，则公用流程将再次发送消息。  
  
        如果重试次数（按照流程配置中的设置）还没有到零，并且活动是同步的，则公用流程将启动一个 0A1 消息。  
  
       > [!NOTE]
       >  CIDX 不支持 0A1 消息。  
  
        如果重试次数已经为零，发送还是不成功，则公用流程将发布错误消息；如果消息不是 CIDX，还要发送 0A1 消息。  
  
        如果活动是同步的，并且消息不是 CIDX，则公用流程将启动一个 0A1 消息。  
  
   5.  如果在“执行时间”期间内未发生任何操作，并且消息不是 CIDX，则公用流程将发送一个 0A1 消息。  
  
## <a name="see-also"></a>请参阅  
 [公用流程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [响应方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/responder-public-process.md)