---
title: "如何运行业务流程管理解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, validating
- process management solution tutorial, submitting orders
- process management solution tutorial, stopping orders
- process management solution tutorial, updating orders
ms.assetid: cb77651e-e16c-49dc-9f8a-88584cd68a8b
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3997fb18e7498ab2bc5f8c77b53740fb87ab6f93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-run-the-business-process-management-solution"></a><span data-ttu-id="20ead-102">如何运行业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-102">How to Run the Business Process Management Solution</span></span>
<span data-ttu-id="20ead-103">以下步骤介绍了如何在单台计算机上运行和验证业务流程管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="20ead-103">The following steps describe how to run and validate the Business Process Management solution on a single computer.</span></span>  
  
-   [<span data-ttu-id="20ead-104">启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-104">Start the Business Process Management Solution</span></span>](#step1)  
  
-   [<span data-ttu-id="20ead-105">运行和验证业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-105">Run and validate the Business Process Management Solution</span></span>](#step3)  
  
## <a name="prerequisites"></a><span data-ttu-id="20ead-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="20ead-106">Prerequisites</span></span>  
 <span data-ttu-id="20ead-107">在运行之前 BPM 解决方案，你必须执行中的步骤[如何安装业务流程管理解决方案](../core/how-to-install-the-business-process-management-solution.md)。</span><span class="sxs-lookup"><span data-stu-id="20ead-107">Before running the BPM solution, you must perform the steps in [How to Install the Business Process Management Solution](../core/how-to-install-the-business-process-management-solution.md).</span></span>  
  
##  <a name="step1"></a><span data-ttu-id="20ead-108">启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-108">Start the Business Process Management Solution</span></span>  
  
#### <a name="to-start-the-business-process-management-solution"></a><span data-ttu-id="20ead-109">启动业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-109">To start the Business Process Management Solution</span></span>  
  
1.  <span data-ttu-id="20ead-110">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="20ead-110">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="20ead-111">在**BizTalk Server 管理控制台**，展开**BizTalk 组**，展开**平台设置**，展开**主机实例**，右键单击**BizTalkServerApplication**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="20ead-111">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, expand **Platform Settings**, expand **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="20ead-112">在**BizTalk Server 管理控制台**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="20ead-112">In the **BizTalk Server Administration Console**, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
    1.  <span data-ttu-id="20ead-113">右键单击 BTSScn.BPM.MessagingApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="20ead-113">Right-click BTSScn.BPM.MessagingApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    2.  <span data-ttu-id="20ead-114">右键单击 BTSScn.BPM.OrderBrokerApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="20ead-114">Right-click BTSScn.BPM.OrderBrokerApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    3.  <span data-ttu-id="20ead-115">右键单击 BTSScn.BPM.CableOrderApp，单击**启动**，然后单击**启动**上**启动应用程序**对话框。</span><span class="sxs-lookup"><span data-stu-id="20ead-115">Right-click BTSScn.BPM.CableOrderApp, click **Start**, and then click **Start** on the **Start Application** dialog box.</span></span>  
  
    4.  <span data-ttu-id="20ead-116">右键单击 BTSScn.BPM.OrderBrokerApp.Test，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="20ead-116">Right-click BTSScn.BPM.OrderBrokerApp.Test, and click **Stop**.</span></span> <span data-ttu-id="20ead-117">在**停止应用程序**对话框中，选择**完全停止-终止实例**，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="20ead-117">In the **Stop Application** dialog box, select **Full Stop - Terminate instance**, and then click **Stop**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ead-118">若要在历史记录数据库中插入信息。</span><span class="sxs-lookup"><span data-stu-id="20ead-118">To insert information in the history database.</span></span> <span data-ttu-id="20ead-119">OrderBroker 业务流程使用其中的 HistoryPort 发送端口**传递通知**属性设置**传输**。</span><span class="sxs-lookup"><span data-stu-id="20ead-119">the OrderBroker orchestration uses the HistoryPort send port of which the **Delivery Notification** property is set **Transmitted**.</span></span> <span data-ttu-id="20ead-120">该发送端口绑定到 HistoryInsert-SPG 发送组，该组包括 HistoryInsert-SP 和 HistoryInsert-Test-SP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="20ead-120">The send port is bounded to the HistoryInsert-SPG send group which includes the HistoryInsert-SP and HistoryInsert-Test-SP send ports.</span></span> <span data-ttu-id="20ead-121">对于这两个发送端口，消息引擎将向 OrderBroker 业务流程发布两条确认消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-121">For these two send ports the message engine will publish two acknowledgment messages to the OrderBroker orchestration.</span></span> <span data-ttu-id="20ead-122">这会使业务流程因未使用的消息而挂起。</span><span class="sxs-lookup"><span data-stu-id="20ead-122">It makes the orchestration suspended due to unconsumed messages.</span></span> <span data-ttu-id="20ead-123">若要避免这种情况，必须取消登记其中一个发送端口。</span><span class="sxs-lookup"><span data-stu-id="20ead-123">To avoid this situation, you must unenlist one of the send ports.</span></span> <span data-ttu-id="20ead-124">在此演练中，通过完全停止 BTSScn.BPM.OrderBrokerApp.Test 应用程序来取消登记 HistoryInsert-Test-SP 发送端口。</span><span class="sxs-lookup"><span data-stu-id="20ead-124">In this walkthrough, unenlist HistoryInsert-Test-SP send port by fully stopping the BTSScn.BPM.OrderBrokerApp.Test application.</span></span> <span data-ttu-id="20ead-125">有关 OrderBroker 业务流程的详细信息，请参阅[OrderBroker 业务流程中的处理](../core/processing-in-the-orderbroker-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="20ead-125">For more information about the OrderBroker orchestration, see [Processing in the OrderBroker Orchestration](../core/processing-in-the-orderbroker-orchestration.md).</span></span> <span data-ttu-id="20ead-126">有关详细信息**传递通知**属性，请参阅[使用确认](../core/using-acknowledgments.md)。</span><span class="sxs-lookup"><span data-stu-id="20ead-126">For more information about **Delivery Notification** property, see [Using Acknowledgments](../core/using-acknowledgments.md).</span></span>  
  
4.  <span data-ttu-id="20ead-127">按以下步骤运行功能模拟程序：</span><span class="sxs-lookup"><span data-stu-id="20ead-127">Run the Facilities Simulator as follows:</span></span>  
  
    1.  <span data-ttu-id="20ead-128">打开命令提示符，将目录更改为 %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="20ead-128">Open a command prompt, change the directory to the %BTSSolutionsPath%\BPM\FacilitiesSimulator\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="20ead-129">键入 `BTSScnBPMFacilities.exe`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="20ead-129">Type `BTSScnBPMFacilities.exe`, and then press ENTER.</span></span> <span data-ttu-id="20ead-130">使 FacilitiesSimulator 保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="20ead-130">Keep the FacilitiesSimulator running.</span></span> <span data-ttu-id="20ead-131">此应用程序将模拟处理 Southridge Video 后端系统的功能。</span><span class="sxs-lookup"><span data-stu-id="20ead-131">This application simulates the facilities processing back-end systems at Southridge Video.</span></span>  
  
    3.  <span data-ttu-id="20ead-132">在 FacilitiesSimulator 中，键入以下接收和传输队列：</span><span class="sxs-lookup"><span data-stu-id="20ead-132">In the FacilitiesSimulator, type the following receive and transmit queues:</span></span>  
  
        |<span data-ttu-id="20ead-133">Name</span><span class="sxs-lookup"><span data-stu-id="20ead-133">Name</span></span>|<span data-ttu-id="20ead-134">值</span><span class="sxs-lookup"><span data-stu-id="20ead-134">Value</span></span>|  
        |----------|-----------|  
        |<span data-ttu-id="20ead-135">**接收队列**</span><span class="sxs-lookup"><span data-stu-id="20ead-135">**Receive Queue**</span></span>|`.\private$\ToFacilitiesQ`|  
        |<span data-ttu-id="20ead-136">**传输队列**</span><span class="sxs-lookup"><span data-stu-id="20ead-136">**Transmit Queue**</span></span>|`.\private$\FromFacilitiesQ`|  
  
    4.  <span data-ttu-id="20ead-137">在 FacilitiesSimulator，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="20ead-137">In the FacilitiesSimulator, Click **Start**.</span></span>  
  
5.  <span data-ttu-id="20ead-138">按以下步骤运行运营服务器：</span><span class="sxs-lookup"><span data-stu-id="20ead-138">Run the Operation Server as follows:</span></span>  
  
    1.  <span data-ttu-id="20ead-139">打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\OperationsServer\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="20ead-139">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\OperationsServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="20ead-140">类型`BTSScnBPMOperations.exe 8881`在命令提示符，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="20ead-140">Type `BTSScnBPMOperations.exe 8881` at the command prompt, and then press ENTER.</span></span> <span data-ttu-id="20ead-141">使运营服务器保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="20ead-141">Keep the Operation Server running.</span></span> <span data-ttu-id="20ead-142">运营服务器将监听 TCP 端口 8881 以接收来自 Ops 适配器的错误消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-142">The Operation Server listens on the TCP port, 8881, to receive error messages from the Ops Adapter.</span></span> <span data-ttu-id="20ead-143">它将显示 Ops 适配器收到的错误消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-143">It displays the error messages received by the Ops Adapter.</span></span>  
  
6.  <span data-ttu-id="20ead-144">按以下步骤运行宽带提供系统：</span><span class="sxs-lookup"><span data-stu-id="20ead-144">Run the Cable Provisioning System as follows:</span></span>  
  
    1.  <span data-ttu-id="20ead-145">打开新的命令提示符，将当前目录更改为 %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="20ead-145">Open a new command prompt, change the current directory to the %BTSSolutionsPath%\BPM\CableProvisioningSystemServer\bin\debug folder.</span></span>  
  
    2.  <span data-ttu-id="20ead-146">键入 `BTSScnBPMProvisioning.exe 8880`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="20ead-146">Type `BTSScnBPMProvisioning.exe 8880`, and then press ENTER.</span></span> <span data-ttu-id="20ead-147">然后，使宽带提供系统保持运行状态。</span><span class="sxs-lookup"><span data-stu-id="20ead-147">Then, keep the Cable Provisioning System running.</span></span> <span data-ttu-id="20ead-148">电缆设置系统侦听 TCP 端口，8880。</span><span class="sxs-lookup"><span data-stu-id="20ead-148">The Cable Provisioning System listens on the TCP port, 8880.</span></span> <span data-ttu-id="20ead-149">此应用程序模拟的后端顺序系统，并显示最后一个订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-149">This application simulates a back-end order system, and displays the final orders.</span></span>  
  
##  <a name="step3"></a><span data-ttu-id="20ead-150">运行和验证业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-150">Run and validate the Business Process Management Solution</span></span>  
  
#### <a name="to-submit-a-new-order-and-validate-the-solution"></a><span data-ttu-id="20ead-151">提交新订单并验证解决方案</span><span class="sxs-lookup"><span data-stu-id="20ead-151">To submit a new order and validate the solution</span></span>  
  
1.  <span data-ttu-id="20ead-152">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 为如下：</span><span class="sxs-lookup"><span data-stu-id="20ead-152">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="20ead-153">上**南广视频客户服务代表顺序输入窗体**页上，在以下表中，输入新的订单，然后单击**提交订单。**</span><span class="sxs-lookup"><span data-stu-id="20ead-153">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order.**</span></span>  
  
    |<span data-ttu-id="20ead-154">条目</span><span class="sxs-lookup"><span data-stu-id="20ead-154">Entry</span></span>|<span data-ttu-id="20ead-155">值</span><span class="sxs-lookup"><span data-stu-id="20ead-155">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="20ead-156">客户 ID</span><span class="sxs-lookup"><span data-stu-id="20ead-156">Customer ID</span></span>|<span data-ttu-id="20ead-157">1</span><span class="sxs-lookup"><span data-stu-id="20ead-157">1</span></span>|  
    |<span data-ttu-id="20ead-158">Order ID</span><span class="sxs-lookup"><span data-stu-id="20ead-158">Order ID</span></span>|<span data-ttu-id="20ead-159">1</span><span class="sxs-lookup"><span data-stu-id="20ead-159">1</span></span>|  
    |<span data-ttu-id="20ead-160">序列号</span><span class="sxs-lookup"><span data-stu-id="20ead-160">Sequence Number</span></span>|<span data-ttu-id="20ead-161">1</span><span class="sxs-lookup"><span data-stu-id="20ead-161">1</span></span>|  
    |<span data-ttu-id="20ead-162">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="20ead-162">Service Type Code</span></span>|<span data-ttu-id="20ead-163">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="20ead-163">New Standard Service</span></span>|  
  
3.  <span data-ttu-id="20ead-164">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-164">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-165">**客户 ID 1 订单 ID 1 的序列号 1**</span><span class="sxs-lookup"><span data-stu-id="20ead-165">**Customer ID 1 Order ID 1 Sequence Number 1**</span></span>  
  
4.  <span data-ttu-id="20ead-166">在运行宽带提供系统的命令提示符下验证已下订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-166">Validate that the placed order at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="20ead-167">该应用程序将显示已分析、激活并完成提交的订单的消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-167">The application display the messages that the submitted order is analyzed, activated, and then completed.</span></span>  
  
5.  <span data-ttu-id="20ead-168">验证功能模拟程序中的消息总数增量为 1。</span><span class="sxs-lookup"><span data-stu-id="20ead-168">Validate that the number of the total messages is incremented by one on the Facilities Simulator.</span></span>  
  
#### <a name="to-submit-a-duplicate-while-the-biztalk-server-is-processing-the-original-order"></a><span data-ttu-id="20ead-169">在 BizTalk Server 处理原始订单时提交重复订单</span><span class="sxs-lookup"><span data-stu-id="20ead-169">To submit a duplicate while the BizTalk Server is processing the original order</span></span>  
  
1.  <span data-ttu-id="20ead-170">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 为如下：</span><span class="sxs-lookup"><span data-stu-id="20ead-170">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="20ead-171">在 FacilitiesSimulator，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="20ead-171">In the FacilitiesSimulator, click **Stop**.</span></span> <span data-ttu-id="20ead-172">这样将不会进一步处理提交的订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-172">It prevents submitted orders from being processed further.</span></span>  
  
3.  <span data-ttu-id="20ead-173">上**南广视频客户服务代表顺序输入窗体**页上，在以下表中，输入新的订单，然后单击**提交订单**两次以模拟重复的订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-173">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order** twice to simulate duplicated orders.</span></span>  
  
    |<span data-ttu-id="20ead-174">条目</span><span class="sxs-lookup"><span data-stu-id="20ead-174">Entry</span></span>|<span data-ttu-id="20ead-175">值</span><span class="sxs-lookup"><span data-stu-id="20ead-175">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="20ead-176">客户 ID</span><span class="sxs-lookup"><span data-stu-id="20ead-176">Customer ID</span></span>|<span data-ttu-id="20ead-177">2</span><span class="sxs-lookup"><span data-stu-id="20ead-177">2</span></span>|  
    |<span data-ttu-id="20ead-178">Order ID</span><span class="sxs-lookup"><span data-stu-id="20ead-178">Order ID</span></span>|<span data-ttu-id="20ead-179">1</span><span class="sxs-lookup"><span data-stu-id="20ead-179">1</span></span>|  
    |<span data-ttu-id="20ead-180">序列号</span><span class="sxs-lookup"><span data-stu-id="20ead-180">Sequence Number</span></span>|<span data-ttu-id="20ead-181">1</span><span class="sxs-lookup"><span data-stu-id="20ead-181">1</span></span>|  
    |<span data-ttu-id="20ead-182">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="20ead-182">Service Type Code</span></span>|<span data-ttu-id="20ead-183">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="20ead-183">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="20ead-184">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-184">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-185">**客户 ID 2 订单 ID 1 的序列号 1**</span><span class="sxs-lookup"><span data-stu-id="20ead-185">**Customer ID 2 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="20ead-186">在 FacilitiesSimulator，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="20ead-186">In the FacilitiesSimulator, click **Start**.</span></span> <span data-ttu-id="20ead-187">将会恢复等待来自功能模拟程序的响应的业务流程。</span><span class="sxs-lookup"><span data-stu-id="20ead-187">The orchestrations waiting for the responses from the Facilities Simulator will resume.</span></span> <span data-ttu-id="20ead-188">在处理第一个订单时该程序将模拟提交一个重复的订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-188">It simulates that a duplicate order is submitted while the first order is being processed.</span></span>  
  
6.  <span data-ttu-id="20ead-189">在运行宽带提供系统的命令提示符下检查已下订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-189">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="20ead-190">该应用程序将显示有关仅分析、激活并完成了第一个订单的消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-190">The application displays the messages that only the first order is analyzed, activated, and then completed.</span></span>  
  
7.  <span data-ttu-id="20ead-191">在运行运营服务器的命令提示符下检查重复订单的错误消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-191">Check the error message for the duplicated orders at the command prompt running the Operation Server.</span></span>  
  
#### <a name="to-update-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="20ead-192">在 BizTalk Server 处理订单时更新订单</span><span class="sxs-lookup"><span data-stu-id="20ead-192">To update an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="20ead-193">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 为如下：</span><span class="sxs-lookup"><span data-stu-id="20ead-193">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="20ead-194">在 FacilitiesSimulator，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="20ead-194">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="20ead-195">上**南广视频客户服务代表顺序输入窗体**页上，在以下表中，输入新的订单，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="20ead-195">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="20ead-196">条目</span><span class="sxs-lookup"><span data-stu-id="20ead-196">Entry</span></span>|<span data-ttu-id="20ead-197">值</span><span class="sxs-lookup"><span data-stu-id="20ead-197">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="20ead-198">客户 ID</span><span class="sxs-lookup"><span data-stu-id="20ead-198">Customer ID</span></span>|<span data-ttu-id="20ead-199">3</span><span class="sxs-lookup"><span data-stu-id="20ead-199">3</span></span>|  
    |<span data-ttu-id="20ead-200">Order ID</span><span class="sxs-lookup"><span data-stu-id="20ead-200">Order ID</span></span>|<span data-ttu-id="20ead-201">1</span><span class="sxs-lookup"><span data-stu-id="20ead-201">1</span></span>|  
    |<span data-ttu-id="20ead-202">序列号</span><span class="sxs-lookup"><span data-stu-id="20ead-202">Sequence Number</span></span>|<span data-ttu-id="20ead-203">1</span><span class="sxs-lookup"><span data-stu-id="20ead-203">1</span></span>|  
    |<span data-ttu-id="20ead-204">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="20ead-204">Service Type Code</span></span>|<span data-ttu-id="20ead-205">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="20ead-205">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="20ead-206">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-206">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-207">**客户 ID 3 订单 ID 1 的序列号 1**</span><span class="sxs-lookup"><span data-stu-id="20ead-207">**Customer ID 3 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="20ead-208">上**南广视频客户服务代表顺序输入窗体**页上，在以下表中，输入更新的顺序，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="20ead-208">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter an updated order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="20ead-209">条目</span><span class="sxs-lookup"><span data-stu-id="20ead-209">Entry</span></span>|<span data-ttu-id="20ead-210">值</span><span class="sxs-lookup"><span data-stu-id="20ead-210">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="20ead-211">客户 ID</span><span class="sxs-lookup"><span data-stu-id="20ead-211">Customer ID</span></span>|<span data-ttu-id="20ead-212">3</span><span class="sxs-lookup"><span data-stu-id="20ead-212">3</span></span>|  
    |<span data-ttu-id="20ead-213">Order ID</span><span class="sxs-lookup"><span data-stu-id="20ead-213">Order ID</span></span>|<span data-ttu-id="20ead-214">1</span><span class="sxs-lookup"><span data-stu-id="20ead-214">1</span></span>|  
    |<span data-ttu-id="20ead-215">序列号</span><span class="sxs-lookup"><span data-stu-id="20ead-215">Sequence Number</span></span>|<span data-ttu-id="20ead-216">2</span><span class="sxs-lookup"><span data-stu-id="20ead-216">2</span></span>|  
    |<span data-ttu-id="20ead-217">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="20ead-217">Service Type Code</span></span>|<span data-ttu-id="20ead-218">新的高级服务</span><span class="sxs-lookup"><span data-stu-id="20ead-218">New Deluxe Service</span></span>|  
  
6.  <span data-ttu-id="20ead-219">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-219">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-220">**客户 ID 3 订单 ID 1 的序列号 2**</span><span class="sxs-lookup"><span data-stu-id="20ead-220">**Customer ID 3 Order ID 1 Sequence Number 2**</span></span>  
  
7.  <span data-ttu-id="20ead-221">在 FacilitiesSimulator，单击**启动**</span><span class="sxs-lookup"><span data-stu-id="20ead-221">In the FacilitiesSimulator, click **Start**</span></span>  
  
8.  <span data-ttu-id="20ead-222">检查结果消息**南广视频客户服务代表顺序输入窗体**页。</span><span class="sxs-lookup"><span data-stu-id="20ead-222">Check the result message on the **Southridge Video Customer Service Rep Order Entry Form** page.</span></span>  
  
9. <span data-ttu-id="20ead-223">在运行宽带提供系统的命令提示符下检查已下订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-223">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="20ead-224">该应用程序将显示已分析两个订单但仅激活和完成了更新的订单的消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-224">The application displays the messages that two orders are analyzed, but only the updated order is activated and completed.</span></span>  
  
10. <span data-ttu-id="20ead-225">单击**启动**，指向**所有程序**，指向**管理工具**，单击**事件查看器**，，然后检查一个新的警告，已中断，原始顺序。</span><span class="sxs-lookup"><span data-stu-id="20ead-225">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the original order was interrupted.</span></span>  
  
11. <span data-ttu-id="20ead-226">在运行运营服务器的命令提示符下检查路由故障错误消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-226">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ead-227">事件日志和运营服务器中将出现错误。</span><span class="sxs-lookup"><span data-stu-id="20ead-227">There will be an error in the event log and in the operations server.</span></span> <span data-ttu-id="20ead-228">来自功能系统的响应消息不再与业务流程实例相关，因为具有更高序列号的新订单所导致的中断已终止该消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-228">The response message from the Facilities System no longer correlates back to an instance of the business process as it was terminated by the interruption caused by the new order with a higher sequence number.</span></span> <span data-ttu-id="20ead-229">因此，该响应消息是孤立消息并将路由到运营服务器。</span><span class="sxs-lookup"><span data-stu-id="20ead-229">Therefore response message is orphaned and will get routed to the operations server.</span></span> <span data-ttu-id="20ead-230">有关顺序更新的详细信息，请参阅[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="20ead-230">For more information about order updates, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
12. <span data-ttu-id="20ead-231">使用记事本打开 %SystemDrive%:\BPMTest\HistoryUpdate-SP 文件夹中的最新消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-231">Open the latest message in the %SystemDrive%:\BPMTest\HistoryUpdate-SP folder with Notepad.</span></span> <span data-ttu-id="20ead-232">检查**CustName**， **OrderNum**， **OrderSeqNum**，和**状态**域，以查看该消息是否已创建新订单和**状态**字段是**已完成**。</span><span class="sxs-lookup"><span data-stu-id="20ead-232">Check **CustName**, **OrderNum**, **OrderSeqNum**, and **Status** fields to see if the message has been created for the new order and the **Status** field is **COMPLETED**.</span></span>  
  
#### <a name="to-terminate-an-order-while-the-biztalk-server-is-processing-the-order"></a><span data-ttu-id="20ead-233">在 BizTalk Server 处理订单时终止订单</span><span class="sxs-lookup"><span data-stu-id="20ead-233">To terminate an order while the BizTalk Server is processing the order</span></span>  
  
1.  <span data-ttu-id="20ead-234">在 Internet Explorer 中，在**地址**框中，键入客户服务 Web 应用程序的 URL 为如下：</span><span class="sxs-lookup"><span data-stu-id="20ead-234">In Internet Explorer, in the **Address** box, type the URL for the Customer Service Web application as following:</span></span>  
  
    -   `http://localhost/CSRWebApp/CSRMainForm.aspx`  
  
2.  <span data-ttu-id="20ead-235">在 FacilitiesSimulator，单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="20ead-235">In the FacilitiesSimulator, click **Stop**.</span></span>  
  
3.  <span data-ttu-id="20ead-236">上**南广视频客户服务代表顺序输入窗体**页上，在以下表中，输入新的订单，然后单击**提交订单**。</span><span class="sxs-lookup"><span data-stu-id="20ead-236">On the **Southridge Video Customer Service Rep Order Entry Form** page, enter a new order in the following table, and then click **Submit Order**.</span></span>  
  
    |<span data-ttu-id="20ead-237">条目</span><span class="sxs-lookup"><span data-stu-id="20ead-237">Entry</span></span>|<span data-ttu-id="20ead-238">值</span><span class="sxs-lookup"><span data-stu-id="20ead-238">Value</span></span>|  
    |-----------|-----------|  
    |<span data-ttu-id="20ead-239">客户 ID</span><span class="sxs-lookup"><span data-stu-id="20ead-239">Customer ID</span></span>|<span data-ttu-id="20ead-240">4</span><span class="sxs-lookup"><span data-stu-id="20ead-240">4</span></span>|  
    |<span data-ttu-id="20ead-241">Order ID</span><span class="sxs-lookup"><span data-stu-id="20ead-241">Order ID</span></span>|<span data-ttu-id="20ead-242">1</span><span class="sxs-lookup"><span data-stu-id="20ead-242">1</span></span>|  
    |<span data-ttu-id="20ead-243">序列号</span><span class="sxs-lookup"><span data-stu-id="20ead-243">Sequence Number</span></span>|<span data-ttu-id="20ead-244">1</span><span class="sxs-lookup"><span data-stu-id="20ead-244">1</span></span>|  
    |<span data-ttu-id="20ead-245">服务类型代码</span><span class="sxs-lookup"><span data-stu-id="20ead-245">Service Type Code</span></span>|<span data-ttu-id="20ead-246">新的标准服务</span><span class="sxs-lookup"><span data-stu-id="20ead-246">New Standard Service</span></span>|  
  
4.  <span data-ttu-id="20ead-247">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-247">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-248">**客户 ID 4 订单 ID 1 的序列号 1**</span><span class="sxs-lookup"><span data-stu-id="20ead-248">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
5.  <span data-ttu-id="20ead-249">上**南广视频客户服务代表顺序输入窗体**页上，单击**终止顺序**。</span><span class="sxs-lookup"><span data-stu-id="20ead-249">On the **Southridge Video Customer Service Rep Order Entry Form** page, click **Terminate Order**.</span></span>  
  
6.  <span data-ttu-id="20ead-250">上**南广视频客户服务代表顺序输入窗体**页上，结果消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20ead-250">On the **Southridge Video Customer Service Rep Order Entry Form** page, the result message as follows:</span></span>  
  
     <span data-ttu-id="20ead-251">**客户 ID 4 订单 ID 1 的序列号 1**</span><span class="sxs-lookup"><span data-stu-id="20ead-251">**Customer ID 4 Order ID 1 Sequence Number 1**</span></span>  
  
7.  <span data-ttu-id="20ead-252">在 FacilitiesSimulator，单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="20ead-252">In the FacilitiesSimulator, click **Start**.</span></span>  
  
8.  <span data-ttu-id="20ead-253">在运行宽带提供系统的命令提示符下检查已下订单。</span><span class="sxs-lookup"><span data-stu-id="20ead-253">Check the placed orders at the command prompt running the Cable Provisioning System.</span></span> <span data-ttu-id="20ead-254">该应用程序将显示仅分析和激活该订单的消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-254">The application displays the messages that order is only analyzed and activated.</span></span>  
  
9. <span data-ttu-id="20ead-255">单击**启动**，指向**所有程序**，指向**管理工具**，单击**事件查看器**，，然后检查一个新的警告，顺序被用户终止。</span><span class="sxs-lookup"><span data-stu-id="20ead-255">Click **Start**, point to **All Programs**, point to **Administrative Tools**, click **Event Viewer**, and then check a new warning that the order was terminated by user.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="20ead-256">有关终止订单的详细信息，请参阅[顺序流通过进程管理器](../core/order-flow-through-the-process-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="20ead-256">For more information about terminating orders, see [Order Flow through the Process Manager](../core/order-flow-through-the-process-manager.md).</span></span>  
  
10. <span data-ttu-id="20ead-257">在运行运营服务器的命令提示符下检查路由故障错误消息。</span><span class="sxs-lookup"><span data-stu-id="20ead-257">Checked the routing failure error message at the command prompt running the Operation Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ead-258">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20ead-258">See Also</span></span>  
 <span data-ttu-id="20ead-259">[在安装业务流程管理解决方案之前](../core/before-installing-the-business-process-management-solution.md) </span><span class="sxs-lookup"><span data-stu-id="20ead-259">[Before Installing the Business Process Management Solution](../core/before-installing-the-business-process-management-solution.md) </span></span>  
 [<span data-ttu-id="20ead-260">业务流程管理解决方案的开发人员计算机设置</span><span class="sxs-lookup"><span data-stu-id="20ead-260">Developer Machine Setup for the Business Process Management Solution</span></span>](../core/developer-machine-setup-for-the-business-process-management-solution.md)