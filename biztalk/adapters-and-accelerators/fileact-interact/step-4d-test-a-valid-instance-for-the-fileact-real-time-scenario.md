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
ms.openlocfilehash: 77a9b887bc509ddf3dd67ea941e72cbbeb04a5ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>步骤 4d: FileAct 实时方案的测试的有效实例
在开始此步骤之前，必须完成[步骤 4c： 对于 FileAct 实时方案创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime PutReqSimple.xml 的文件。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  验证从传输 Sample_Put.txt 文件： 到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，C:\SWIFTAdapterTutorial\Fileact\ClientLocation 和响应出现在 C:\SWIFTAdapterTutorial\Fileact\ResponseClient 和 C:\SWIFTAdapterTutorial\Fileact\ResponseServer。  
  
4.  检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。 这些消息应包含以下传输状态：  
  
     HandleFileEventRequest 消息\<软件 TransferStatus > 已接受\</Sw-TransferStatus >  
  
     HandleFileEventRequest 消息\<软件 TransferStatus > 启动\</Sw-TransferStatus >  
  
     HandleFileEventRequest 消息\<软件 TransferStatus > 已完成\</Sw-TransferStatus >  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试 FileAct 实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A： 启动 FileAct 实时方案 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4B： 开始发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [步骤 4c: FileAct 实时方案为创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)