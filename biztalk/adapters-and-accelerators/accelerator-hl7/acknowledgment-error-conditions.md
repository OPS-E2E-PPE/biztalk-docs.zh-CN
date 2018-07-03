---
title: 错误条件确认 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26bc0524e76521fcb673c6d5d3dc70f43cb12798
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970254"
---
# <a name="acknowledgment-error-conditions"></a>错误条件确认
以下条件将导致严重的错误条件时 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 是处理确认 (ACK) 消息：  
  
- 缺少必填的字段以 MSH9  
  
- 缺少必填的字段以 MSH12  
  
  以下条件会导致出现非致命错误条件。 在此情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成确认，但也将挂起的确认：  
  
- MSH11 中的所需的字段丢失  
  
- 缺少 MSH10 值  
  
- 标头中的可选字段的枚举类型错误。  
  
> [!NOTE]
>  当 MSH 15 设置为 AL 或 ER，标头中找到的枚举类型错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成的状态的提交确认**MSA_1 = CR**。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [设置用于接收 ACK 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)