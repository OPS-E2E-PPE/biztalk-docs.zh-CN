---
title: 步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c937edd-9524-4f8f-9bd1-68e24f2eebdc
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f3d90a04e25ec200ad2bf3ac0943956330c602a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364927"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例
在开始此步骤之前，必须完成[步骤 3B:将替换为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)。  
  
### <a name="to-create-a-test-instance"></a>若要创建测试实例  
  
1.  在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：  
  
    ```  
    SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
  
    ```  
  
2.  使用名称 ExchangeReqSimple.xml 保存该文件。  
  
3.  在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：  
  
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
  
## <a name="see-also"></a>请参阅  
 [步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)