---
title: 消息流中发起程序 BTARN |Microsoft 文档
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
ms.openlocfilehash: 85fed6404627fd8abfa9d50e7d56d98ff7306f09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210589"
---
# <a name="message-flow-in-the-initiator-btarn"></a>发起方 BTARN 中的消息流
发起方计算机的消息流开始于以其专用格式接收来自后端业务线应用程序的消息。 该消息流包括将收到的消息转换为与 RosettaNet 实现框架 (RNIF) 兼容的消息，然后通过 Internet 将经过转换的消息发送到响应方计算机。  
  
 如果合作伙伴接口流程 (PIP) 是单操作的，则唯一的响应是确认信号消息。 有关单操作消息流的信息，请参阅本主题后面的“初始消息的消息流”。 如果 PIP 是双操作的，则除了单操作消息流以外，发起方还将收到响应消息以及确认答复。  
  
 如果 PIP 是异步的，则通过 Internet 的每次消息传输将在不同的 HTTP 连接上进行； 如果 PIP 是同步的，则每次消息传输将在同一连接上进行，HTTP 适配器将一直保持该连接，直到相应流程完成为止。 在双操作同步方案中，响应方计算机不会向发起方计算机发送确认消息以响应初始请求消息， 而是以响应消息作为确认消息。  
  
## <a name="btarn-components-on-the-initiator-computer"></a>发起方计算机上的 BTARN 组件  
 当消息流通过发起方计算机上的 [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 时，下列组件将对消息进行处理：  
  
-   SQL 适配器  
  
-   XML 接收管道  
  
-   发起方专用流程  
  
-   发起方公用流程  
  
-   XML 发送管道  
  
-   HTTP 适配器  
  
-   RNIFSend.aspx 页  
  
 有关这些组件，以及它们如何处理消息的详细信息，请参阅[消息处理中 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)。  
  
## <a name="flow-of-an-initiated-message"></a>初始消息的消息流  
 下列步骤说明通过发起方 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 计算机的初始消息的消息流。 下图显示了这一过程：  
  
 ![](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-initiator-send-message-flow.gif "RN3_Initiator_Send_Message_Flow")  
  
1.  业务线应用程序发送到消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。  
  
2.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将该消息从 [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库发送到 SQL 适配器。  
  
3.  XML 接收管道对该消息执行简单 XML 验证。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 将消息路由至 MessageBox 数据库。  
  
5.  专用流程处理消息的服务内容。  
  
6.  公用流程处理消息的 RNIF 头。  
  
7.  [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将该消息路由回 MessageBox 数据库。  
  
8.  接收管道对消息进行组装并签名/加密/编码。  
  
9. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将该消息路由到 HTTP 适配器。  
  
10. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将消息路由至 RNIFSend.aspx 页，该页将其通过 Internet 发送到其目标。  
  
## <a name="see-also"></a>另请参阅  
 [BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-btarn.md)   
 [响应方 BTARN 中的消息流](../../adapters-and-accelerators/accelerator-rosettanet/message-flow-in-the-responder-btarn.md)   
 [消息处理在 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)