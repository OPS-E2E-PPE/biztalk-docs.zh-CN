---
title: "步骤 3E： 将文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息添加 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b9314f86-a2c9-4ef3-8474-b7e2e2f8bf66
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18e26d13196a46045191b9e5767040e2216ceba2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3e-add-a-file-send-port-to-capture-swexchangefileresponse-message-for-the-fileact-real-time-scenario"></a><span data-ttu-id="40e10-102">步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="40e10-102">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="40e10-103">在开始此步骤之前，必须完成[步骤 3D: FileAct 实时方案添加 FILEACT 发送端口](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="40e10-103">Before you begin this step, you must complete [Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swexchangefileresponse-message"></a><span data-ttu-id="40e10-104">若要添加一个文件，将发送端口捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="40e10-104">To add a FILE send port to capture Sw:ExchangeFileResponse message</span></span>  
  
1.  <span data-ttu-id="40e10-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="40e10-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="40e10-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="40e10-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="40e10-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="40e10-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="40e10-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendResponseToSender。</span><span class="sxs-lookup"><span data-stu-id="40e10-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToSender.</span></span>  
  
5.  <span data-ttu-id="40e10-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="40e10-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="40e10-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseClient，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="40e10-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseClient, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="40e10-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="40e10-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="40e10-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="40e10-112">**Use this**</span></span>|<span data-ttu-id="40e10-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="40e10-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="40e10-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="40e10-114">**Send handler**</span></span>|<span data-ttu-id="40e10-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="40e10-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="40e10-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="40e10-116">**Send pipeline**</span></span>|<span data-ttu-id="40e10-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="40e10-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="40e10-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="40e10-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="40e10-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="40e10-119">**Use this**</span></span>|<span data-ttu-id="40e10-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="40e10-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="40e10-121">**属性**</span><span class="sxs-lookup"><span data-stu-id="40e10-121">**Property**</span></span>|<span data-ttu-id="40e10-122">从下拉列表中选择**BTS。SPName**。</span><span class="sxs-lookup"><span data-stu-id="40e10-122">From the drop-down list, select **BTS.SPName**.</span></span>|  
    |<span data-ttu-id="40e10-123">**运算符**</span><span class="sxs-lookup"><span data-stu-id="40e10-123">**Operator**</span></span>|<span data-ttu-id="40e10-124">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="40e10-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="40e10-125">**值**</span><span class="sxs-lookup"><span data-stu-id="40e10-125">**Value**</span></span>|<span data-ttu-id="40e10-126">类型 Tutorial_FA_SendRequest_RealTime。</span><span class="sxs-lookup"><span data-stu-id="40e10-126">Type Tutorial_FA_SendRequest_RealTime.</span></span>|  
    |<span data-ttu-id="40e10-127">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="40e10-127">**Group by**</span></span>|<span data-ttu-id="40e10-128">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="40e10-128">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="40e10-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="40e10-129">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40e10-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40e10-130">See Also</span></span>  
 <span data-ttu-id="40e10-131">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="40e10-131">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="40e10-132">[步骤 3A： 添加一个文件接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="40e10-132">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="40e10-133">[步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="40e10-133">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="40e10-134">[步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="40e10-134">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 [<span data-ttu-id="40e10-135">步骤 3D: FileAct 实时方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="40e10-135">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)