---
title: "消息流中对响应方 BTARN |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ad33db4f67336f41ac868a7a14e1266a85dd45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-flow-in-the-responder-btarn"></a>响应方 BTARN 中的消息流
通过 Internet 从发起程序计算机中接收消息开头响应方计算机上的消息流。 它包括将该消息转换从 RosettaNet 实现框架 (RNIF)-符合到为后端的应用程序，然后将消息路由到业务线应用程序专有格式的消息的消息。  
  
 如果合作伙伴接口流程 (PIP) 是单操作的，则唯一的响应是确认信号消息。 如果 PIP，双操作响应方将处理和发送响应消息，和随后接收确认时该响应。  
  
 如果 PIP 是异步的，则通过 Internet 的每次消息传输将在不同的 HTTP 连接上进行； 如果 PIP 是同步的，则每次消息传输将在同一连接上进行，HTTP 适配器将一直保持该连接，直到相应流程完成为止。 在双操作同步方案中，响应方计算机不会向发起方计算机发送确认消息以响应初始请求消息， 而是以响应消息作为确认消息。  
  
## <a name="btarn-components-on-the-responder-computer"></a>响应方计算机上的 BTARN 组件  
 因为消息流经[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]响应方在计算机上，以下组件将处理该消息：  
  
-   RNIFReceive.aspx 页  
  
-   HTTP 适配器  
  
-   接收管道  
  
-   响应方公共过程  
  
-   响应方专用流程  
  
-   SQL 适配器  
  
-   发送管道  
  
 有关这些组件，以及它们如何处理消息的详细信息，请参阅[消息处理中 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。  
  
## <a name="message-flow-on-the-responder-computer"></a>响应方计算机上的消息流  
 已收到消息的消息流通过响应方 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 计算机的步骤如下：  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1.  RNIFReceive aspx 页从发起方接收传入的消息。  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息提交给 HTTP 适配器，HTTP 适配器再将其提交给接收管道。  
  
3.  接收管道将解码、 进行反汇编，并在消息中，执行方解析，并且然后将消息转换为后端业务线应用程序的专有格式。  
  
4.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由至 MessageBox 数据库。  
  
5.  公用流程处理消息的 RNIF 头。  
  
6.  专用流程处理消息的服务内容。 它会生成都会返回到公共进程、 MessageBox 数据库、 向发送管道，然后返回的 HTTP 适配器通过 Internet 发起程序的确认。  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由至 MessageBox 数据库。  
  
8.  发送管道将汇编; 而然后符号/加密/编码消息。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息路由到的 SQL 适配器。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息提交至[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，而在后端业务线应用程序。  
  
## <a name="see-also"></a>另请参阅  
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [发起方 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)