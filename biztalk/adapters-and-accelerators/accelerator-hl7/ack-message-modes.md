---
title: "ACK 消息模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122f0851005c7d8abba6c1739ae86a1d65d89625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-modes"></a>ACK 消息模式
确认 (ACK) 消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 确定确认模式和要用于填充 MSH15 和 MSH16 你想要生成的确认字段值。 这些值是贸易合作伙伴管理 (TPM) 配置中存在。 还为 ACK 模式可能有以下值：  
  
> [!NOTE]
>  在以下列表中，该 HL7 规范强制包含项 1 至 3，并且它们包含 MSH15 和 MSH16 值。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]定义项目 4 以表示不应生成确认。  
  
1.  原始-在验证标头和正文之后发送一个 ACK。 此模式涉及架构验证。  
  
2.  增强-发送的两个 ACK 消息：  
  
    -   接受 ACK – 接收系统会将此类型的 ACK 发送的标头在验证之后。 此 ACK 向发出信号，启动应用程序消息已提交到数据库。  
  
    -   应用程序 ACK 接收系统会将此类型的 ACK 发送后完成的消息验证，包括标头和正文。  
  
3.  延迟的两个 ACK 消息发送。  
  
    -   原始模式： 接收的系统会将此类型的 ACK 发送的标头和正文在验证之后。 此模式涉及架构验证。  
  
    -   延迟模式： 业务线应用程序对其进行处理后确认消息。 应用程序提供对延迟的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，它将它作为独立消息处理，并将其传递给目标。  
  
4.  静态-在成功或失败发送的 ACK。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [静态确认](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)