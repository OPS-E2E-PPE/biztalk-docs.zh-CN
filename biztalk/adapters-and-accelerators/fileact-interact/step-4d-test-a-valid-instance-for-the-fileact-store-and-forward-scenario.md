---
title: 步骤 4d:测试有效实例为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad1781cd33b5fad50a53df08868177d1d01bd07
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364676"
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="f7465-102">步骤 4d:测试有效实例为 FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="f7465-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="f7465-103">在开始此步骤之前，必须完成[步骤 4c:创建测试实例为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="f7465-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="f7465-104">若要测试有效实例</span><span class="sxs-lookup"><span data-stu-id="f7465-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="f7465-105">放入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF PutReqSimple.xml 的文件。</span><span class="sxs-lookup"><span data-stu-id="f7465-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.</span></span>  
  
2.  <span data-ttu-id="f7465-106">验证在一段时间后，PutReqSimple.xml 文件将从文件夹中消失。</span><span class="sxs-lookup"><span data-stu-id="f7465-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="f7465-107">验证，Sample_Put.txt 文件传输从 C:\SWIFTAdapterTurorial\Fileact\ClientLocation 到 C:\SWIFTAdapterTutorial\Fileact\ServerLocation，以及响应显示在 C:\SWIFTAdapterTutorial\ResponseServer。</span><span class="sxs-lookup"><span data-stu-id="f7465-107">Verify that the Sample_Put.txt file is transferred from C:\SWIFTAdapterTurorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="f7465-108">检查三个 HandleFileEventRequest 消息的状态事件 (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="f7465-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="f7465-109">这些消息应包含以下传输状态：</span><span class="sxs-lookup"><span data-stu-id="f7465-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="f7465-110">HandleFileEventRequest 消息\<Sw TransferStatus\>已接受\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="f7465-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="f7465-111">HandleFileEventRequest 消息\<Sw TransferStatus\>启动\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="f7465-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="f7465-112">HandleFileEventRequest 消息\<Sw TransferStatus\>Completed\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="f7465-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7465-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7465-113">See Also</span></span>  
 <span data-ttu-id="f7465-114">[步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f7465-114">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="f7465-115">[步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="f7465-115">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="f7465-116">[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="f7465-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="f7465-117">步骤 4c:创建为 FileAct 存储和转发方案测试实例</span><span class="sxs-lookup"><span data-stu-id="f7465-117">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)