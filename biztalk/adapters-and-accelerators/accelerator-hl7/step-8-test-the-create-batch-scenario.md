---
title: 步骤 8： 测试 Create-batch 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc7fac40-fd3e-413b-82cc-7ad08226094c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d880d1f9d586878a28803ef5060cfb770bf67a7d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007806"
---
# <a name="step-8-test-the-create-batch-scenario"></a>步骤 8： 测试 Create-batch 方案
在此步骤中，通过删除你想要到源 Tutorial_BTAHL7Pickup 文件夹进行批处理的消息的测试实例来测试创建 Batch 方案。 设置发送端口提取消息源文件夹中，并将其; 发送接收端口接收它;和接收管道对其进行处理，并将其放入目标 Tutorial_BTAHL7Drop 文件夹。  

### <a name="to-test-the-create-batch-scenario"></a>若要测试创建批处理方案  

1. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Batching Tutorial\Instances**文件夹。  

2. 选择**CreateBatchMessage1.txt**，并**CreateBatchMessage2.txt**，右键单击它们，，然后单击**复制**。  

3. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Pickup**文件夹。  

4. 右键单击文件夹，然后依次**粘贴**。  

### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>若要验证创建批次方案的结果  

1. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BatchACKDrop**文件夹。 后短时间，您应该看到确认批处理的处理的实例出现在文件夹中。 如果未显示，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器的错误消息。 该文件应具有名称\< *Guid*\>.txt。 此批处理应包含两个确认收到最初发送两条消息后生成。 此批处理应具有以下字段：  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchSource|Tutorial_BatchSource|2|@shouldalert|  

    在批处理中的确认应具有以下字段：  


   |    MSH.9    | MSA.2 | MSA.1 |       MSH.3        |        MSH.5         |
   |-------------|-------|-------|--------------------|----------------------|
   | ACK ^ A03 ^ ACK | Msg01 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |
   | ACK ^ A03 ^ ACK | Msg02 |  AA   | Tutorial_BatchDest | Tutorial_BatchSource |


2. 使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BatchMsgDrop**文件夹。 一小时后，您应该可以看到处理的实例消息批次出现在文件夹中。 如果未显示，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器的错误消息。 该文件应具有名称\< *Guid*\>.txt。 此批处理应包含最初发送两条消息。 此批处理应具有以下字段：  

   |FHS.5|BHS.5|BTS.1|FTS.1|  
   |-----------|-----------|-----------|-----------|  
   |Tutorial_BatchDest|Tutorial_BatchDest|2|@shouldalert|  

    批中的消息应具有以下字段：  

   |MSH.9|MSH.10|MSH.3|MSH.5|  
   |-----------|------------|-----------|-----------|  
   |ADT^A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
   |ADT^A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  

    批处理包装在两个集的标头和尾部特定于批：  

   -   文件标头和尾部 （FHS 和 FT），其中用于括起的文件，可以包含多个批次。 请注意文件接收应用程序 (**Tutorial_BatchDest**) 在 FHS5 字段和文件创建日期/时间 FHS7 中。 请注意，在 FTS2 文件批处理计数 （文件中的批数） (1)。  

   -   批处理标头和尾部 （BHS 和 BTS），用于将每个批次。 请注意在 BTS2 中接收应用程序和批处理创建日期/时间，如 FHS 和批处理消息计数 (2) 中所示的文件。  

## <a name="see-also"></a>请参阅  
 [第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 3 部分：Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)