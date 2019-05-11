---
title: 步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7366140b-ab89-4bea-9cdb-aa27e8dea8a0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9673f80bf19b365297b76ba3775f8f73813052f3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65365512"
---
# <a name="step-3d-add-a-fileact-send-port-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="3f365-102">步骤 3D:添加 FILEACT 发送端口为 FileAct 存储和转发方案</span><span class="sxs-lookup"><span data-stu-id="3f365-102">Step 3D: Add a FILEACT Send Port for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="3f365-103">在开始此步骤之前，必须完成[步骤 3c:添加 FILE 发送端口以捕获为 FileAct 存储和转发方案: handlefilerequest 和 sw: handlesnfrequest 消息](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)。</span><span class="sxs-lookup"><span data-stu-id="3f365-103">Before you begin this step, you must complete [Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="3f365-104">若要添加 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="3f365-104">To add a FILEACT send port</span></span>  
  
1.  <span data-ttu-id="3f365-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3f365-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3f365-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3f365-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="3f365-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="3f365-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="3f365-108">在中**发送端口属性**窗口中，命名该发送端口，Tutorial_FA_SendRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="3f365-108">In the **Send Port Properties** window, name the send port, Tutorial_FA_SendRequest_SnF.</span></span>  
  
5.  <span data-ttu-id="3f365-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3f365-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="3f365-110">在中**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f365-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="3f365-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3f365-111">**Use this**</span></span>|<span data-ttu-id="3f365-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3f365-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3f365-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="3f365-113">**Password**</span></span>|<span data-ttu-id="3f365-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="3f365-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3f365-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="3f365-115">**User name**</span></span>|<span data-ttu-id="3f365-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="3f365-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="3f365-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="3f365-117">**Adapter Mode**</span></span>|<span data-ttu-id="3f365-118">从下拉列表中，选择**存储和转发**。</span><span class="sxs-lookup"><span data-stu-id="3f365-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="3f365-119">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="3f365-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="3f365-120">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3f365-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3f365-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="3f365-121">**Request Type**</span></span>|<span data-ttu-id="3f365-122">设置为适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f365-122">Set to the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3f365-123">**ResponseCrypto**</span><span class="sxs-lookup"><span data-stu-id="3f365-123">**ResponseCrypto**</span></span>|<span data-ttu-id="3f365-124">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3f365-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3f365-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="3f365-125">**Requestor**</span></span>|<span data-ttu-id="3f365-126">设置为适当\<请求程序\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="3f365-126">Set to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="3f365-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="3f365-127">**Responder**</span></span>|<span data-ttu-id="3f365-128">设置为适当\<响应方\>字符串。</span><span class="sxs-lookup"><span data-stu-id="3f365-128">Set to the appropriate \<Responder\> string.</span></span>|  
    |<span data-ttu-id="3f365-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="3f365-129">**Service Name**</span></span>|<span data-ttu-id="3f365-130">设置为适当\<服务名称\>。</span><span class="sxs-lookup"><span data-stu-id="3f365-130">Set to the appropriate \<service name\>.</span></span>|  
    |<span data-ttu-id="3f365-131">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="3f365-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="3f365-132">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3f365-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3f365-133">**FileCompression**</span><span class="sxs-lookup"><span data-stu-id="3f365-133">**FileCompression**</span></span>|<span data-ttu-id="3f365-134">从下拉列表中，选择**None**。</span><span class="sxs-lookup"><span data-stu-id="3f365-134">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="3f365-135">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="3f365-135">**Event end-point**</span></span>|<span data-ttu-id="3f365-136">键入相应压降终结点。</span><span class="sxs-lookup"><span data-stu-id="3f365-136">Type the appropriate SAG end-point.</span></span>|  
    |<span data-ttu-id="3f365-137">**物理文件夹名称**</span><span class="sxs-lookup"><span data-stu-id="3f365-137">**Physical Folder Name**</span></span>|<span data-ttu-id="3f365-138">键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。</span><span class="sxs-lookup"><span data-stu-id="3f365-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="3f365-139">**传输终结点**</span><span class="sxs-lookup"><span data-stu-id="3f365-139">**Transfer end-point**</span></span>|<span data-ttu-id="3f365-140">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="3f365-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="3f365-141">此值应与配置中压降 SnL 终结点匹配。</span><span class="sxs-lookup"><span data-stu-id="3f365-141">This value should match the SnL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="3f365-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="3f365-142">**ServiceProfile**</span></span>|<span data-ttu-id="3f365-143">从下拉列表中，选择**事务计数**。</span><span class="sxs-lookup"><span data-stu-id="3f365-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="3f365-144">**送达通知**</span><span class="sxs-lookup"><span data-stu-id="3f365-144">**Delivery notification**</span></span>|<span data-ttu-id="3f365-145">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="3f365-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="3f365-146">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="3f365-146">**Notify queue**</span></span>|<span data-ttu-id="3f365-147">键入基于 SWIFT 与预配的队列名称。</span><span class="sxs-lookup"><span data-stu-id="3f365-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!WARNING]
    >  <span data-ttu-id="3f365-148">如果要传输消息的事务计数，服务配置文件将模式设置为"事务计数"FileAct 发送端口。</span><span class="sxs-lookup"><span data-stu-id="3f365-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="3f365-149">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3f365-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="3f365-150">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f365-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="3f365-151">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3f365-151">**Use this**</span></span>|<span data-ttu-id="3f365-152">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3f365-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3f365-153">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="3f365-153">**Send handler**</span></span>|<span data-ttu-id="3f365-154">从下拉列表中，选择 Fileact 主机。</span><span class="sxs-lookup"><span data-stu-id="3f365-154">From the drop-down list, select the Fileact host.</span></span>|  
    |<span data-ttu-id="3f365-155">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="3f365-155">**Send pipeline**</span></span>|<span data-ttu-id="3f365-156">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="3f365-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="3f365-157">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="3f365-157">**Receive pipeline**</span></span>|<span data-ttu-id="3f365-158">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="3f365-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="3f365-159">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3f365-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="3f365-160">**使用此**</span><span class="sxs-lookup"><span data-stu-id="3f365-160">**Use this**</span></span>|<span data-ttu-id="3f365-161">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="3f365-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="3f365-162">**属性**</span><span class="sxs-lookup"><span data-stu-id="3f365-162">**Property**</span></span>|<span data-ttu-id="3f365-163">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="3f365-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="3f365-164">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="3f365-164">**Operator**</span></span>|<span data-ttu-id="3f365-165">从下拉列表中，选择**==**。</span><span class="sxs-lookup"><span data-stu-id="3f365-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="3f365-166">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="3f365-166">**Value**</span></span>|<span data-ttu-id="3f365-167">类型 Tutorial_FA_InputRequest_SnF。</span><span class="sxs-lookup"><span data-stu-id="3f365-167">Type Tutorial_FA_InputRequest_SnF.</span></span>|  
    |<span data-ttu-id="3f365-168">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="3f365-168">**Group by**</span></span>|<span data-ttu-id="3f365-169">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="3f365-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="3f365-170">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="3f365-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f365-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f365-171">See Also</span></span>  
 <span data-ttu-id="3f365-172">[步骤 3：创建发送端口和接收端口为 FileAct 存储和转发方案](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="3f365-172">[Step 3: Create Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3-create-send-ports-and-receive-ports-for-the-fileact-store-and-forward.md) </span></span>  
 <span data-ttu-id="3f365-173">[步骤 3a:为 FileAct 存储和转发方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3f365-173">[Step 3A: Add a FILE Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="3f365-174">[步骤 3b:为 FileAct 存储和转发方案添加 FILEACT 接收位置](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="3f365-174">[Step 3B: Add a FILEACT Receive Location for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="3f365-175">步骤 3c:添加 FILE 发送端口以捕获为 FileAct 存储和转发方案: handlefilerequest 和 sw: handlesnfrequest 消息</span><span class="sxs-lookup"><span data-stu-id="3f365-175">Step 3C: Add a FILE Send Port to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlefilerequest-and-sw-handlesnfrequest.md)