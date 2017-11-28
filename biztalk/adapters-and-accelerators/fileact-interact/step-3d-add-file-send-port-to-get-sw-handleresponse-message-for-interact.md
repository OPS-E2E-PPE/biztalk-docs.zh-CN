---
title: "步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e05e4d20-4cf2-402f-aaea-66987cb6515a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a0c8c8721d9f7de7b1cd1e57537aa02d2ed8fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-add-a-file-send-port-to-capture-the-swhandleresponse-message-for-the-interact-real-time-scenario"></a><span data-ttu-id="d72e6-102">步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="d72e6-102">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="d72e6-103">完成[步骤 3c： 将文件发送端口交互实时方案捕获 Sw:HandleRequest 消息添加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="d72e6-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-a-file-send-port-to-capture-swhandleresponse-message"></a><span data-ttu-id="d72e6-104">添加文件发送端口捕获 Sw:HandleResponse 消息</span><span class="sxs-lookup"><span data-stu-id="d72e6-104">Add a FILE send port to capture Sw:HandleResponse message</span></span>  
  
1.  <span data-ttu-id="d72e6-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d72e6-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d72e6-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="d72e6-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="d72e6-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="d72e6-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendResponseToSender**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendResponseToSender**.</span></span>  
  
5.  <span data-ttu-id="d72e6-109">在**发送端口属性**窗口中，从**Transporttype**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-109">In the **Send Port Properties** window, from the **Transporttype** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d72e6-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入**C:\SWIFTAdapterTutorial\Interact\Response**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type **C:\SWIFTAdapterTutorial\Interact\Response**, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d72e6-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d72e6-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="d72e6-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d72e6-112">**Use this**</span></span>|<span data-ttu-id="d72e6-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d72e6-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d72e6-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d72e6-114">**Send handler**</span></span>|<span data-ttu-id="d72e6-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d72e6-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d72e6-116">**Send pipeline**</span></span>|<span data-ttu-id="d72e6-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="d72e6-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d72e6-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d72e6-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d72e6-119">**Use this**</span></span>|<span data-ttu-id="d72e6-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d72e6-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d72e6-121">第一行：**属性**</span><span class="sxs-lookup"><span data-stu-id="d72e6-121">First row: **Property**</span></span>|<span data-ttu-id="d72e6-122">从下拉列表中选择**BTS。SPName**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-122">From the drop-down list, select **BTS.SPName**.</span></span>|  
    |<span data-ttu-id="d72e6-123">第一行：**运算符**</span><span class="sxs-lookup"><span data-stu-id="d72e6-123">First row: **Operator**</span></span>|<span data-ttu-id="d72e6-124">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="d72e6-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d72e6-125">第一行：**值**</span><span class="sxs-lookup"><span data-stu-id="d72e6-125">First row: **Value**</span></span>|<span data-ttu-id="d72e6-126">类型**Tutorial_IA_HandleRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-126">Type **Tutorial_IA_HandleRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="d72e6-127">第一行：**分组依据**</span><span class="sxs-lookup"><span data-stu-id="d72e6-127">First row: **Group by**</span></span>|<span data-ttu-id="d72e6-128">从下拉列表中选择**或**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="d72e6-129">第二行：**属性**</span><span class="sxs-lookup"><span data-stu-id="d72e6-129">Second row: **Property**</span></span>|<span data-ttu-id="d72e6-130">从下拉列表中选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="d72e6-131">第二行：**运算符**</span><span class="sxs-lookup"><span data-stu-id="d72e6-131">Second row: **Operator**</span></span>|<span data-ttu-id="d72e6-132">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="d72e6-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d72e6-133">第二行：**值**</span><span class="sxs-lookup"><span data-stu-id="d72e6-133">Second row: **Value**</span></span>|<span data-ttu-id="d72e6-134">类型**SwInt ExchangeResponse**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-134">Type **SwInt-ExchangeResponse**.</span></span>|  
    |<span data-ttu-id="d72e6-135">第二行：**分组依据**</span><span class="sxs-lookup"><span data-stu-id="d72e6-135">Second row: **Group by**</span></span>|<span data-ttu-id="d72e6-136">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="d72e6-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="d72e6-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d72e6-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d72e6-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d72e6-138">See Also</span></span>  
 <span data-ttu-id="d72e6-139">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d72e6-139">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d72e6-140">[步骤 3A： 添加一个文件接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d72e6-140">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d72e6-141">[步骤 3B： 添加交互接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d72e6-141">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="d72e6-142">[步骤 3c： 添加要捕获的 Sw:HandleRequest 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d72e6-142">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="d72e6-143">步骤 3E： 添加的交互发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="d72e6-143">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)