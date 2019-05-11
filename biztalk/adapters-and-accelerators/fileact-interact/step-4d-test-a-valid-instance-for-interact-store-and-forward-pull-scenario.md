---
title: 步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100a2ba467515e5d041fcb47b03092d5c7c49cf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364756"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例
在开始此步骤之前，必须完成[步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-test-a-valid-instance"></a>若要测试有效实例  
  
1.  删除文件 ExchangeReqSimple.xml 到 c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF。  
  
2.  验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。  
  
3.  放入 c:\SWIFTAdapterTutorial\Interact\PullRequest 文件 acquirequeue.xml。  
  
4.  浏览到位于文件夹中： handlerequest C:\SWIFTAdapterTutorial\Interact\PullResponse 验证。  
  
5.  在文本编辑器中，（如记事本） 打开 sw: handlerequest 消息并验证有效负载部分是与文件 ExchangeReqSimple.xml 相同。  
  
## <a name="see-also"></a>请参阅  
 [步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md)   
 [步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)