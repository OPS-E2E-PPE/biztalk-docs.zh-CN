---
title: 步骤 4B:启动发送端口和接收端口为 FileAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c56b5f7b-551a-4bd2-97c7-0996f5d1b1a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69fb541f792577c2a1bca5e7914a4e2cd6580d65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364918"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a>步骤 4B:启动发送端口和接收端口为 FileAct 实时方案
在开始此步骤之前，必须完成[步骤 4A:启动 SWIFTNet 服务为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动的发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_FA_SendResponseToReceiver**  
  
    -   **Tutorial_FA_SendResponseToSender**  
  
    -   **Tutorial_FA_SendRequest_RealTime**  
  
    -   **Tutorial_ GetStatusReports**  
  
4.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:  
  
    -   **Tutorial_FA_InputRequest_RealTime**  
  
    -   **Tutorial_FA_HandleRequestOneWay_RealTime**  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 实时端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md)   
 [步骤 4c:为 FileAct 实时方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)   
 [步骤 4d:为 FileAct 实时方案测试有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)