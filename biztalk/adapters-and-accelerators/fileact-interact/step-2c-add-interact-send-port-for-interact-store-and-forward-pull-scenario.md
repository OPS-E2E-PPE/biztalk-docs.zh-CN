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
ms.openlocfilehash: e2fe383d80c467376852067026a7c5a4fe4640ba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2c-add-an-interact-send-port-for-the-interact-store-and-forward-pull-scenario"></a><span data-ttu-id="83ea2-102">步骤 2c： 交互应用商店应用和进 （请求） 方案中添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="83ea2-102">Step 2C: Add an INTERACT Send Port for the InterAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="83ea2-103">在开始此步骤之前，必须完成[步骤 2B： 发送端口添加文件，以捕获 Sw:HandleRequest 消息交互，应用商店应用和向前 （请求） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)。</span><span class="sxs-lookup"><span data-stu-id="83ea2-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md).</span></span>  
  
### <a name="to-add-an-interact-send-port"></a><span data-ttu-id="83ea2-104">若要添加交互发送端口</span><span class="sxs-lookup"><span data-stu-id="83ea2-104">To add an INTERACT send port</span></span>  
  
1.  <span data-ttu-id="83ea2-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="83ea2-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="83ea2-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="83ea2-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="83ea2-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_IA_SendRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-108">In the **Send Port Properties** window, name the send port, **Tutorial_IA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="83ea2-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**交互**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **INTERACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="83ea2-110">在**交互传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83ea2-110">In the **INTERACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="83ea2-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="83ea2-111">**Use this**</span></span>|<span data-ttu-id="83ea2-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="83ea2-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="83ea2-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="83ea2-113">**Password**</span></span>|<span data-ttu-id="83ea2-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="83ea2-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="83ea2-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="83ea2-115">**User name**</span></span>|<span data-ttu-id="83ea2-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="83ea2-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="83ea2-117">**消息格式**</span><span class="sxs-lookup"><span data-stu-id="83ea2-117">**Message format**</span></span>|<span data-ttu-id="83ea2-118">**InteractMessage**</span><span class="sxs-lookup"><span data-stu-id="83ea2-118">**InteractMessage**</span></span>|  
    |<span data-ttu-id="83ea2-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="83ea2-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="83ea2-120">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="83ea2-120">**FALSE**</span></span>|  
    |<span data-ttu-id="83ea2-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="83ea2-121">**Request Type**</span></span>|<span data-ttu-id="83ea2-122">键入相应\<RequestType > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="83ea2-122">Type the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="83ea2-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="83ea2-123">**ResponseCrypto**</span></span>|<span data-ttu-id="83ea2-124">**FALSE**</span><span class="sxs-lookup"><span data-stu-id="83ea2-124">**FALSE**</span></span>|  
    |<span data-ttu-id="83ea2-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="83ea2-125">**Requestor**</span></span>|<span data-ttu-id="83ea2-126">键入相应\<RequestorDN > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="83ea2-126">Type the appropriate \<RequestorDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="83ea2-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="83ea2-127">**Responder**</span></span>|<span data-ttu-id="83ea2-128">键入相应\<ResponderDN > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="83ea2-128">Type the appropriate \<ResponderDN> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="83ea2-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="83ea2-129">**Service Name**</span></span>|<span data-ttu-id="83ea2-130">键入相应\<服务名称 >，将根据 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="83ea2-130">Type the appropriate \<service name>, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="83ea2-131">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="83ea2-131">**Delivery Notification**</span></span>|<span data-ttu-id="83ea2-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="83ea2-133">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="83ea2-133">**Notify queue**</span></span>|<span data-ttu-id="83ea2-134">键入相应的队列名称，基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="83ea2-134">Type the appropriate queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="83ea2-135">如果只传输负载，设置到交互中的"负载"MessageFormat receive 端口和交互发送端口。</span><span class="sxs-lookup"><span data-stu-id="83ea2-135">If only payload is to be transferred, set the MessageFormat to “Payload” in the INTERACT receive port and INTERACT send port.</span></span> <span data-ttu-id="83ea2-136">设置为 PassThru 接收和发送管道。</span><span class="sxs-lookup"><span data-stu-id="83ea2-136">Set the Receive and Send pipelines to PassThru.</span></span>  
  
7.  <span data-ttu-id="83ea2-137">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-137">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="83ea2-138">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83ea2-138">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="83ea2-139">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="83ea2-139">**Use this**</span></span>|<span data-ttu-id="83ea2-140">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="83ea2-140">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="83ea2-141">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="83ea2-141">**Send handler**</span></span>|<span data-ttu-id="83ea2-142">从下拉列表中，选择的交互主机。</span><span class="sxs-lookup"><span data-stu-id="83ea2-142">From the drop-down list, select the Interact host.</span></span>|  
    |<span data-ttu-id="83ea2-143">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="83ea2-143">**Send pipeline**</span></span>|<span data-ttu-id="83ea2-144">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-144">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="83ea2-145">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="83ea2-145">**Receive pipeline**</span></span>|<span data-ttu-id="83ea2-146">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-146">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="83ea2-147">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="83ea2-147">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="83ea2-148">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="83ea2-148">**Use this**</span></span>|<span data-ttu-id="83ea2-149">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="83ea2-149">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="83ea2-150">**属性**</span><span class="sxs-lookup"><span data-stu-id="83ea2-150">**Property**</span></span>|<span data-ttu-id="83ea2-151">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-151">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="83ea2-152">**运算符**</span><span class="sxs-lookup"><span data-stu-id="83ea2-152">**Operator**</span></span>|<span data-ttu-id="83ea2-153">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="83ea2-153">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="83ea2-154">**值**</span><span class="sxs-lookup"><span data-stu-id="83ea2-154">**Value**</span></span>|<span data-ttu-id="83ea2-155">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-155">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="83ea2-156">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="83ea2-156">**Group by**</span></span>|<span data-ttu-id="83ea2-157">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="83ea2-157">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="83ea2-158">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="83ea2-158">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83ea2-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83ea2-159">See Also</span></span>  
 <span data-ttu-id="83ea2-160">[步骤 2A： 添加文件接收交互应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="83ea2-160">[Step 2A: Add FILE Receive Locations for the InterAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-interact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="83ea2-161">步骤 2B： 添加要捕获 Sw:HandleRequest 消息交互，应用商店应用和进 （请求） 方案的文件发送端口</span><span class="sxs-lookup"><span data-stu-id="83ea2-161">Step 2B: Add FILE Send Ports to Capture the Sw:HandleRequest Message for the InterAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports-to-get-sw-handlerequest-message-for-interact.md)