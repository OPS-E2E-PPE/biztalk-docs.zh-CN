---
title: 步骤 3：测试批处理中的批处理方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c487d39d-b2be-41d4-963e-d0ee9ba169fb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c619c6f6ba1ee874c6b6eb54b9e499957d1dcee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65288189"
---
# <a name="step-3-test-the-batch-inbatch-out-scenario"></a>步骤 3：测试在入站批处理/出站批处理方案
在此步骤中，您将测试批处理中 / 批处理出教程通过删除测试实例中的批处理 / 出消息批处理到的文件夹。 设置发送端口将消息发送、 接收端口将接收它，并接收管道将对其进行处理并将其放到目标文件夹。  
  
### <a name="to-test-the-batch-inbatch-out-scenario"></a>若要测试批处理中 / 出站批处理方案  
  
1. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Batching Tutorial\Instances**文件夹。  
  
2. 右键单击**BatchInBatchOut.txt**，然后单击**副本**。  
  
3. 浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for HL7\SDK\End 端到端 Tutorial\Tutorial_BTAHL7PickUp**文件夹。  
  
4. 右键单击文件夹，然后依次**粘贴**。  
  
### <a name="to-verify-the-results-of-the-batch-inbatch-out-tutorial"></a>若要验证的批处理结果中 / 出站教程批处理  
  
- 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Drop**文件夹。 一段时间后应会看到已处理的批处理消息，并确认实例，出现在文件夹中。 如果未显示，检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]一条错误消息的事件查看器。 每个文件应包含不同的名称，形式\< *Guid*\>.txt。  
  
   第一条消息应为包含两条消息的批处理。 BizTalk Accelerator for HL7 (BTAHL7) 具有包含这两条消息按顺序在.txt 文件中。 此批处理不包含 FHS/FTS 和 BHS/BTS 标记。 批处理必须包含任一所有 FHS/FTS 和 BHS/BTS 标记，或此批处理消息、 没有 FHS/FTS 和没有 BHS/BTS 标记等。  
  
  |MSH.9|MSH.10|MSH.3|MSH.5|  
  |-----------|------------|-----------|-----------|  
  |ADT^A03|000001|Tutorial_BatchSource|MESA_IS|  
  |ADT^A03|000002|Tutorial_BatchSource|MESA_IS|  
  
   第二条消息应发送到批消息，包含以下字段的响应中的单个应用程序确认：  
  
  |MSH.9|MSH.3|MSH.5|MSA.1|MSA.2|  
  |-----------|-----------|-----------|-----------|-----------|  
  |ACK^A03^ACK|MESA_IS|Tutorial_BatchSource|AA|000001|  
  
## <a name="see-also"></a>请参阅  
 [第 1 部分：零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 3 部分：Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)