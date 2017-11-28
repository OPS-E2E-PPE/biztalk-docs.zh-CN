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
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-real-time-scenario"></a><span data-ttu-id="a24a3-102">步骤 4B： 开始发送端口和接收端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="a24a3-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="a24a3-103">在开始此步骤之前，必须完成[步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md)。</span><span class="sxs-lookup"><span data-stu-id="a24a3-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="a24a3-104">若要启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="a24a3-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="a24a3-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a24a3-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a24a3-106">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a24a3-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="a24a3-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="a24a3-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="a24a3-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="a24a3-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="a24a3-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="a24a3-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="a24a3-110">**Tutorial_IA_SendRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="a24a3-110">**Tutorial_IA_SendRequest_RealTime**</span></span>  
  
4.  <span data-ttu-id="a24a3-111">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a24a3-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="a24a3-112">对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:</span><span class="sxs-lookup"><span data-stu-id="a24a3-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="a24a3-113">**Tutorial_IA_InputRequest_RealTime**</span><span class="sxs-lookup"><span data-stu-id="a24a3-113">**Tutorial_IA_InputRequest_RealTime**</span></span>  
  
    -   <span data-ttu-id="a24a3-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span><span class="sxs-lookup"><span data-stu-id="a24a3-114">**Tutorial_IA_HandleRequestOneWay_RealTime**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a24a3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a24a3-115">See Also</span></span>  
 <span data-ttu-id="a24a3-116">[步骤 4： 测试交互实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a24a3-116">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="a24a3-117">[步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="a24a3-117">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="a24a3-118">[步骤 4c： 创建的测试实例交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a24a3-118">[Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="a24a3-119">步骤 4d： 测试的有效实例交互实时方案</span><span class="sxs-lookup"><span data-stu-id="a24a3-119">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-real-time-scenario.md)