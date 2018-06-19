---
title: 步骤 3B： 添加交互接收位置交互应用商店应用和向前方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: da077518-b2ee-4b5f-88d0-fe73af2baa7a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e9aa8e153cf510f2d24cbe30a62317d26810e4a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966667"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="416f9-102">步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置</span><span class="sxs-lookup"><span data-stu-id="416f9-102">Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="416f9-103">完成[步骤 3A： 添加文件接收位置交互应用商店应用和转发方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="416f9-103">Complete [Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-receive-location"></a><span data-ttu-id="416f9-104">添加交互接收位置</span><span class="sxs-lookup"><span data-stu-id="416f9-104">Add an INTERACT receive location</span></span>  
  
1.  <span data-ttu-id="416f9-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="416f9-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="416f9-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="416f9-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="416f9-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="416f9-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="416f9-108">在**接收端口属性**窗口中，名称接收端口，Tutorial_IA_HandleRequestOneWay_SnF。</span><span class="sxs-lookup"><span data-stu-id="416f9-108">In the **Receive Port Properties** window, name the receive port, Tutorial_IA_HandleRequestOneWay_SnF.</span></span>  
  
5.  <span data-ttu-id="416f9-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="416f9-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="416f9-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="416f9-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="416f9-111">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="416f9-111">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="416f9-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="416f9-112">**Use this**</span></span>|<span data-ttu-id="416f9-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="416f9-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="416f9-114">**密码**</span><span class="sxs-lookup"><span data-stu-id="416f9-114">**Password**</span></span>|<span data-ttu-id="416f9-115">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="416f9-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="416f9-116">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="416f9-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="416f9-117">**用户名**</span><span class="sxs-lookup"><span data-stu-id="416f9-117">**User name**</span></span>|<span data-ttu-id="416f9-118">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="416f9-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="416f9-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="416f9-119">**Application name**</span></span>|<span data-ttu-id="416f9-120">键入的服务器\<应用程序接口名称\>压降框中路由组。</span><span class="sxs-lookup"><span data-stu-id="416f9-120">Type the Server \<Application Interface Name\> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="416f9-121">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="416f9-121">**Crypto Mode**</span></span>|<span data-ttu-id="416f9-122">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="416f9-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="416f9-123">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="416f9-123">**LogMessageBody**</span></span>|<span data-ttu-id="416f9-124">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-124">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="416f9-125">**注意：** 如果设置为 TRUE 时，它会保留 BizTalk 跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="416f9-125">**Note:**  If you set to TRUE, it preserves the message body in the BizTalk Tracking database.</span></span> <span data-ttu-id="416f9-126">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="416f9-126">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="416f9-127">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="416f9-127">**LogMessages**</span></span>|<span data-ttu-id="416f9-128">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-128">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="416f9-129">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="416f9-129">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="416f9-130">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="416f9-130">**Message format**</span></span>|<span data-ttu-id="416f9-131">从下拉列表中选择**InterActMessage**。</span><span class="sxs-lookup"><span data-stu-id="416f9-131">From the drop-down list, select **InterActMessage**.</span></span>|  
    |<span data-ttu-id="416f9-132">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="416f9-132">**MemberRef**</span></span>|<span data-ttu-id="416f9-133">从下拉列表中选择**ResponseHeader**。</span><span class="sxs-lookup"><span data-stu-id="416f9-133">From the drop-down list, select **ResponseHeader**.</span></span>|  
    |<span data-ttu-id="416f9-134">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="416f9-134">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="416f9-135">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="416f9-136">**响应方**</span><span class="sxs-lookup"><span data-stu-id="416f9-136">**Responder**</span></span>|<span data-ttu-id="416f9-137">键入相应\<响应方\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="416f9-137">Type the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="416f9-138">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="416f9-138">**ResponseCrypto**</span></span>|<span data-ttu-id="416f9-139">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-139">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="416f9-140">**超时**</span><span class="sxs-lookup"><span data-stu-id="416f9-140">**Timeout**</span></span>|<span data-ttu-id="416f9-141">键入适当数量会发生超时之前等待的秒。</span><span class="sxs-lookup"><span data-stu-id="416f9-141">Type an appropriate number of seconds before timeout should occur.</span></span>|  
    |<span data-ttu-id="416f9-142">**获取队列**</span><span class="sxs-lookup"><span data-stu-id="416f9-142">**Acquire queue**</span></span>|<span data-ttu-id="416f9-143">键入根据 SWIFT 你设置的队列名称。</span><span class="sxs-lookup"><span data-stu-id="416f9-143">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="416f9-144">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="416f9-144">**ForceAcquire**</span></span>|<span data-ttu-id="416f9-145">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-145">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="416f9-146">**排序依据**</span><span class="sxs-lookup"><span data-stu-id="416f9-146">**Order by**</span></span>|<span data-ttu-id="416f9-147">从下拉列表中选择**交互**。</span><span class="sxs-lookup"><span data-stu-id="416f9-147">From the drop-down list, select **Interact**.</span></span>|  
    |<span data-ttu-id="416f9-148">**推送会话**</span><span class="sxs-lookup"><span data-stu-id="416f9-148">**Push session**</span></span>|<span data-ttu-id="416f9-149">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-149">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="416f9-150">**恢复模式**</span><span class="sxs-lookup"><span data-stu-id="416f9-150">**Recovery mode**</span></span>|<span data-ttu-id="416f9-151">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="416f9-151">From the drop-down list, select **TRUE**.</span></span>|  
    |<span data-ttu-id="416f9-152">**SNL 终结点**</span><span class="sxs-lookup"><span data-stu-id="416f9-152">**SNL end-point**</span></span>|<span data-ttu-id="416f9-153">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="416f9-153">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="416f9-154">此值应与匹配压降中配置的 SnL 终结点。</span><span class="sxs-lookup"><span data-stu-id="416f9-154">This value should match the SnL endpoint you configured in SAG.</span></span>|  
  
8.  <span data-ttu-id="416f9-155">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="416f9-155">Click **OK**.</span></span>  
  
9. <span data-ttu-id="416f9-156">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="416f9-156">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="416f9-157">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="416f9-157">**Use this**</span></span>|<span data-ttu-id="416f9-158">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="416f9-158">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="416f9-159">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="416f9-159">**Receive handler**</span></span>|<span data-ttu-id="416f9-160">从下拉列表中选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="416f9-160">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="416f9-161">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="416f9-161">**Receive pipeline**</span></span>|<span data-ttu-id="416f9-162">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="416f9-162">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="416f9-163">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="416f9-163">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="416f9-164">完成步骤</span><span class="sxs-lookup"><span data-stu-id="416f9-164">Complete steps</span></span>
 <span data-ttu-id="416f9-165">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="416f9-165">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="416f9-166">[步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="416f9-166">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="416f9-167">步骤 3C：为 InterAct 存储和转发方案添加 FILE 发送端口以捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="416f9-167">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  
 [<span data-ttu-id="416f9-168">步骤 3D：为 InterAct 存储和转发方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="416f9-168">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario.md)