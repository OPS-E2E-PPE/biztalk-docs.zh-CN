---
title: "步骤 4c： 交互应用商店应用和向前情况下创建的测试实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44addc30191dd9541d7f5964a3de0eec244c9993
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="8fa41-102">步骤 4c： 交互应用商店应用和向前情况下创建的测试实例</span><span class="sxs-lookup"><span data-stu-id="8fa41-102">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="8fa41-103">在开始此步骤之前，必须完成[步骤 4B： 启动的发送端口和接收端口交互应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="8fa41-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="8fa41-104">若要创建的测试实例</span><span class="sxs-lookup"><span data-stu-id="8fa41-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="8fa41-105">在文本编辑器中，（如记事本） 打开新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="8fa41-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="8fa41-106">ExchangeReqSimple.xml 的名称保存该文件。</span><span class="sxs-lookup"><span data-stu-id="8fa41-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fa41-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fa41-107">See Also</span></span>  
 <span data-ttu-id="8fa41-108">[步骤 4： 测试的交互，存储和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8fa41-108">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="8fa41-109">[步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="8fa41-109">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="8fa41-110">[步骤 4B： 开始发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="8fa41-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="8fa41-111">步骤 4d： 交互应用商店应用和正向方案中测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="8fa41-111">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)