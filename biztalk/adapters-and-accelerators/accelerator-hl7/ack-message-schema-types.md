---
title: "ACK 消息架构类型 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29657226c993a68b8cd557a39a7837717e2c66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-schema-types"></a>ACK 消息架构类型
确认消息架构有两种形式：  
  
-   **常规确认 (ACK)**。 如果应用程序未定义的特殊业务线应用程序级别的确认消息，或者如果发生了预先排除在应用程序处理的错误，你可以使用常规确认 (ACK)。 你还可以使用它对于接受级别的确认。 下表列出的 ACK 消息结构。  
  
    |ACK ^ 而异 ^ ACK|常规确认|章节|  
    |--------------------|----------------------------|-------------|  
    |MSH|消息标头|2|  
    |MSA|消息确认|2|  
    |[错误]|错误|2|  
  
-   **延迟确认 (MCF)**。 此消息仅存在于 HL7 版本 2.1 的向后兼容性。 你将其用作创建的一般形式的异步应用程序级别确认，MCF 消息的协议的一部分。 下表列出 MCF 消息结构。  
  
    |MCF ^ 而异 ^ ACK|延迟的确认|章节|  
    |--------------------|----------------------------|-------------|  
    |MSH|消息标头|2|  
    |MSA|消息确认|2|  
    |[错误]|错误|2|  
  
 确认的消息具有 MSH9 字段设置为**ACK ^\<***触发器事件***> ^ ACK**或**MCF ^\<** *触发器事件***> ^ ACK**。 因此，MSH9 的第一个组件是不足以确定 ACK 架构。 文档名称[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 管道使用始终包含 HL7 作为命名空间。 类型名称是 MSH9_1 字段，它是 ACK 或 MCF 的内容。 因此，如上例中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]管道查找具有名称 HL7 的架构。ACK 或 HL7。MCF，具体取决于 MSH9_1 字段的值。 消息正文的架构是相同的 2.X 版本的所有消息。  
  
> [!NOTE]
>  在批处理中 / 批处理出 ACK 方案中，确认标头的内容，如下所示：  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]设置 MSH1，2、 8 和 15 至你的用户界面中配置的内容。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 MSH7 设置为系统时间。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认 MSH9 集  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将 MSH12 设置为 2.4 或 2.5。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [确认错误条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)