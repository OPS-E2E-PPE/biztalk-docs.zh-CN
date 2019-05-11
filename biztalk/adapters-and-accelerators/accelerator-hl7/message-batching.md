---
title: 消息批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- batching, about batching
- messages, batching
- batching, messages
ms.assetid: d852cf00-3882-4f0f-a4c3-2a39483710ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f487d479036f9946dbd32ff9444d8cd714a0a1f1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303827"
---
# <a name="message-batching"></a>消息批处理
协议标准、 计划问题或消息大小限制可能会促使对消息进行批处理的需求。 运行状况级别 7 (HL7) 批处理包含包围在 HL7 批处理标头和尾部批处理的消息。 消息分隔符分隔各条消息的批处理中。  
  
 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]批处理方案支持以下三个消息：  
  
-   **零碎的入站的批处理**。 在此方案中，BTAHL7 接收 HL7 消息批，，然后将各个消息路由到目标系统。  
  
-   **在批处理 / 出站批处理**。在此方案中，BTAHL7 接收 HL7 消息批、 验证在批处理中的单个消息并将消息批然后路由到目标系统。  
  
-   **创建批处理或出站批处理**。 在此方案中，BTAHL7 接收单个消息，并将它们路由到目标系统之前对其进行批量。  
  
    > [!NOTE]
    >  BTAHL7 不会启用默认情况下的出站批处理的消息批处理。 您必须使用 BizTalk 浏览器第一次登记 BTAHL7 批处理业务流程，并启动批处理业务流程。 有关启用消息批处理的详细信息，请参阅[配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [零碎的入站批处理](../../adapters-and-accelerators/accelerator-hl7/fragmented-inbound-batch.md)  
  
-   [配置批处理](../../adapters-and-accelerators/accelerator-hl7/configuring-batching.md)  
  
-   [计划批处理](../../adapters-and-accelerators/accelerator-hl7/scheduling-batching.md)  
  
-   [配置批处理确认](../../adapters-and-accelerators/accelerator-hl7/configuring-batching-acknowledgments.md)