---
title: 步骤 4c:创建测试实例的 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4539670824f23ddd4b4104da890c38ed6736fc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364795"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a>步骤 4c:创建测试实例的 InterAct 实时方案
在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)。  
  
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
  
2.  使用名称保存文件**ExchangeReqSimple.xml**。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 InterAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [步骤 4B:启动发送端口和接收端口的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [步骤 4d:测试有效实例为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)