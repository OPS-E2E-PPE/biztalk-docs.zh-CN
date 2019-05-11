---
title: 步骤 4d:为 InterAct 存储和转发方案测试有效实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6aa49df8-ccf6-455a-99ff-38879d2b7bf9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9bac2a14267b0767cd0498ecfbb8b0f96f686e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364664"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario"></a>步骤 4d:为 InterAct 存储和转发方案测试有效实例
在开始此步骤之前，必须完成[步骤 4c:为 InterAct 存储和转发方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  删除文件 ExchangeReqSimple.xml 到 c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  浏览到 C:\SWIFTAdapterTutorial\Interact\HandleRequest。 验证该： handlerequest 在文件夹中。  
  
4.  在文本编辑器中，（如记事本） 打开 sw: handlerequest 消息并验证有效负载部分是与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A:InterAct 存储和转发方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)   
 [步骤 4c:为 InterAct 存储和转发方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md)