---
title: "MLLP 接收和发送组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send components
- Minimal Lower Layer Protocol (MLLP)
- MLLP adapters
- MLLP adapters, wrappers
- wrappers [MLLP adapters]
- receive components
ms.assetid: 2f1c4099-8f52-437a-bdc1-efe707fbf347
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab82aa317b205d62b8bd05aff513e80d406b658b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-receive-and-send-components"></a>MLLP 接收和发送组件
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持所有[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]本机适配器类型，包括文件、 HTTP、 SQL 和 FTP。 对于 HL7 编码接收和发送的消息，但是，你通常使用 MLLP 适配器。 此适配器是使用最小的较低层协议 (MLLP) 的 TCP/IP 套接字适配器。 此协议提供的双向消息支持和端到端卫生保健的应用程序集成。  
  
 你可以配置 MLLP 为双向适配器或单向适配器接收适配器。 你可以配置 MLLP 发送适配器，如双向请求-响应发送适配器、 单向发送适配器配置为在同一套接字连接，收到确认 (Ack) 或单向发送不返回任何消息的适配器。 当你使用双向请求作出响应发送 MLLP 适配器，你可以配置要返回确认或响应消息的接收端口。 有关示例 MLLP 发送和接收适配器，请参阅[Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。  
  
 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收或发送 MLLP 适配器上的需要以下包装：  
  
-   \<SB > 启动块字符  
  
-   \<EB > 结束块字符  
  
-   \<CR > 回车符返回字节 （可选）  
  
 MLLP 适配器提供错误处理缺少\<SB > 或\<EB > 包装器、 删除的连接或超时。 使用 MLLP 适配器，你可以配置上的连接数的限制。 装有 MLLP 适配器，可以使用多种类型的确认。  
  
## <a name="see-also"></a>另请参阅  
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)