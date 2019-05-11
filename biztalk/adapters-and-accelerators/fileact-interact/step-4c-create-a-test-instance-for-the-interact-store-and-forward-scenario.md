---
title: 步骤 4c:为 InterAct 存储和转发方案创建测试实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8a15ba9273346b5038df485e26c3df3234066a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364806"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a>步骤 4c:为 InterAct 存储和转发方案创建测试实例
在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)。  
  
### <a name="to-create-a-test-instance"></a>若要创建测试实例  
  
1.  在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  使用名称 ExchangeReqSimple.xml 保存该文件。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A:InterAct 存储和转发方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [步骤 4d:为 InterAct 存储和转发方案测试有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)