---
title: '步骤 4d: FileAct 实时方案的测试的有效实例 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 906a7eb08dc7542d7fa383aeb9035c0a5536cff3
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963771"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="5ded4-102">步骤 4d: FileAct 实时方案的测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="5ded4-102">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="5ded4-103">在开始此步骤之前，必须完成[步骤 4c： 对于 FileAct 实时方案创建的测试实例](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="5ded4-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="5ded4-104">若要测试的有效实例</span><span class="sxs-lookup"><span data-stu-id="5ded4-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="5ded4-105">放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime PutReqSimple.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="5ded4-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span></span>  
  
2.  <span data-ttu-id="5ded4-106">验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。</span><span class="sxs-lookup"><span data-stu-id="5ded4-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="5ded4-107">验证从传输 Sample_Put.txt 文件： 到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，C:\SWIFTAdapterTutorial\Fileact\ClientLocation 和响应出现在 C:\SWIFTAdapterTutorial\Fileact\ResponseClient 和 C:\SWIFTAdapterTutorial\Fileact\ResponseServer。</span><span class="sxs-lookup"><span data-stu-id="5ded4-107">Verify that the Sample_Put.txt file is transferred from: C:\SWIFTAdapterTutorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\Fileact\ResponseClient and C:\SWIFTAdapterTutorial\Fileact\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="5ded4-108">检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ded4-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="5ded4-109">这些消息应包含以下传输状态：</span><span class="sxs-lookup"><span data-stu-id="5ded4-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="5ded4-110">HandleFileEventRequest 消息\<软件 TransferStatus\>已接受\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5ded4-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="5ded4-111">HandleFileEventRequest 消息\<软件 TransferStatus\>启动\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5ded4-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="5ded4-112">HandleFileEventRequest 消息\<软件 TransferStatus\>已完成\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="5ded4-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ded4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ded4-113">See Also</span></span>  
 <span data-ttu-id="5ded4-114">[步骤 4： 测试 FileAct 实时的端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5ded4-114">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="5ded4-115">[步骤 4A： 启动 FileAct 实时方案 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5ded4-115">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="5ded4-116">[步骤 4B： 开始发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5ded4-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="5ded4-117">步骤 4C：为 FileAct 实时方案创建测试实例</span><span class="sxs-lookup"><span data-stu-id="5ded4-117">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)