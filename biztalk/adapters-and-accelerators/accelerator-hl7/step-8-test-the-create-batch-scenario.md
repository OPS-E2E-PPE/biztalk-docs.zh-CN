---
title: 步骤 8： 测试创建批处理方案 |Microsoft 文档
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
ms.openlocfilehash: 865717858e27509a9f9e4af611b39ba10be212a5
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25961131"
---
# <a name="step-8-test-the-create-batch-scenario"></a>步骤 8： 测试创建批处理方案
在此步骤中，你都将删除你想要到源 Tutorial_BTAHL7Pickup 文件夹批处理的消息的测试实例测试创建批次方案。 你将设置为发送端口选取来自源文件夹的消息，并将其; 发送接收端口接收它;和接收管道处理它，并将它放置到目标 Tutorial_BTAHL7Drop 文件夹。  
  
### <a name="to-test-the-create-batch-scenario"></a>若要测试的创建批次方案  
  
1.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: \Batching Tutorial\Instances**文件夹。  
  
2.  选择**CreateBatchMessage1.txt**，和**CreateBatchMessage2.txt**，右键单击它们，，然后单击**复制**。  
  
3.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BTAHL7Pickup**文件夹。  
  
4.  右键单击文件夹，并依次**粘贴**。  
  
### <a name="to-verify-the-results-of-the-create-batch-scenario"></a>若要验证创建批次方案的结果  
  
1.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BatchACKDrop**文件夹。 一段时间后，你应看到在文件夹中显示确认批处理处理的的实例。 如果没有出现，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器的错误消息。 该文件应具有名称\< *Guid*\>.txt。 此批处理应包含在接收两个最初发送的消息时生成的两个确认。 此批处理应具有以下字段：  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchSource|Tutorial_BatchSource|2|1|  
  
     在批处理中的确认应具有以下字段：  
  
    |MSH.9|MSA.2|MSA.1|MSH.3|MSH.5|  
    |-----------|-----------|-----------|-----------|-----------|  
    |ACK^A03^ACK|Msg01|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
    |ACK^A03^ACK|Msg02|AA|Tutorial_BatchDest|Tutorial_BatchSource|  
  
2.  使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]资源管理器，浏览到 **\<*驱动器*\>: files\microsoft BizTalk\<版本\>HL7\SDK\End 端到端的快捷键Tutorial\Tutorial_BatchMsgDrop**文件夹。 后一小时，您应该看到消息批处理的实例出现在文件夹中。 如果没有出现，请检查[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器的错误消息。 该文件应具有名称\< *Guid*\>.txt。 此批处理应包含两条最初发送的消息。 此批处理应具有以下字段：  
  
    |FHS.5|BHS.5|BTS.1|FTS.1|  
    |-----------|-----------|-----------|-----------|  
    |Tutorial_BatchDest|Tutorial_BatchDest|2|1|  
  
     在批处理中的消息应具有以下字段：  
  
    |MSH.9|MSH.10|MSH.3|MSH.5|  
    |-----------|------------|-----------|-----------|  
    |ADT^A03|Msg01|Tutorial_BatchSource|Tutorial_BatchDest|  
    |ADT^A03|Msg02|Tutorial_BatchSource|Tutorial_BatchDest|  
  
     批处理包装在两个集的标头和尾部特定于批：  
  
    -   文件头和尾 （FHS 和 FT），这用于括起可以包括多个批处理文件。 请注意文件接收应用程序 (**Tutorial_BatchDest**) FHS5 字段和文件创建中日期/时间 FHS7 中。 请注意文件批数 （在文件中的批数），在 FTS2 (1)。  
  
    -   一个批处理标头和尾部 （BHS 和 BTS），用于将每个批括起来。 请注意在 BTS2 中接收应用程序和批处理创建日期/时间，如下所示 FHS 和批处理消息计数 (2) 的文件。  
  
## <a name="see-also"></a>另请参阅  
 [第 1 部分： 零碎的入站的批处理方案](../../adapters-and-accelerators/accelerator-hl7/part-1-fragmented-inbound-batch-scenario.md)   
 [第 3 部分：Create-Batch 方案](../../adapters-and-accelerators/accelerator-hl7/part-3-create-batch-scenario.md)