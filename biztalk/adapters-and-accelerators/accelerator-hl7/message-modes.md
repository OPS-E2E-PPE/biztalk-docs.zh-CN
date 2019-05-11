---
title: 消息模式 |Microsoft Docs
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
ms.openlocfilehash: a0480d4742076b0c99b29a6f34054cf713e09bf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303769"
---
# <a name="message-modes"></a>消息模式
有两个基础所有 HL7 消息的基本概念。 这些概念的地址不同的方式交换数据的独立系统可以进行交互，并提供支持的互操作性要求通过分布式卫生保健系统中的时间结构。 下面列出的概念定义 HL7 设计背后的基础主题：  
  
- **消息传送模式**。 交换信息的三个基本用途的识别： 广播请求信息 (interrogative) （声明性） 的信息，并请求系统执行操作 （命令性）。 每个这些用途有其特定的要求和消息流的模式。  
  
- **确认模式**。 需要支持紧密和松散耦合的消息传送的样式。 HL7 的确认模式启用发送应用程序需要从接收方，响应，或若要启用要保证消息传递的基础网络。  
  
- **本地化**。 需要支持特定的本地要求通过允许实体以引入消息规范的特定于站点的材料。  
  
- **演变**。 需要标准版本之间的互操作性，从而支持具有多个接口和许多应用程序的站点。 这使实体到阶段接口升级，而不是需要的所有接口的同时进行升级。  
  
  Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持更高版本要求：  
  
- HL7 确认模式。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持的原始确认模式通过将应用程序确认传递回原始消息发件人。  
  
- 不同的消息传递模式。 这使广播到多个目标，将联系在一起对关联的查询响应的查询。  
  
- 支持多个版本，包括 XML 和竖线分隔的编码。  
  
- 若要启用各种环境的 HL7 版本和升级之间的映射。  
  
- 业务流程内本地化 （自定义）。  
  
- 若要支持调试和计算结果的新接口的工具。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [消息类型和事件](../../adapters-and-accelerators/accelerator-hl7/message-types-and-events.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)