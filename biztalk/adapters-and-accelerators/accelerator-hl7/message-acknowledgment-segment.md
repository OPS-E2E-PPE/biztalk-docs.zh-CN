---
title: "消息确认段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9547b6d8ddf3013facd94930b5d91ec42db0e5d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-acknowledgment-segment"></a>消息确认段
确认 (ACK) 消息的消息确认 (MSA) 段标识 ACK 正在确认哪种类型的系统发送，并指示哪些消息的确认。 它由两个所需的段组成： 一个确认代码和消息控制 id。  
  
## <a name="acknowledgment-code-msa1"></a>确认代码： MSA1  
 下表列出可用 MSA1 字段值，该值指示消息接收的结果。  
  
|值|含义|Description|  
|-----------|-------------|-----------------|  
|AA|应用程序确认|系统收到消息并处理它与任何问题。|  
|要从中|应用程序错误|处理问题相关的消息或其结构发生了接收应用程序。 发送系统应诊断并更正该问题后尝试重新发送消息。|  
|AR|应用程序拒绝|问题发生在与 MSH9 中的值相关的接收位置 （消息类型），MSH11 （处理 ID），或 MSH12 (版本 ID)，在这种情况下发送系统应诊断并更正该问题后重新发送消息;或接收已与消息或其结构，在其中情况下，发送系统应重新发送消息在适当的段，且不会更改消息后不相关的系统出现问题。|  
  
## <a name="message-control-id-msa2"></a>消息控件 ID (MSA2)  
 MSA2 字段标识 ACK 正在确认的消息。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 会在 MSA2 基于确认模式生成值。 此值使发送和接收应用程序在以保证消息并且该确认同步。 下表列出 MSA2 字段的可用值。  
  
|确认模式|MSA2 中的值|  
|-------------------------|-------------------|  
|原始模式|转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息|  
|增强的模式： 提交确认|转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息|  
|增强的模式： 应用程序确认|生成的 GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的确认|  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [确认错误条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)