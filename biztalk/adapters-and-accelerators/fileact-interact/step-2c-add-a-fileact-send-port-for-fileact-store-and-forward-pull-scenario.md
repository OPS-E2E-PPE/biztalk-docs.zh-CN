---
title: '步骤 2c: FileAct 存储和转发 （请求） 方案的 FILEACT 发送端口添加 |Microsoft 文档'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8743a868-9625-477b-a7da-673bfa262723
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 803a8c671081afd3ba18b81d4770b80b26205eaf
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964043"
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="a6b6d-102">步骤 2c： 添加 FileAct 应用商店应用和进 （请求） 方案 FILEACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="a6b6d-102">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="a6b6d-103">在开始此步骤之前，必须完成[步骤 2B： 发送端口添加文件，以捕获 Sw:HandleFileRequest 和 FileAct 存储和转发 （请求） 方案的 Sw:HandleSnFRequest 消息](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="a6b6d-104">若要添加 FileACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="a6b6d-104">To add a FileACT send port</span></span>  
  
1.  <span data-ttu-id="a6b6d-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6b6d-106">在控制台树中，展开 BizTalk 组中，，然后展开你想要创建发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="a6b6d-107">右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="a6b6d-108">在**发送端口属性**窗口中，名称发送端口**Tutorial_FA_SendRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="a6b6d-109">在**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a6b6d-110">在**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6b6d-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a6b6d-111">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-111">**Use this**</span></span>|<span data-ttu-id="a6b6d-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6b6d-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-113">**Password**</span></span>|<span data-ttu-id="a6b6d-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a6b6d-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-115">**User name**</span></span>|<span data-ttu-id="a6b6d-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a6b6d-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-117">**Adapter Mode**</span></span>|<span data-ttu-id="a6b6d-118">从下拉列表中选择**存储和转发**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="a6b6d-119">**不可否认性指示器**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="a6b6d-120">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6b6d-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-121">**Request Type**</span></span>|<span data-ttu-id="a6b6d-122">设置为相应\<RequestType\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-122">Set to the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a6b6d-123">**RequestCrypto**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-123">**RequestCrypto**</span></span>|<span data-ttu-id="a6b6d-124">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6b6d-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-125">**Requestor**</span></span>|<span data-ttu-id="a6b6d-126">设置为相应\<请求者\>基于 SWIFT 你设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-126">Set to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a6b6d-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-127">**Responder**</span></span>|<span data-ttu-id="a6b6d-128">设置为相应\<响应方\>字符串。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-128">Set to the appropriate \<Responder\> string.</span></span>|  
    |<span data-ttu-id="a6b6d-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-129">**Service Name**</span></span>|<span data-ttu-id="a6b6d-130">设置为相应**\<服务名称\>**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-130">Set to the appropriate **\<service name\>**.</span></span>|  
    |<span data-ttu-id="a6b6d-131">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="a6b6d-132">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6b6d-133">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-133">**Event end-point**</span></span>|<span data-ttu-id="a6b6d-134">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-134">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6b6d-135">**文件压缩**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-135">**File Compression**</span></span>|<span data-ttu-id="a6b6d-136">从下拉列表中选择**无**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-136">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="a6b6d-137">**物理文件夹名称**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-137">**Physical Folder Name**</span></span>|<span data-ttu-id="a6b6d-138">键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="a6b6d-139">**传输终结点**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-139">**Transfer end-point**</span></span>|<span data-ttu-id="a6b6d-140">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="a6b6d-141">此值应与匹配压降中配置的 SNL 终结点。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-141">This value should match the SNL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="a6b6d-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-142">**ServiceProfile**</span></span>|<span data-ttu-id="a6b6d-143">从下拉列表中选择**事务计数**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="a6b6d-144">**传递通知**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-144">**Delivery notification**</span></span>|<span data-ttu-id="a6b6d-145">从下拉列表中选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6b6d-146">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-146">**Notify queue**</span></span>|<span data-ttu-id="a6b6d-147">键入根据 SWIFT 你设置的队列名称。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="a6b6d-148">如果消息与事务计数要传输，服务配置文件中设置模式为"事务计数"FileAct 发送端口。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="a6b6d-149">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a6b6d-150">在**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6b6d-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="a6b6d-151">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-151">**Use this**</span></span>|<span data-ttu-id="a6b6d-152">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6b6d-153">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-153">**Send handler**</span></span>|<span data-ttu-id="a6b6d-154">从下拉列表中选择**FileActHost**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-154">From the drop-down list, select the **FileActHost**.</span></span>|  
    |<span data-ttu-id="a6b6d-155">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-155">**Send pipeline**</span></span>|<span data-ttu-id="a6b6d-156">从下拉列表中选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="a6b6d-157">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-157">**Receive pipeline**</span></span>|<span data-ttu-id="a6b6d-158">从下拉列表中选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="a6b6d-159">在**发送端口属性**窗口，请在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6b6d-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="a6b6d-160">**使用此方法**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-160">**Use this**</span></span>|<span data-ttu-id="a6b6d-161">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6b6d-162">**属性**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-162">**Property**</span></span>|<span data-ttu-id="a6b6d-163">从下拉列表中选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="a6b6d-164">**运算符**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-164">**Operator**</span></span>|<span data-ttu-id="a6b6d-165">从下拉列表中选择**==**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a6b6d-166">**值**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-166">**Value**</span></span>|<span data-ttu-id="a6b6d-167">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-167">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="a6b6d-168">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="a6b6d-168">**Group by**</span></span>|<span data-ttu-id="a6b6d-169">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="a6b6d-170">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a6b6d-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b6d-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6b6d-171">See Also</span></span>  
 <span data-ttu-id="a6b6d-172">[步骤 2A： 添加文件接收 FileAct 应用商店应用和进 （请求） 方案的位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a6b6d-172">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="a6b6d-173">步骤 2B：为 FileAct 存储和转发（拉取）方案添加 FILE 发送端口以捕获 Sw:HandleFileRequest 和 Sw:HandleSnFRequest 消息</span><span class="sxs-lookup"><span data-stu-id="a6b6d-173">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)