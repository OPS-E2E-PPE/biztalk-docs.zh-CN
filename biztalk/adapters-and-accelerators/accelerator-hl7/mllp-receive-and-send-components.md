---
title: MLLP 接收和发送组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5db561b2c4f2bcd738fbb8932bba028df250c7e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65290441"
---
# <a name="mllp-receive-and-send-components"></a>MLLP 接收和发送组件
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持所有 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]本机适配器类型，包括文件、 HTTP、 SQL 和 FTP。 对于 HL7 编码接收和发送的消息，但是，您通常使用 MLLP 适配器。 此适配器是使用最少的较低层协议 (MLLP) 的 TCP/IP 套接字适配器。 此协议提供的双向消息支持和端到端卫生保健应用程序集成。  
  
 你可以配置 MLLP 接收适配器为双向适配器或单向适配器。 您可以配置 MLLP 发送适配器，如双向要求-响应发送适配器、 一个单向发送适配器配置为在同一套接字连接，接收确认 (Ack) 或一个单向发送适配器不返回任何消息。 当您使用双向要求响应发送 MLLP 适配器，您可以配置接收端口以返回是 Ack 或响应消息。 有关示例 MLLP 发送和接收适配器，请参阅[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。  
  
 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收或发送 MLLP 适配器上的需要以下包装器：  
  
- \<SB\>开始块字符  
  
- \<EB\>结束块字符  
  
- \<CR\>回车符返回字节 （可选）  
  
  MLLP 适配器提供的错误处理缺少\<SB\>或\<EB\>包装、 连接中断或超时。 使用 MLLP 适配器，您可以配置上的连接数限制。 使用 MLLP 适配器，可以使用具有多种类型的确认。  
  
## <a name="see-also"></a>请参阅  
 [处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)