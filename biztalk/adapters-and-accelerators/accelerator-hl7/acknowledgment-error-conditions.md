---
title: "确认错误条件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- acknowledgements, errors
- errors, acknowledgements
ms.assetid: 605c7fa0-2365-4cb6-92fb-6df570905ca8
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15b481f4cdb60822841021f7f708a6caea021b8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgment-error-conditions"></a>确认错误条件
以下条件将导致严重的错误条件时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 是处理确认 (ACK) 消息：  
  
-   缺少必填的字段以 MSH9  
  
-   缺少必填的字段以 MSH12  
  
 以下条件会导致出现非致命错误条件。 在此情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 ACK，但也将挂起的确认：  
  
-   缺少必填的字段在 MSH11  
  
-   缺少 MSH10 值  
  
-   标头中的可选字段的枚举类型错误。  
  
> [!NOTE]
>  枚举类型错误时 MSH 15 设置为 AL 或 ER，在标头中找到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成的状态一起提交 ACK **MSA_1 = CR**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [ACK 消息架构类型](../../adapters-and-accelerators/accelerator-hl7/ack-message-schema-types.md)   
 [消息确认段](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)