---
title: 步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案 |Microsoft Docs
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
ms.openlocfilehash: 48b8f9ec4d2403d72de24d737aeae55305f5068b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364942"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a>步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案
在开始此步骤之前，必须完成[步骤 4:测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动的发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_ IA_SendPullResponseToReceiver**  
  
    -   **Tutorial_IA_SendRequest_SnF**  
  
    -   **Tutorial_IA_DynamicSendPort**  
  
4.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:  
  
    -   **Tutorial_IA_InputRequest_SnF**  
  
    -   **Tutorial_ IA_InputRequest_PullMode**  
  
## <a name="see-also"></a>请参阅  
 [步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md)   
 [步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)   
 [步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)