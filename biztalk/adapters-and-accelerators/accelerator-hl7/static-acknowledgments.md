---
title: 静态确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- static acknowledgements
- acknowledgements, static acknowledgements
ms.assetid: 1cdd01fc-1dae-4851-917f-4f13a0f9595a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8081dc0f3c37c40cb1103567ae06f80037a12730
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206277"
---
# <a name="static-acknowledgments"></a>静态确认
BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持原始、 增强、 延迟，和静态确认 (ACK) 模式。 如果你选择静态 ACK 模式中的一方[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成包含仅相对值的指示成功或失败的静态确认。 是否接收系统接收和处理消息，在成功和失败值配置中，该值指示静态 ACK[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
 在原始，增强，和延迟模式，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成动态确认。 它们 HL7 编码，并且包含 MSA.1 确认代码字段和 ERR 段等字段。 动态 ACK MSA.1 字段将指示失败条件是拒绝还是出现错误，导致不同的处理 (请参阅[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。 ERR 段提供有关错误的详细的信息。 静态 Ack 提供任何此类信息。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]处理不同于动态确认静态 ACK 如果双向发送端口 （这就只会发送下一条消息后接收 ACK） 收到静态 ACK，并确认指示失败 （或不是有效的 ACK），[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将将转移到辅助传输或挂起消息。 它不会重试消息，就像如果它收到动态 ACK，取决于在故障条件。  
  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器处理静态 ACK，它将写入**IsStaticAck**为消息上下文的布尔属性。 序列化程序使用此值以确定它是否应处理为静态的确认消息  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)