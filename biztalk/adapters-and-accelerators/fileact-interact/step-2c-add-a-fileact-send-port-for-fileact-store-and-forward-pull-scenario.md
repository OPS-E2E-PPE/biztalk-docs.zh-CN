---
title: 步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案 |Microsoft Docs
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
ms.openlocfilehash: ac2579d61aa20db0dcb445b30ebac1bb429221cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366023"
---
# <a name="step-2c-add-a-fileact-send-port-for-the-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="a6f7c-102">步骤 2c:添加 FILEACT 发送端口为 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="a6f7c-102">Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="a6f7c-103">在开始此步骤之前，必须完成[步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-103">Before you begin this step, you must complete [Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md).</span></span>  
  
### <a name="to-add-a-fileact-send-port"></a><span data-ttu-id="a6f7c-104">若要添加 FileACT 发送端口</span><span class="sxs-lookup"><span data-stu-id="a6f7c-104">To add a FileACT send port</span></span>  
  
1.  <span data-ttu-id="a6f7c-105">启动**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-105">Start **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a6f7c-106">在控制台树中，依次展开 BizTalk 组，和你想要创建的发送端口的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-106">In the console tree, expand the BizTalk group, and then expand the BizTalk application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="a6f7c-107">右键单击**发送端口**，依次指向**新建**，然后单击**静态要求响应发送端口**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-107">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
4.  <span data-ttu-id="a6f7c-108">在中**发送端口属性**窗口中，命名该发送端口， **Tutorial_FA_SendRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-108">In the **Send Port Properties** window, name the send port, **Tutorial_FA_SendRequest_SnF**.</span></span>  
  
5.  <span data-ttu-id="a6f7c-109">在中**发送端口属性**窗口中，从**传输类型**下拉列表中，选择**FILEACT**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-109">In the **Send Port Properties** window, from the **Transport type** drop-down list, select **FILEACT**, and then click **Configure**.</span></span>  
  
6.  <span data-ttu-id="a6f7c-110">在中**FILEACT 传输属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6f7c-110">In the **FILEACT Transport Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a6f7c-111">**使用此**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-111">**Use this**</span></span>|<span data-ttu-id="a6f7c-112">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-112">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6f7c-113">**密码**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-113">**Password**</span></span>|<span data-ttu-id="a6f7c-114">根据压降连接需要设置密码。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-114">Set the password as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a6f7c-115">**用户名**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-115">**User name**</span></span>|<span data-ttu-id="a6f7c-116">根据压降连接需要设置的用户名。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-116">Set the user name as appropriate for SAG connectivity.</span></span>|  
    |<span data-ttu-id="a6f7c-117">**适配器模式**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-117">**Adapter Mode**</span></span>|<span data-ttu-id="a6f7c-118">从下拉列表中，选择**存储和转发**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-118">From the drop-down list, select **Store and Forward**.</span></span>|  
    |<span data-ttu-id="a6f7c-119">**不可否认指示器**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-119">**Non-Repudiation Indicator**</span></span>|<span data-ttu-id="a6f7c-120">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-120">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6f7c-121">**请求类型**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-121">**Request Type**</span></span>|<span data-ttu-id="a6f7c-122">设置为适当\<RequestType\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-122">Set to the appropriate \<RequestType\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a6f7c-123">**RequestCrypto**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-123">**RequestCrypto**</span></span>|<span data-ttu-id="a6f7c-124">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-124">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6f7c-125">**请求者**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-125">**Requestor**</span></span>|<span data-ttu-id="a6f7c-126">设置为适当\<请求程序\>为基础的 SWIFT 应用预配的字符串。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-126">Set to the appropriate \<Requestor\> string, based on your provisioning with SWIFT.</span></span>|  
    |<span data-ttu-id="a6f7c-127">**响应方**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-127">**Responder**</span></span>|<span data-ttu-id="a6f7c-128">设置为适当\<响应方\>字符串。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-128">Set to the appropriate \<Responder\> string.</span></span>|  
    |<span data-ttu-id="a6f7c-129">**服务名称**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-129">**Service Name**</span></span>|<span data-ttu-id="a6f7c-130">设置为适当 **\<服务名称\>** 。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-130">Set to the appropriate **\<service name\>**.</span></span>|  
    |<span data-ttu-id="a6f7c-131">**确认指示器**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-131">**Acknowledgement Indicator**</span></span>|<span data-ttu-id="a6f7c-132">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-132">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6f7c-133">**事件终结点**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-133">**Event end-point**</span></span>|<span data-ttu-id="a6f7c-134">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-134">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6f7c-135">**文件压缩**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-135">**File Compression**</span></span>|<span data-ttu-id="a6f7c-136">从下拉列表中，选择**None**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-136">From the drop-down list, select **None**.</span></span>|  
    |<span data-ttu-id="a6f7c-137">**物理文件夹名称**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-137">**Physical Folder Name**</span></span>|<span data-ttu-id="a6f7c-138">键入 C:\SWIFTAdapterTutorial\Fileact\ClientLocation。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-138">Type C:\SWIFTAdapterTutorial\Fileact\ClientLocation.</span></span>|  
    |<span data-ttu-id="a6f7c-139">**传输终结点**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-139">**Transfer end-point**</span></span>|<span data-ttu-id="a6f7c-140">键入压降路由组的相应终结点。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-140">Type the appropriate end-point for the SAG routing set.</span></span> <span data-ttu-id="a6f7c-141">此值应与配置中压降 SNL 终结点匹配。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-141">This value should match the SNL endpoint you configured in SAG.</span></span>|  
    |<span data-ttu-id="a6f7c-142">**ServiceProfile**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-142">**ServiceProfile**</span></span>|<span data-ttu-id="a6f7c-143">从下拉列表中，选择**事务计数**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-143">From the drop-down list, select **Transaction Count**.</span></span>|  
    |<span data-ttu-id="a6f7c-144">**送达通知**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-144">**Delivery notification**</span></span>|<span data-ttu-id="a6f7c-145">从下拉列表中，选择**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-145">From the drop-down list, select **FALSE**.</span></span>|  
    |<span data-ttu-id="a6f7c-146">**通知队列**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-146">**Notify queue**</span></span>|<span data-ttu-id="a6f7c-147">键入基于 SWIFT 与预配的队列名称。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-147">Type the queue name, based on your provisioning with SWIFT.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="a6f7c-148">如果要传输消息的事务计数，服务配置文件将模式设置为"事务计数"FileAct 发送端口。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-148">If message with Transaction Count is to be transferred, set the Service Profile Mode to “Transaction Count” in the FileAct send port.</span></span>  
  
7.  <span data-ttu-id="a6f7c-149">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-149">Click **OK**.</span></span>  
  
8.  <span data-ttu-id="a6f7c-150">在中**发送端口属性**窗口中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6f7c-150">In the **Send Port Properties** window, do the following:</span></span>  
  
    |<span data-ttu-id="a6f7c-151">**使用此**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-151">**Use this**</span></span>|<span data-ttu-id="a6f7c-152">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-152">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6f7c-153">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-153">**Send handler**</span></span>|<span data-ttu-id="a6f7c-154">从下拉列表中，选择**FileActHost**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-154">From the drop-down list, select the **FileActHost**.</span></span>|  
    |<span data-ttu-id="a6f7c-155">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-155">**Send pipeline**</span></span>|<span data-ttu-id="a6f7c-156">从下拉列表中，选择**XMLTransmit**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-156">From the drop-down list, select **XMLTransmit**.</span></span>|  
    |<span data-ttu-id="a6f7c-157">**接收管道**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-157">**Receive pipeline**</span></span>|<span data-ttu-id="a6f7c-158">从下拉列表中，选择**XMLReceive**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-158">From the drop-down list, select **XMLReceive**.</span></span>|  
  
9. <span data-ttu-id="a6f7c-159">在中**发送端口属性**窗口，然后在**筛选器**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6f7c-159">In the **Send Port Properties** window, on the **Filters** tab, do the following:</span></span>  
  
    |<span data-ttu-id="a6f7c-160">**使用此**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-160">**Use this**</span></span>|<span data-ttu-id="a6f7c-161">**若要执行此操作**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-161">**To do this**</span></span>|  
    |------------------|--------------------|  
    |<span data-ttu-id="a6f7c-162">**属性**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-162">**Property**</span></span>|<span data-ttu-id="a6f7c-163">从下拉列表中，选择**BTS。ReceivePortName**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-163">From the drop-down list, select **BTS.ReceivePortName**.</span></span>|  
    |<span data-ttu-id="a6f7c-164">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-164">**Operator**</span></span>|<span data-ttu-id="a6f7c-165">从下拉列表中，选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-165">From the drop-down list, select **==**.</span></span>|  
    |<span data-ttu-id="a6f7c-166">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-166">**Value**</span></span>|<span data-ttu-id="a6f7c-167">类型**Tutorial_IA_InputRequest_SnF**。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-167">Type **Tutorial_IA_InputRequest_SnF**.</span></span>|  
    |<span data-ttu-id="a6f7c-168">**分组依据**</span><span class="sxs-lookup"><span data-stu-id="a6f7c-168">**Group by**</span></span>|<span data-ttu-id="a6f7c-169">保留默认值。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-169">Leave the default value.</span></span>|  
  
10. <span data-ttu-id="a6f7c-170">单击“确定”  。</span><span class="sxs-lookup"><span data-stu-id="a6f7c-170">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f7c-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f7c-171">See Also</span></span>  
 <span data-ttu-id="a6f7c-172">[步骤 2A:为 FileAct 存储和转发 （拉取） 方案添加文件接收位置](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a6f7c-172">[Step 2A: Add FILE Receive Locations for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2a-add-file-receive-locations-for-fileact-store-and-forward-scenario.md) </span></span>  
 [<span data-ttu-id="a6f7c-173">步骤 2B:添加 FILE 发送端口以捕获 sw: handlefilerequest 和 sw: handlesnfrequest 消息 FileAct 存储和转发 （拉取） 方案</span><span class="sxs-lookup"><span data-stu-id="a6f7c-173">Step 2B: Add FILE Send Ports to Capture the Sw:HandleFileRequest and Sw:HandleSnFRequest Messages for the FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-2b-add-file-send-ports--get-sw-handlefilerequest-and-sw-handlesnfrequest.md)