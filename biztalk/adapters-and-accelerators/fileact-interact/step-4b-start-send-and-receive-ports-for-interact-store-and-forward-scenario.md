---
title: 步骤 4B： 开始发送端口和接收端口交互应用商店应用和进 （请求） 方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00ab119d-ed44-4f4a-84ea-20f2c41e5a92
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b747c76b30b9f7d04bef379be9eaccaaeca063ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223637"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="e9973-102">步骤 4B： 开始发送端口和接收交互应用商店应用和进 （请求） 方案的端口</span><span class="sxs-lookup"><span data-stu-id="e9973-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="e9973-103">在开始此步骤之前，必须完成[步骤 4： 测试的交互，存储和转发的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="e9973-103">Before you begin this step, you must complete[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="e9973-104">若要启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="e9973-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="e9973-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="e9973-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="e9973-106">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9973-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="e9973-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="e9973-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="e9973-108">**Tutorial_ IA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="e9973-108">**Tutorial_ IA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="e9973-109">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="e9973-109">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="e9973-110">**Tutorial_IA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="e9973-110">**Tutorial_IA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="e9973-111">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e9973-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="e9973-112">对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:</span><span class="sxs-lookup"><span data-stu-id="e9973-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="e9973-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="e9973-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="e9973-114">**Tutorial_ IA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="e9973-114">**Tutorial_ IA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9973-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9973-115">See Also</span></span>  
 <span data-ttu-id="e9973-116">[步骤 4A： 启动 SWIFTNet 服务交互，应用商店应用和进 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e9973-116">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="e9973-117">[步骤 4c： 交互应用商店应用和进 （请求） 方案中创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="e9973-117">[Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="e9973-118">步骤 4d： 交互应用商店应用和进 （请求） 方案中测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="e9973-118">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)