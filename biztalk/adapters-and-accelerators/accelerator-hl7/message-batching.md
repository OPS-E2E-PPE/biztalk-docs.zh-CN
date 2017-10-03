---
title: "消息批处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 849f14113d5a5e4776c303ef7a5ea4e1e50a552b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-batching"></a>消息批处理
协议标准、 计划问题或消息大小限制可能会促使对消息进行批处理的需求。 运行状况级别七 (HL7) 批处理包含包围在 HL7 批处理标头和批处理尾的消息。 消息分隔符分隔批处理中的单个消息。  
  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]支持下列三个消息批处理方案：  
  
-   **零碎的入站的批处理**。 在此方案中，BTAHL7 接收的 HL7 消息批次，并随后将各条消息路由到目标系统。  
  
-   **在批处理 / 批处理出**。在此方案中，BTAHL7 接收 HL7 消息批、 验证批处理中的单个消息和将消息批然后路由到目标系统。  
  
-   **创建批处理或出站批处理**。 在此方案中，BTAHL7 接收单个消息，并将它们路由到目标系统之前对它们进行批处理。  
  
    > [!NOTE]
    >  BTAHL7 不会启用默认情况下的出站批处理消息批处理。 你必须使用 BizTalk 资源管理器首先登记 BTAHL7 批处理业务流程，，然后启动批处理业务流程。 有关启用消息批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [零碎的入站的批处理](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [计划批处理](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [配置批处理确认](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)