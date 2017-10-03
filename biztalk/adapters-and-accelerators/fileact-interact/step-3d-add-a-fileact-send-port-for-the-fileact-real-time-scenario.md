---
title: "步骤 3D: FileAct 实时方案添加 FILEACT 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8a22ba41-4f43-4fbb-92f7-a0fd7558d2ce
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3ab2de6dabd581cb36d23ce218fb1b902ac04e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario"></a><span data-ttu-id="a8f1e-102">步骤 3D: FileAct 实时方案添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="a8f1e-102">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="a8f1e-103">在开始此步骤之前，必须完成[步骤 3c: FileAct 实时方案将文件发送端口添加到捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-103">Before you start this step, you must complete [Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="a8f1e-104">若要添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="a8f1e-104">To add a FILEACT send port</span></span>  
  
1.  <span data-ttu-id="a8f1e-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a8f1e-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="a8f1e-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="a8f1e-108">在**发送端口属性**窗口中，名称发送端口 Tutorial_FA_SendRequest_RealTime。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendRequest_RealTime.</span></span>  
  
5.  <span data-ttu-id="a8f1e-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a8f1e-110">在**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8f1e-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a8f1e-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-111">**Use this**</span></span>|<span data-ttu-id="a8f1e-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a8f1e-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-113">**Password**</span></span>|<span data-ttu-id="a8f1e-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a8f1e-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-115">**User name**</span></span>|<span data-ttu-id="a8f1e-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a8f1e-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-117">**Adapter Mode**</span></span>|<span data-ttu-id="a8f1e-118">从下拉列表中选择**存储和转发**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="a8f1e-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="a8f1e-120">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a8f1e-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-121">**Request Type**</span></span>|<span data-ttu-id="a8f1e-122">设置为相应\<RequestType > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-122">Set to the appropriate \<RequestType> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a8f1e-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-123">**ResponseCrypto**</span></span>|<span data-ttu-id="a8f1e-124">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a8f1e-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-125">**Requestor**</span></span>|<span data-ttu-id="a8f1e-126">设置为相应\<请求者 > 基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-126">Set to the appropriate \<Requestor> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a8f1e-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-127">**Responder**</span></span>|<span data-ttu-id="a8f1e-128">设置为相应\<响应方 > SWIFT 你设置基于字符串。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-128">Set to the appropriate \<Responder> string based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a8f1e-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-129">**Service Name**</span></span>|<span data-ttu-id="a8f1e-130">设置为相应\<服务名称 > 基于 SWIFT 你预配。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-130">Set to the appropriate \<service name> based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a8f1e-131">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="a8f1e-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a8f1e-133">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-133">**Event end-point**</span></span>|<span data-ttu-id="a8f1e-134">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-134">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a8f1e-135">**文件压缩**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-135">**File Compression**</span></span>|<span data-ttu-id="a8f1e-136">从下拉列表中选择**无**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-136">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="a8f1e-137">**物理文件夹名称**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-137">**Physical Folder Name**</span></span>|<span data-ttu-id="a8f1e-138">键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="a8f1e-139">**传输终结点**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-139">**Transfer end-point**</span></span>|<span data-ttu-id="a8f1e-140">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="a8f1e-141">此值应与匹配压降中配置的 SnL 终结点。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-141">This value should match the SnL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="a8f1e-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-142">**ServiceProfile**</span></span>|<span data-ttu-id="a8f1e-143">从下拉列表中选择**事务计数**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="a8f1e-144">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-144">**Delivery notification**</span></span>|<span data-ttu-id="a8f1e-145">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a8f1e-146">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-146">**Notify queue**</span></span>|<span data-ttu-id="a8f1e-147">键入根据 SWIFT 你设置的队列名称。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="a8f1e-148">如果消息与事务计数要传输，服务配置文件中设置模式为"事务计数"FileAct 发送端口。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="a8f1e-149">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a8f1e-150">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8f1e-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="a8f1e-151">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-151">**Use this**</span></span>|<span data-ttu-id="a8f1e-152">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a8f1e-153">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-153">**Send handler**</span></span>|<span data-ttu-id="a8f1e-154">从下拉列表中，选择 Fileact 主机。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-154">From the drop-down list, select the Fileact host.</span></span>|  
    |<span data-ttu-id="a8f1e-155">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-155">**Send pipeline**</span></span>|<span data-ttu-id="a8f1e-156">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="a8f1e-157">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-157">**Receive pipeline**</span></span>|<span data-ttu-id="a8f1e-158">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="a8f1e-159">在发送端口属性窗口上**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a8f1e-159">In the Send Port Properties window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="a8f1e-160">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-160">**Use this**</span></span>|<span data-ttu-id="a8f1e-161">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a8f1e-162">**属性**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-162">**Property**</span></span>|<span data-ttu-id="a8f1e-163">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="a8f1e-164">**运算符**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-164">**Operator**</span></span>|<span data-ttu-id="a8f1e-165">从下拉列表中选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a8f1e-166">**值**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-166">**Value**</span></span>|<span data-ttu-id="a8f1e-167">类型 Tutorial_FA_InputRequest_RealTime。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-167">Type Tutorial_FA_InputRequest_RealTime.</span></span>|  
    |<span data-ttu-id="a8f1e-168">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="a8f1e-168">**Group by**</span></span>|<span data-ttu-id="a8f1e-169">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="a8f1e-170">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a8f1e-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f1e-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8f1e-171">See Also</span></span>  
 <span data-ttu-id="a8f1e-172">[步骤 3： 创建发送端口和 FileAct 实时方案接收端口](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a8f1e-172">[Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-the-send-ports-and-receive-ports-for-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a8f1e-173">[步骤 3A： 添加一个文件接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a8f1e-173">[Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a8f1e-174">[步骤 3B： 添加 FILEACT 接收位置 FileAct 实时方案](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a8f1e-174">[Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a8f1e-175">[步骤 3c： 添加文件发送端口 FileAct 实时方案捕获 Sw:HandleRequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span><span class="sxs-lookup"><span data-stu-id="a8f1e-175">[Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md) </span></span>  
 [<span data-ttu-id="a8f1e-176">步骤 3E： 添加文件发送端口 FileAct 实时方案捕获 Sw:ExchangeFileResponse 消息</span><span class="sxs-lookup"><span data-stu-id="a8f1e-176">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)