---
title: 步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59780635-e1b6-4e74-a89a-73ec26d6c670
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f5bb27dc2ff57df0a821cc64e3f26349c278601
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365662"
---
# <a name="step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario"></a><span data-ttu-id="60635-102">步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="60635-102">Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="60635-103">完整[步骤 3A:将文件接收位置添加交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="60635-103">Complete [Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-receive-location"></a><span data-ttu-id="60635-104">添加 INTERACT 接收位置</span><span class="sxs-lookup"><span data-stu-id="60635-104">Add an INTERACT receive location</span></span>  
  
1.  <span data-ttu-id="60635-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="60635-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="60635-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的接收端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="60635-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a receive port.</span></span>  
  
3.  <span data-ttu-id="60635-107">右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口。**</span><span class="sxs-lookup"><span data-stu-id="60635-107">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Port.**</span></span>  
  
4.  <span data-ttu-id="60635-108">在中**接收端口属性**窗口中，命名的接收端口， **Tutorial_IA_HandleRequestOneWay_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="60635-108">In the **Receive Port Properties** window, name the receive port, **Tutorial_IA_HandleRequestOneWay_RealTime**.</span></span>  
  
5.  <span data-ttu-id="60635-109">在中**接收端口属性**窗口，然后在**接收位置**选项卡上，单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="60635-109">In the **Receive Port Properties** window, on the **Receive Locations** tab, click **New**.</span></span>  
  
6.  <span data-ttu-id="60635-110">在中**接收位置属性**窗口，然后在**常规**选项卡上，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="60635-110">In the **Receive Location Properties** window, on the **General** tab, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
7.  <span data-ttu-id="60635-111">在中**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="60635-111">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="60635-112">**使用此**</span><span class="sxs-lookup"><span data-stu-id="60635-112">**Use this**</span></span>|<span data-ttu-id="60635-113">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="60635-113">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="60635-114">**密码**</span><span class="sxs-lookup"><span data-stu-id="60635-114">**Password**</span></span>|<span data-ttu-id="60635-115">键入用于连接到压降的密码。</span><span class="sxs-lookup"><span data-stu-id="60635-115">Type the password you use to connect to SAG.</span></span> <span data-ttu-id="60635-116">有关详细信息，请参阅压降帮助。</span><span class="sxs-lookup"><span data-stu-id="60635-116">See SAG Help for more information.</span></span>|  
    |<span data-ttu-id="60635-117">**用户名**</span><span class="sxs-lookup"><span data-stu-id="60635-117">**User name**</span></span>|<span data-ttu-id="60635-118">键入用于连接到压降的用户名。</span><span class="sxs-lookup"><span data-stu-id="60635-118">Type the user name you use to connect to SAG.</span></span>|  
    |<span data-ttu-id="60635-119">**应用程序名称**</span><span class="sxs-lookup"><span data-stu-id="60635-119">**Application name**</span></span>|<span data-ttu-id="60635-120">键入的服务器\<*应用程序接口名称*\>为压降框路由组。</span><span class="sxs-lookup"><span data-stu-id="60635-120">Type the Server \<*Application Interface Name*\> for the SAG box routing set.</span></span>|  
    |<span data-ttu-id="60635-121">**加密模式**</span><span class="sxs-lookup"><span data-stu-id="60635-121">**Crypto Mode**</span></span>|<span data-ttu-id="60635-122">从下拉列表中，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="60635-122">From the drop-down list, select **Advanced**.</span></span>|  
    |<span data-ttu-id="60635-123">**LogMessageBody**</span><span class="sxs-lookup"><span data-stu-id="60635-123">**LogMessageBody**</span></span>|<span data-ttu-id="60635-124">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="60635-124">From the drop-down list, select **FALSE**.</span></span> <span data-ttu-id="60635-125">**注意：** 如果设置为 TRUE 时，它将保留消息正文跟踪数据库中。</span><span class="sxs-lookup"><span data-stu-id="60635-125">**Note:**  If you set to TRUE, it preserves the message body in the tracking database.</span></span> <span data-ttu-id="60635-126">但是，出于安全原因，消息正文可以永远不会查看 BAM 门户中。</span><span class="sxs-lookup"><span data-stu-id="60635-126">However, for security reasons, the message body can never be viewed in the BAM portal.</span></span>|  
    |<span data-ttu-id="60635-127">**LogMessages**</span><span class="sxs-lookup"><span data-stu-id="60635-127">**LogMessages**</span></span>|<span data-ttu-id="60635-128">从下拉列表中，选择 **，则返回 TRUE**。</span><span class="sxs-lookup"><span data-stu-id="60635-128">From the drop-down list, select **TRUE**.</span></span> <span data-ttu-id="60635-129">这样，要捕获和跟踪在 BAM 门户中的消息事件。</span><span class="sxs-lookup"><span data-stu-id="60635-129">This enables the message events to be captured and tracked in the BAM portal.</span></span>|  
    |<span data-ttu-id="60635-130">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="60635-130">**Message format**</span></span>|<span data-ttu-id="60635-131">从下拉列表中，选择**InterActMessage**。</span><span class="sxs-lookup"><span data-stu-id="60635-131">From the drop-down list, select **InterActMessage**.</span></span>|  
    |<span data-ttu-id="60635-132">**MemberRef**</span><span class="sxs-lookup"><span data-stu-id="60635-132">**MemberRef**</span></span>|<span data-ttu-id="60635-133">从下拉列表中，选择**ResponseHeader**。</span><span class="sxs-lookup"><span data-stu-id="60635-133">From the drop-down list, select **ResponseHeader**.</span></span>|  
    |<span data-ttu-id="60635-134">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="60635-134">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="60635-135">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="60635-135">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="60635-136">**响应方**</span><span class="sxs-lookup"><span data-stu-id="60635-136">**Responder**</span></span>|<span data-ttu-id="60635-137">键入适当\< *ResponderDN* \>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="60635-137">Type the appropriate \<*ResponderDN*\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="60635-138">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="60635-138">**ResponseCrypto**</span></span>|<span data-ttu-id="60635-139">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="60635-139">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="60635-140">**超时**</span><span class="sxs-lookup"><span data-stu-id="60635-140">**Timeout**</span></span>|<span data-ttu-id="60635-141">应会出现类适当的连接超时之前等待的秒数。</span><span class="sxs-lookup"><span data-stu-id="60635-141">Type an appropriate number of seconds before connection timeout should occur.</span></span>|  
    |<span data-ttu-id="60635-142">**获取队列**</span><span class="sxs-lookup"><span data-stu-id="60635-142">**Acquire queue**</span></span>|<span data-ttu-id="60635-143">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-143">Leave the default value for this property.</span></span> <span data-ttu-id="60635-144">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-144">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="60635-145">**ForceAcquire**</span><span class="sxs-lookup"><span data-stu-id="60635-145">**ForceAcquire**</span></span>|<span data-ttu-id="60635-146">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-146">Leave the default value for this property.</span></span> <span data-ttu-id="60635-147">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-147">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="60635-148">**排序依据**</span><span class="sxs-lookup"><span data-stu-id="60635-148">**Order by**</span></span>|<span data-ttu-id="60635-149">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-149">Leave the default value for this property.</span></span> <span data-ttu-id="60635-150">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-150">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="60635-151">**推送会话**</span><span class="sxs-lookup"><span data-stu-id="60635-151">**Push session**</span></span>|<span data-ttu-id="60635-152">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-152">Leave the default value for this property.</span></span> <span data-ttu-id="60635-153">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-153">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="60635-154">**恢复模式**</span><span class="sxs-lookup"><span data-stu-id="60635-154">**Recovery mode**</span></span>|<span data-ttu-id="60635-155">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-155">Leave the default value for this property.</span></span> <span data-ttu-id="60635-156">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-156">This property is used for Store-and-Forward scenarios.</span></span>|  
    |<span data-ttu-id="60635-157">**SNL 终结点**</span><span class="sxs-lookup"><span data-stu-id="60635-157">**SNL end-point**</span></span>|<span data-ttu-id="60635-158">保留此属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="60635-158">Leave the default value for this property.</span></span> <span data-ttu-id="60635-159">此属性用于存储和转发方案。</span><span class="sxs-lookup"><span data-stu-id="60635-159">This property is used for Store-and-Forward scenarios.</span></span>|  
  
8.  <span data-ttu-id="60635-160">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="60635-160">Click **OK**.</span></span>  
  
9. <span data-ttu-id="60635-161">在中**接收位置属性**窗口，然后在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="60635-161">In the **Receive Location Properties** window, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="60635-162">**使用此**</span><span class="sxs-lookup"><span data-stu-id="60635-162">**Use this**</span></span>|<span data-ttu-id="60635-163">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="60635-163">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="60635-164">**接收处理程序**</span><span class="sxs-lookup"><span data-stu-id="60635-164">**Receive handler**</span></span>|<span data-ttu-id="60635-165">从下拉列表中，选择**BizTalkServerIsolatedHost**。</span><span class="sxs-lookup"><span data-stu-id="60635-165">From the drop-down list, select **BizTalkServerIsolatedHost**.</span></span>|  
    |<span data-ttu-id="60635-166">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="60635-166">**Receive pipeline**</span></span>|<span data-ttu-id="60635-167">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="60635-167">From the drop-down list, select **XMLReceive**.</span></span>|  
  
10. <span data-ttu-id="60635-168">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="60635-168">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60635-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="60635-169">See Also</span></span>  
 <span data-ttu-id="60635-170">[步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="60635-170">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="60635-171">[步骤 3a:添加 FILE 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="60635-171">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="60635-172">[步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="60635-172">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="60635-173">[步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span><span class="sxs-lookup"><span data-stu-id="60635-173">[Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) </span></span>  
 [<span data-ttu-id="60635-174">步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="60635-174">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario.md)