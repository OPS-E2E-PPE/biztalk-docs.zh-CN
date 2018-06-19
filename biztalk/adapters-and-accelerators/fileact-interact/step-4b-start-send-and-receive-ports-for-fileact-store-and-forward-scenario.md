---
title: 步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口 |Microsoft 文档
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
ms.openlocfilehash: ad4c6b9d17ab1ea55c1f8378f1cb481a07b09e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224389"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a>步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口
在开始此步骤之前，必须完成[步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)。  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a>若要启动发送端口和接收端口  
  
1.  启动**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。  
  
3.  以下每个发送端口，右键单击发送端口，然后单击**启动**:  
  
    -   **Tutorial_ FA_SendPullResponseToReceiver**  
  
    -   **Tutorial_ FA_SendRequest_SnF**  
  
    -   **Tutorial_ FA_DynamicSendPort**  
  
4.  在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。  
  
5.  对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:  
  
    -   **Tutorial_ FA_InputRequest_SnF**  
  
    -   **Tutorial_ FA_InputRequest_PullMode**  
  
## <a name="see-also"></a>另请参阅  
 [步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4c： 创建 FileAct 应用商店应用和进 （请求） 方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md)   
 [步骤 4d： 测试 FileAct 应用商店应用和进 （请求） 方案的有效实例](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)