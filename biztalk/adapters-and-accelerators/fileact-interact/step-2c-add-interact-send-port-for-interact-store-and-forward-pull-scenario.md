---
title: 步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3373f7653856800c3cb8a64ca07afe88eb86d192
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366104"
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="3bd1d-102">步骤 2c:为 InterAct 存储和转发 （拉取） 方案添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="3bd1d-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="3bd1d-103">在开始此步骤之前，必须完成[步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="3bd1d-104">若要添加 INTERACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="3bd1d-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="3bd1d-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3bd1d-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="3bd1d-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="3bd1d-108">在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_IA_SendRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="3bd1d-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**INTERACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="3bd1d-110">在中**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3bd1d-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="3bd1d-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-111">**Use this**</span></span>|<span data-ttu-id="3bd1d-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3bd1d-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-113">**Password**</span></span>|<span data-ttu-id="3bd1d-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3bd1d-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-115">**User name**</span></span>|<span data-ttu-id="3bd1d-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3bd1d-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-117">**Message format**</span></span>|<span data-ttu-id="3bd1d-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="3bd1d-119">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="3bd1d-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-120">**FALSE**</span></span>|  
    |<span data-ttu-id="3bd1d-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-121">**Request Type**</span></span>|<span data-ttu-id="3bd1d-122">键入适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3bd1d-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-123">**ResponseCrypto**</span></span>|<span data-ttu-id="3bd1d-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-124">**FALSE**</span></span>|  
    |<span data-ttu-id="3bd1d-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-125">**Requestor**</span></span>|<span data-ttu-id="3bd1d-126">键入适当\<RequestorDN\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3bd1d-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-127">**Responder**</span></span>|<span data-ttu-id="3bd1d-128">键入适当\<ResponderDN\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3bd1d-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-129">**Service Name**</span></span>|<span data-ttu-id="3bd1d-130">键入适当\<服务名称\>、 根据使用 SWIFT 应用预配。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3bd1d-131">**送达通知**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-131">**Delivery Notification**</span></span>|<span data-ttu-id="3bd1d-132">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3bd1d-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-133">**Notify queue**</span></span>|<span data-ttu-id="3bd1d-134">键入相应的队列名称，根据你使用 SWIFT 预配。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="3bd1d-135">如果只传输有效负载，设置为"有效负载"，在交互 MessageFormat 接收端口和 INTERACT 发送端口。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="3bd1d-136">将接收和发送管道设置为 PassThru。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="3bd1d-137">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3bd1d-138">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3bd1d-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="3bd1d-139">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-139">**Use this**</span></span>|<span data-ttu-id="3bd1d-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3bd1d-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-141">**Send handler**</span></span>|<span data-ttu-id="3bd1d-142">从下拉列表中，选择交互主机。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="3bd1d-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-143">**Send pipeline**</span></span>|<span data-ttu-id="3bd1d-144">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="3bd1d-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-145">**Receive pipeline**</span></span>|<span data-ttu-id="3bd1d-146">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="3bd1d-147">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3bd1d-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3bd1d-148">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-148">**Use this**</span></span>|<span data-ttu-id="3bd1d-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3bd1d-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-150">**Property**</span></span>|<span data-ttu-id="3bd1d-151">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="3bd1d-152">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-152">**Operator**</span></span>|<span data-ttu-id="3bd1d-153">从下拉列表中，选择**==**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="3bd1d-154">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-154">**Value**</span></span>|<span data-ttu-id="3bd1d-155">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="3bd1d-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="3bd1d-156">**Group by**</span></span>|<span data-ttu-id="3bd1d-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="3bd1d-158">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3bd1d-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bd1d-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bd1d-159">See Also</span></span>  
 <span data-ttu-id="3bd1d-160">[步骤 2A:为 InterAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3bd1d-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="3bd1d-161">步骤 2B:添加 FILE 发送端口以捕获 sw: handlerequest 消息为 InterAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="3bd1d-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)