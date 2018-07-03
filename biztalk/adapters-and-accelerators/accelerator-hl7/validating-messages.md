---
title: 验证消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, acknowledgements
- messages, acknowledgements
- acknowledgements, validating
- validating, messages
- acknowledgements, messages
- messages, validating
ms.assetid: 7dba0f40-5e19-4598-82cb-22c71e9536c6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35894722d2c95f197a1fe4072c2229cf96fea64f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010054"
---
# <a name="validating-messages"></a>验证消息
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持从应用程序的入站消息发送确认 (ACK) 或贸易合作伙伴可能需要转换为 HL7 HL7 XML 回执的窗体中编码的确认消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 通常将生成回执后它会检查根据相关入站 （贸易合作伙伴格式） 文档规范对入站的消息。 当所有段都通过验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回回执，表明对应用程序接受。 否则为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成回执，该值指示错误或失败/拒绝。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认传输报告针对 HL7 标准语法和示意性错误。 如果验证失败，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将文档放在挂起的消息队列，并返回详细说明，拒绝的回执。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器执行涉及到检查数据类型、 语法和架构验证的验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 在分析中的位置详细信息以及回执记录出现的任何示意性错误。  
  
 在配置时，您需要创建[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用确认进行响应所需项目 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器创建 HL7 规范确认 XML 实例。 BizTalk 将此转换为相应的 BizTalk 映射中的所需的版本格式，并验证目标格式。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序然后将该消息转换为 HL7 编码实例。  
  
> [!NOTE]
>  如果入站消息的分隔符之间没有冲突并且中指定的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成确认消息，它使用相同的入站消息的分隔符并替代的配置设置。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)