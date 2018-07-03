---
title: 确认 |Microsoft Docs
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
ms.openlocfilehash: 46dedd4f2173fd4a3ad36c272963334b4ce66a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969782"
---
# <a name="acknowledgments"></a>鸣谢
使用 Microsoft BizTalk Accelerator for HL7 与参与方级别配置 HL7 确认 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 配置资源管理器。 确认将应用于参与方发送 HL7 消息通过接收位置 （可能是 MLLP 适配器） 和 HL7 2.X 接收管道。 一条消息完成分析和验证，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以创建包含验证过程的结果 （成功或错误） 的确认消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 可以通过两种方式之一返回确认消息。 如果原始发送方提交原始消息通过双向接收端口配置[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]返回通过该原始端口位置的确认消息。 如果原始的发送端口提交原始消息通过单向接收端口，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将确认消息提交到 MessageBox 数据库并将其使用订阅模型路由。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 用于接收消息处理基于 HL7 消息 (MSH 3.1) 的发送应用程序字段中的值自动执行参与方关联。  
  
## <a name="see-also"></a>请参阅  
 [消息流](../../adapters-and-accelerators/accelerator-hl7/message-flow.md)