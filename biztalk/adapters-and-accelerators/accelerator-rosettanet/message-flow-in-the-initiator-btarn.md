---
title: 消息发起方 BTARN 中的流 |Microsoft Docs
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
- initiator BTARN
ms.assetid: 315f3d4c-5e40-4b8e-b135-9da98dc2db1e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02a1e9832a633c1b638b7a6b527e607654e75870
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283031"
---
# <a name="message-flow-in-the-initiator-btarn"></a>发起方 BTARN 中的消息流
发起方计算机上的消息流开始，从后端业务线应用程序，以其专用格式接收一条消息。 它涉及到将该消息转换为 RosettaNet 实现框架 (RNIF) 的兼容的消息，并向响应方计算机通过 Internet 发送消息。  
  
 如果合作伙伴接口流程 (PIP) 是单操作，则唯一的响应是确认信号消息。 有关单操作消息流的信息，请参阅本主题后面的"流的"初始消息。 如果 PIP 是双操作，发起方将收到响应消息，并确认，除了单操作消息流答复。  
  
 如果 PIP 是异步的通过 Internet 每次消息传输会在不同的 HTTP 连接上发生。 如果 PIP 是同步的每次消息传输会发生在同一连接上的 HTTP 适配器的进程之前保存已完成。 在双操作同步方案中，响应方计算机不会发送到发起方计算机以响应初始请求消息的确认。 响应消息作为确认。  
  
## <a name="btarn-components-on-the-initiator-computer"></a>发起方计算机上的 BTARN 组件  
 当消息流通过[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]在发起方计算机上的以下组件将处理该消息：  
  
- SQL 适配器  
  
- XML 接收管道  
  
- 发起方专用流程  
  
- 发起方公用流程  
  
- XML 发送管道  
  
- HTTP 适配器  
  
- RNIFSend.aspx 页  
  
  有关这些组件，以及它们如何处理消息的详细信息，请参阅[BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。  
  
## <a name="flow-of-an-initiated-message"></a>启动消息流  
 以下步骤说明通过发起方的初始消息的消息流[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]计算机。 下图显示了此过程。  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1. 业务线应用程序将消息发送给 Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
2. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息从发送[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库添加到 SQL 适配器。  
  
3. XML 接收管道执行简单 XML 验证，消息。  
  
4. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 将消息路由到 MessageBox 数据库。  
  
5. 专用流程处理消息的服务内容。  
  
6. 公用流程处理消息的 RNIF 头。  
  
7. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由回 MessageBox 数据库。  
  
8. 发送管道执行的程序集和签名/加密/编码的消息。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由到 HTTP 适配器。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将消息路由到 RNIFSend.aspx 页，将其通过 Internet 发送到其目标。  
  
## <a name="see-also"></a>请参阅  
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [响应方 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md)   
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)