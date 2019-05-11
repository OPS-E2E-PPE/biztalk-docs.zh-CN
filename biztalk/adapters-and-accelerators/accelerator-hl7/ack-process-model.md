---
title: ACK 进程模型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, process flow
- ACK process model
ms.assetid: 3c6a5eef-57ef-41f7-9782-e1cbc4dd78e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4775605dc9b8eb41e60e39bee5a763913ce04901
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247706"
---
# <a name="ack-process-model"></a>ACK 进程模型
以下一系列步骤描述了确认 (ACK) 进程模型：  
  
1. 当招生人员登录患者入院信息到病人入院系统 (ADT) 时，系统将生成的触发器事件。  
  
2. ADT 系统生成 HL7 编码患者注册消息 (ADT ^ A04) 并将其传递到 BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
3. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统将 MLLP 包装应用上 ADT ^ A04 消息并将它路由到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
   -   预配置的原始模式确认要求  
  
   -   MSH 15 和 16 具有 null 值  
  
4. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证消息，并且如果验证成功发生，它将生成的确认消息的状态**MSA01 = AA**。  
  
5. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎转换 ADT ^ A04 消息由与 MLLP 包装器将其括起来并将其路由到实验室的信息系统 (LIS)。  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 增强型模式确认会预先配置  
  
   - MSH 15 和 16 = AL  
  
6. LIS 接口层验证标头： 提交消息，并生成状态为接受 ACK **MSA1 = CA**。 接口层将与 MLLP 包装到消息路由[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
7. LIS 接口层验证整个消息并生成 ACK 应用程序状态**MSA1 = AA**。 接口层将与 MLLP 包装到消息路由[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
   - [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 确认所需确认该确认会预先配置  
  
   - MSH 15 = AL，指示接收系统必须确认并提交接受消息的确认  
  
8. LIS 接口层的消息传递到格式要求根据应用程序层。  
  
9. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证 LIS 接口层 （上述步骤 7 中） 从收到的确认，并返回到 LIS 接口层的状态的 ACK **MSA1 = CA**。  
  
10. LIS 系统的用户查看患者信息。  
  
## <a name="see-also"></a>请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)