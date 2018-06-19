---
title: ACK 进程模型 |Microsoft 文档
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
ms.openlocfilehash: 846ecf4d8eee4eca0e8a75a3444a1478b7db5910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205917"
---
# <a name="ack-process-model"></a>ACK 进程模型
下面的步骤序列描述的确认 (ACK) 进程模型：  
  
1.  当许可人员登录患者许可信息到许可系统 (ADT) 时，系统将生成的触发器事件。  
  
2.  ADT 系统生成 HL7 编码患者注册消息 (ADT ^ A04) 并将其传递给 BizTalk 快捷键的 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
3.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统上 ADT 适用的 MLLP 包装 ^ A04 消息并将它路由到[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
    -   预先配置的原始模式确认的要求  
  
    -   MSH 15 和 16 具有 null 值  
  
4.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎来验证消息，如果成功验证时，它将生成状态的 ACK 消息**MSA01 = AA**。  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎转换 ADT ^ A04 条消息所使用 MLLP 包装器将其括起来，并将其路由到实验室信息系统 (LIS)。  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]以增强型模式确认预先配置  
  
    -   MSH 15 和 16 = AL  
  
6.  LIS 接口层验证标头： 提交消息，并生成状态为接受 ACK **MSA1 = CA**。 接口层将路由到 MLLP 包装的消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
7.  LIS 接口层验证整个消息并生成 ACK 应用程序状态**MSA1 = AA**。 接口层将路由到 MLLP 包装的消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎。  
  
    -   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]以 ACK 所需确认该确认预先配置  
  
    -   MSH 15 = AL，指示接收的系统必须确认并提交接受消息的确认  
  
8.  LIS 接口层将邮件传递到应用程序层根据格式要求。  
  
9. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接口引擎验证从 LIS 界面层 （在步骤 7 上面） 接收到 ACK，并回状态 LIS 接口层的 ACK **MSA1 = CA**。  
  
10. LIS 系统的用户查看患者信息。  
  
## <a name="see-also"></a>另请参阅  
 [创建和处理确认](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [编程指南](../../adapters-and-accelerators/accelerator-hl7/programming-guide1.md)