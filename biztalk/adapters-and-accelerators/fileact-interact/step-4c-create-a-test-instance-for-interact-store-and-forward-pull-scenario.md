---
title: 步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c937edd-9524-4f8f-9bd1-68e24f2eebdc
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f3d90a04e25ec200ad2bf3ac0943956330c602a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364927"
---
# <a name="step-4c-create-a-test-instance-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="66210-102">步骤 4c:为 InterAct 存储和转发 （拉取） 方案创建测试实例</span><span class="sxs-lookup"><span data-stu-id="66210-102">Step 4C: Create a Test Instance for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="66210-103">在开始此步骤之前，必须完成[步骤 3B:将替换为 InterAct 存储和转发 （拉取） 方案的动态发送端口业务流程绑定](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="66210-103">Before you begin this step, you must complete [Step 3B: Bind the orchestration with dynamic send port for InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="66210-104">若要创建测试实例</span><span class="sxs-lookup"><span data-stu-id="66210-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="66210-105">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="66210-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    SwInt-ExchangeRequest>  
    <SwInt-Request>  
    <SwInt-RequestPayload>  
    Get Well soon  
    </SwInt-RequestPayload>  
    </SwInt-Request>  
    </SwInt-ExchangeRequest>  
  
    ```  
  
2.  <span data-ttu-id="66210-106">使用名称 ExchangeReqSimple.xml 保存该文件。</span><span class="sxs-lookup"><span data-stu-id="66210-106">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
3.  <span data-ttu-id="66210-107">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="66210-107">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue>ptsguspp_genericfa!x</SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>FileAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  <span data-ttu-id="66210-108">使用名称 acquirequeue.xml 保存文件。</span><span class="sxs-lookup"><span data-stu-id="66210-108">Save the File with the name acquirequeue.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66210-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="66210-109">See Also</span></span>  
 <span data-ttu-id="66210-110">[步骤 4A:InterAct 存储和转发 （拉取） 方案启动 SWIFTNet 服务](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="66210-110">[Step 4A: Start the SWIFTNet Service for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-the-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="66210-111">[步骤 4B:启动发送端口和接收端口为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="66210-111">[Step 4B: Start the Send Ports and Receive Ports for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="66210-112">步骤 4d:为 InterAct 存储和转发 （拉取） 方案测试有效实例</span><span class="sxs-lookup"><span data-stu-id="66210-112">Step 4D: Test a Valid Instance for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-interact-store-and-forward-pull-scenario.md)