---
title: ACK 配置设置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06cedaee1ca0ad574920cfb646f69d63157c8e67
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968054"
---
# <a name="ack-configuration-settings"></a>ACK 配置设置
Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]分析器生成确认基于贸易合作伙伴管理 (TPM) 设置。 确认 (ACK) 设置都依赖于合作伙伴信息。 不使用架构类型。 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]与 MSH15 字段含有 AL、 SU 或 ER，接收到 ACK 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可能会发送此信息基于分析的 ACK 标头和 TPM 配置的结果的 ACK。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 检索合作伙伴确认设置并返回以下五个值之一：  
  
> [!NOTE]
>  HL7 规范也要求使用项 1 至 4，并且用于填充您生成的 ACK 消息 MSH15 字段。 第 5 项是[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]的特定表示不能生成确认。  
  
1.  AL – 始终  
  
2.  NE – 永远不会  
  
3.  SU-成功  
  
4.  ER-错误  
  
5.  否-不会生成确认  
  
## <a name="ack-configuration-inconsistency"></a>ACK 配置不一致问题  
 在确认配置用户界面设置和消息实例 MSH15 和 MSH16 字段内的值之间的不一致的情况下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时的两个 ACK 生成触发器之一需要发送确认。 对于其他不一致，实例中的数据将覆盖在配置用户界面中的设置。  
  
## <a name="see-also"></a>请参阅  
 [配置消息确认](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)