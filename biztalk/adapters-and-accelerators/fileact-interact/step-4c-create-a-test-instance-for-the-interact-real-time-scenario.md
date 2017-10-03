---
title: "步骤 4c： 创建的测试实例交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3557acdc-eb3f-4c70-b64a-3f523a1ba650
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0035074eba0eec6994aa7ab024afbcec10984
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="a7a5d-102">步骤 4c： 创建的测试实例交互实时方案</span><span class="sxs-lookup"><span data-stu-id="a7a5d-102">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="a7a5d-103">在开始此步骤之前，必须完成[步骤 4B： 对于交互的实时方案中启动的发送端口和接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a5d-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="a7a5d-104">若要创建的测试实例</span><span class="sxs-lookup"><span data-stu-id="a7a5d-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="a7a5d-105">在文本编辑器中，（如记事本） 打开新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="a7a5d-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="a7a5d-106">名称保存该文件**ExchangeReqSimple.xml**。</span><span class="sxs-lookup"><span data-stu-id="a7a5d-106">Save the file with the name **ExchangeReqSimple.xml**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a5d-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7a5d-107">See Also</span></span>  
 <span data-ttu-id="a7a5d-108">[步骤 4： 测试交互实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a7a5d-108">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="a7a5d-109">[步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="a7a5d-109">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="a7a5d-110">[步骤 4B： 开始发送端口和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a7a5d-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="a7a5d-111">步骤 4d： 测试的有效实例交互实时方案</span><span class="sxs-lookup"><span data-stu-id="a7a5d-111">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)