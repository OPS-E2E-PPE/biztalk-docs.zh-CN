---
title: "步骤 3： 创建发送端口和接收端口 FileAct 实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d7d39c7-a08b-4fbb-85fe-b30a8d62524b
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa7b0465ca6909998379ea94ef173d30387da602
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="23656-102">步骤 3： 创建发送端口和 FileAct 实时方案接收端口</span><span class="sxs-lookup"><span data-stu-id="23656-102">Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="23656-103">在开始此部分中的步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到 FileAct 实时方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="23656-103">Before you begin the steps in this section, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="23656-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="23656-104">In This Section</span></span>  
  
-   [<span data-ttu-id="23656-105">步骤 3A： 添加一个文件接收位置 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="23656-105">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="23656-106">步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="23656-106">Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="23656-107">步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="23656-107">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)  
  
-   [<span data-ttu-id="23656-108">步骤 3D: FileAct 实时方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="23656-108">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="23656-109">步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="23656-109">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
-   [<span data-ttu-id="23656-110">单步 3F： 添加 FileAct 实时方案，以捕获软件 HandleFileEventRequest 消息文件发送端口</span><span class="sxs-lookup"><span data-stu-id="23656-110">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>](../../adapters-and-accelerators/fileact-interact/step-3f-add-file-send-port-to-get-sw-handlefileeventrequest-messages--fileact.md)