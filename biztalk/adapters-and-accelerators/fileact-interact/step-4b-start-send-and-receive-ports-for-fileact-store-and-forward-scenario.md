---
title: "步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2215c5-fb43-4c7e-a42d-5d131a6dee38
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ad4c6b9d17ab1ea55c1f8378f1cb481a07b09e34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-4b-start-the-send-ports-and-receive-ports-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="d5477-102">步骤 4B： 开始发送端口和接收 FileAct 应用商店应用和进 （请求） 方案的端口</span><span class="sxs-lookup"><span data-stu-id="d5477-102">Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="d5477-103">在开始此步骤之前，必须完成[步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="d5477-103">Before you begin this step, you must complete [Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-start-the-send-ports-and-receive-ports"></a><span data-ttu-id="d5477-104">若要启动发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="d5477-104">To start the send ports and receive ports</span></span>  
  
1.  <span data-ttu-id="d5477-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d5477-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d5477-106">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5477-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the send ports.</span></span>  
  
3.  <span data-ttu-id="d5477-107">以下每个发送端口，右键单击发送端口，然后单击**启动**:</span><span class="sxs-lookup"><span data-stu-id="d5477-107">For each of the following send ports, right-click the send port, and then click **Start**:</span></span>  
  
    -   <span data-ttu-id="d5477-108">**Tutorial_ FA_SendPullResponseToReceiver**</span><span class="sxs-lookup"><span data-stu-id="d5477-108">**Tutorial_ FA_SendPullResponseToReceiver**</span></span>  
  
    -   <span data-ttu-id="d5477-109">**Tutorial_ FA_SendRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="d5477-109">**Tutorial_ FA_SendRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="d5477-110">**Tutorial_ FA_DynamicSendPort**</span><span class="sxs-lookup"><span data-stu-id="d5477-110">**Tutorial_ FA_DynamicSendPort**</span></span>  
  
4.  <span data-ttu-id="d5477-111">在控制台树中，展开 BizTalk 组中，，然后展开你在其中创建接收位置的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5477-111">In the console tree, expand the BizTalk group, and then expand the BizTalk application where you created the receive locations.</span></span>  
  
5.  <span data-ttu-id="d5477-112">对于每个以下的接收位置，右键单击接收位置，然后单击**启用**:</span><span class="sxs-lookup"><span data-stu-id="d5477-112">For each of the following receive locations, right-click the receive location, and then click **Enable**:</span></span>  
  
    -   <span data-ttu-id="d5477-113">**Tutorial_ FA_InputRequest_SnF**</span><span class="sxs-lookup"><span data-stu-id="d5477-113">**Tutorial_ FA_InputRequest_SnF**</span></span>  
  
    -   <span data-ttu-id="d5477-114">**Tutorial_ FA_InputRequest_PullMode**</span><span class="sxs-lookup"><span data-stu-id="d5477-114">**Tutorial_ FA_InputRequest_PullMode**</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5477-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5477-115">See Also</span></span>  
 <span data-ttu-id="d5477-116">[步骤 4A： 启动 FileAct 存储和转发 （请求） 方案的 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d5477-116">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="d5477-117">[步骤 4c： 创建 FileAct 应用商店应用和进 （请求） 方案的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d5477-117">[Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 [<span data-ttu-id="d5477-118">步骤 4d： 测试 FileAct 应用商店应用和进 （请求） 方案的有效实例</span><span class="sxs-lookup"><span data-stu-id="d5477-118">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)