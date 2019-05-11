---
title: 步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9503976d47f70a0077b5a30598d5daa826855e1e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365466"
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="22f11-102">步骤 3E:添加 INTERACT 发送端口为 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="22f11-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="22f11-103">完整[步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="22f11-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="22f11-104">添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="22f11-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="22f11-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="22f11-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="22f11-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="22f11-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="22f11-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="22f11-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="22f11-108">在中**发送端口属性**窗口中，命名发送端口**Tutorial_IA_SendRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="22f11-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="22f11-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="22f11-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="22f11-110">在中**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22f11-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="22f11-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="22f11-111">**Use this**</span></span>|<span data-ttu-id="22f11-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="22f11-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="22f11-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="22f11-113">**Password**</span></span>|<span data-ttu-id="22f11-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="22f11-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="22f11-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="22f11-115">**User name**</span></span>|<span data-ttu-id="22f11-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="22f11-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="22f11-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="22f11-117">**Adapter Mode**</span></span>|<span data-ttu-id="22f11-118">从下拉列表中，选择**实时**。</span><span class="sxs-lookup"><span data-stu-id="22f11-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="22f11-119">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="22f11-119">**Message format**</span></span>|<span data-ttu-id="22f11-120">**InteractMessage**。</span><span class="sxs-lookup"><span data-stu-id="22f11-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="22f11-121">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="22f11-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="22f11-122">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="22f11-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="22f11-123">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="22f11-123">**Request Type**</span></span>|<span data-ttu-id="22f11-124">键入适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="22f11-124">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="22f11-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="22f11-125">**ResponseCrypto**</span></span>|<span data-ttu-id="22f11-126">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="22f11-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="22f11-127">**请求者**</span><span class="sxs-lookup"><span data-stu-id="22f11-127">**Requestor**</span></span>|<span data-ttu-id="22f11-128">将其设置为适当\<请求程序\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="22f11-128">Set it to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="22f11-129">**响应方**</span><span class="sxs-lookup"><span data-stu-id="22f11-129">**Responder**</span></span>|<span data-ttu-id="22f11-130">将其设置为适当\<响应方\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="22f11-130">Set it to the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="22f11-131">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="22f11-131">**Service Name**</span></span>|<span data-ttu-id="22f11-132">将其设置为适当\<服务名称\>、 根据使用 SWIFT 应用预配。</span><span class="sxs-lookup"><span data-stu-id="22f11-132">Set it to the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="22f11-133">**送达通知**</span><span class="sxs-lookup"><span data-stu-id="22f11-133">**Delivery Notification**</span></span>|<span data-ttu-id="22f11-134">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="22f11-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="22f11-135">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="22f11-135">**Notify queue**</span></span>|<span data-ttu-id="22f11-136">键入相应的队列名称，根据你使用 SWIFT 预配。</span><span class="sxs-lookup"><span data-stu-id="22f11-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="22f11-137">如果只传输有效负载，集到交互"Payloadonly"MessageFormat 接收端口和 INTERACT 发送端口。</span><span class="sxs-lookup"><span data-stu-id="22f11-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="22f11-138">设置接收并向 PassThru 发送管道。</span><span class="sxs-lookup"><span data-stu-id="22f11-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="22f11-139">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="22f11-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="22f11-140">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22f11-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="22f11-141">**使用此**</span><span class="sxs-lookup"><span data-stu-id="22f11-141">**Use this**</span></span>|<span data-ttu-id="22f11-142">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="22f11-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="22f11-143">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="22f11-143">**Send handler**</span></span>|<span data-ttu-id="22f11-144">从下拉列表中，选择交互主机。</span><span class="sxs-lookup"><span data-stu-id="22f11-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="22f11-145">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="22f11-145">**Send pipeline**</span></span>|<span data-ttu-id="22f11-146">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="22f11-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="22f11-147">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="22f11-147">**Receive pipeline**</span></span>|<span data-ttu-id="22f11-148">**XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="22f11-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="22f11-149">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="22f11-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="22f11-150">**使用此**</span><span class="sxs-lookup"><span data-stu-id="22f11-150">**Use this**</span></span>|<span data-ttu-id="22f11-151">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="22f11-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="22f11-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="22f11-152">**Property**</span></span>|<span data-ttu-id="22f11-153">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="22f11-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="22f11-154">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="22f11-154">**Operator**</span></span>|<span data-ttu-id="22f11-155">从下拉列表中，选择**==**。</span><span class="sxs-lookup"><span data-stu-id="22f11-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="22f11-156">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="22f11-156">**Value**</span></span>|<span data-ttu-id="22f11-157">类型**Tutorial_IA_InputRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="22f11-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="22f11-158">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="22f11-158">**Group by**</span></span>|<span data-ttu-id="22f11-159">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="22f11-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="22f11-160">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="22f11-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f11-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="22f11-161">See Also</span></span>  
 <span data-ttu-id="22f11-162">[步骤 3：创建发送和接收端口 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="22f11-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="22f11-163">[步骤 3a:添加 FILE 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="22f11-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="22f11-164">[步骤 3b:添加 INTERACT 接收位置 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="22f11-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="22f11-165">[步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="22f11-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="22f11-166">步骤 3D:添加 FILE 发送端口以捕获 sw: handleresponse 消息为 InterAct 实时方案</span><span class="sxs-lookup"><span data-stu-id="22f11-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)