---
title: 确认 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, acknowledgements
- parties, acknowledgements
- acknowledgements, about acknowledgements
- acknowledgements, messages
- acknowledgements, parties
ms.assetid: d25352a4-bae9-4de9-a504-2339bea25c4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c519ec4649ee1fbcfbc51edb7e3e8fe6ba6b5871
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204341"
---
# <a name="acknowledgments"></a>鸣谢
在方级别使用配置 HL7 确认[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 配置资源管理器。 确认将应用于通过接收位置 （可能是 MLLP 适配器） 和 HL7 HL7 消息发送方 2.X 接收管道。 当一条消息完成分析和验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以创建一条确认消息，其中包含验证过程的结果 （成功或错误）。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以在两种方式之一返回确认消息。 如果原始发送方提交通过双向原始消息接收端口配置，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回通过该原始端口位置的确认消息。 如果原始发送端口提交原始消息通过单向接收端口，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将确认消息提交到 MessageBox 数据库并将其使用订阅模型路由。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 用于接收消息处理根据 HL7 消息 (MSH 3.1) 发送应用程序域内的值自动执行当事方关联。  
  
## <a name="see-also"></a>另请参阅  
 [消息流](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)