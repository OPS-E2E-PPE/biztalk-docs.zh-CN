---
title: 步骤 3：创建发送端口和接收端口为 FileAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7d39c7-a08b-4fbb-85fe-b30a8d62524b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70a0b8e561c9e26714b53730e7c4e7e4b1a9d323
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365744"
---
# <a name="step-3-create-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="c9d2f-102">步骤 3：创建发送端口和接收端口为 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="c9d2f-102">Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="c9d2f-103">在开始本部分中的步骤之前，必须完成[步骤 2:为 FileAct 实时方案向 Paramfile 添加 SWIFTNet 配置](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="c9d2f-103">Before you begin the steps in this section, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c9d2f-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="c9d2f-104">In This Section</span></span>  
  
-   [<span data-ttu-id="c9d2f-105">步骤 3a:为 FileAct 实时方案添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="c9d2f-105">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="c9d2f-106">步骤 3b:为 FileAct 实时方案添加 FILEACT 接收位置</span><span class="sxs-lookup"><span data-stu-id="c9d2f-106">Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="c9d2f-107">步骤 3c:添加 FILE 发送端口以捕获为 FileAct 实时方案： handlerequest 消息</span><span class="sxs-lookup"><span data-stu-id="c9d2f-107">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)  
  
-   [<span data-ttu-id="c9d2f-108">步骤 3D:为 FileAct 实时方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="c9d2f-108">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="c9d2f-109">步骤 3E:添加 FILE 发送端口以捕获 sw: exchangefileresponse 消息为 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="c9d2f-109">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
-   [<span data-ttu-id="c9d2f-110">步骤 3F:添加 FILE 发送端口为 FileAct 实时方案，以捕获 Sw-handlefileeventrequest 消息</span><span class="sxs-lookup"><span data-stu-id="c9d2f-110">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>](../../adapters-and-accelerators/fileact-interact/step-3f-add-file-send-port-to-get-sw-handlefileeventrequest-messages--fileact.md)