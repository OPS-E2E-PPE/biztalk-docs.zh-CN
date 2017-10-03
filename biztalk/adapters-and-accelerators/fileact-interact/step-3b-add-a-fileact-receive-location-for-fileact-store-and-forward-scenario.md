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
ms.openlocfilehash: 2c717d23886860363ca9c94d1eec79195f873fff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-a-fileact-receive-location-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="3ab32-102">步骤 3B： 添加 FILEACT 接收位置 FileAct 应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="3ab32-102">Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="3ab32-103">在开始此步骤之前，必须完成[步骤 3A： 添加文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md)。</span><span class="sxs-lookup"><span data-stu-id="3ab32-103">Before you begin this step, you must complete [Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-add-an-fileact-receive-location"></a><span data-ttu-id="3ab32-104">若要添加 FILEACT 接收位置</span><span class="sxs-lookup"><span data-stu-id="3ab32-104">To add an FILEACT receive location</span></span>  
  
1.  <span data-ttu-id="3ab32-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3ab32-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3ab32-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="3ab32-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="3ab32-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="3ab32-108">在**接收端口属性**窗口中，名称接收端口，Tutorial_FA_HandleRequestOneWay_SnF。</span><span class="sxs-lookup"><span data-stu-id="3ab32-108">In the **Receive Port Properties** window, name the receive port, Tutorial_FA_HandleRequestOneWay_SnF.</span></span>  
  
5.  <span data-ttu-id="3ab32-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="3ab32-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**FILEACT**，和然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="3ab32-111">在**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3ab32-111">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="3ab32-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="3ab32-112">**Use this**</span></span>|<span data-ttu-id="3ab32-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3ab32-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3ab32-114">**密码**</span><span class="sxs-lookup"><span data-stu-id="3ab32-114">**Password**</span></span>|<span data-ttu-id="3ab32-115">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="3ab32-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="3ab32-116">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="3ab32-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="3ab32-117">**用户名**</span><span class="sxs-lookup"><span data-stu-id="3ab32-117">**User name**</span></span>|<span data-ttu-id="3ab32-118">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="3ab32-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="3ab32-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="3ab32-119">**Application name**</span></span>|<span data-ttu-id="3ab32-120">键入的服务器\<应用程序接口名称 > 压降框中路由组。</span><span class="sxs-lookup"><span data-stu-id="3ab32-120">Type the Server \<Application Interface Name> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="3ab32-121">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="3ab32-121">**Crypto Mode**</span></span>|<span data-ttu-id="3ab32-122">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="3ab32-123">**FACrypto 模式**</span><span class="sxs-lookup"><span data-stu-id="3ab32-123">**FACrypto Mode**</span></span>|<span data-ttu-id="3ab32-124">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-124">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="3ab32-125">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="3ab32-125">**LogMessages**</span></span>|<span data-ttu-id="3ab32-126">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-126">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="3ab32-127">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="3ab32-127">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="3ab32-128">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="3ab32-128">**MemberRef**</span></span>|<span data-ttu-id="3ab32-129">从下拉列表中选择**ResponsePayload**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-129">From the drop-down list, select **ResponsePayload**.</span></span>|  
    |<span data-ttu-id="3ab32-130">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="3ab32-130">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="3ab32-131">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-131">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3ab32-132">**响应方**</span><span class="sxs-lookup"><span data-stu-id="3ab32-132">**Responder**</span></span>|<span data-ttu-id="3ab32-133">键入相应\<响应方 > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="3ab32-133">Type the appropriate \<Responder> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3ab32-134">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="3ab32-134">**ResponseCrypto**</span></span>|<span data-ttu-id="3ab32-135">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3ab32-136">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="3ab32-136">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="3ab32-137">从下拉列表中选择**ResponsePayload**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-137">From the drop-down list, select **ResponsePayload**.</span></span>|  
    |<span data-ttu-id="3ab32-138">**FileCompression**</span><span class="sxs-lookup"><span data-stu-id="3ab32-138">**FileCompression**</span></span>|<span data-ttu-id="3ab32-139">从下拉列表中，选择无。</span><span class="sxs-lookup"><span data-stu-id="3ab32-139">From the drop-down list, select None.</span></span>|  
    |<span data-ttu-id="3ab32-140">**PhysicalFolderName**</span><span class="sxs-lookup"><span data-stu-id="3ab32-140">**PhysicalFolderName**</span></span>|<span data-ttu-id="3ab32-141">键入服务器上的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="3ab32-141">Type the name of the folder on the server.</span></span> <span data-ttu-id="3ab32-142">例如，C:\Fileact\ServerLocation。</span><span class="sxs-lookup"><span data-stu-id="3ab32-142">For example, C:\Fileact\ServerLocation.</span></span>|  
    |<span data-ttu-id="3ab32-143">**SubscribeFileEvents**</span><span class="sxs-lookup"><span data-stu-id="3ab32-143">**SubscribeFileEvents**</span></span>|<span data-ttu-id="3ab32-144">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-144">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3ab32-145">**TransferAnswer**</span><span class="sxs-lookup"><span data-stu-id="3ab32-145">**TransferAnswer**</span></span>|<span data-ttu-id="3ab32-146">从下拉列表中选择**已接受**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-146">From the drop-down list, select **Accepted**.</span></span>|  
    |<span data-ttu-id="3ab32-147">**AllFileEvents**</span><span class="sxs-lookup"><span data-stu-id="3ab32-147">**AllFileEvents**</span></span>|<span data-ttu-id="3ab32-148">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-148">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="3ab32-149">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="3ab32-149">**Event end-point**</span></span>|<span data-ttu-id="3ab32-150">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="3ab32-150">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="3ab32-151">**FullFileStatus**</span><span class="sxs-lookup"><span data-stu-id="3ab32-151">**FullFileStatus**</span></span>|<span data-ttu-id="3ab32-152">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-152">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="3ab32-153">**超时**</span><span class="sxs-lookup"><span data-stu-id="3ab32-153">**Timeout**</span></span>|<span data-ttu-id="3ab32-154">键入适当数量会发生超时之前等待的秒。</span><span class="sxs-lookup"><span data-stu-id="3ab32-154">Type an appropriate number of seconds before timeout should occur.</span></span>|  
    |<span data-ttu-id="3ab32-155">**获取队列**</span><span class="sxs-lookup"><span data-stu-id="3ab32-155">**Acquire queue**</span></span>|<span data-ttu-id="3ab32-156">键入根据 SWIFT 你设置的队列名称。</span><span class="sxs-lookup"><span data-stu-id="3ab32-156">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3ab32-157">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="3ab32-157">**ForceAcquire**</span></span>|<span data-ttu-id="3ab32-158">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-158">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="3ab32-159">**排序依据**</span><span class="sxs-lookup"><span data-stu-id="3ab32-159">**Order by**</span></span>|<span data-ttu-id="3ab32-160">从下拉列表中选择**FileAct**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-160">From the drop-down list, select **FileAct**.</span></span>|  
    |<span data-ttu-id="3ab32-161">**推送会话**</span><span class="sxs-lookup"><span data-stu-id="3ab32-161">**Push session**</span></span>|<span data-ttu-id="3ab32-162">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-162">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="3ab32-163">**恢复模式**</span><span class="sxs-lookup"><span data-stu-id="3ab32-163">**Recovery mode**</span></span>|<span data-ttu-id="3ab32-164">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-164">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3ab32-165">**SNL 终结点**</span><span class="sxs-lookup"><span data-stu-id="3ab32-165">**SNL end-point**</span></span>|<span data-ttu-id="3ab32-166">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="3ab32-166">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="3ab32-167">此值应与匹配压降中配置的 SnL 终结点。</span><span class="sxs-lookup"><span data-stu-id="3ab32-167">This value should match the SnL endpoint you configured in SAG.</span></span>|  
  
8.  <span data-ttu-id="3ab32-168">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-168">Click **OK**.</span></span>  
  
9. <span data-ttu-id="3ab32-169">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3ab32-169">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3ab32-170">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="3ab32-170">**Use this**</span></span>|<span data-ttu-id="3ab32-171">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3ab32-171">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3ab32-172">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="3ab32-172">**Receive handler**</span></span>|<span data-ttu-id="3ab32-173">从下拉列表中选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-173">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="3ab32-174">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="3ab32-174">**Receive pipeline**</span></span>|<span data-ttu-id="3ab32-175">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-175">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="3ab32-176">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3ab32-176">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ab32-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ab32-177">See Also</span></span>  
 <span data-ttu-id="3ab32-178">[步骤 3： 创建发送端口和接收端口 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="3ab32-178">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="3ab32-179">[步骤 3A： 添加一个文件接收位置 FileAct 应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3ab32-179">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="3ab32-180">[步骤 3c： 添加要捕获的 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息的 FileAct 应用商店和向前情况下的文件发送端口](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span><span class="sxs-lookup"><span data-stu-id="3ab32-180">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md) </span></span>  
 [<span data-ttu-id="3ab32-181">步骤 3D： 添加 FILEACT 发送端口 FileAct 应用商店应用和转发方案</span><span class="sxs-lookup"><span data-stu-id="3ab32-181">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario.md)