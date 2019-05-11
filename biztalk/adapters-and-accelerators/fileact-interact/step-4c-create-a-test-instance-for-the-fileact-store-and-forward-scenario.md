---
title: 步骤 4c:创建测试实例为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477abefa-63d0-4cf2-9e4f-67467195efa8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf28aaae49d670933db8315ed3dd333a28462d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364789"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="dee6a-102">步骤 4c:创建为 FileAct 存储和转发方案测试实例</span><span class="sxs-lookup"><span data-stu-id="dee6a-102">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="dee6a-103">在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md)。</span><span class="sxs-lookup"><span data-stu-id="dee6a-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="dee6a-104">若要创建测试实例</span><span class="sxs-lookup"><span data-stu-id="dee6a-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="dee6a-105">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="dee6a-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Sw-ExchangeFileRequest>  
    <Sw-FileRequest>  
    <Sw-FileOpRequest>  
    <Sw-PutFileRequest>  
    <Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
    </Sw-PutFileRequest>  
    </Sw-FileOpRequest>  
    </Sw-FileRequest>  
    </Sw-ExchangeFileRequest>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dee6a-106">您必须将 %physicalfoldername%FILEACT 中配置的实际文件夹名称替换为接收位置。</span><span class="sxs-lookup"><span data-stu-id="dee6a-106">You must replace %PhysicalFolderName% with the actual folder name you configured in the FILEACT receive location.</span></span>  
  
2.  <span data-ttu-id="dee6a-107">"PutReqSimple.xml"的名称保存该文件。</span><span class="sxs-lookup"><span data-stu-id="dee6a-107">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="dee6a-108">请确保文件 (Sample_put.txt) 位于客户端位置文件夹。</span><span class="sxs-lookup"><span data-stu-id="dee6a-108">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dee6a-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="dee6a-109">See Also</span></span>  
 <span data-ttu-id="dee6a-110">[步骤 4：测试 FileAct 存储和转发端到端方案](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dee6a-110">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="dee6a-111">[步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="dee6a-111">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="dee6a-112">[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="dee6a-112">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="dee6a-113">步骤 4d:测试有效实例为 FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="dee6a-113">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario.md)