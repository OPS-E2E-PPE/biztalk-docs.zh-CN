---
title: "步骤 3A： 添加一个文件接收位置 FileAct 实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73b044b4-6611-493f-969c-02b52cb56ba7
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 266b29281ea7518cffee1461da2a3eaac66d9429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario"></a><span data-ttu-id="35e6f-102">步骤 3A： 添加一个文件接收位置 FileAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="35e6f-102">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="35e6f-103">在开始此步骤之前，必须完成[步骤 2： 将 SWIFTNet 配置添加到 FileAct 实时方案 Paramfile](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="35e6f-103">Before you begin this step, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-receive-location"></a><span data-ttu-id="35e6f-104">若要添加文件接收位置</span><span class="sxs-lookup"><span data-stu-id="35e6f-104">To add a FILE receive location</span></span>  
  
1.  <span data-ttu-id="35e6f-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="35e6f-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="35e6f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="35e6f-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="35e6f-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="35e6f-108">在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_InputRequest_RealTime。</span><span class="sxs-lookup"><span data-stu-id="35e6f-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_InputRequest_RealTime.</span></span>  
  
5.  <span data-ttu-id="35e6f-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="35e6f-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**文件**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="35e6f-111">在**文件传输属性**对话框中，在**接收文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-111">In the **FILE Transport Properties** dialog box, in the **Receive folder** box, type C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="35e6f-112">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="35e6f-112">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="35e6f-113">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="35e6f-113">**Use this**</span></span>|<span data-ttu-id="35e6f-114">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="35e6f-114">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="35e6f-115">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="35e6f-115">**Receive handler**</span></span>|<span data-ttu-id="35e6f-116">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-116">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="35e6f-117">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="35e6f-117">**Receive pipeline**</span></span>|<span data-ttu-id="35e6f-118">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-118">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="35e6f-119">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="35e6f-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35e6f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35e6f-120">See Also</span></span>  
 <span data-ttu-id="35e6f-121">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35e6f-121">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="35e6f-122">[步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35e6f-122">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="35e6f-123">[步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="35e6f-123">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 <span data-ttu-id="35e6f-124">[步骤 3D: FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35e6f-124">[Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="35e6f-125">步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="35e6f-125">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)