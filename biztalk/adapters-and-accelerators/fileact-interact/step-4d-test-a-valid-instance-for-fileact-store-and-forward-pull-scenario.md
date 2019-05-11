---
title: 步骤 4d:测试有效实例为 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c7aabe-206f-4b89-b739-ac1e63675451
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cf19da7b9fb0e6cbeefb3ccb9f7ff2cfbc8f86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364779"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 4d:测试 FileAct 存储和转发 （拉取） 方案的有效实例
在开始此步骤之前，必须完成[步骤 4c:创建测试实例为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  文件 PutReqSimple.xml 放到**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  Drop 到文件 fileactcquirequeue.xml **C:\SWIFTAdapterTutorial\FileAct\PullRequest**。  
  
4.  验证从传输 Sample_Put.txt 文件**C:\SWIFTAdapterTutorial\Fileact\ClientLocation**到**C:\SWIFTAdapterTutorial\Fileact\ServerLocation**，且这些响应将显示在**C:\SWIFTAdapterTutorial\PullResponse**。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [步骤 4c:创建测试实例为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)