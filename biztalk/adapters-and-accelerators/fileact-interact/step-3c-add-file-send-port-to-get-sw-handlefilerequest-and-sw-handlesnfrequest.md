---
title: 步骤 3c： 将文件发送端口捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下添加 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc41e352-acc5-47eb-bb87-38990f0e76a7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae6858164ee82f935c607246e7e93ffd86908f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225941"
---
# <a name="step-3c-add-a-file-send-port-to-capture-the-swhandlefilerequest-and-swhandlesnfrequest-messages-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="d3d1c-102">步骤 3c： 添加要捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下的文件发送端口</span><span class="sxs-lookup"><span data-stu-id="d3d1c-102">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="d3d1c-103">在开始此步骤之前，必须完成[步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-103">Before you begin this step, you must complete [Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-a-file-send-port-to-capture-swresponseserver-message"></a><span data-ttu-id="d3d1c-104">若要添加一个文件，将发送端口捕获 Sw:ResponseServer 消息</span><span class="sxs-lookup"><span data-stu-id="d3d1c-104">To add a FILE send port to capture Sw:ResponseServer message</span></span>  
  
1.  <span data-ttu-id="d3d1c-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d3d1c-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="d3d1c-107">右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口。**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-107">Right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port.**</span></span>  
  
4.  <span data-ttu-id="d3d1c-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendResponseToReceiver。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendResponseToReceiver.</span></span>  
  
5.  <span data-ttu-id="d3d1c-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**文件**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILE**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="d3d1c-110">在**文件传输属性**对话框中，在**目标文件夹**框中，键入 C:\SWIFTAdapterTutorial\Fileact\ResponseServer，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-110">In the **FILE Transport Properties** dialog box, in the **Destination folder** box, type C:\SWIFTAdapterTutorial\Fileact\ResponseServer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="d3d1c-111">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3d1c-111">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="d3d1c-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-112">**Use this**</span></span>|<span data-ttu-id="d3d1c-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d3d1c-114">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-114">**Send handler**</span></span>|<span data-ttu-id="d3d1c-115">从下拉列表中选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-115">From the drop-down list, select **BizTalkServerApplication**.</span></span>|  
    |<span data-ttu-id="d3d1c-116">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-116">**Send pipeline**</span></span>|<span data-ttu-id="d3d1c-117">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-117">From the drop-down list, select **XMLTransmit**.</span></span>|  
  
8.  <span data-ttu-id="d3d1c-118">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3d1c-118">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d3d1c-119">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-119">**Use this**</span></span>|<span data-ttu-id="d3d1c-120">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-120">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d3d1c-121">**第一行： 属性**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-121">**First row: Property**</span></span>|<span data-ttu-id="d3d1c-122">从下拉列表中选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-122">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="d3d1c-123">**第一行： 运算符**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-123">**First row: Operator**</span></span>|<span data-ttu-id="d3d1c-124">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-124">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d3d1c-125">**第一行： 值**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-125">**First row: Value**</span></span>|<span data-ttu-id="d3d1c-126">类型**软件 HandleFileRequest**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-126">Type **Sw-HandleFileRequest**.</span></span>|  
    |<span data-ttu-id="d3d1c-127">**第一行： 分组依据**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-127">**First row: Group by**</span></span>|<span data-ttu-id="d3d1c-128">从下拉列表中选择**或**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-128">From the drop-down list, select **OR**.</span></span>|  
    |<span data-ttu-id="d3d1c-129">**第二行： 属性**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-129">**Second row: Property**</span></span>|<span data-ttu-id="d3d1c-130">从下拉列表中选择**BTS。MessageType**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-130">From the drop-down list, select **BTS.MessageType**.</span></span>|  
    |<span data-ttu-id="d3d1c-131">**第二行： 运算符**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-131">**Second row: Operator**</span></span>|<span data-ttu-id="d3d1c-132">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-132">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="d3d1c-133">**第二行： 值**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-133">**Second row: Value**</span></span>|<span data-ttu-id="d3d1c-134">类型**软件 HandleSnFRequest**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-134">Type **Sw-HandleSnFRequest**.</span></span>|  
    |<span data-ttu-id="d3d1c-135">**第二行： 分组依据**</span><span class="sxs-lookup"><span data-stu-id="d3d1c-135">**Second row: Group by**</span></span>|<span data-ttu-id="d3d1c-136">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-136">Leave the default value.</span></span>|  
  
9. <span data-ttu-id="d3d1c-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d3d1c-137">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d1c-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d1c-138">See Also</span></span>  
 <span data-ttu-id="d3d1c-139">[步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d3d1c-139">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="d3d1c-140">[步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d3d1c-140">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="d3d1c-141">[步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d3d1c-141">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="d3d1c-142">步骤 3D： 添加 FILEACT 发送端口 FileAct 应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="d3d1c-142">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)