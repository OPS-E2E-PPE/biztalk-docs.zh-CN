---
title: "步骤 4d： 交互应用商店应用和进 （请求） 方案中测试的有效实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c9c8ea24eeb5541cf84448363ca91fcb8171f19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4d： 交互应用商店应用和进 （请求） 方案中测试的有效实例
在开始此步骤之前，必须完成[步骤 4c： 创建交互应用商店应用和向前 （请求） 方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  删除 c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF 将文件 ExchangeReqSimple.xml。  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  放到 c:\SWIFTAdapterTutorial\Interact\PullRequest 文件 acquirequeue.xml。  
  
4.  浏览到 C:\SWIFTAdapterTutorial\Interact\PullResponse 确认 Sw:HandleRequest 位于文件夹中。  
  
5.  在文本编辑器中，（如记事本） 打开 Sw:HandleRequest 消息，并验证的负载部分与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和进 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B： 开始发送端口和接收交互应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 4c： 交互应用商店应用和进 （请求） 方案中创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)