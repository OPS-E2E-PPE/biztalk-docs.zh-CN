---
title: "ACK 配置设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, configuring
- configuring, acknowledgements
ms.assetid: 46e92560-7b1e-4d53-9de8-8ded4de90695
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93dea42fd084f22b4644f0acbb21860d69f75027
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="ack-configuration-settings"></a>ACK 配置设置
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]分析器会生成基于贸易合作伙伴管理 (TPM) 设置的确认。 确认 (ACK) 设置都依赖于合作伙伴信息。 不使用架构类型。 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]含有 AL、 SU 或 ER 的 MSH15 字段接收到 ACK 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可能会发送此信息基于分析的 ACK 标头和 TPM 配置的结果的 ACK。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]检索合作伙伴确认设置并返回以下五个值之一：  
  
> [!NOTE]
>  HL7 规范强制包含使用项 1 至 4，并且用于填充你生成 ACK 消息 MSH15 字段。 第 5 项是[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]-特定，表示无法生成确认  
  
1.  AL – 始终  
  
2.  NE – 永远不会  
  
3.  SU – 成功  
  
4.  ER – 错误  
  
5.  否-不生成 ACK  
  
## <a name="ack-configuration-inconsistency"></a>ACK 配置不一致问题  
 在之间 ACK 配置用户界面设置的消息实例 MSH15 和 MSH16 字段内的值不一致的情况下[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]需要两个 ACK 生成触发器之一时发送 ACK。 其他不一致，对于实例中的数据将覆盖配置用户界面中的设置。  
  
## <a name="see-also"></a>另请参阅  
 [配置消息确认](../../adapters-and-accelerators/accelerator-hl7/configuring-message-acknowledgments.md)   
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)