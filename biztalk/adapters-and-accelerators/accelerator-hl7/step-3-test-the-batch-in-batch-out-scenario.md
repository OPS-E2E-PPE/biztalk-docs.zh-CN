---
title: "步骤 3： 测试批处理中的批处理方案出 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eec20b86b3e921fba8d1636a0aab7803ec1615d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>步骤 3： 测试中的批处理/批处理出方案
在此步骤中，测试批处理中 / 批处理出教程通过删除批处理中的测试实例 / 批处理到文件夹出消息。 你将设置为发送端口将发送消息、 接收端口将接收它，和接收管道将对其进行处理，并将其放到目标文件夹。  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>若要测试批处理中 / 批处理出方案  
  
1.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到  **\<*驱动器*>: \Batching Tutorial\Instances** 文件夹。  
  
2.  右键单击**BatchInBatchOut.txt**，然后单击**复制**。  
  
3.  浏览到  **\<*驱动器*>: files\microsoft BizTalk\<版本 > Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp * * 文件夹。  
  
4.  右键单击文件夹，并依次**粘贴**。  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>若要验证的批处理的结果中 / 批处理出教程  
  
-   使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到  **\<*驱动器*>: files\microsoft BizTalk\<版本 > HL7\SDK\End 端到端 Tutorial\ 快捷键Tutorial_BTAHL7Drop * * 文件夹。 一段时间后你应看到的批处理消息，并确认已处理的实例，请在文件夹中显示。 如果它们不会出现，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]一条错误消息的事件查看器。 每个文件应具有不同名称的形式\< *Guid*>.txt。  
  
     第一条消息应包含两条消息批处理。 BizTalk Accelerator for HL7 (BTAHL7) 已包含这两条消息按顺序在.txt 文件。 此批处理不包含 FHS/FT 和 BHS/BTS 标记。 批处理必须包含任一所有 FHS/FT 和 BHS/BTS 标记，或如此批处理消息、 没有 FHS/FT 和无 BHS/BTS 标记。  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT ^ A03|000001|Tutorial_BatchSource|MESA_IS|  
    |ADT ^ A03|000002|Tutorial_BatchSource|MESA_IS|  
  
     第二个消息都应在批处理消息，使用以下字段的响应中发送的单个应用程序确认：  
  
    |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK ^ A03 ^ ACK|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>另请参阅  
 [第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 3 部分： 创建批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)