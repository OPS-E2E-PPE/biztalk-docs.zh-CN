---
title: 验证消息 |Microsoft 文档
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
ms.openlocfilehash: 1edaffcab50d6a8af508cb16c9eede39c5ddb952
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206885"
---
# <a name="validating-messages"></a>验证消息
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持从应用程序的入站消息发送确认 (ACK) 或贸易合作伙伴可能需要转换为 HL7 HL7 XML 回执形式 ACK 消息编码。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]它签入相关入站 （贸易合作伙伴格式） 文档规范针对入站的消息后，通常会生成回执。 当所有段都通过验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回回执，该值指示对应用程序接受。 否则为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成，该值指示错误或失败/拒绝回执。  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] ACK 传输报告针对 HL7 标准的语法和示意性错误。 如果验证失败，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将挂起的消息队列中的文档并返回详细说明拒绝回执。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器执行包括检查数据类型、 语法和架构验证的验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在分析中的位置的详细信息以及回执记录出现的任何示意性错误。  
  
 在配置时，你需要创建[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用确认进行响应所需项目 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器将创建 HL7 规范 ACK XML 实例。 BizTalk 将此转换为适当的 BizTalk 映射中的所需的版本格式，并验证目标格式。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]序列化程序然后将消息转换为 HL7 编码实例。  
  
> [!NOTE]
>  如果的入站消息分隔符之间存在冲突，并且在指定的那些[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将生成一条确认消息，使用相同的分隔符的入站消息和替代的配置设置。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)   
 [ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)