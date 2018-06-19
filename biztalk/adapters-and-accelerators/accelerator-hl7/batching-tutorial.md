---
title: 批处理教程 |Microsoft 文档
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
ms.openlocfilehash: 27e2aff66468c697c92adb4c452250b70dae2e59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204381"
---
# <a name="batching-tutorial"></a>批处理教程
本教程提供了分步过程使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]接收和发送批处理的消息。 批处理为单个复合消息涉及接收和/或发送的一组单个消息 （或确认）。  
  
 BTAHL7 支持下列三个消息批处理方案：  
  
-   **零碎的入站的批处理**。 在此方案中，BTAHL7 接收的 HL7 消息批次，并随后将各条消息路由到目标系统。  
  
-   **在批处理 / 批处理出**。BTAHL7 接收的 HL7 消息批次，验证各条消息内批处理，然后将消息批路由到目标系统。  
  
-   **创建批处理 （或出站批处理）**。 BTAHL7 接收单个消息，并将它们路由到目标系统之前对它们进行批处理。  
  
 本教程包括以下三种批处理方案的每个部分。 使用本教程中提供; 的顺序的三个部分第 1 部分包含必需的步骤，第 2 部分和第 3 部分。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [准备使用批处理教程](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-batching-tutorial.md)  
  
-   [第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)  
  
-   [第 2 部分： 中的批处理 / 批处理出方案](../../adapters-and-accelerators/accelerator-hl7/part-2-batch-in-batch-out-scenario.md)  
  
-   [第 3 部分： 创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)