---
title: 步骤 3D:为 InterAct 存储和转发方案添加 INTERACT 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd126d9a-f4e4-429e-bab0-8b4c9c555e36
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55dcfb21444cfdd38faf6e9100d9ff4c9307450b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365542"
---
# <a name="step-3d-add-an-interact-send-port-for-the-interact-store-and-forward-scenario"></a><span data-ttu-id="5e1ff-102">步骤 3D:为 InterAct 存储和转发方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="5e1ff-102">Step 3D: Add an INTERACT Send Port for the InterAct Store and Forward Scenario</span></span>
<span data-ttu-id="5e1ff-103">完整[步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)开始此步骤之前。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-103">Complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md) before you begin this step.</span></span>
  
## <a name="add-an-interact-send-port"></a><span data-ttu-id="5e1ff-104">添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="5e1ff-104">Add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="5e1ff-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5e1ff-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="5e1ff-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="5e1ff-108">在中**发送端口属性**窗口中，命名该发送端口，Tutorial_IA_SendRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-108">In the **Send Port Properties** window, name the send port, Tutorial_IA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="5e1ff-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="5e1ff-110">在中**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e1ff-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="5e1ff-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-111">**Use this**</span></span>|<span data-ttu-id="5e1ff-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5e1ff-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-113">**Password**</span></span>|<span data-ttu-id="5e1ff-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5e1ff-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-115">**User name**</span></span>|<span data-ttu-id="5e1ff-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="5e1ff-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-117">**Message format**</span></span>|<span data-ttu-id="5e1ff-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="5e1ff-119">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="5e1ff-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-120">**FALSE**</span></span>|  
    |<span data-ttu-id="5e1ff-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-121">**Request Type**</span></span>|<span data-ttu-id="5e1ff-122">键入适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5e1ff-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-123">**ResponseCrypto**</span></span>|<span data-ttu-id="5e1ff-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-124">**FALSE**</span></span>|  
    |<span data-ttu-id="5e1ff-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-125">**Requestor**</span></span>|<span data-ttu-id="5e1ff-126">键入适当\<RequestorDN\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5e1ff-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-127">**Responder**</span></span>|<span data-ttu-id="5e1ff-128">键入适当\<ResponderDN\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5e1ff-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-129">**Service Name**</span></span>|<span data-ttu-id="5e1ff-130">键入适当\<服务名称\>、 根据使用 SWIFT 应用预配。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="5e1ff-131">**送达通知**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-131">**Delivery Notification**</span></span>|<span data-ttu-id="5e1ff-132">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="5e1ff-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-133">**Notify queue**</span></span>|<span data-ttu-id="5e1ff-134">键入相应的队列名称，根据你使用 SWIFT 预配。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="5e1ff-135">如果只传输有效负载，设置为"有效负载"，在交互 MessageFormat 接收端口和 INTERACT 发送端口。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="5e1ff-136">将接收和发送管道设置为 PassThru。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="5e1ff-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="5e1ff-138">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e1ff-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="5e1ff-139">**使用此**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-139">**Use this**</span></span>|<span data-ttu-id="5e1ff-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5e1ff-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-141">**Send handler**</span></span>|<span data-ttu-id="5e1ff-142">从下拉列表中，选择交互主机。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="5e1ff-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-143">**Send pipeline**</span></span>|<span data-ttu-id="5e1ff-144">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="5e1ff-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-145">**Receive pipeline**</span></span>|<span data-ttu-id="5e1ff-146">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="5e1ff-147">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5e1ff-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="5e1ff-148">**使用此**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-148">**Use this**</span></span>|<span data-ttu-id="5e1ff-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="5e1ff-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-150">**Property**</span></span>|<span data-ttu-id="5e1ff-151">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="5e1ff-152">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-152">**Operator**</span></span>|<span data-ttu-id="5e1ff-153">从下拉列表中，选择**==**。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="5e1ff-154">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-154">**Value**</span></span>|<span data-ttu-id="5e1ff-155">类型 Tutorial_IA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-155">Type Tutorial_IA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="5e1ff-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="5e1ff-156">**Group by**</span></span>|<span data-ttu-id="5e1ff-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="5e1ff-158">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="5e1ff-158">Click **OK**.</span></span>  
  
## <a name="complete-steps"></a><span data-ttu-id="5e1ff-159">完成的步骤</span><span class="sxs-lookup"><span data-stu-id="5e1ff-159">Complete steps</span></span>
 <span data-ttu-id="5e1ff-160">[步骤 3：创建发送端口和接收端口为 InterAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5e1ff-160">[Step 3: Create Send Ports and Receive Ports for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-and-receive-ports-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="5e1ff-161">[步骤 3a:为 InterAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5e1ff-161">[Step 3A: Add a FILE Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="5e1ff-162">[步骤 3b:为 InterAct 存储和转发方案添加 INTERACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="5e1ff-162">[Step 3B: Add an INTERACT Receive Location for the InterAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-interact-receive-location-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="5e1ff-163">步骤 3c:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="5e1ff-163">Step 3C: Add a FILE Send Port to Capture the Sw:HandleRequest Message for the InterAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-interact-store-and-forward.md)  