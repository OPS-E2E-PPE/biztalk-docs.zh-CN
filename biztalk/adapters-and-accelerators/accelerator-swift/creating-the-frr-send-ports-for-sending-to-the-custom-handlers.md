---
title: 创建 FRR 发送端口将发送到自定义处理程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, send ports
- send ports, creating
- FRR, creating send ports
ms.assetid: 036f1f97-17a2-4e02-a85a-a52739a48528
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6326ae6e82e819d3cdf76ecc4d81e2a377ea65
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966539"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="71fd3-102">创建 FRR 发送端口将发送到自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="71fd3-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="71fd3-103">若要执行 FIN 响应对帐，你需要创建一系列发送端口，其中每个发送一条消息 （原始消息或响应） 从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到处理相关的消息的自定义处理程序。</span><span class="sxs-lookup"><span data-stu-id="71fd3-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  
  
 <span data-ttu-id="71fd3-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="71fd3-104">**Summary**</span></span>  
  
 <span data-ttu-id="71fd3-105">创建具有以下属性和组件，按照 BTS 值区分每个发送端口的一系列。筛选器中的操作：</span><span class="sxs-lookup"><span data-stu-id="71fd3-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  
  
|<span data-ttu-id="71fd3-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="71fd3-106">Property/Component</span></span>|<span data-ttu-id="71fd3-107">设置</span><span class="sxs-lookup"><span data-stu-id="71fd3-107">Setting</span></span>|  
|-------------------------|-------------|  
|<span data-ttu-id="71fd3-108">发送端口</span><span class="sxs-lookup"><span data-stu-id="71fd3-108">Send port</span></span>|<span data-ttu-id="71fd3-109">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="71fd3-109">Static one-way port</span></span>|  
|<span data-ttu-id="71fd3-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="71fd3-110">Transport type</span></span>|<span data-ttu-id="71fd3-111">FILE</span><span class="sxs-lookup"><span data-stu-id="71fd3-111">FILE</span></span>|  
|<span data-ttu-id="71fd3-112">目标文件夹 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="71fd3-112">Destination folder (Address URI)</span></span>|<span data-ttu-id="71fd3-113">你想要将消息发送到文件夹</span><span class="sxs-lookup"><span data-stu-id="71fd3-113">The folder that you want to send the message to</span></span>|  
|<span data-ttu-id="71fd3-114">文件名称 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="71fd3-114">File name (Address URI)</span></span>|<span data-ttu-id="71fd3-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="71fd3-115">%MessageID%.txt</span></span>|  
|<span data-ttu-id="71fd3-116">发送管道</span><span class="sxs-lookup"><span data-stu-id="71fd3-116">Send pipeline</span></span>|[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="71fd3-117">.BizTalk.DefaultPipelines。</span><span class="sxs-lookup"><span data-stu-id="71fd3-117">.BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="71fd3-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="71fd3-118">PassThruTransmit</span></span>|  
|<span data-ttu-id="71fd3-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="71fd3-119">Filters</span></span>|<span data-ttu-id="71fd3-120">下表中所示</span><span class="sxs-lookup"><span data-stu-id="71fd3-120">As shown in the tables below</span></span>|  
  
 <span data-ttu-id="71fd3-121">通过 BTS 的值来区分不同的消息的发送端口。发送端口的筛选器中的操作。</span><span class="sxs-lookup"><span data-stu-id="71fd3-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  
  
### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="71fd3-122">若要添加 FRR 发送端口将发送到自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="71fd3-122">To add FRR send ports for sending to the custom handlers</span></span>  
  
1.  <span data-ttu-id="71fd3-123">在 BizTalk Server 管理控制台中，右键单击**发送端口**，指向**新建**，然后单击**静态一个 waySend 端口**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  
  
2.  <span data-ttu-id="71fd3-124">在发送端口属性对话框中，在**名称**框中，键入发送端口，如 FRRCustomHandlersSendPort 的名称。</span><span class="sxs-lookup"><span data-stu-id="71fd3-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  
  
3.  <span data-ttu-id="71fd3-125">有关**类型**，选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-125">For **Type**, select **FILE**.</span></span>  
  
4.  <span data-ttu-id="71fd3-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-126">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="71fd3-127">在文件传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  
  
6.  <span data-ttu-id="71fd3-128">在浏览文件夹对话框中，移动到你想要从发送消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="71fd3-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="71fd3-129">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-129">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71fd3-130">如果此文件夹不存在，则可以创建使用**新建文件夹**命令。</span><span class="sxs-lookup"><span data-stu-id="71fd3-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  
  
7.  <span data-ttu-id="71fd3-131">在**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71fd3-132">你可以创建用于每种类型的消息的不同文件夹。</span><span class="sxs-lookup"><span data-stu-id="71fd3-132">You can create a different folder for each type of message.</span></span>  
  
8.  <span data-ttu-id="71fd3-133">在发送端口属性对话框中的发送处理程序，验证**BizTalkServerApplication**选择。</span><span class="sxs-lookup"><span data-stu-id="71fd3-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  
  
9. <span data-ttu-id="71fd3-134">有关**发送管道**，选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  
  
10. <span data-ttu-id="71fd3-135">单击**筛选器**在左窗格中，然后再执行以下：</span><span class="sxs-lookup"><span data-stu-id="71fd3-135">Click **Filters** in the left pane, and then do the following:</span></span>  
  
    |<span data-ttu-id="71fd3-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="71fd3-136">Use this</span></span>|<span data-ttu-id="71fd3-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="71fd3-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="71fd3-138">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-138">**Property**</span></span>|<span data-ttu-id="71fd3-139">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="71fd3-140">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-140">**Operator**</span></span>|<span data-ttu-id="71fd3-141">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-141">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-142">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-142">**Value**</span></span>|<span data-ttu-id="71fd3-143">类型**A4SWIFT_FrrService**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="71fd3-144">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-144">**Group**</span></span>|<span data-ttu-id="71fd3-145">**And**</span><span class="sxs-lookup"><span data-stu-id="71fd3-145">**And**</span></span>|  
    |<span data-ttu-id="71fd3-146">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-146">**Property**</span></span>|<span data-ttu-id="71fd3-147">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="71fd3-148">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-148">**Operator**</span></span>|<span data-ttu-id="71fd3-149">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-149">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-150">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-150">**Value**</span></span>|<span data-ttu-id="71fd3-151">BTS 之一的类型。下表中的操作值。</span><span class="sxs-lookup"><span data-stu-id="71fd3-151">Type one of the BTS.Operation values from the table below.</span></span>|  
  
     <span data-ttu-id="71fd3-152">有关 BTS。操作中，输入以下值之一：</span><span class="sxs-lookup"><span data-stu-id="71fd3-152">For BTS.Operation, enter one of the following values:</span></span>  
  
    |<span data-ttu-id="71fd3-153">消息类型</span><span class="sxs-lookup"><span data-stu-id="71fd3-153">Message type</span></span>|<span data-ttu-id="71fd3-154">BTS。操作值</span><span class="sxs-lookup"><span data-stu-id="71fd3-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="71fd3-155">所有类别 0 到 9 SWIFT FIN 消息类型</span><span class="sxs-lookup"><span data-stu-id="71fd3-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="71fd3-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="71fd3-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="71fd3-157">MQ 系列平移/NAN （MQ 系列传输级 ACK/否认）</span><span class="sxs-lookup"><span data-stu-id="71fd3-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="71fd3-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="71fd3-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="71fd3-159">MT010 （未送达警告）</span><span class="sxs-lookup"><span data-stu-id="71fd3-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="71fd3-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="71fd3-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="71fd3-161">MT011 （传递通知）</span><span class="sxs-lookup"><span data-stu-id="71fd3-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="71fd3-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="71fd3-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="71fd3-163">MT012 （发件人通知）</span><span class="sxs-lookup"><span data-stu-id="71fd3-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="71fd3-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="71fd3-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="71fd3-165">MT015 （DNK 或延迟的否认）</span><span class="sxs-lookup"><span data-stu-id="71fd3-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="71fd3-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="71fd3-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="71fd3-167">MT019 （中止通知）</span><span class="sxs-lookup"><span data-stu-id="71fd3-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="71fd3-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="71fd3-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="71fd3-169">MTS21_FIN_ACKNAK （发送由 LT (ACK) 的 FIN 消息的确认</span><span class="sxs-lookup"><span data-stu-id="71fd3-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="71fd3-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="71fd3-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="71fd3-171">MTS21_FIN_ACKNAK （否定确认发送由 LT （否认） 的 FIN 消息的</span><span class="sxs-lookup"><span data-stu-id="71fd3-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="71fd3-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="71fd3-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  
  
11. <span data-ttu-id="71fd3-173">为类别 0 到 9 SWIFT FIN 成功不发送的消息执行以下**筛选器**窗格中：</span><span class="sxs-lookup"><span data-stu-id="71fd3-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="71fd3-174">**A4SWIFT_FRRFailedReason**应分组中的以下筛选器的属性。</span><span class="sxs-lookup"><span data-stu-id="71fd3-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  
  
    |<span data-ttu-id="71fd3-175">使用此选项</span><span class="sxs-lookup"><span data-stu-id="71fd3-175">Use this</span></span>|<span data-ttu-id="71fd3-176">执行的操作</span><span class="sxs-lookup"><span data-stu-id="71fd3-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="71fd3-177">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-177">**Property**</span></span>|<span data-ttu-id="71fd3-178">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="71fd3-179">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-179">**Operator**</span></span>|<span data-ttu-id="71fd3-180">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-180">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-181">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-181">**Value**</span></span>|<span data-ttu-id="71fd3-182">类型**A4SWIFT_FrrService**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="71fd3-183">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-183">**Group**</span></span>|<span data-ttu-id="71fd3-184">**And**</span><span class="sxs-lookup"><span data-stu-id="71fd3-184">**And**</span></span>|  
    |<span data-ttu-id="71fd3-185">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-185">**Property**</span></span>|<span data-ttu-id="71fd3-186">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="71fd3-187">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-187">**Operator**</span></span>|<span data-ttu-id="71fd3-188">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-188">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-189">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-189">**Value**</span></span>|<span data-ttu-id="71fd3-190">类型**True**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-190">Type **True**.</span></span>|  
    |<span data-ttu-id="71fd3-191">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-191">**Group**</span></span>|<span data-ttu-id="71fd3-192">**And**</span><span class="sxs-lookup"><span data-stu-id="71fd3-192">**And**</span></span>|  
    |<span data-ttu-id="71fd3-193">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-193">**Property**</span></span>|<span data-ttu-id="71fd3-194">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="71fd3-195">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-195">**Operator**</span></span>|<span data-ttu-id="71fd3-196">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-196">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-197">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-197">**Value**</span></span>|<span data-ttu-id="71fd3-198">类型**A4SWIFT_FrrSendMTMsg**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="71fd3-199">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-199">**Group**</span></span>|<span data-ttu-id="71fd3-200">**And**</span><span class="sxs-lookup"><span data-stu-id="71fd3-200">**And**</span></span>|  
    |<span data-ttu-id="71fd3-201">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-201">**Property**</span></span>|<span data-ttu-id="71fd3-202">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="71fd3-203">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-203">**Operator**</span></span>|<span data-ttu-id="71fd3-204">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-204">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-205">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-205">**Value**</span></span>|<span data-ttu-id="71fd3-206">类型 *\<NAKErrorCode\>*，如"Y01"。</span><span class="sxs-lookup"><span data-stu-id="71fd3-206">Type *\<NAKErrorCode\>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="71fd3-207">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-207">**Group**</span></span>|<span data-ttu-id="71fd3-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="71fd3-208">**Or**</span></span>|  
    |<span data-ttu-id="71fd3-209">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-209">**Property**</span></span>|<span data-ttu-id="71fd3-210">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="71fd3-211">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-211">**Operator**</span></span>|<span data-ttu-id="71fd3-212">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-212">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-213">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-213">**Value**</span></span>|<span data-ttu-id="71fd3-214">类型**TimedOut**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="71fd3-215">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-215">**Group**</span></span>|<span data-ttu-id="71fd3-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="71fd3-216">**Or**</span></span>|  
    |<span data-ttu-id="71fd3-217">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-217">**Property**</span></span>|<span data-ttu-id="71fd3-218">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="71fd3-219">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-219">**Operator**</span></span>|<span data-ttu-id="71fd3-220">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-220">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-221">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-221">**Value**</span></span>|<span data-ttu-id="71fd3-222">类型**TransportError**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="71fd3-223">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-223">**Group**</span></span>|<span data-ttu-id="71fd3-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="71fd3-224">**Or**</span></span>|  
    |<span data-ttu-id="71fd3-225">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-225">**Property**</span></span>|<span data-ttu-id="71fd3-226">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="71fd3-227">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-227">**Operator**</span></span>|<span data-ttu-id="71fd3-228">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-228">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-229">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-229">**Value**</span></span>|<span data-ttu-id="71fd3-230">类型**DelayedNAK**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="71fd3-231">**分组**</span><span class="sxs-lookup"><span data-stu-id="71fd3-231">**Group**</span></span>|<span data-ttu-id="71fd3-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="71fd3-232">**Or**</span></span>|  
    |<span data-ttu-id="71fd3-233">**属性**</span><span class="sxs-lookup"><span data-stu-id="71fd3-233">**Property**</span></span>|<span data-ttu-id="71fd3-234">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="71fd3-235">**运算符**</span><span class="sxs-lookup"><span data-stu-id="71fd3-235">**Operator**</span></span>|<span data-ttu-id="71fd3-236">选择 **==** 。</span><span class="sxs-lookup"><span data-stu-id="71fd3-236">Select **==**.</span></span>|  
    |<span data-ttu-id="71fd3-237">**值**</span><span class="sxs-lookup"><span data-stu-id="71fd3-237">**Value**</span></span>|<span data-ttu-id="71fd3-238">类型**AbortMessage**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-238">Type **AbortMessage**.</span></span>|  
  
12. <span data-ttu-id="71fd3-239">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-239">Click **Apply**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="71fd3-240">发送端口中，右键单击，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="71fd3-240">Right-click the send port, and then click **Start**.</span></span>  
  
14. <span data-ttu-id="71fd3-241">重复步骤 2 至 13 以创建所需的每种消息类型发送端口。</span><span class="sxs-lookup"><span data-stu-id="71fd3-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>