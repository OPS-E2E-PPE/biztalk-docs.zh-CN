---
title: "步骤 4d: FileAct 实时方案的测试的有效实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 906a7eb08dc7542d7fa383aeb9035c0a5536cff3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>步骤 4d: FileAct 实时方案的测试的有效实例
在开始此步骤之前，必须完成[步骤 4c： 对于 FileAct 实时方案创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime PutReqSimple.xml 的文件。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  验证从传输 Sample_Put.txt 文件： 到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，C:\SWIFTAdapterTutorial\Fileact\ClientLocation 和响应出现在 C:\SWIFTAdapterTutorial\Fileact\ResponseClient 和 C:\SWIFTAdapterTutorial\Fileact\ResponseServer。  
  
4.  检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。 这些消息应包含以下传输状态：  
  
     HandleFileEventRequest 消息\<软件 TransferStatus\>已接受\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<软件 TransferStatus\>启动\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<软件 TransferStatus\>已完成\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试 FileAct 实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A： 启动 FileAct 实时方案 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4B： 开始发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [步骤 4C：为 FileAct 实时方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)