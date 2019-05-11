---
title: 步骤 4d:为 FileAct 实时方案测试有效实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76721d1a7870c10eb1008e3bc4f5183985816ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364741"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a>步骤 4d:为 FileAct 实时方案测试有效实例
在开始此步骤之前，必须完成[步骤 4c:为 FileAct 实时方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime PutReqSimple.xml 的文件。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  验证从传输 Sample_Put.txt 文件：到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，C:\SWIFTAdapterTutorial\Fileact\ClientLocation 和该响应将出现 C:\SWIFTAdapterTutorial\Fileact\ResponseClient 和 C:\SWIFTAdapterTutorial\Fileact\ResponseServer 中。  
  
4.  检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。 这些消息应包含以下传输状态：  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>已接受\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>启动\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>Completed\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md)   
 [步骤 4c:为 FileAct 实时方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)