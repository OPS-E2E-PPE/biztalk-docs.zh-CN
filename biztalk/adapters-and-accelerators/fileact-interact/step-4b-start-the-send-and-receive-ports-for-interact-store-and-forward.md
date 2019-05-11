---
title: 步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7b0ecd4-ea08-4567-80bd-14f465ba4867
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1c3efec973c57ad056d738a9048c276d677644b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364854"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="246cd-102">步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="246cd-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="246cd-103">在开始此步骤之前，必须完成[步骤 4A:InterAct 存储和转发方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="246cd-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="246cd-104">若要启动的发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="246cd-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="246cd-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="246cd-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="246cd-106">在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="246cd-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="246cd-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="246cd-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="246cd-108">**Tutorial_IA_SendResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="246cd-108">**Tutorial_IA_SendResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="246cd-109">**Tutorial_IA_SendResponseToSender**</span><span class="sxs-lookup"><span data-stu-id="246cd-109">**Tutorial_IA_SendResponseToSender**</span></span>  
  
    -   <span data-ttu-id="246cd-110">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="246cd-110">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
4.  <span data-ttu-id="246cd-111">在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="246cd-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="246cd-112">对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:</span><span class="sxs-lookup"><span data-stu-id="246cd-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="246cd-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="246cd-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="246cd-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span><span class="sxs-lookup"><span data-stu-id="246cd-114">**Tutorial_IA_HandleRequestOneWay_SnF**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="246cd-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="246cd-115">See Also</span></span>  
 <span data-ttu-id="246cd-116">[步骤 4：测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="246cd-116">[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="246cd-117">[步骤 4A:InterAct 存储和转发方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="246cd-117">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="246cd-118">[步骤 4c:为 InterAct 存储和转发方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="246cd-118">[Step 4C: Create a Test Instance for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="246cd-119">步骤 4d:为 InterAct 存储和转发方案测试有效实例</span><span class="sxs-lookup"><span data-stu-id="246cd-119">Step 4D: Test a Valid Instance for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-interact-store-and-forward-scenario.md)