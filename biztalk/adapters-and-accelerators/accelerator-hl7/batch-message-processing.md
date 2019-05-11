---
title: 批处理消息处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f954de27e2e18adbb38a2eeed86557b4752aaa8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65248254"
---
# <a name="batch-message-processing"></a>批处理消息处理
Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理三种类型的 HL7 2.X 批处理方案：  
  
- 零碎的入站的批处理方案。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将这些批次分析为单独的输出消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 零碎的批处理中，将发送确认 (Ack) 为每个消息。  
  
- 在批处理 / 批处理方案。 这些是入站批处理的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不进行分段，但通过，并且将保持不变的批作为发送。 如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送确认的批处理，确认包括版本 id。  
  
- 创建批处理方案。 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]合并输出批处理到不同的输入的消息。  
  
  可以设置两种方式之一中的批的格式：  
  
- 使用文件标头和尾部 (FHS/FTS) 和批头部和尾部 (BHS/BTS)。  
  
- 与任何文件或批处理标头/尾部。  
  
## <a name="see-also"></a>请参阅  
 [消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [第 1 部分：零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 2 部分：在批处理 / 批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [第 3 部分：创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)