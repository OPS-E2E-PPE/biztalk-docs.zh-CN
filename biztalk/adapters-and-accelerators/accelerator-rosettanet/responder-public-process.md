---
title: 响应方公用流程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c89c246bca80fdb648df909cd4f01fca4e2691dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210861"
---
# <a name="responder-public-process"></a>响应方公共过程
响应方在此公共过程从发起方，接收 RosettaNet 实现框架 (RNIF) 消息，并相应地做出响应。  
  
## <a name="message-flow-in-the-responder-public-process"></a>响应方公共过程中的消息流  
 响应方公共过程通过邮件流未，如下所示：  
  
1.  响应方公共过程从响应方 MessageBox 数据库接收 RNIF 消息。  
  
2.  公共过程从操作消息提取的服务内容和标头，并将其发送到专用的流程。  
  
    > [!NOTE]
    >  响应方公共过程对传入的消息 （和任何其他验证包含在验证适配器中，如果适用） 执行标准的验证。 如果验证成功，公用流程将启动应用程序适配器来执行特定的实现根据通知。 响应方公共过程会将消息保存在 MessageBox 数据库中，并将通知响应方专用流程，因此具有消息保存到 MessageBox (使用`BeginNotify`中的方法`ApplicationAdapter`类)。 有关验证适配器和应用程序适配器的详细信息，请参阅[ValidationAdapter &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)和[ApplicationAdapter &#91;RN3 &#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).  
  
3.  如果活动是异步的单个操作，公共过程通过包装服务内容消息部分与该前导码，服务标头，并 （在 RNIF 2.01) 来构造一条 RNIF 信号消息 （确认接受） 的传递标头。 公共过程构造该前导码、 服务标头和使用方之间的贸易合作伙伴协议中存储信息的传递标头： 过程配置设置、 有关源的配置信息和目标方和合作伙伴接口过程 (PIP) 变量。 然后，过程将信号消息发送到发起方。  
  
    > [!NOTE]
    >  如果消息是单操作消息，消息流已完成。  
  
4.  在公共进程进入等待状态 （等待操作由响应方私有进程）。  
  
5.  以下操作可以结束等待状态 （等待操作由响应方私有进程）：  
  
    1.  响应方专用流程返回响应服务内容消息和标头，以响应的原始操作消息 （是双操作消息）。  
  
         如果公共过程从专用流程收到响应服务内容，公共过程构造包含服务内容的 RNIF 消息。 它会通过包装了服务内容消息部分和标头包含有关源和目标方和 PIP 变量存储在双方之间的协议的配置信息。  
  
         公共过程将 RNIF 消息发送到发起方使用的操作/信号角色链接端口。  
  
         如果公共进程接收通知， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未未成功发送消息、 公共过程将状态发送回专用的过程中，连接，然后结束。  
  
         如果公用流程接收到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 成功发送消息的通知，则公用流程进入等待状态（等待发起方的操作）。 该等待状态是类似于时它正在等待由响应方的操作进入发起方等待状态。  
  
    2.  公共过程从发起方接收故障通知消息 （起）。  
  
    > [!NOTE]
    >  它已成功处理传入的消息后，响应方专用流程将通知响应方公共过程。 仅在对响应方后公用流程已收到此通知 (从`EndNotify`中的方法`ApplicationAdapter`类) 将成功完成的响应方公共过程。  
  
6.  响应方公共进程进入等待状态 （正在等待从发起方到响应方公共过程发送响应消息的响应中收到信号）。  
  
## <a name="see-also"></a>另请参阅  
 [公共进程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [发起方公共流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)   
 [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)   
 [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)