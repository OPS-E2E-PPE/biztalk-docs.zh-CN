---
title: "步骤 3B： 添加交互接收位置交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 59780635-e1b6-4e74-a89a-73ec26d6c670
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9912e47f56dcf9c8ccc42af944616858ec9b93fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="7c16f-102">步骤 3B： 添加交互接收位置交互实时方案</span><span class="sxs-lookup"><span data-stu-id="7c16f-102">Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="7c16f-103">完成[步骤 3A： 对于交互的实时方案中添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="7c16f-103">Complete [Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-receive-location"></a><span data-ttu-id="7c16f-104">添加交互接收位置</span><span class="sxs-lookup"><span data-stu-id="7c16f-104">Add an INTERACT receive location</span></span>  
  
1.  <span data-ttu-id="7c16f-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="7c16f-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建接收端口 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7c16f-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="7c16f-107">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="7c16f-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="7c16f-108">在**接收端口属性**窗口中，名称接收端口， **Tutorial_IA_HandleRequestOneWay_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_HandleRequestOneWay_RealTime**.</span></span>  
  
5.  <span data-ttu-id="7c16f-109">在**接收端口属性**窗口，请在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="7c16f-110">在**接收位置属性**窗口，请在**常规**选项卡上，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="7c16f-111">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7c16f-111">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="7c16f-112">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="7c16f-112">**Use this**</span></span>|<span data-ttu-id="7c16f-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="7c16f-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7c16f-114">**密码**</span><span class="sxs-lookup"><span data-stu-id="7c16f-114">**Password**</span></span>|<span data-ttu-id="7c16f-115">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="7c16f-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="7c16f-116">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="7c16f-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="7c16f-117">**用户名**</span><span class="sxs-lookup"><span data-stu-id="7c16f-117">**User name**</span></span>|<span data-ttu-id="7c16f-118">键入用于连接到压降的用户名称。</span><span class="sxs-lookup"><span data-stu-id="7c16f-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="7c16f-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="7c16f-119">**Application name**</span></span>|<span data-ttu-id="7c16f-120">键入的服务器\<*应用程序接口名称*> 压降框中路由组。</span><span class="sxs-lookup"><span data-stu-id="7c16f-120">Type the Server \<*Application Interface Name*> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="7c16f-121">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="7c16f-121">**Crypto Mode**</span></span>|<span data-ttu-id="7c16f-122">从下拉列表中选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="7c16f-123">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="7c16f-123">**LogMessageBody**</span></span>|<span data-ttu-id="7c16f-124">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-124">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="7c16f-125">**注意：**如果设置为 TRUE 时，它将保留跟踪数据库的消息正文。</span><span class="sxs-lookup"><span data-stu-id="7c16f-125">**Note:**  If you set to TRUE, it preserves the message body in the tracking database.</span></span> <span data-ttu-id="7c16f-126">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="7c16f-126">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="7c16f-127">**日志消息**</span><span class="sxs-lookup"><span data-stu-id="7c16f-127">**LogMessages**</span></span>|<span data-ttu-id="7c16f-128">从下拉列表中选择**TRUE**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-128">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="7c16f-129">这样将捕获和 BAM 门户中跟踪消息事件。</span><span class="sxs-lookup"><span data-stu-id="7c16f-129">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="7c16f-130">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="7c16f-130">**Message format**</span></span>|<span data-ttu-id="7c16f-131">从下拉列表中选择**InterActMessage**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-131">From the drop-down list, select **InterActMessage**.</span></span>|  
    |<span data-ttu-id="7c16f-132">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="7c16f-132">**MemberRef**</span></span>|<span data-ttu-id="7c16f-133">从下拉列表中选择**ResponseHeader**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-133">From the drop-down list, select **ResponseHeader**.</span></span>|  
    |<span data-ttu-id="7c16f-134">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="7c16f-134">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="7c16f-135">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="7c16f-136">**响应方**</span><span class="sxs-lookup"><span data-stu-id="7c16f-136">**Responder**</span></span>|<span data-ttu-id="7c16f-137">键入相应\< *ResponderDN*> 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="7c16f-137">Type the appropriate \<*ResponderDN*> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="7c16f-138">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="7c16f-138">**ResponseCrypto**</span></span>|<span data-ttu-id="7c16f-139">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-139">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="7c16f-140">**超时**</span><span class="sxs-lookup"><span data-stu-id="7c16f-140">**Timeout**</span></span>|<span data-ttu-id="7c16f-141">应发生类型适当数量的连接超时前的秒数。</span><span class="sxs-lookup"><span data-stu-id="7c16f-141">Type an appropriate number of seconds before connection timeout should occur.</span></span>|  
    |<span data-ttu-id="7c16f-142">**获取队列**</span><span class="sxs-lookup"><span data-stu-id="7c16f-142">**Acquire queue**</span></span>|<span data-ttu-id="7c16f-143">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-143">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-144">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-144">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="7c16f-145">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="7c16f-145">**ForceAcquire**</span></span>|<span data-ttu-id="7c16f-146">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-146">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-147">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-147">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="7c16f-148">**排序依据**</span><span class="sxs-lookup"><span data-stu-id="7c16f-148">**Order by**</span></span>|<span data-ttu-id="7c16f-149">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-149">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-150">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-150">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="7c16f-151">**推送会话**</span><span class="sxs-lookup"><span data-stu-id="7c16f-151">**Push session**</span></span>|<span data-ttu-id="7c16f-152">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-152">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-153">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-153">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="7c16f-154">**恢复模式**</span><span class="sxs-lookup"><span data-stu-id="7c16f-154">**Recovery mode**</span></span>|<span data-ttu-id="7c16f-155">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-155">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-156">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-156">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="7c16f-157">**SNL 终结点**</span><span class="sxs-lookup"><span data-stu-id="7c16f-157">**SNL end-point**</span></span>|<span data-ttu-id="7c16f-158">将此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="7c16f-158">Leave the default value for this property.</span></span> <span data-ttu-id="7c16f-159">此属性用于存储转发方案。</span><span class="sxs-lookup"><span data-stu-id="7c16f-159">This property is used for Store-and-Forward scenarios.</span></span>|  
  
8.  <span data-ttu-id="7c16f-160">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-160">Click **OK**.</span></span>  
  
9. <span data-ttu-id="7c16f-161">在**接收位置属性**窗口，请在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7c16f-161">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="7c16f-162">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="7c16f-162">**Use this**</span></span>|<span data-ttu-id="7c16f-163">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="7c16f-163">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="7c16f-164">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="7c16f-164">**Receive handler**</span></span>|<span data-ttu-id="7c16f-165">从下拉列表中选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-165">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="7c16f-166">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="7c16f-166">**Receive pipeline**</span></span>|<span data-ttu-id="7c16f-167">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-167">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="7c16f-168">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7c16f-168">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c16f-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c16f-169">See Also</span></span>  
 <span data-ttu-id="7c16f-170">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7c16f-170">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="7c16f-171">[步骤 3A： 添加一个文件接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7c16f-171">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="7c16f-172">[步骤 3c： 添加要捕获的 Sw:HandleRequest 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="7c16f-172">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="7c16f-173">[步骤 3D： 添加要捕获的 Sw:HandleResponse 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="7c16f-173">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="7c16f-174">步骤 3E： 添加的交互发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="7c16f-174">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)