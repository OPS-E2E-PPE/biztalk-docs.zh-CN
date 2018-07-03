---
title: 消息确认段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- segments, acknowledgements
- acknowledgements, segments
ms.assetid: 6f2b9f6f-a328-4a0f-9e7d-edba32cc045a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f771968e6d7c7f58ccd8d3e68b43aac0eb64e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968494"
---
# <a name="message-acknowledgment-segment"></a>消息确认段
确认 (ACK) 消息的消息确认 (MSA) 段标识确认正在确认哪种类型的系统发送，并指示哪些消息通知。 它包含两个所需的段： 确认代码和消息，控制 id。  

## <a name="acknowledgment-code-msa1"></a>确认代码： MSA1  
 下表列出了可用 MSA1 字段值，该值指示消息接收结果。  

|ReplTest1|含义|Description|  
|-----------|-------------|-----------------|  
|AA|应用程序确认|系统收到消息并处理它的任何问题。|  
|AE|应用程序错误|与消息或其结构相关的处理问题出现在接收应用程序。 发送系统应诊断并更正问题，然后再尝试重新发送消息。|  
|AR|应用程序拒绝|问题发生在接收位置与 MSH9 中的值 （消息类型）、 MSH11 （处理 ID） 或 MSH12 (版本 ID)、 发送系统应诊断并更正该问题后重新发送消息; 在这种情况下或在接收已对消息或其结构，在其中用例发送系统应重新发送该消息在适当的时间段，而无需更改到消息后不相关的系统出现问题。|  

## <a name="message-control-id-msa2"></a>消息控件 ID (MSA2)  
 MSA2 字段用于标识确认正在确认的消息。 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 中 MSA2 基于确认模式生成值。 此值允许发送和接收应用程序，以保证消息并且确认同步。 下表列出了 MSA2 字段的可用值。  


|            确认模式            |                                                           MSA2 中的值                                                            |
|-------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
|               原始模式               |                  转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息                   |
|   增强模式： 提交确认    |                  转置 MSH10 中的值的值 （消息控件 ID） 字段的原始消息                   |
| 增强模式： 应用程序确认 | 通过生成的 GUID[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]确认 |

## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [设置用于接收 Ack 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [错误条件确认](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)