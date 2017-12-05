---
title: "步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和向前方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f30bb7d-1efb-4350-8809-be35f5634ea0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9357c172ff538bce73d3618739f3db4f98141814
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="d4b16-102">步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="d4b16-102">Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="d4b16-103">在开始此步骤之前，必须完成[步骤 3A： 添加文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="d4b16-103">Before you begin this step, you must complete [Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-an-fileact-receive-location"></a><span data-ttu-id="d4b16-104">若要添加 FILEACT 接收位置</span><span class="sxs-lookup"><span data-stu-id="d4b16-104">To add an FILEACT receive location</span></span>  
  
1.  <span data-ttu-id="d4b16-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d4b16-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4b16-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="d4b16-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="d4b16-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="d4b16-108">在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_HandleRequestOneWay_SnF。</span><span class="sxs-lookup"><span data-stu-id="d4b16-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_HandleRequestOneWay_SnF.</span></span>  
  
5.  <span data-ttu-id="d4b16-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="d4b16-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**FILEACT**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="d4b16-111">在**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4b16-111">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="d4b16-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d4b16-112">**Use this**</span></span>|<span data-ttu-id="d4b16-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d4b16-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d4b16-114">**密码**</span><span class="sxs-lookup"><span data-stu-id="d4b16-114">**Password**</span></span>|<span data-ttu-id="d4b16-115">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="d4b16-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="d4b16-116">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="d4b16-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="d4b16-117">**用户名**</span><span class="sxs-lookup"><span data-stu-id="d4b16-117">**User name**</span></span>|<span data-ttu-id="d4b16-118">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="d4b16-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="d4b16-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="d4b16-119">**Application name**</span></span>|<span data-ttu-id="d4b16-120">键入的服务器\<应用程序接口名称\>压降框中路由组。</span><span class="sxs-lookup"><span data-stu-id="d4b16-120">Type the Server \<Application Interface Name\> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="d4b16-121">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="d4b16-121">**Crypto Mode**</span></span>|<span data-ttu-id="d4b16-122">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="d4b16-123">**FACrypto 模式**</span><span class="sxs-lookup"><span data-stu-id="d4b16-123">**FACrypto Mode**</span></span>|<span data-ttu-id="d4b16-124">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-124">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="d4b16-125">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="d4b16-125">**LogMessages**</span></span>|<span data-ttu-id="d4b16-126">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-126">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="d4b16-127">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="d4b16-127">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="d4b16-128">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="d4b16-128">**MemberRef**</span></span>|<span data-ttu-id="d4b16-129">从下拉列表中选择**ResponsePayload**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-129">From the drop-down list, select **ResponsePayload**.</span></span>|  
    |<span data-ttu-id="d4b16-130">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="d4b16-130">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="d4b16-131">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-131">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="d4b16-132">**响应方**</span><span class="sxs-lookup"><span data-stu-id="d4b16-132">**Responder**</span></span>|<span data-ttu-id="d4b16-133">键入相应\<响应方\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="d4b16-133">Type the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="d4b16-134">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="d4b16-134">**ResponseCrypto**</span></span>|<span data-ttu-id="d4b16-135">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="d4b16-136">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="d4b16-136">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="d4b16-137">从下拉列表中选择**ResponsePayload**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-137">From the drop-down list, select **ResponsePayload**.</span></span>|  
    |<span data-ttu-id="d4b16-138">**FileCompression**</span><span class="sxs-lookup"><span data-stu-id="d4b16-138">**FileCompression**</span></span>|<span data-ttu-id="d4b16-139">从下拉列表中，选择无。</span><span class="sxs-lookup"><span data-stu-id="d4b16-139">From the drop-down list, select None.</span></span>|  
    |<span data-ttu-id="d4b16-140">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="d4b16-140">**PhysicalFolderName**</span></span>|<span data-ttu-id="d4b16-141">键入服务器上的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="d4b16-141">Type the name of the folder on the server.</span></span> <span data-ttu-id="d4b16-142">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="d4b16-142">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="d4b16-143">**SubscribeFileEvents**</span><span class="sxs-lookup"><span data-stu-id="d4b16-143">**SubscribeFileEvents**</span></span>|<span data-ttu-id="d4b16-144">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-144">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="d4b16-145">**TransferAnswer**</span><span class="sxs-lookup"><span data-stu-id="d4b16-145">**TransferAnswer**</span></span>|<span data-ttu-id="d4b16-146">从下拉列表中选择**已接受**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-146">From the drop-down list, select **Accepted**.</span></span>|  
    |<span data-ttu-id="d4b16-147">**AllFileEvents**</span><span class="sxs-lookup"><span data-stu-id="d4b16-147">**AllFileEvents**</span></span>|<span data-ttu-id="d4b16-148">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-148">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="d4b16-149">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="d4b16-149">**Event end-point**</span></span>|<span data-ttu-id="d4b16-150">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="d4b16-150">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="d4b16-151">**FullFileStatus**</span><span class="sxs-lookup"><span data-stu-id="d4b16-151">**FullFileStatus**</span></span>|<span data-ttu-id="d4b16-152">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-152">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="d4b16-153">**超时**</span><span class="sxs-lookup"><span data-stu-id="d4b16-153">**Timeout**</span></span>|<span data-ttu-id="d4b16-154">键入适当数量会发生超时之前等待的秒。</span><span class="sxs-lookup"><span data-stu-id="d4b16-154">Type an appropriate number of seconds before timeout should occur.</span></span>|  
    |<span data-ttu-id="d4b16-155">**获取队列**</span><span class="sxs-lookup"><span data-stu-id="d4b16-155">**Acquire queue**</span></span>|<span data-ttu-id="d4b16-156">键入根据 SWIFT 你设置的队列名称。</span><span class="sxs-lookup"><span data-stu-id="d4b16-156">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="d4b16-157">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="d4b16-157">**ForceAcquire**</span></span>|<span data-ttu-id="d4b16-158">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-158">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="d4b16-159">**排序依据**</span><span class="sxs-lookup"><span data-stu-id="d4b16-159">**Order by**</span></span>|<span data-ttu-id="d4b16-160">从下拉列表中选择**FileAct**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-160">From the drop-down list, select **FileAct**.</span></span>|  
    |<span data-ttu-id="d4b16-161">**推送会话**</span><span class="sxs-lookup"><span data-stu-id="d4b16-161">**Push session**</span></span>|<span data-ttu-id="d4b16-162">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-162">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="d4b16-163">**恢复模式**</span><span class="sxs-lookup"><span data-stu-id="d4b16-163">**Recovery mode**</span></span>|<span data-ttu-id="d4b16-164">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-164">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="d4b16-165">**SNL 终结点**</span><span class="sxs-lookup"><span data-stu-id="d4b16-165">**SNL end-point**</span></span>|<span data-ttu-id="d4b16-166">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="d4b16-166">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="d4b16-167">此值应与匹配压降中配置的 SnL 终结点。</span><span class="sxs-lookup"><span data-stu-id="d4b16-167">This value should match the SnL endpoint you configured in SAG.</span></span>|  
  
8.  <span data-ttu-id="d4b16-168">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-168">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d4b16-169">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d4b16-169">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="d4b16-170">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="d4b16-170">**Use this**</span></span>|<span data-ttu-id="d4b16-171">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="d4b16-171">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="d4b16-172">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="d4b16-172">**Receive handler**</span></span>|<span data-ttu-id="d4b16-173">从下拉列表中选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-173">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="d4b16-174">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="d4b16-174">**Receive pipeline**</span></span>|<span data-ttu-id="d4b16-175">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-175">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="d4b16-176">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d4b16-176">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4b16-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4b16-177">See Also</span></span>  
 <span data-ttu-id="d4b16-178">[步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="d4b16-178">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="d4b16-179">[步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="d4b16-179">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="d4b16-180">[步骤 3c： 添加要捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span><span class="sxs-lookup"><span data-stu-id="d4b16-180">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span></span>  
 [<span data-ttu-id="d4b16-181">步骤 3D：为 FileAct 存储和转发方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="d4b16-181">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)