---
title: 消息类型和事件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message events
- HL7, message types
- message types
- messages, message types
ms.assetid: d53d51d0-216d-472b-97b7-8a96b8013510
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b9880da0ca5fea84c5a2b3d6e9f3a43ace41970
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205949"
---
# <a name="message-types-and-events"></a>消息类型和事件
HL7 标准具有已分组到一起作为实际事件的特定分组相关消息*消息类型*ADT。 这些消息涉及触发事件，如患者管理。 版本 2.4 的 HL7 标准定义 100 个以上的消息类型，其中每个 HL7 组织分配有唯一的三个字符消息类型代码。 随着 HL7 标准的版本已演变，HL7 组织已添加新的消息类型，以提供新功能。  
  
 所有消息类型都包含的消息事件，也称为*事件*。 你可以将为在特定消息类型中已分组的消息的唯一类型的事件。 例如，请访问管理员/通知 （消息事件 A01） 和放电/结束访问 （消息事件 A03） 是按患者管理消息类型 (ADT) 包含的唯一消息。 HL7 组织已为每个消息事件分配一个唯一的三个字符事件代码。  
  
 只有一个消息类型可以包含特定的消息事件。 消息类型可以包含多个消息事件。 但是，特定的消息事件的结构而异的 HL7 标准版本之间。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [触发事件和消息](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)