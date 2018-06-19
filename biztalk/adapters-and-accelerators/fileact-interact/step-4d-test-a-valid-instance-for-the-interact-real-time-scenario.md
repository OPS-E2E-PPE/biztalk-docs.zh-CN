---
title: 步骤 4d： 测试的有效实例交互实时方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e163c3ac-a00d-40cf-b1b8-4a38f74ab0e8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94bdb2acd8147ec5041df7d6a1c4324ca833d9e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223765"
---
# <a name="step-4d-test-a-valid-instance-for-the-interact-real-time-scenario"></a><span data-ttu-id="dcc25-102">步骤 4d： 测试的有效实例交互实时方案</span><span class="sxs-lookup"><span data-stu-id="dcc25-102">Step 4D: Test a Valid Instance for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="dcc25-103">在开始此步骤之前，必须完成[步骤 4c： 对于交互实时方案创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="dcc25-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="dcc25-104">若要测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="dcc25-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="dcc25-105">放入 C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime ExchangeReqSimple.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="dcc25-105">Drop the file ExchangeReqSimple.xml into C:\SWIFTAdapterTutorial\Interact\InputRequest_RealTime.</span></span>  
  
2.  <span data-ttu-id="dcc25-106">验证在一段时间后，ExchangeReqSimple.xml 文件将从文件夹中消失。</span><span class="sxs-lookup"><span data-stu-id="dcc25-106">Verify that after a moment, the ExchangeReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="dcc25-107">浏览到 C:\SWIFTAdapterTutorial\Interact\HandleRequest 若要查看句柄请求消息，Sw:HandleRequest。</span><span class="sxs-lookup"><span data-stu-id="dcc25-107">Browse to C:\SWIFTAdapterTutorial\Interact\HandleRequest to view the handle request message, Sw:HandleRequest.</span></span>  
  
4.  <span data-ttu-id="dcc25-108">浏览到 C:\SWIFTAdapterTutorial\Interact\Response 若要查看句柄响应消息，Sw:HandleResponse。</span><span class="sxs-lookup"><span data-stu-id="dcc25-108">Browse to C:\SWIFTAdapterTutorial\Interact\Response to view the handle response message, Sw:HandleResponse.</span></span>  
  
5.  <span data-ttu-id="dcc25-109">在文本编辑器中，（如记事本） 打开 Sw:HandleRequest 消息，并验证的负载部分与文件 ExchangeReqSimple.xml 相同。</span><span class="sxs-lookup"><span data-stu-id="dcc25-109">Open the Sw:HandleRequest message in a text editor, such as Notepad, and verify that the payload section is the same as in the file ExchangeReqSimple.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcc25-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dcc25-110">See Also</span></span>  
 <span data-ttu-id="dcc25-111">[步骤 4： 测试交互实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dcc25-111">[Step 4: Test the InterAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-the-interact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="dcc25-112">[步骤 4A： 启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span><span class="sxs-lookup"><span data-stu-id="dcc25-112">[Step 4A: Start the SWIFTNet Service](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service.md) </span></span>  
 <span data-ttu-id="dcc25-113">[步骤 4B： 开始发送端口和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dcc25-113">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="dcc25-114">步骤 4c： 创建的测试实例交互实时方案</span><span class="sxs-lookup"><span data-stu-id="dcc25-114">Step 4C: Create a Test Instance for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-interact-real-time-scenario.md)