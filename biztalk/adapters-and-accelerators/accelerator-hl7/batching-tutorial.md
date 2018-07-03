---
title: 批处理教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching tutorial
- tutorials, batching tutorial
- batching tutorial, about the tutorial
- batching, tutorial
ms.assetid: e9010638-74cf-47cd-8cc9-9d6fd08a1b8d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 790303ac2026cbbce2fdb1c436e3dc8c7e9ff7f7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980078"
---
# <a name="batching-tutorial"></a>批处理教程
本教程提供了分步过程使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]来接收和发送批处理的消息。 批处理为单个复合消息包括接收和/或发送的一组各个消息 （或确认）。  
  
 BTAHL7 支持以下三种消息批处理方案：  
  
- **零碎的入站的批处理**。 在此方案中，BTAHL7 接收 HL7 消息批，，然后将各个消息路由到目标系统。  
  
- **在批处理 / 出站批处理**。BTAHL7 接收 HL7 消息批、 验证在批处理中的单个消息并将消息批然后路由到目标系统。  
  
- **创建批次 （或出站批处理）**。 BTAHL7 接收单个消息，并将它们路由到目标系统之前对其进行批量。  
  
  本教程包括三个批处理方案的每个部分。 使用本教程中提供; 的顺序的三个部分第 1 部分包含有关第 2 部分和第 3 部分的先决条件步骤。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为使用批处理教程做准备](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [第 1 部分：零碎的入站批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [第 2 部分：入站批处理/出站批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [第 3 部分：Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)