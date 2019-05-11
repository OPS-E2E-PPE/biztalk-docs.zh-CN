---
title: ACK 消息架构类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923cd9122f1b0d322f5a12d3be38f660a67d054e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247568"
---
# <a name="ack-message-schema-types"></a>ACK 消息架构类型
确认消息架构有两种形式：  

- **常规确认 (ACK)**。 如果应用程序未定义的特殊业务线应用程序级别的确认消息，或者如果发生了使该列不能应用程序处理的错误，可以使用常规确认 (ACK)。 此外可以使用它对于接受级别的确认。 下表列出了 ACK 消息结构。  


  | ACK ^ 各不相同 ^ ACK | 常规确认 | 一章 |
  |----------------|------------------------|---------|
  |      MSH       |     消息标头     |    2    |
  |      MSA       | 消息确认 |    2    |
  |    [ ERR ]     |         错误          |    2    |


- **延迟确认 (MCF)**。 此消息仅存在与 HL7 2.1 版的向后兼容性。 您将其用作创建泛型窗体，异步应用程序级别确认，MCF 消息的协议的一部分。 下表列出了 MCF 消息结构。  

  |MCF ^ 各不相同 ^ ACK|延迟的确认|一章|  
  |--------------------|----------------------------|-------------|  
  |MSH|消息标头|2|  
  |MSA|消息确认|2|  
  |[ ERR ]|错误|2|  

  确认的消息具有 MSH9 字段设置为**ACK ^\<**<em>触发器事件</em>**\>^ ACK**或**MCF ^\<** <em>触发器事件</em>**\>^ ACK**。 因此，MSH9 的第一个组件就足以确定确认架构。 文档名称的 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 管道使用始终包含 HL7 作为命名空间。 类型名称是 ACK 或 MCF 的 MSH9_1 字段的内容。 因此，如以上示例中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]管道查找与名称 HL7 的架构。ACK 或 HL7。MCF，具体取决于 MSH9_1 字段的值。 消息正文的架构是相同的 2.X 版本的所有消息。  

> [!NOTE]
>  在中的批处理 / 出 ACK 方案中，确认标头的内容的批处理，则按如下所示：  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 设置 MSH1，2、 8 和 15 到用户界面中配置。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将 MSH7 设置为系统时间。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将 MSH9 设置为确认。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 设置为 2.4 或 2.5 MSH12。  

## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [设置用于接收 Ack 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [错误条件确认](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)