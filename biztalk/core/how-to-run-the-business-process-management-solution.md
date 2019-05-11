---
title: 如何运行业务流程管理解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd8054daf0c5cd86cd7df1d303882cb57003e58a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384086"
---
# <a name="how-to-run-the-business-process-management-solution"></a><span data-ttu-id="bb1b7-102">如何运行业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-102">How to Run the Business Process Management Solution</span></span>
<span data-ttu-id="bb1b7-103">以下步骤介绍如何运行和验证业务流程管理解决方案在单台计算机上。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-103">The following steps describe how to run and validate the Business Process Management solution on a single computer.</span></span>  
  
-   [<span data-ttu-id="bb1b7-104">启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-104">Start the Business Process Management Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="bb1b7-105">运行并验证业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-105">Run and validate the Business Process Management Solution</span></span>](#step3)  
  
## <a name="prerequisites"></a><span data-ttu-id="bb1b7-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="bb1b7-106">Prerequisites</span></span>  
 <span data-ttu-id="bb1b7-107">之前运行 BPM 解决方案，必须先执行中的步骤[如何安装业务流程管理解决方案](../core/how-to-install-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-107">Before running the BPM solution, you must perform the steps in [How to Install the Business Process Management Solution](../core/how-to-install-the-business-process-management-solution.md).</span></span>  
  
##  <a name="step1"></a> <span data-ttu-id="bb1b7-108">启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-108">Start the Business Process Management Solution</span></span>  
  
#### <a name="to-start-the-business-process-management-solution"></a><span data-ttu-id="bb1b7-109">若要启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-109">To start the Business Process Management Solution</span></span>  
  
1. <span data-ttu-id="bb1b7-110">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="bb1b7-111">在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-111">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span>  
  
3. <span data-ttu-id="bb1b7-112">在中**BizTalk Server 管理控制台**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-112">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
   1.  <span data-ttu-id="bb1b7-113">右键单击 BTSScn.BPM.MessagingApp 中，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-113">Right-click BTSScn.BPM.MessagingApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
   2.  <span data-ttu-id="bb1b7-114">右键单击 BTSScn.BPM.OrderBrokerApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-114">Right-click BTSScn.BPM.OrderBrokerApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
   3.  <span data-ttu-id="bb1b7-115">右键单击 BTSScn.BPM.CableOrderApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-115">Right-click BTSScn.BPM.CableOrderApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
   4.  <span data-ttu-id="bb1b7-116">右键单击 BTSScn.BPM.OrderBrokerApp.Test，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-116">Right-click BTSScn.BPM.OrderBrokerApp.Test, and click **Stop**.</span></span> <span data-ttu-id="bb1b7-117">在中**停止应用程序**对话框中，选择**完全停止-终止实例**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-117">In the **Stop Application** dialog box, select **Full Stop - Terminate instance**, and then click **Stop**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="bb1b7-118">若要将信息插入历史记录数据库中。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-118">To insert information in the history database.</span></span> <span data-ttu-id="bb1b7-119">OrderBroker 业务流程使用 HistoryPort 发送端口的这**送达通知**属性设置**传输**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-119">the OrderBroker orchestration uses the HistoryPort send port of which the **Delivery Notification** property is set **Transmitted**.</span></span> <span data-ttu-id="bb1b7-120">发送端口绑定到 HISTORYINSERT-SPG 发送组，该组包括 HISTORYINSERT-SP 和测试-HISTORYINSERT-SP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-120">The send port is bounded to the HistoryInsert-SPG send group which includes the HistoryInsert-SP and HistoryInsert-Test-SP send ports.</span></span> <span data-ttu-id="bb1b7-121">对于这两个发送端口的消息引擎将向 OrderBroker 业务流程发布两条确认消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-121">For these two send ports the message engine will publish two acknowledgment messages to the OrderBroker orchestration.</span></span> <span data-ttu-id="bb1b7-122">它使业务流程由于未使用的消息而挂起。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-122">It makes the orchestration suspended due to unconsumed messages.</span></span> <span data-ttu-id="bb1b7-123">若要避免这种情况下，必须取消登记发送端口之一。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-123">To avoid this situation, you must unenlist one of the send ports.</span></span> <span data-ttu-id="bb1b7-124">在此演练中，取消登记通过完全停止 BTSScn.BPM.OrderBrokerApp.Test 应用程序的测试-HISTORYINSERT-SP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-124">In this walkthrough, unenlist HistoryInsert-Test-SP send port by fully stopping the BTSScn.BPM.OrderBrokerApp.Test application.</span></span> <span data-ttu-id="bb1b7-125">有关 OrderBroker 业务流程的详细信息，请参阅[在 OrderBroker 业务流程中处理](../core/processing-in-the-orderbroker-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-125">For more information about the OrderBroker orchestration, see [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span> <span data-ttu-id="bb1b7-126">有关详细信息**送达通知**属性，请参阅[使用确认](../core/using-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-126">For more information about **Delivery Notification** property, see [Using Acknowledgments](../core/using-acknowledgments.md).</span></span>  
  
4. <span data-ttu-id="bb1b7-127">按如下所示运行功能模拟程序：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-127">Run the Facilities Simulator as follows:</span></span>  
  
   1.  <span data-ttu-id="bb1b7-128">打开命令提示符下，将目录更改为 %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-128">Open a command prompt, change the directory to the %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug folder.</span></span>  
  
   2.  <span data-ttu-id="bb1b7-129">键入 `BTSScnBPMFacilities.exe`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-129">Type `BTSScnBPMFacilities.exe`, and then press ENTER.</span></span> <span data-ttu-id="bb1b7-130">使 facilitiessimulator 保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-130">Keep the FacilitiesSimulator running.</span></span> <span data-ttu-id="bb1b7-131">此应用程序模拟处理 Southridge video 后端系统的功能。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-131">This application simulates the facilities processing back-end systems at Southridge Video.</span></span>  
  
   3.  <span data-ttu-id="bb1b7-132">在 FacilitiesSimulator 中，键入以下接收和传输队列：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-132">In the FacilitiesSimulator, type the following receive and transmit queues:</span></span>  
  
       |<span data-ttu-id="bb1b7-133">“属性”</span><span class="sxs-lookup"><span data-stu-id="bb1b7-133">Name</span></span>|<span data-ttu-id="bb1b7-134">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-134">Value</span></span>|  
       |----------|-----------|  
       |<span data-ttu-id="bb1b7-135">**接收队列**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-135">**Receive Queue**</span></span>|`.\private$\ToFacilitiesQ`|  
       |<span data-ttu-id="bb1b7-136">**传输队列**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-136">**Transmit Queue**</span></span>|`.\private$\FromFacilitiesQ`|  
  
   4.  <span data-ttu-id="bb1b7-137">在 FacilitiesSimulator 中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-137">In the FacilitiesSimulator, Click **Start**.</span></span>  
  
5. <span data-ttu-id="bb1b7-138">按如下所示运行运营服务器：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-138">Run the Operation Server as follows:</span></span>  
  
   1.  <span data-ttu-id="bb1b7-139">打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\OperationsServer\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-139">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\OperationsServer\bin\debug folder.</span></span>  
  
   2.  <span data-ttu-id="bb1b7-140">类型`BTSScnBPMOperations.exe 8881`在命令提示符，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-140">Type `BTSScnBPMOperations.exe 8881` at the command prompt, and then press ENTER.</span></span> <span data-ttu-id="bb1b7-141">保持运行的操作服务器。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-141">Keep the Operation Server running.</span></span> <span data-ttu-id="bb1b7-142">操作服务器侦听 TCP 端口 8881 以接收来自 Ops 适配器错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-142">The Operation Server listens on the TCP port, 8881, to receive error messages from the Ops Adapter.</span></span> <span data-ttu-id="bb1b7-143">它将显示 Ops 适配器收到的错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-143">It displays the error messages received by the Ops Adapter.</span></span>  
  
6. <span data-ttu-id="bb1b7-144">按如下所示运行宽带提供系统：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-144">Run the Cable Provisioning System as follows:</span></span>  
  
   1.  <span data-ttu-id="bb1b7-145">打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-145">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug folder.</span></span>  
  
   2.  <span data-ttu-id="bb1b7-146">键入 `BTSScnBPMProvisioning.exe 8880`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-146">Type `BTSScnBPMProvisioning.exe 8880`, and then press ENTER.</span></span> <span data-ttu-id="bb1b7-147">然后，请运行宽带提供系统。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-147">Then, keep the Cable Provisioning System running.</span></span> <span data-ttu-id="bb1b7-148">宽带提供系统侦听 TCP 端口 8880。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-148">The Cable Provisioning System listens on the TCP port, 8880.</span></span> <span data-ttu-id="bb1b7-149">此应用程序模拟后端订单系统，并显示最终的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-149">This application simulates a back-end order system, and displays the final orders.</span></span>  
  
##  <a name="step3"></a> <span data-ttu-id="bb1b7-150">运行并验证业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-150">Run and validate the Business Process Management Solution</span></span>  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a><span data-ttu-id="bb1b7-151">若要提交新订单并验证解决方案</span><span class="sxs-lookup"><span data-stu-id="bb1b7-151">To submit a new order and validate the solution</span></span>  
  
1.  <span data-ttu-id="bb1b7-152">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-152">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="bb1b7-153">上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单。**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-153">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order.**</span></span>  
  
    |<span data-ttu-id="bb1b7-154">条目</span><span class="sxs-lookup"><span data-stu-id="bb1b7-154">Entry</span></span>|<span data-ttu-id="bb1b7-155">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-155">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="bb1b7-156">客户 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-156">Customer ID</span></span>|<span data-ttu-id="bb1b7-157">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-157">1</span></span>|  
    |<span data-ttu-id="bb1b7-158">订单 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-158">Order ID</span></span>|<span data-ttu-id="bb1b7-159">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-159">1</span></span>|  
    |<span data-ttu-id="bb1b7-160">序列号</span><span class="sxs-lookup"><span data-stu-id="bb1b7-160">Sequence Number</span></span>|<span data-ttu-id="bb1b7-161">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-161">1</span></span>|  
    |<span data-ttu-id="bb1b7-162">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="bb1b7-162">Service Type Code</span></span>|<span data-ttu-id="bb1b7-163">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="bb1b7-163">New Standard Service</span></span>|  
  
3.  <span data-ttu-id="bb1b7-164">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-164">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-165">**客户 ID 1 订单 ID 1 序列号 1**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-165">**Customer ID 1 Order ID 1 Sequence Number 1**</span></span>  
  
4.  <span data-ttu-id="bb1b7-166">验证已下的订单命令提示运行宽带提供系统。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-166">Validate that the placed order at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="bb1b7-167">应用程序显示的提交的顺序是分析、 激活和完成的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-167">The application display the messages that the submitted order is analyzed, activated, and then completed.</span></span>  
  
5.  <span data-ttu-id="bb1b7-168">验证的总消息数就会递增 1 功能模拟程序。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-168">Validate that the number of the total messages is incremented by one on the Facilities Simulator.</span></span>  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a><span data-ttu-id="bb1b7-169">提交重复时 BizTalk Server 正在处理的原始顺序</span><span class="sxs-lookup"><span data-stu-id="bb1b7-169">To submit a duplicate while the BizTalk Server is processing the original order</span></span>  
  
1.  <span data-ttu-id="bb1b7-170">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-170">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="bb1b7-171">在 FacilitiesSimulator 中，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-171">In the FacilitiesSimulator, click **Stop**.</span></span> <span data-ttu-id="bb1b7-172">它会阻止进一步处理提交的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-172">It prevents submitted orders from being processed further.</span></span>  
  
3.  <span data-ttu-id="bb1b7-173">上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**两次以模拟重复的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-173">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order** twice to simulate duplicated orders.</span></span>  
  
    |<span data-ttu-id="bb1b7-174">条目</span><span class="sxs-lookup"><span data-stu-id="bb1b7-174">Entry</span></span>|<span data-ttu-id="bb1b7-175">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-175">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="bb1b7-176">客户 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-176">Customer ID</span></span>|<span data-ttu-id="bb1b7-177">2</span><span class="sxs-lookup"><span data-stu-id="bb1b7-177">2</span></span>|  
    |<span data-ttu-id="bb1b7-178">订单 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-178">Order ID</span></span>|<span data-ttu-id="bb1b7-179">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-179">1</span></span>|  
    |<span data-ttu-id="bb1b7-180">序列号</span><span class="sxs-lookup"><span data-stu-id="bb1b7-180">Sequence Number</span></span>|<span data-ttu-id="bb1b7-181">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-181">1</span></span>|  
    |<span data-ttu-id="bb1b7-182">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="bb1b7-182">Service Type Code</span></span>|<span data-ttu-id="bb1b7-183">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="bb1b7-183">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="bb1b7-184">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-184">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-185">**客户 ID 为 2 的订单 ID 1 序列号 1**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-185">**Customer ID 2 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="bb1b7-186">在 FacilitiesSimulator 中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-186">In the FacilitiesSimulator, click **Start**.</span></span> <span data-ttu-id="bb1b7-187">等待来自功能模拟程序的响应的业务流程将继续进行。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-187">The orchestrations waiting for the responses from the Facilities Simulator will resume.</span></span> <span data-ttu-id="bb1b7-188">模拟在处理第一个订单时提交重复订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-188">It simulates that a duplicate order is submitted while the first order is being processed.</span></span>  
  
6.  <span data-ttu-id="bb1b7-189">检查在命令提示符处运行宽带提供系统已下的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-189">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="bb1b7-190">应用程序将显示仅第一个订单是分析、 激活和完成的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-190">The application displays the messages that only the first order is analyzed, activated, and then completed.</span></span>  
  
7.  <span data-ttu-id="bb1b7-191">检查在命令提示符处运行运营服务器重复订单错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-191">Check the error message for the duplicated orders at the command prompt running the Operation Server.</span></span>  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="bb1b7-192">若要在 BizTalk Server 处理订单时更新订单</span><span class="sxs-lookup"><span data-stu-id="bb1b7-192">To update an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="bb1b7-193">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-193">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="bb1b7-194">在 FacilitiesSimulator 中，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-194">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="bb1b7-195">上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-195">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="bb1b7-196">条目</span><span class="sxs-lookup"><span data-stu-id="bb1b7-196">Entry</span></span>|<span data-ttu-id="bb1b7-197">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-197">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="bb1b7-198">客户 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-198">Customer ID</span></span>|<span data-ttu-id="bb1b7-199">3</span><span class="sxs-lookup"><span data-stu-id="bb1b7-199">3</span></span>|  
    |<span data-ttu-id="bb1b7-200">订单 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-200">Order ID</span></span>|<span data-ttu-id="bb1b7-201">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-201">1</span></span>|  
    |<span data-ttu-id="bb1b7-202">序列号</span><span class="sxs-lookup"><span data-stu-id="bb1b7-202">Sequence Number</span></span>|<span data-ttu-id="bb1b7-203">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-203">1</span></span>|  
    |<span data-ttu-id="bb1b7-204">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="bb1b7-204">Service Type Code</span></span>|<span data-ttu-id="bb1b7-205">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="bb1b7-205">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="bb1b7-206">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-206">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-207">**客户 ID 3 订单 ID 1 序列号 1**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-207">**Customer ID 3 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="bb1b7-208">上**Southridge Video 客户服务申请单输入表单**页上，输入下表中更新的订单，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-208">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter an updated order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="bb1b7-209">条目</span><span class="sxs-lookup"><span data-stu-id="bb1b7-209">Entry</span></span>|<span data-ttu-id="bb1b7-210">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-210">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="bb1b7-211">客户 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-211">Customer ID</span></span>|<span data-ttu-id="bb1b7-212">3</span><span class="sxs-lookup"><span data-stu-id="bb1b7-212">3</span></span>|  
    |<span data-ttu-id="bb1b7-213">订单 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-213">Order ID</span></span>|<span data-ttu-id="bb1b7-214">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-214">1</span></span>|  
    |<span data-ttu-id="bb1b7-215">序列号</span><span class="sxs-lookup"><span data-stu-id="bb1b7-215">Sequence Number</span></span>|<span data-ttu-id="bb1b7-216">2</span><span class="sxs-lookup"><span data-stu-id="bb1b7-216">2</span></span>|  
    |<span data-ttu-id="bb1b7-217">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="bb1b7-217">Service Type Code</span></span>|<span data-ttu-id="bb1b7-218">新的高级服务</span><span class="sxs-lookup"><span data-stu-id="bb1b7-218">New Deluxe Service</span></span>|  
  
6.  <span data-ttu-id="bb1b7-219">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-219">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-220">**客户 ID 3 订单 ID 1 序列号 2**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-220">**Customer ID 3 Order ID 1 Sequence Number 2**</span></span>  
  
7.  <span data-ttu-id="bb1b7-221">在 FacilitiesSimulator 中，单击**开始**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-221">In the FacilitiesSimulator, click **Start**</span></span>  
  
8.  <span data-ttu-id="bb1b7-222">检查结果消息**Southridge Video 客户服务申请单输入表单**页。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-222">Check the result message on the **Southridge Video Customer Service Rep Order Entry Form** page.</span></span>  
  
9. <span data-ttu-id="bb1b7-223">检查在命令提示符处运行宽带提供系统已下的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-223">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="bb1b7-224">应用程序将显示两种顺序进行分析，但激活和完成更新的订单的消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-224">The application displays the messages that two orders are analyzed, but only the updated order is activated and completed.</span></span>  
  
10. <span data-ttu-id="bb1b7-225">单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**事件查看器**，然后选中一个新的警告，原始订单已中断。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-225">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the original order was interrupted.</span></span>  
  
11. <span data-ttu-id="bb1b7-226">检查在命令提示符处运行运营服务器的路由故障错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-226">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb1b7-227">将在事件日志和操作服务器中出现错误。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-227">There will be an error in the event log and in the operations server.</span></span> <span data-ttu-id="bb1b7-228">因为具有更高版本的序列号的新订单所导致的中断已终止，来自功能系统的响应消息不再关联回业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-228">The response message from the Facilities System no longer correlates back to an instance of the business process as it was terminated by the interruption caused by the new order with a higher sequence number.</span></span> <span data-ttu-id="bb1b7-229">因此响应消息孤立用户，并将路由到操作服务器。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-229">Therefore response message is orphaned and will get routed to the operations server.</span></span> <span data-ttu-id="bb1b7-230">有关订单更新的详细信息，请参阅[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-230">For more information about order updates, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
12. <span data-ttu-id="bb1b7-231">使用记事本 %SystemDrive%:\BPMTest\HistoryUpdate-SP 文件夹中打开的最新消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-231">Open the latest message in the %SystemDrive%:\BPMTest\HistoryUpdate-SP folder with Notepad.</span></span> <span data-ttu-id="bb1b7-232">检查**CustName**， **OrderNum**， **OrderSeqNum**，以及**状态**域，以查看该消息是否已创建的新订单和**状态**字段是**COMPLETED**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-232">Check **CustName**, **OrderNum**, **OrderSeqNum**, and **Status** fields to see if the message has been created for the new order and the **Status** field is **COMPLETED**.</span></span>  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="bb1b7-233">若要终止订单时 BizTalk Server 处理订单</span><span class="sxs-lookup"><span data-stu-id="bb1b7-233">To terminate an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="bb1b7-234">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-234">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="bb1b7-235">在 FacilitiesSimulator 中，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-235">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="bb1b7-236">上**Southridge Video 客户服务申请单输入表单**页上，在以下表中，输入新的订单，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-236">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="bb1b7-237">条目</span><span class="sxs-lookup"><span data-stu-id="bb1b7-237">Entry</span></span>|<span data-ttu-id="bb1b7-238">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-238">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="bb1b7-239">客户 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-239">Customer ID</span></span>|<span data-ttu-id="bb1b7-240">4</span><span class="sxs-lookup"><span data-stu-id="bb1b7-240">4</span></span>|  
    |<span data-ttu-id="bb1b7-241">订单 ID</span><span class="sxs-lookup"><span data-stu-id="bb1b7-241">Order ID</span></span>|<span data-ttu-id="bb1b7-242">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-242">1</span></span>|  
    |<span data-ttu-id="bb1b7-243">序列号</span><span class="sxs-lookup"><span data-stu-id="bb1b7-243">Sequence Number</span></span>|<span data-ttu-id="bb1b7-244">1</span><span class="sxs-lookup"><span data-stu-id="bb1b7-244">1</span></span>|  
    |<span data-ttu-id="bb1b7-245">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="bb1b7-245">Service Type Code</span></span>|<span data-ttu-id="bb1b7-246">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="bb1b7-246">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="bb1b7-247">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-247">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-248">**客户 ID 4 订单 ID 1 序列号 1**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-248">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="bb1b7-249">上**Southridge Video 客户服务申请单输入表单**页上，单击**终止订单**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-249">On the **Southridge Video Customer Service Rep Order Entry Form** page, click **Terminate Order**.</span></span>  
  
6.  <span data-ttu-id="bb1b7-250">上**Southridge Video 客户服务申请单输入表单**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb1b7-250">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="bb1b7-251">**客户 ID 4 订单 ID 1 序列号 1**</span><span class="sxs-lookup"><span data-stu-id="bb1b7-251">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
7.  <span data-ttu-id="bb1b7-252">在 FacilitiesSimulator 中，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-252">In the FacilitiesSimulator, click **Start**.</span></span>  
  
8.  <span data-ttu-id="bb1b7-253">检查在命令提示符处运行宽带提供系统已下的订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-253">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="bb1b7-254">应用程序显示的消息顺序仅分析和激活。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-254">The application displays the messages that order is only analyzed and activated.</span></span>  
  
9. <span data-ttu-id="bb1b7-255">单击**启动**，依次指向**所有程序**，指向**管理工具**，单击**事件查看器**，然后选中一个新的警告，用户已终止订单。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-255">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the order was terminated by user.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bb1b7-256">有关终止订单的详细信息，请参阅[订单流通过进程管理器](../core/order-flow-through-the-process-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-256">For more information about terminating orders, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
10. <span data-ttu-id="bb1b7-257">检查在命令提示符处运行运营服务器的路由故障错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1b7-257">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb1b7-258">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb1b7-258">See Also</span></span>  
 <span data-ttu-id="bb1b7-259">[安装业务流程管理解决方案之前](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="bb1b7-259">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="bb1b7-260">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="bb1b7-260">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)