---
title: 步骤 4c:为 InterAct 存储和转发方案创建测试实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 64a69dcc-d307-47c0-87e8-b0cb2a4d655b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e8a15ba9273346b5038df485e26c3df3234066a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364806"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="84792-102">步骤 4c:为 InterAct 存储和转发方案创建测试实例</span><span class="sxs-lookup"><span data-stu-id="84792-102">Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="84792-103">在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="84792-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="84792-104">若要创建测试实例</span><span class="sxs-lookup"><span data-stu-id="84792-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="84792-105">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="84792-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
    ```  
  
2.  <span data-ttu-id="84792-106">使用名称 ExchangeReqSimple.xml 保存该文件。</span><span class="sxs-lookup"><span data-stu-id="84792-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84792-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="84792-107">See Also</span></span>  
 <span data-ttu-id="84792-108">[步骤 4：测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84792-108">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="84792-109">[步骤 4A:InterAct 存储和转发方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="84792-109">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="84792-110">[步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="84792-110">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="84792-111">步骤 4d:为 InterAct 存储和转发方案测试有效实例</span><span class="sxs-lookup"><span data-stu-id="84792-111">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)