---
title: "步骤 3E： 添加的交互发送端口交互实时方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9522386-e980-4ab1-b65a-939ca7936ad9
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec380c088f27fe09f518c385990e3801b5c019dd
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3e-add-an-interact-send-port-for-the-interact-real-time-scenario"></a><span data-ttu-id="eef58-102">步骤 3E： 添加的交互发送端口交互实时方案</span><span class="sxs-lookup"><span data-stu-id="eef58-102">Step 3E: Add an INTERACT Send Port for the InterAct Real-Time Scenario</span></span>
<span data-ttu-id="eef58-103">完成[步骤 3D： 将文件发送端口交互实时方案捕获 Sw:HandleResponse 消息添加](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="eef58-103">Complete [Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="eef58-104">添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="eef58-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="eef58-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="eef58-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="eef58-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="eef58-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="eef58-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="eef58-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="eef58-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="eef58-108">In the **Send Port Properties** window, name the send port **Tutorial_IA_SendRequest_RealTime**.</span></span>  
  
5.  <span data-ttu-id="eef58-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="eef58-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="eef58-110">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eef58-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="eef58-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="eef58-111">**Use this**</span></span>|<span data-ttu-id="eef58-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="eef58-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="eef58-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="eef58-113">**Password**</span></span>|<span data-ttu-id="eef58-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="eef58-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="eef58-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="eef58-115">**User name**</span></span>|<span data-ttu-id="eef58-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="eef58-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="eef58-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="eef58-117">**Adapter Mode**</span></span>|<span data-ttu-id="eef58-118">从下拉列表中选择**实时**。</span><span class="sxs-lookup"><span data-stu-id="eef58-118">From the drop-down list, select **RealTime**.</span></span>|  
    |<span data-ttu-id="eef58-119">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="eef58-119">**Message format**</span></span>|<span data-ttu-id="eef58-120">**InteractMessage**。</span><span class="sxs-lookup"><span data-stu-id="eef58-120">**InteractMessage**.</span></span>|  
    |<span data-ttu-id="eef58-121">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="eef58-121">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="eef58-122">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="eef58-122">**FALSE**.</span></span>|  
    |<span data-ttu-id="eef58-123">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="eef58-123">**Request Type**</span></span>|<span data-ttu-id="eef58-124">键入相应\<RequestType\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="eef58-124">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="eef58-125">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="eef58-125">**ResponseCrypto**</span></span>|<span data-ttu-id="eef58-126">**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="eef58-126">**FALSE**.</span></span>|  
    |<span data-ttu-id="eef58-127">**请求者**</span><span class="sxs-lookup"><span data-stu-id="eef58-127">**Requestor**</span></span>|<span data-ttu-id="eef58-128">将其设置为相应\<请求者\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="eef58-128">Set it to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="eef58-129">**响应方**</span><span class="sxs-lookup"><span data-stu-id="eef58-129">**Responder**</span></span>|<span data-ttu-id="eef58-130">将其设置为相应\<响应方\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="eef58-130">Set it to the appropriate \<Responder\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="eef58-131">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="eef58-131">**Service Name**</span></span>|<span data-ttu-id="eef58-132">将其设置为相应\<服务名称\>，具体取决 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="eef58-132">Set it to the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="eef58-133">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="eef58-133">**Delivery Notification**</span></span>|<span data-ttu-id="eef58-134">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="eef58-134">From the drop-down list, select  **FALSE**.</span></span>|  
    |<span data-ttu-id="eef58-135">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="eef58-135">**Notify queue**</span></span>|<span data-ttu-id="eef58-136">键入相应的队列名称，基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="eef58-136">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="eef58-137">如果只传输负载，设置到交互中的"Payloadonly"MessageFormat receive 端口和交互发送端口。</span><span class="sxs-lookup"><span data-stu-id="eef58-137">If only payload is to be transferred, set the MessageFormat to “Payloadonly” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="eef58-138">设置接收和发送到 PassThru 的管道。</span><span class="sxs-lookup"><span data-stu-id="eef58-138">Set the receive and send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="eef58-139">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eef58-139">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="eef58-140">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eef58-140">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="eef58-141">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="eef58-141">**Use this**</span></span>|<span data-ttu-id="eef58-142">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="eef58-142">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="eef58-143">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="eef58-143">**Send handler**</span></span>|<span data-ttu-id="eef58-144">从下拉列表中，选择的交互主机。</span><span class="sxs-lookup"><span data-stu-id="eef58-144">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="eef58-145">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="eef58-145">**Send pipeline**</span></span>|<span data-ttu-id="eef58-146">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="eef58-146">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="eef58-147">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="eef58-147">**Receive pipeline**</span></span>|<span data-ttu-id="eef58-148">**XMLReceive**</span><span class="sxs-lookup"><span data-stu-id="eef58-148">**XMLReceive**</span></span>|  
  
9. <span data-ttu-id="eef58-149">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="eef58-149">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="eef58-150">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="eef58-150">**Use this**</span></span>|<span data-ttu-id="eef58-151">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="eef58-151">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="eef58-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="eef58-152">**Property**</span></span>|<span data-ttu-id="eef58-153">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="eef58-153">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="eef58-154">**运算符**</span><span class="sxs-lookup"><span data-stu-id="eef58-154">**Operator**</span></span>|<span data-ttu-id="eef58-155">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="eef58-155">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="eef58-156">**值**</span><span class="sxs-lookup"><span data-stu-id="eef58-156">**Value**</span></span>|<span data-ttu-id="eef58-157">类型**Tutorial_IA_InputRequest_RealTime**。</span><span class="sxs-lookup"><span data-stu-id="eef58-157">Type **Tutorial_IA_InputRequest_RealTime**.</span></span>|  
    |<span data-ttu-id="eef58-158">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="eef58-158">**Group by**</span></span>|<span data-ttu-id="eef58-159">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="eef58-159">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="eef58-160">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="eef58-160">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef58-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eef58-161">See Also</span></span>  
 <span data-ttu-id="eef58-162">[步骤 3： 创建发送和接收端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="eef58-162">[Step 3: Create Send and Receive Ports for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="eef58-163">[步骤 3A： 添加一个文件接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="eef58-163">[Step 3A: Add a FILE Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="eef58-164">[步骤 3B： 添加交互接收位置交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="eef58-164">[Step 3B: Add an INTERACT Receive Location for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-an-interact-receive-location-for-the-interact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="eef58-165">[步骤 3c： 添加要捕获的 Sw:HandleRequest 消息的文件发送端口交互实时方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="eef58-165">[Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="eef58-166">步骤 3D：为 InterAct 实时方案添加 FILE 发送端口以捕获 Sw:HandleResponse 消息</span><span class="sxs-lookup"><span data-stu-id="eef58-166">Step 3D: Add a FILE Send Port to Capture the Sw:HandleResponse Message for the InterAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-file-send-port-to-get-sw-handleresponse-message-for-interact.md)