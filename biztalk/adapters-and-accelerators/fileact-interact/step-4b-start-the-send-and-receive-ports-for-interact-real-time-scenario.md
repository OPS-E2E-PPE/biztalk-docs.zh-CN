---
title: "步骤 4B： 开始发送端口和接收端口交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dffee9a6-5877-4744-9b46-12ca4f8fa959
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3391f966fb1033ec1886f44b62158f910179d72f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a>步骤 4B： 开始发送端口和接收端口交互实时方案
在开始此步骤之前，必须完成[步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_IA_SendResponseToReceiver**  
  
    -   **Tutorial_IA_SendResponseToSender**  
  
    -   **Tutorial_IA_SendRequest_RealTime**  
  
4.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:  
  
    -   **Tutorial_IA_InputRequest_RealTime**  
  
    -   **Tutorial_IA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4： 测试交互实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md)   
 [步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)   
 [步骤 4c： 创建的测试实例交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)   
 [步骤 4d： 测试的有效实例交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)