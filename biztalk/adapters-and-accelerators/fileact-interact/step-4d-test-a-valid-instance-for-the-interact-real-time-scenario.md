---
title: 步骤 4d： 测试的有效实例交互实时方案 |Microsoft 文档
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
ms.openlocfilehash: 94bdb2acd8147ec5041df7d6a1c4324ca833d9e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223765"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a>步骤 4d： 测试的有效实例交互实时方案
在开始此步骤之前，必须完成[步骤 4c： 对于交互实时方案创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试的有效实例  
  
1.  放入 C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime ExchangeReqSimple.xml 的文件。  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  浏览到 C:\SWIFTAdapterTutorial\Interact\HandleRequest 若要查看句柄请求消息，Sw:HandleRequest。  
  
4.  浏览到 C:\SWIFTAdapterTutorial\Interact\Response 若要查看句柄响应消息，Sw:HandleResponse。  
  
5.  在文本编辑器中，（如记事本） 打开 Sw:HandleRequest 消息，并验证的负载部分与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试交互实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [步骤 4B： 开始发送端口和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)   
 [步骤 4c： 创建的测试实例交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)