---
title: 消息类型和事件 |Microsoft Docs
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
ms.openlocfilehash: 143223d0ed0f03d6eaa66141ea052ed701638e56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303651"
---
# <a name="message-types-and-events"></a>消息类型和事件
HL7 标准已分组到一起作为实际事件的特定分组相关的消息*消息类型*ADT。 这些消息涉及到触发器事件，如患者的管理。 版本 2.4 的 HL7 标准定义了超过 100 个消息类型，其中每个 HL7 组织分配有唯一的三个字符消息类型代码。 HL7 标准的版本不断演进，如 HL7 组织已添加新的消息类型来提供新的功能。  
  
 所有消息类型都包含的消息事件，也称为*事件*。 您可以看作是将事件消息中的特定消息类型分组的唯一类型。 例如，管理员/访问通知 （消息事件 A01） 和放电装置/结束访问 （消息事件 A03） 是唯一患者管理消息类型 (ADT) 包含的消息。 HL7 组织分配的每个消息事件的三个字符的唯一事件代码。  
  
 只有一个消息类型可以包含特定的消息事件。 消息类型可以包含多个消息事件。 但是，特定的消息事件的结构而异的 HL7 标准版本之间。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [触发器事件和消息](../../adapters-and-accelerators/accelerator-hl7/trigger-events-and-messages.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)