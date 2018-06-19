---
title: 步骤 4d： 测试 FileAct 应用商店应用和进 （请求） 方案的有效实例 |Microsoft 文档
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
ms.openlocfilehash: cf6f53257ff2a9194cf85597d0806780f15c8e52
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223693"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 4d： 测试 FileAct 应用商店应用和进 （请求） 方案的有效实例
在开始此步骤之前，必须完成[步骤 4c： 创建 FileAct 应用商店应用和向前 （请求） 方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  删除文件 PutReqSimple.xml 到**C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF**。  
  
2.  验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。  
  
3.  拖放到文件 fileactcquirequeue.xml **C:\SWIFTAdapterTutorial\FileAct\PullRequest**。  
  
4.  验证从传输 Sample_Put.txt 文件**C:\SWIFTAdapterTutorial\Fileact\ClientLocation**到**C:\SWIFTAdapterTutorial\Fileact\ServerLocation**，并且响应显示在**C:\SWIFTAdapterTutorial\PullResponse**。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)   
 [步骤 4c： 创建 FileAct 应用商店应用和进 （请求） 方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)