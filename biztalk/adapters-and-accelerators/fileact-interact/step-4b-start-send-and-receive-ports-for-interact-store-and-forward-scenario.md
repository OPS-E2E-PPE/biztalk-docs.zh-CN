---
title: 步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案 |Microsoft Docs
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
ms.openlocfilehash: 48b8f9ec4d2403d72de24d737aeae55305f5068b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364942"
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="f9d60-102">步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="f9d60-102">Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="f9d60-103">在开始此步骤之前，必须完成[步骤 4:测试 InterAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="f9d60-103">Before you begin this step, you must complete[Step 4: Test the InterAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-store-and-forward-end-to-end-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="f9d60-104">若要启动的发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="f9d60-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="f9d60-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f9d60-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="f9d60-106">在控制台树中，依次展开 BizTalk 组中，和你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9d60-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="f9d60-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="f9d60-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="f9d60-108">**Tutorial_ IA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="f9d60-108">**Tutorial_ IA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="f9d60-109">**Tutorial_IA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="f9d60-109">**Tutorial_IA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="f9d60-110">**Tutorial_IA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="f9d60-110">**Tutorial_IA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="f9d60-111">在控制台树中，依次展开 BizTalk 组中，和你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9d60-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="f9d60-112">对于每个以下的接收位置，右键单击该接收位置，然后依次**启用**:</span><span class="sxs-lookup"><span data-stu-id="f9d60-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="f9d60-113">**Tutorial_IA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="f9d60-113">**Tutorial_IA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="f9d60-114">**Tutorial_ IA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="f9d60-114">**Tutorial_ IA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9d60-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9d60-115">See Also</span></span>  
 <span data-ttu-id="f9d60-116">[步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f9d60-116">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="f9d60-117">[步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f9d60-117">[Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="f9d60-118">步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例</span><span class="sxs-lookup"><span data-stu-id="f9d60-118">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)