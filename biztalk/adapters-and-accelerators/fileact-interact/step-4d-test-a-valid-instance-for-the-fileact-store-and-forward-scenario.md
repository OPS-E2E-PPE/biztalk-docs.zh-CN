---
title: 步骤 4d:测试有效实例为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad1781cd33b5fad50a53df08868177d1d01bd07
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364676"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a>步骤 4d:测试有效实例为 FileAct 存储和转发方案
在开始此步骤之前，必须完成[步骤 4c:创建测试实例为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF PutReqSimple.xml 的文件。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  验证，Sample_Put.txt 文件传输从 C:\SWIFTAdapterTurorial\Fileact\ClientLocation 到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，以及响应显示在 C:\SWIFTAdapterTutorial\ResponseServer。  
  
4.  检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。 这些消息应包含以下传输状态：  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>已接受\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>启动\</Sw-TransferStatus\>  
  
     HandleFileEventRequest 消息\<Sw TransferStatus\>Completed\</Sw-TransferStatus\>  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)   
 [步骤 4c:创建为 FileAct 存储和转发方案测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)