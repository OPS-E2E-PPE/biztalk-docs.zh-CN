---
title: 步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c2933d0-bbe3-4486-832e-5009b2d760ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 100a2ba467515e5d041fcb47b03092d5c7c49cf2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364756"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="65d2b-102">步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例</span><span class="sxs-lookup"><span data-stu-id="65d2b-102">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="65d2b-103">在开始此步骤之前，必须完成[步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="65d2b-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="65d2b-104">若要测试有效实例</span><span class="sxs-lookup"><span data-stu-id="65d2b-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="65d2b-105">删除文件 ExchangeReqSimple.xml 到 c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="65d2b-105">Drop the file ExchangeReqSimple.xml into c:\SWIFTAdapterTutorial\Interact\InputRequest_SnF.</span></span>  
  
2.  <span data-ttu-id="65d2b-106">验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。</span><span class="sxs-lookup"><span data-stu-id="65d2b-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="65d2b-107">放入 c:\SWIFTAdapterTutorial\Interact\PullRequest 文件 acquirequeue.xml。</span><span class="sxs-lookup"><span data-stu-id="65d2b-107">Drop the file acquirequeue.xml into c:\SWIFTAdapterTutorial\Interact\PullRequest.</span></span>  
  
4.  <span data-ttu-id="65d2b-108">浏览到位于文件夹中： handlerequest C:\SWIFTAdapterTutorial\Interact\PullResponse 验证。</span><span class="sxs-lookup"><span data-stu-id="65d2b-108">Browse to C:\SWIFTAdapterTutorial\Interact\PullResponse Verify that Sw:HandleRequest is in the folder.</span></span>  
  
5.  <span data-ttu-id="65d2b-109">在文本编辑器中，（如记事本） 打开 sw: handlerequest 消息并验证有效负载部分是与文件 ExchangeReqSimple.xml 相同。</span><span class="sxs-lookup"><span data-stu-id="65d2b-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65d2b-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="65d2b-110">See Also</span></span>  
 <span data-ttu-id="65d2b-111">[步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="65d2b-111">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="65d2b-112">[步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="65d2b-112">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="65d2b-113">步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例</span><span class="sxs-lookup"><span data-stu-id="65d2b-113">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-interact-store-and-forward-pull-scenario.md)