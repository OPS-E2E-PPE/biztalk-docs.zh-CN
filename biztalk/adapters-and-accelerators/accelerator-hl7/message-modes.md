---
title: 消息模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, about message modes
- messages, message modes
- message modes, HL7 messages
ms.assetid: 2d832b67-6f0e-45e1-95ac-cb80b74a7831
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b09a610d000ae6beaef75b1ed0144d1597d517b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205053"
---
# <a name="message-modes"></a>消息模式
有两个生成所有 HL7 消息的基本概念。 这些概念地址不同的方式交换数据的独立系统可以在其中进行交互，并提供了一段时间内的分布式卫生保健系统支持的互操作性要求的结构。 下面列出的概念定义后面 HL7 设计在基础主题：  
  
-   **消息传送模式**。 识别信息交换的三个基本目的： 广播请求信息 (interrogative) （声明性） 的信息并请求系统执行操作 （命令性）。 其中每个目的都有其特定的要求和消息流的模式。  
  
-   **确认模式**。 需要支持紧密和松散耦合的消息传送的样式。 HL7 确认模式启用发送应用程序需要从接收方，响应，或若要启用保证消息传递基础网络。  
  
-   **本地化**。 公司需要以满足特定的本地要求通过允许实体以将特定于站点的材料引入到消息的规范。  
  
-   **演变**。 需要通过启用标准版本之间的互操作性支持许多接口与许多应用程序的站点。 这使阶段接口升级，而不是需要的所有接口的同时升级到的实体。  
  
 下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持上述要求：  
  
-   HL7 确认模式。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]支持通过将应用程序确认传递回原始消息发件人的原始确认模式。  
  
-   不同的消息传递模式。 这使广播到多个目标，并将联系在一起对关联的查询响应的查询。  
  
-   支持多个版本，包括 XML 和竖线分隔的编码。  
  
-   若要启用不同的环境的 HL7 版本和升级之间的映射。  
  
-   在业务流程的本地化 （自定义项）。  
  
-   若要支持调试和新的接口的计算的工具。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [消息类型和事件](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)