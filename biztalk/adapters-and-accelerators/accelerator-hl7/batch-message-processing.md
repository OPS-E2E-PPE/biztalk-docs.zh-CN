---
title: "批处理消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, batching
- batching, examples
- batching, batch types
ms.assetid: 264f91b5-3e33-4b87-9da3-866eaa464b0f
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad80bb8fe9a59163ee17e7862bece728fdc52b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batch-message-processing"></a>批处理消息处理
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理三种类型的 HL7 2.X 批处理方案：  
  
-   零碎的入站的批处理方案。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将这些批分析为单独的输出消息。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]零碎的批次中发送确认 (Ack) 中的为每条消息。  
  
-   在批处理 / 批处理出方案。 这些是入站批处理，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]并非片段，但传递并以保持不变的批处理形式发送。 如果[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送的批处理，ACK 的 ACK 包括版本 id。  
  
-   创建批处理方案。 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]合并到输出批处理多个单独输入的消息。  
  
 可以设置两种方式之一中的批的格式：  
  
-   使用文件标头和尾部 (FHS/FT) 和批处理标头和尾部 (BHS/BTS)。  
  
-   与任何文件或批处理标头/拖车安排。  
  
## <a name="see-also"></a>另请参阅  
 [消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)   
 [批处理教程](../../adapters-and-accelerators/accelerator-hl7/batching-tutorial.md)   
 [第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 2 部分： 中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)   
 [第 3 部分： 创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)