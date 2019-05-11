---
title: 步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea2215c5-fb43-4c7e-a42d-5d131a6dee38
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b477e88b5fa31a22e63672516e744a3e61f5d062
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364879"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案
在开始此步骤之前，必须完成[步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动的发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_ FA_SendPullResponseToReceiver**  
  
    -   **Tutorial_ FA_SendRequest_SnF**  
  
    -   **Tutorial_ FA_DynamicSendPort**  
  
4.  在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:  
  
    -   **Tutorial_ FA_InputRequest_SnF**  
  
    -   **Tutorial_ FA_InputRequest_PullMode**  
  
## <a name="see-also"></a>请参阅  
 [步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4c:创建测试实例为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4d:测试 FileAct 存储和转发 （拉取） 方案的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)