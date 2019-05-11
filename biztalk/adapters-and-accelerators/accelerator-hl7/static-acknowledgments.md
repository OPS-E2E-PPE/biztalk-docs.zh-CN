---
title: 静态确认 |Microsoft Docs
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
ms.openlocfilehash: 4c9c310dde71d50dcf49fe4d54e2e5679f899de6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291598"
---
# <a name="static-acknowledgments"></a>静态确认
BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持原始、 增强、 延迟和静态确认 (ACK) 模式。 如果您选择静态 ACK 模式中的参与方[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成包含仅相对值的指示成功或失败的静态确认。 静态确认指示是否接收系统接收和处理消息，在成功和失败的值中配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
 在原始，增强，和延迟模式，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成动态 Ack。 进行 HL7 编码，且包含字段，如 MSA.1 确认代码字段和 ERR 段。 动态 ACK MSA.1 字段将指示失败条件是拒绝还是错误，这会导致不同的处理 (请参阅[消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md))。 ERR 段提供了有关错误的详细的信息。 静态确认提供没有此类信息。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理了静态确认以不同的方式从动态确认。 如果一个双向发送端口 （这将收到确认后才发送下一条消息） 接收静态确认，并确认指示失败 （或不是有效的确认），[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将移动到的辅助传输或挂起消息。 它不会重试消息，就像它收到了动态的确认，根据失败条件。  
  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器处理静态 ACK，则它写入**IsStaticAck**到消息上下文的布尔属性。 序列化程序使用此值以确定它是否应处理消息作为静态的确认。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)