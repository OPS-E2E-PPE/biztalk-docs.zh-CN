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
ms.openlocfilehash: 7ac1d379f2e68431f197f2db339cd0ac9f50c92e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="08067-102">步骤 3D： 交互应用商店应用和向前情况下添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="08067-102">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="08067-103">完成[步骤 3c： 将文件发送端口捕获 Sw:HandleRequest 消息交互，应用商店应用和转发方案添加](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)在开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="08067-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="08067-104">添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="08067-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="08067-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="08067-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="08067-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="08067-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="08067-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="08067-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="08067-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_IA_SendRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="08067-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="08067-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="08067-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="08067-110">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08067-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="08067-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="08067-111">**Use this**</span></span>|<span data-ttu-id="08067-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="08067-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="08067-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="08067-113">**Password**</span></span>|<span data-ttu-id="08067-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="08067-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="08067-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="08067-115">**User name**</span></span>|<span data-ttu-id="08067-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="08067-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="08067-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="08067-117">**Message format**</span></span>|<span data-ttu-id="08067-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="08067-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="08067-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="08067-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="08067-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="08067-120">**FALSE**</span></span>|  
    |<span data-ttu-id="08067-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="08067-121">**Request Type**</span></span>|<span data-ttu-id="08067-122">键入相应\<RequestType > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="08067-122">Type the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="08067-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="08067-123">**ResponseCrypto**</span></span>|<span data-ttu-id="08067-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="08067-124">**FALSE**</span></span>|  
    |<span data-ttu-id="08067-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="08067-125">**Requestor**</span></span>|<span data-ttu-id="08067-126">键入相应\<RequestorDN > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="08067-126">Type the appropriate \<RequestorDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="08067-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="08067-127">**Responder**</span></span>|<span data-ttu-id="08067-128">键入相应\<ResponderDN > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="08067-128">Type the appropriate \<ResponderDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="08067-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="08067-129">**Service Name**</span></span>|<span data-ttu-id="08067-130">键入相应\<服务名称 >，将根据 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="08067-130">Type the appropriate \<service name>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="08067-131">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="08067-131">**Delivery Notification**</span></span>|<span data-ttu-id="08067-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="08067-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="08067-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="08067-133">**Notify queue**</span></span>|<span data-ttu-id="08067-134">键入相应的队列名称，基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="08067-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="08067-135">如果只传输负载，设置到交互中的"负载"MessageFormat receive 端口和交互发送端口。</span><span class="sxs-lookup"><span data-stu-id="08067-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="08067-136">设置为 PassThru 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="08067-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="08067-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="08067-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="08067-138">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08067-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="08067-139">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="08067-139">**Use this**</span></span>|<span data-ttu-id="08067-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="08067-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="08067-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="08067-141">**Send handler**</span></span>|<span data-ttu-id="08067-142">从下拉列表中，选择的交互主机。</span><span class="sxs-lookup"><span data-stu-id="08067-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="08067-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="08067-143">**Send pipeline**</span></span>|<span data-ttu-id="08067-144">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="08067-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="08067-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="08067-145">**Receive pipeline**</span></span>|<span data-ttu-id="08067-146">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="08067-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="08067-147">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="08067-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="08067-148">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="08067-148">**Use this**</span></span>|<span data-ttu-id="08067-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="08067-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="08067-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="08067-150">**Property**</span></span>|<span data-ttu-id="08067-151">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="08067-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="08067-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="08067-152">**Operator**</span></span>|<span data-ttu-id="08067-153">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="08067-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="08067-154">**值**</span><span class="sxs-lookup"><span data-stu-id="08067-154">**Value**</span></span>|<span data-ttu-id="08067-155">类型 Tutorial_IA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="08067-155">Type Tutorial_IA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="08067-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="08067-156">**Group by**</span></span>|<span data-ttu-id="08067-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="08067-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="08067-158">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="08067-158">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="08067-159">完成步骤</span><span class="sxs-lookup"><span data-stu-id="08067-159">Complete steps</span></span>
 <span data-ttu-id="08067-160">[步骤 3： 创建发送端口和交互应用商店应用和向前情况下接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="08067-160">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="08067-161">[步骤 3A： 添加一个文件接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="08067-161">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="08067-162">[步骤 3B： 添加交互接收交互应用商店应用和向前情况下的位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="08067-162">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="08067-163">步骤 3c： 添加文件发送端口交互应用商店应用和向前情况下捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="08067-163">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  