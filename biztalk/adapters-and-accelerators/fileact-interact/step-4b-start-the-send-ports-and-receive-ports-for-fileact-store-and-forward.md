---
title: 步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f8c34b1-24a5-4ac7-bb96-27834bc3c711
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b1cea7699cfb45ebf736e0547e1f0cca9fcf63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364893"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-scenario"></a>步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案
在开始此步骤之前，必须完成[步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动的发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_FA_SendResponseToReceiver**  
  
    -   **Tutorial_FA_SendRequest_SnF**  
  
    -   **Tutorial_ GetStatusReports**  
  
4.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:  
  
    -   **Tutorial_FA_InputRequest_SnF**  
  
    -   **Tutorial_FA_HandleRequestOneWay_SnF**  
  
## <a name="see-also"></a>请参阅  
 [步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md)   
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 4c:创建为 FileAct 存储和转发方案测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)   
 [步骤 4d:测试有效实例为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)