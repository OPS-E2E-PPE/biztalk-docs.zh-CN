---
title: 步骤 4c:创建测试实例为 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50fc72f0-ec00-46f9-b24b-fe8d5e5079ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c8bcd3d65e219a6720aaae0400185f59a851679
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364908"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="36a21-102">步骤 4c:创建测试实例为 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="36a21-102">Step 4C: Create a Test Instance for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="36a21-103">在开始此步骤之前，必须完成[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="36a21-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="36a21-104">若要创建测试实例</span><span class="sxs-lookup"><span data-stu-id="36a21-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="36a21-105">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="36a21-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
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
    >  <span data-ttu-id="36a21-106">必须替换 *%physicalfoldername%* FILEACT 中配置的实际文件夹名称与接收位置。</span><span class="sxs-lookup"><span data-stu-id="36a21-106">You must replace *%PhysicalFolderName%* with the actual folder name which you configured in the FILEACT receive location.</span></span>  
  
2.  <span data-ttu-id="36a21-107">使用名称 ExchangeReqSimple.xml 保存该文件。</span><span class="sxs-lookup"><span data-stu-id="36a21-107">Save the File with the name ExchangeReqSimple.xml.</span></span>  
  
3.  <span data-ttu-id="36a21-108">在文本编辑器中，（如记事本） 打开一个新文件并粘贴以下：</span><span class="sxs-lookup"><span data-stu-id="36a21-108">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8" ?>  
    <Sw-ExchangeSnFRequest>  
    <Sw-SnFRequest>  
    <Sw-SnFOpRequest>  
    <Sw-AcquireSnFRequest>  
    <SwInt-Queue Type the queue name, based on your provisioning with SWIFT </SwInt-Queue>  
    <Sw-SessionMode>Pull</Sw-SessionMode>  
    <Sw-ForceAcquire>TRUE</Sw-ForceAcquire>  
    <Sw-OrderBy>InterAct</Sw-OrderBy>  
    <Sw-RecoveryMode>TRUE</Sw-RecoveryMode>  
    </Sw-AcquireSnFRequest>  
    </Sw-SnFOpRequest>  
    </Sw-SnFRequest>  
    </Sw-ExchangeSnFRequest>  
  
    ```  
  
4.  <span data-ttu-id="36a21-109">使用名称 acquirequeue.xml 保存文件。</span><span class="sxs-lookup"><span data-stu-id="36a21-109">Save the File with the name acquirequeue.xml.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36a21-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="36a21-110">See Also</span></span>  
 <span data-ttu-id="36a21-111">[步骤 4A:启动 SWIFTNet 服务为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="36a21-111">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-swiftnet-service-for-fileact-store-and-forward-pull-scenario.md) </span></span>  
 <span data-ttu-id="36a21-112">[步骤 4B:启动发送端口和接收端口为 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="36a21-112">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-send-and-receive-ports-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="36a21-113">步骤 4d:测试 FileAct 存储和转发 （拉取） 方案的有效实例</span><span class="sxs-lookup"><span data-stu-id="36a21-113">Step 4D: Test a Valid Instance for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-fileact-store-and-forward-pull-scenario.md)