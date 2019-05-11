---
title: 消息响应方 BTARN 中的流 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Accelerator for RosettaNet, message flow
- BTARN, components
- messages, message flow
- responder BTARN
ms.assetid: 66de8694-a248-47e8-9483-9eedf2324b33
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1d797b4f2722f5a686a087c81a661df556de20e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283004"
---
# <a name="message-flow-in-the-responder-btarn"></a>响应方 BTARN 中的消息流
响应方计算机上的消息流开始，通过 Internet 从发起方计算机接收消息。 它涉及到将该消息转换从 RosettaNet 实现框架 (RNIF) 的消息中的后端应用程序，然后将消息路由到业务线应用程序的专有格式兼容的消息。  
  
 如果合作伙伴接口流程 (PIP) 是单操作，则唯一的响应是确认信号消息。 如果 PIP 是双操作，该响应程序将处理和发送响应消息，并随后接收确认时响应。  
  
 如果 PIP 是异步的通过 Internet 每次消息传输会在不同的 HTTP 连接上发生。 如果 PIP 是同步的每次消息传输会发生在同一连接上的 HTTP 适配器的进程之前保存已完成。 在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始请求消息的确认。 响应消息作为确认。  
  
## <a name="btarn-components-on-the-responder-computer"></a>响应方计算机上的 BTARN 组件  
 当消息流通过 Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]响应方计算机上的以下组件将处理该消息：  
  
- RNIFReceive.aspx 页  
  
- HTTP 适配器  
  
- 接收管道  
  
- 响应方公用流程  
  
- 响应方专用流程  
  
- SQL 适配器  
  
- 发送管道  
  
  有关这些组件，以及它们如何处理消息的详细信息，请参阅[BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。  
  
## <a name="message-flow-on-the-responder-computer"></a>响应方计算机上的消息流  
 通过响应方接收的消息的消息流[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]计算机是按如下所示：  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-responder-receive-message-flow.gif "RN3_Responder_Receive_Message_Flow")  
  
1. RNIFReceive aspx 页从发起方接收的传入消息。  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息提交到 HTTP 适配器，将其提交给接收管道。  
  
3. 接收管道进行解码、 拆装，并对消息执行参与方解析，然后会将消息转换成后端业务线应用程序的专有格式。  
  
4. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由到 MessageBox 数据库。  
  
5. 公用流程处理消息的 RNIF 头。  
  
6. 专用流程处理消息的服务内容。 它会生成，会返回到公用流程、 到 MessageBox 数据库、 到发送管道中，然后对返回的 HTTP 适配器通过 Internet 到发起方的确认。  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由到 MessageBox 数据库。  
  
8. 发送管道的组装，然后签名/加密 / 对消息进行编码。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由到 SQL 适配器。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息提交到[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，和后端上的业务线应用程序。  
  
## <a name="see-also"></a>请参阅  
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [发起程序 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-initiator-btarn.md)