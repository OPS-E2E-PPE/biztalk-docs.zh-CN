---
title: 响应方公用流程 |Microsoft Docs
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
ms.openlocfilehash: 7a98cfde175b9377be11bf4b18570eb93bd16437
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282427"
---
# <a name="responder-public-process"></a>响应方公用流程
响应方在此公用流程接收 RosettaNet 实现框架 (RNIF) 消息从发起方，并做出相应响应。  
  
## <a name="message-flow-in-the-responder-public-process"></a>响应方公用流程中的消息流  
 通过响应方公用流程的消息流如下所示：  
  
1. 响应方公用流程从响应方 MessageBox 数据库接收 RNIF 消息。  
  
2. 公用流程从操作消息提取的服务内容和标头，并将其发送到专用流程。  
  
   > [!NOTE]
   >  响应方公用流程执行标准验证传入消息 （和任何其他验证包含在验证适配器，如果适用）。 如果验证成功，则公用流程将启动应用程序适配器来执行特定的实现根据通知。 响应方公用流程会将消息保存在 MessageBox 数据库中，并将通知响应方专用流程，它具有该消息保存在 MessageBox 中 (使用`BeginNotify`中的方法`ApplicationAdapter`类)。 有关验证适配器和应用程序适配器的详细信息，请参阅[ValidationAdapter &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)并[ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)。  
  
3. 如果活动是异步的单个操作，则公用流程构造 RNIF 信号消息 （确认接受），方法是包装服务内容消息部分使用前导头、 服务头和 （适用于 RNIF 2.01) 传递头。 公用流程将构造前导头、 服务头和传递头使用参与方之间的贸易合作伙伴协议中存储的信息： 进程配置设置，有关源的配置信息和目标参与方和合作伙伴接口流程 (PIP) 变量。 然后，过程将信号消息发送到发起方。  
  
   > [!NOTE]
   >  如果消息是单操作消息，消息流已完成。  
  
4. 公用流程进入等待状态 （等待操作的响应方专用流程）。  
  
5. 以下操作可以结束等待状态 （等待操作的响应方专用流程）：  
  
   1. 响应方专用流程与原始操作消息 （在双操作消息） 的响应中返回的响应服务内容消息和标头。  
  
       如果公用流程从专用流程接收响应服务内容，则公用流程将构造包含服务内容的 RNIF 消息。 它会通过将服务内容消息部分包含有关源和目标参与方和参与方之间协议中存储的 PIP 变量的配置信息的标头。  
  
       公用流程将 RNIF 消息发送到发起方使用的操作/信号角色链接端口。  
  
       如果公用流程接收通知，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未成功发送消息，则公用流程将该状态发送回专用流程，然后结束。  
  
       如果公用流程接收通知的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]成功发送消息，流程进入等待状态 （等待操作由发起方）。 该等待状态是类似于发起方时它正在等待由响应方操作进入等待状态。  
  
   2. 公用流程从发起方接收失败通知消息 (NoF)。  
  
   > [!NOTE]
   >  它已成功处理传入消息后，响应方专用流程将通知响应方公用流程。 仅后响应方公用流程已收到此通知 (从`EndNotify`中的方法`ApplicationAdapter`类) 将成功完成响应方公用流程。  
  
6. 响应方公用流程进入等待状态 （等待发起方到响应方公用流程发送响应消息的响应中收到的信号）。  
  
## <a name="see-also"></a>请参阅  
 [公用流程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md)   
 [发起方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md)   
 [ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)   
 [ValidationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)