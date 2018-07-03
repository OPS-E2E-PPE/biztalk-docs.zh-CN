---
title: ACK 消息模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message modes, ACK messages
- messages, acknowledgements
- acknowledgements, message modes
- ACK message modes
ms.assetid: ab4a9470-dab2-46d4-8d0a-54dc12f2fa90
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181617a41ba892a8ac04f2bf2154bbe78e8c892e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967847"
---
# <a name="ack-message-modes"></a>ACK 消息模式
对于确认 (ACK) 消息，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 确定的确认模式和要用于填充你想要生成的确认 MSH15 和 MSH16 字段值。 这些值是在贸易合作伙伴管理 (TPM) 配置中存在。 下面是可能值为 ACK 模式：  
  
> [!NOTE]
>  在以下列表中，HL7 规范强制项 1 至 3，并且它们包含 MSH15 和 MSH16 值。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 定义项 4，以表示不应生成确认。  
  
1. 原始-一个 ACK 验证标头和正文后发送。 此模式都涉及到架构验证。  
  
2. 增强的两个发送的确认消息：  
  
   -   接受确认 – 接收系统标头的验证后会发送此类型的确认。 此确认向发出信号，起始应用程序的消息是提交到数据库。  
  
   -   应用程序确认接收系统完成消息验证，包括标头和正文后会发送此类型的确认。  
  
3. 延迟-发送两条确认消息。  
  
   - 原始模式： 接收系统后验证标头和正文会发送此类型的确认。 此模式都涉及到架构验证。  
  
   - 延迟模式下： 业务线应用程序在处理它之后确认消息。 应用程序提供对延迟的消息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，它将它作为独立的消息处理，并将其传送到目标。  
  
4. 静态-在成功或失败时发送的确认。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)   
 [静态确认](../../adapters-and-accelerators/accelerator-hl7/static-acknowledgments.md)