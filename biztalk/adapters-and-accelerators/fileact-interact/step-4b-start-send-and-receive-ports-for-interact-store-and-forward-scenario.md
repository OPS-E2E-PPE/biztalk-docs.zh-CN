---
title: 步骤 4B： 开始发送端口和接收端口交互应用商店应用和进 （请求） 方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b747c76b30b9f7d04bef379be9eaccaaeca063ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223637"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4B： 开始发送端口和接收交互应用商店应用和进 （请求） 方案的端口
在开始此步骤之前，必须完成[步骤 4： 测试的交互，存储和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_ IA_SendPullResponseToReceiver**  
  
    -   **Tutorial_IA_SendRequest_SnF**  
  
    -   **Tutorial_IA_DynamicSendPort**  
  
4.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:  
  
    -   **Tutorial_IA_InputRequest_SnF**  
  
    -   **Tutorial_ IA_InputRequest_PullMode**  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和进 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4c： 交互应用商店应用和进 （请求） 方案中创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)   
 [步骤 4d： 交互应用商店应用和进 （请求） 方案中测试的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)