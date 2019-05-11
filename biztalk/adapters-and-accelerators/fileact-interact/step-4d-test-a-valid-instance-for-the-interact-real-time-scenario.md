---
title: 步骤 4d:测试有效实例为 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 190ba5003d24803bd8b8b3c304e671eb6ab4303c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364647"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a>步骤 4d:测试有效实例为 InterAct 实时方案
在开始此步骤之前，必须完成[步骤 4c:创建测试实例的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime ExchangeReqSimple.xml 的文件。  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  浏览到 C:\SWIFTAdapterTutorial\Interact\HandleRequest 若要查看句柄请求消息： handlerequest。  
  
4.  浏览到 C:\SWIFTAdapterTutorial\Interact\Response 若要查看句柄响应消息： handleresponse。  
  
5.  在文本编辑器中，（如记事本） 打开 sw: handlerequest 消息并验证有效负载部分是与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 InterAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [步骤 4B:启动发送端口和接收端口的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [步骤 4c:创建测试实例的 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)