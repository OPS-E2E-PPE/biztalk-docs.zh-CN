---
title: "步骤 4B： 开始发送端口和交互应用商店应用和向前情况下接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7b0ecd4-ea08-4567-80bd-14f465ba4867
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f5d92b70a1c98a2ff21443980be57d969281fbd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="f82f1-102">步骤 4B： 开始发送端口和交互应用商店应用和向前情况下接收端口</span><span class="sxs-lookup"><span data-stu-id="f82f1-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="f82f1-103">在开始此步骤之前，必须完成[步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="f82f1-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="f82f1-104">若要启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="f82f1-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="f82f1-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f82f1-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f82f1-106">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f82f1-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="f82f1-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="f82f1-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="f82f1-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="f82f1-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="f82f1-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="f82f1-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="f82f1-110">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="f82f1-110">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
4.  <span data-ttu-id="f82f1-111">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f82f1-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="f82f1-112">对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:</span><span class="sxs-lookup"><span data-stu-id="f82f1-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="f82f1-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="f82f1-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="f82f1-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span><span class="sxs-lookup"><span data-stu-id="f82f1-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f82f1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f82f1-115">See Also</span></span>  
 <span data-ttu-id="f82f1-116">[步骤 4： 测试的交互，存储和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f82f1-116">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="f82f1-117">[步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f82f1-117">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="f82f1-118">[步骤 4c： 交互应用商店应用和向前情况下创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f82f1-118">[Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="f82f1-119">步骤 4d： 交互应用商店应用和正向方案中测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="f82f1-119">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)