---
title: "步骤 4c： 交互应用商店应用和进 （请求） 方案中创建的测试实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c937edd-9524-4f8f-9bd1-68e24f2eebdc
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf5d0908593110b04f6e5cd0f5912b66264dc7a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4c： 交互应用商店应用和进 （请求） 方案中创建的测试实例
在开始此步骤之前，必须完成[步骤 3B： 将绑定与交互应用商店应用和向前 （请求） 方案的动态发送端口业务流程](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)。  
  
### <a name="to-create-a-test-instance"></a>若要创建的测试实例  
  
1.  在文本编辑器中，（如记事本） 打开新文件并粘贴以下：  
  
    ```  
    SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
  
    ```  
  
2.  ExchangeReqSimple.xml 的名称保存该文件。  
  
3.  在文本编辑器中，（如记事本） 打开新文件并粘贴以下：  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue>ptsguspp_genericfa!x</SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>FileAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  使用名称 acquirequeue.xml 保存文件。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和进 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B： 开始发送端口和接收交互应用商店应用和进 （请求） 方案的端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 4d： 交互应用商店应用和进 （请求） 方案中测试的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)