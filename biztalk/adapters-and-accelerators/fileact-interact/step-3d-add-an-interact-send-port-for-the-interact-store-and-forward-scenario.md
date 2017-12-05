---
title: "步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11b4e17a4435c5d9e6e99cd3ed471fa8819923e8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="fdc62-102">步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="fdc62-102">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="fdc62-103">完成[步骤 3c： 将文件发送端口捕获 Sw:HandleRequest 消息交互，应用商店应用和转发方案添加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="fdc62-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="fdc62-104">添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="fdc62-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="fdc62-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="fdc62-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdc62-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="fdc62-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="fdc62-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_IA_SendRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="fdc62-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="fdc62-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="fdc62-110">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fdc62-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="fdc62-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="fdc62-111">**Use this**</span></span>|<span data-ttu-id="fdc62-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fdc62-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fdc62-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="fdc62-113">**Password**</span></span>|<span data-ttu-id="fdc62-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="fdc62-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="fdc62-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="fdc62-115">**User name**</span></span>|<span data-ttu-id="fdc62-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="fdc62-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="fdc62-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="fdc62-117">**Message format**</span></span>|<span data-ttu-id="fdc62-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="fdc62-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="fdc62-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="fdc62-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="fdc62-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="fdc62-120">**FALSE**</span></span>|  
    |<span data-ttu-id="fdc62-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="fdc62-121">**Request Type**</span></span>|<span data-ttu-id="fdc62-122">键入相应\<RequestType\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="fdc62-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="fdc62-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="fdc62-123">**ResponseCrypto**</span></span>|<span data-ttu-id="fdc62-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="fdc62-124">**FALSE**</span></span>|  
    |<span data-ttu-id="fdc62-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="fdc62-125">**Requestor**</span></span>|<span data-ttu-id="fdc62-126">键入相应\<RequestorDN\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="fdc62-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="fdc62-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="fdc62-127">**Responder**</span></span>|<span data-ttu-id="fdc62-128">键入相应\<ResponderDN\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="fdc62-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="fdc62-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="fdc62-129">**Service Name**</span></span>|<span data-ttu-id="fdc62-130">键入相应\<服务名称\>，具体取决 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="fdc62-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="fdc62-131">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="fdc62-131">**Delivery Notification**</span></span>|<span data-ttu-id="fdc62-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="fdc62-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="fdc62-133">**Notify queue**</span></span>|<span data-ttu-id="fdc62-134">键入相应的队列名称，基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="fdc62-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="fdc62-135">如果只传输负载，设置到交互中的"负载"MessageFormat receive 端口和交互发送端口。</span><span class="sxs-lookup"><span data-stu-id="fdc62-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="fdc62-136">设置为 PassThru 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="fdc62-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="fdc62-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="fdc62-138">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fdc62-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="fdc62-139">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="fdc62-139">**Use this**</span></span>|<span data-ttu-id="fdc62-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fdc62-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fdc62-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="fdc62-141">**Send handler**</span></span>|<span data-ttu-id="fdc62-142">从下拉列表中，选择的交互主机。</span><span class="sxs-lookup"><span data-stu-id="fdc62-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="fdc62-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="fdc62-143">**Send pipeline**</span></span>|<span data-ttu-id="fdc62-144">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="fdc62-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="fdc62-145">**Receive pipeline**</span></span>|<span data-ttu-id="fdc62-146">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="fdc62-147">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fdc62-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="fdc62-148">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="fdc62-148">**Use this**</span></span>|<span data-ttu-id="fdc62-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="fdc62-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="fdc62-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="fdc62-150">**Property**</span></span>|<span data-ttu-id="fdc62-151">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="fdc62-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="fdc62-152">**Operator**</span></span>|<span data-ttu-id="fdc62-153">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="fdc62-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="fdc62-154">**值**</span><span class="sxs-lookup"><span data-stu-id="fdc62-154">**Value**</span></span>|<span data-ttu-id="fdc62-155">类型 Tutorial_IA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="fdc62-155">Type Tutorial_IA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="fdc62-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="fdc62-156">**Group by**</span></span>|<span data-ttu-id="fdc62-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="fdc62-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="fdc62-158">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="fdc62-158">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="fdc62-159">完成步骤</span><span class="sxs-lookup"><span data-stu-id="fdc62-159">Complete steps</span></span>
 <span data-ttu-id="fdc62-160">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="fdc62-160">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="fdc62-161">[步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="fdc62-161">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="fdc62-162">[步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="fdc62-162">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="fdc62-163">步骤 3C：为 InterAct 存储和转发方案添加 FILE 发送端口以捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="fdc62-163">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  