---
title: "步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57038f77-85c3-4811-ab3d-df6e2da8fbcf
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb46943b20676dbe98f79db8760043bb51606c56
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="18e48-102">步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="18e48-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="18e48-103">在开始此步骤之前，必须完成[步骤 2B： 发送端口添加文件，以捕获 Sw:HandleRequest 消息交互，应用商店应用和向前 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="18e48-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="18e48-104">若要添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="18e48-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="18e48-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="18e48-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="18e48-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="18e48-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="18e48-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="18e48-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="18e48-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="18e48-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="18e48-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="18e48-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="18e48-110">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="18e48-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="18e48-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="18e48-111">**Use this**</span></span>|<span data-ttu-id="18e48-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="18e48-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="18e48-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="18e48-113">**Password**</span></span>|<span data-ttu-id="18e48-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="18e48-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="18e48-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="18e48-115">**User name**</span></span>|<span data-ttu-id="18e48-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="18e48-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="18e48-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="18e48-117">**Message format**</span></span>|<span data-ttu-id="18e48-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="18e48-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="18e48-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="18e48-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="18e48-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="18e48-120">**FALSE**</span></span>|  
    |<span data-ttu-id="18e48-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="18e48-121">**Request Type**</span></span>|<span data-ttu-id="18e48-122">键入相应\<RequestType\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="18e48-122">Type the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="18e48-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="18e48-123">**ResponseCrypto**</span></span>|<span data-ttu-id="18e48-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="18e48-124">**FALSE**</span></span>|  
    |<span data-ttu-id="18e48-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="18e48-125">**Requestor**</span></span>|<span data-ttu-id="18e48-126">键入相应\<RequestorDN\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="18e48-126">Type the appropriate \<RequestorDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="18e48-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="18e48-127">**Responder**</span></span>|<span data-ttu-id="18e48-128">键入相应\<ResponderDN\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="18e48-128">Type the appropriate \<ResponderDN\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="18e48-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="18e48-129">**Service Name**</span></span>|<span data-ttu-id="18e48-130">键入相应\<服务名称\>，具体取决 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="18e48-130">Type the appropriate \<service name\>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="18e48-131">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="18e48-131">**Delivery Notification**</span></span>|<span data-ttu-id="18e48-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="18e48-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="18e48-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="18e48-133">**Notify queue**</span></span>|<span data-ttu-id="18e48-134">键入相应的队列名称，基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="18e48-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="18e48-135">如果只传输负载，设置到交互中的"负载"MessageFormat receive 端口和交互发送端口。</span><span class="sxs-lookup"><span data-stu-id="18e48-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="18e48-136">设置为 PassThru 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="18e48-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="18e48-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="18e48-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="18e48-138">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="18e48-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="18e48-139">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="18e48-139">**Use this**</span></span>|<span data-ttu-id="18e48-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="18e48-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="18e48-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="18e48-141">**Send handler**</span></span>|<span data-ttu-id="18e48-142">从下拉列表中，选择的交互主机。</span><span class="sxs-lookup"><span data-stu-id="18e48-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="18e48-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="18e48-143">**Send pipeline**</span></span>|<span data-ttu-id="18e48-144">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="18e48-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="18e48-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="18e48-145">**Receive pipeline**</span></span>|<span data-ttu-id="18e48-146">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="18e48-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="18e48-147">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="18e48-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="18e48-148">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="18e48-148">**Use this**</span></span>|<span data-ttu-id="18e48-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="18e48-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="18e48-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="18e48-150">**Property**</span></span>|<span data-ttu-id="18e48-151">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="18e48-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="18e48-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="18e48-152">**Operator**</span></span>|<span data-ttu-id="18e48-153">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="18e48-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="18e48-154">**值**</span><span class="sxs-lookup"><span data-stu-id="18e48-154">**Value**</span></span>|<span data-ttu-id="18e48-155">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="18e48-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="18e48-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="18e48-156">**Group by**</span></span>|<span data-ttu-id="18e48-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="18e48-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="18e48-158">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="18e48-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18e48-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="18e48-159">See Also</span></span>  
 <span data-ttu-id="18e48-160">[步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="18e48-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="18e48-161">步骤 2B：为 InterAct 存储和转发（拉取）方案添加 FILE 发送端口以捕获 Sw:HandleRequest 消息</span><span class="sxs-lookup"><span data-stu-id="18e48-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)