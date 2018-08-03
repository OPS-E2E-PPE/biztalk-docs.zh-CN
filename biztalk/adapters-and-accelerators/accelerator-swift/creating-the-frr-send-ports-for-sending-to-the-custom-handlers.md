---
title: 创建 FRR 发送端口将发送到自定义处理程序 |Microsoft Docs
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
ms.openlocfilehash: ed467b149674580b9ed8921a59433c5402a24a0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013934"
---
# <a name="creating-the-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="f1fec-102">创建 FRR 发送端口将发送到自定义处理程序</span><span class="sxs-lookup"><span data-stu-id="f1fec-102">Creating the FRR Send Ports for Sending to the Custom Handlers</span></span>
<span data-ttu-id="f1fec-103">若要执行 FIN 响应对帐，需要创建一系列的发送端口，其中每个将发送一条消息 （原始消息或响应） 从[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到的自定义处理程序处理相关的消息。</span><span class="sxs-lookup"><span data-stu-id="f1fec-103">To perform FIN Response Reconciliation, you need to create a series of send ports, each of which sends a message (original message or response) from [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to the custom handlers that process the correlated messages.</span></span>  

 <span data-ttu-id="f1fec-104">**摘要**</span><span class="sxs-lookup"><span data-stu-id="f1fec-104">**Summary**</span></span>  

 <span data-ttu-id="f1fec-105">创建具有以下属性和组件，BTS 值进行区分每个发送端口的一系列。在筛选器中的操作：</span><span class="sxs-lookup"><span data-stu-id="f1fec-105">Create a series of send ports with the following properties and components, each one distinguished by the value of BTS.Operation in the filter:</span></span>  


|        <span data-ttu-id="f1fec-106">属性 / 组件</span><span class="sxs-lookup"><span data-stu-id="f1fec-106">Property/Component</span></span>        |                                             <span data-ttu-id="f1fec-107">设置</span><span class="sxs-lookup"><span data-stu-id="f1fec-107">Setting</span></span>                                              |
|----------------------------------|--------------------------------------------------------------------------------------------------|
|            <span data-ttu-id="f1fec-108">发送端口</span><span class="sxs-lookup"><span data-stu-id="f1fec-108">Send port</span></span>             |                                       <span data-ttu-id="f1fec-109">静态单向端口</span><span class="sxs-lookup"><span data-stu-id="f1fec-109">Static one-way port</span></span>                                        |
|          <span data-ttu-id="f1fec-110">传输类型</span><span class="sxs-lookup"><span data-stu-id="f1fec-110">Transport type</span></span>          |                                               <span data-ttu-id="f1fec-111">FILE</span><span class="sxs-lookup"><span data-stu-id="f1fec-111">FILE</span></span>                                               |
| <span data-ttu-id="f1fec-112">目标文件夹 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="f1fec-112">Destination folder (Address URI)</span></span> |                         <span data-ttu-id="f1fec-113">你想要发送到的文件夹</span><span class="sxs-lookup"><span data-stu-id="f1fec-113">The folder that you want to send the message to</span></span>                          |
|     <span data-ttu-id="f1fec-114">文件名 (地址 URI)</span><span class="sxs-lookup"><span data-stu-id="f1fec-114">File name (Address URI)</span></span>      |                                         <span data-ttu-id="f1fec-115">%MessageID%.txt</span><span class="sxs-lookup"><span data-stu-id="f1fec-115">%MessageID%.txt</span></span>                                          |
|          <span data-ttu-id="f1fec-116">发送管道</span><span class="sxs-lookup"><span data-stu-id="f1fec-116">Send pipeline</span></span>           | <span data-ttu-id="f1fec-117">Microsoft。BizTalk.DefaultPipelines。</span><span class="sxs-lookup"><span data-stu-id="f1fec-117">Microsoft .BizTalk.DefaultPipelines.</span></span> <span data-ttu-id="f1fec-118">PassThruTransmit</span><span class="sxs-lookup"><span data-stu-id="f1fec-118">PassThruTransmit</span></span> |
|             <span data-ttu-id="f1fec-119">筛选器</span><span class="sxs-lookup"><span data-stu-id="f1fec-119">Filters</span></span>              |                                   <span data-ttu-id="f1fec-120">下表中所示</span><span class="sxs-lookup"><span data-stu-id="f1fec-120">As shown in the tables below</span></span>                                   |

 <span data-ttu-id="f1fec-121">通过 BTS 的值来区分不同的消息的发送端口。发送端口的筛选器中的操作。</span><span class="sxs-lookup"><span data-stu-id="f1fec-121">The send ports for the different messages are distinguished by the value of BTS.Operation in the send port's filter.</span></span>  

### <a name="to-add-frr-send-ports-for-sending-to-the-custom-handlers"></a><span data-ttu-id="f1fec-122">若要添加用于将发送到自定义处理程序的 FRR 发送端口</span><span class="sxs-lookup"><span data-stu-id="f1fec-122">To add FRR send ports for sending to the custom handlers</span></span>  

1.  <span data-ttu-id="f1fec-123">在 BizTalk Server 管理控制台中，右键单击**发送端口**，依次指向**新建**，然后单击**静态一个 waySend 端口**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-123">In the BizTalk Server Administration Console, right-click **Send Ports**, point to **New**, and then click **Static One-waySend Port**.</span></span>  

2.  <span data-ttu-id="f1fec-124">在发送端口属性对话框中，在**名称**框中，键入发送端口，例如 FRRCustomHandlersSendPort 的名称。</span><span class="sxs-lookup"><span data-stu-id="f1fec-124">In the Send Port Properties dialog box, in the **Name** box, type a name for the send port, such as FRRCustomHandlersSendPort.</span></span>  

3.  <span data-ttu-id="f1fec-125">有关**类型**，选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-125">For **Type**, select **FILE**.</span></span>  

4.  <span data-ttu-id="f1fec-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-126">Click **Configure**.</span></span>  

5.  <span data-ttu-id="f1fec-127">在 FILE 传输属性对话框中，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-127">In the FILE Transport Properties dialog box, click **Browse**.</span></span>  

6.  <span data-ttu-id="f1fec-128">在浏览文件夹对话框中，转至你想要从发送消息的文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1fec-128">In the Browse For Folder dialog box, move to the folder that you want to send messages from.</span></span> <span data-ttu-id="f1fec-129">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="f1fec-129">Click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f1fec-130">如果此文件夹不存在，则可以创建使用其**建立新文件夹**命令。</span><span class="sxs-lookup"><span data-stu-id="f1fec-130">If this folder does not exist, you can create it using the **Make New Folder** command.</span></span>  

7.  <span data-ttu-id="f1fec-131">在中**文件名**框中，键入 **%MessageID%.txt**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-131">In the **File name** box, type **%MessageID%.txt**, and then click **OK**.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f1fec-132">可以创建每种类型的消息的不同文件夹。</span><span class="sxs-lookup"><span data-stu-id="f1fec-132">You can create a different folder for each type of message.</span></span>  

8.  <span data-ttu-id="f1fec-133">在发送端口属性对话框中，对于发送处理程序，验证是否**BizTalkServerApplication**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="f1fec-133">In the Send Port Properties dialog box, for Send handler, verify that **BizTalkServerApplication** is selected.</span></span>  

9. <span data-ttu-id="f1fec-134">有关**发送管道**，选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-134">For **Send Pipeline**, select **PassThruTransmit**.</span></span>  

10. <span data-ttu-id="f1fec-135">单击**筛选器**中左窗格中，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f1fec-135">Click **Filters** in the left pane, and then do the following:</span></span>  

    |<span data-ttu-id="f1fec-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f1fec-136">Use this</span></span>|<span data-ttu-id="f1fec-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f1fec-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f1fec-138">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-138">**Property**</span></span>|<span data-ttu-id="f1fec-139">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-139">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="f1fec-140">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-140">**Operator**</span></span>|<span data-ttu-id="f1fec-141">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-141">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-142">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-142">**Value**</span></span>|<span data-ttu-id="f1fec-143">类型**A4SWIFT_FrrService**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-143">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="f1fec-144">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-144">**Group**</span></span>|<span data-ttu-id="f1fec-145">**And**</span><span class="sxs-lookup"><span data-stu-id="f1fec-145">**And**</span></span>|  
    |<span data-ttu-id="f1fec-146">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-146">**Property**</span></span>|<span data-ttu-id="f1fec-147">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-147">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="f1fec-148">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-148">**Operator**</span></span>|<span data-ttu-id="f1fec-149">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-149">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-150">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-150">**Value**</span></span>|<span data-ttu-id="f1fec-151">一个 BTS 的类型。下表中的操作值。</span><span class="sxs-lookup"><span data-stu-id="f1fec-151">Type one of the BTS.Operation values from the table below.</span></span>|  

     <span data-ttu-id="f1fec-152">为 BTS。操作中，输入以下值之一：</span><span class="sxs-lookup"><span data-stu-id="f1fec-152">For BTS.Operation, enter one of the following values:</span></span>  

    |<span data-ttu-id="f1fec-153">消息类型</span><span class="sxs-lookup"><span data-stu-id="f1fec-153">Message type</span></span>|<span data-ttu-id="f1fec-154">BTS。操作值</span><span class="sxs-lookup"><span data-stu-id="f1fec-154">BTS.Operation value</span></span>|  
    |------------------|-------------------------|  
    |<span data-ttu-id="f1fec-155">所有类别 0 到 9 SWIFT FIN 消息类型</span><span class="sxs-lookup"><span data-stu-id="f1fec-155">All Category 0 to 9 SWIFT FIN message types</span></span>|<span data-ttu-id="f1fec-156">**A4SWIFT_FrrSendMTMsg**</span><span class="sxs-lookup"><span data-stu-id="f1fec-156">**A4SWIFT_FrrSendMTMsg**</span></span>|  
    |<span data-ttu-id="f1fec-157">MQ 系列平移/NAN (MQ Series 传输级 ACK/NAK)</span><span class="sxs-lookup"><span data-stu-id="f1fec-157">MQ Series PAN/NAN (MQ Series transport-level ACK/NAK)</span></span>|<span data-ttu-id="f1fec-158">**A4SWIFT_FrrSendTransport**</span><span class="sxs-lookup"><span data-stu-id="f1fec-158">**A4SWIFT_FrrSendTransport**</span></span>|  
    |<span data-ttu-id="f1fec-159">MT010 （未送达警告）</span><span class="sxs-lookup"><span data-stu-id="f1fec-159">MT010 (Non-Delivery Warning)</span></span>|<span data-ttu-id="f1fec-160">**A4SWIFT_FrrSend010NDW**</span><span class="sxs-lookup"><span data-stu-id="f1fec-160">**A4SWIFT_FrrSend010NDW**</span></span>|  
    |<span data-ttu-id="f1fec-161">MT011 （送达通知）</span><span class="sxs-lookup"><span data-stu-id="f1fec-161">MT011 (Delivery Notification)</span></span>|<span data-ttu-id="f1fec-162">**A4SWIFT_FrrSend011Delivered**</span><span class="sxs-lookup"><span data-stu-id="f1fec-162">**A4SWIFT_FrrSend011Delivered**</span></span>|  
    |<span data-ttu-id="f1fec-163">MT012 （发件人通知）</span><span class="sxs-lookup"><span data-stu-id="f1fec-163">MT012 (Sender Notification)</span></span>|<span data-ttu-id="f1fec-164">**A4SWIFT_FrrSend012SenderACK**</span><span class="sxs-lookup"><span data-stu-id="f1fec-164">**A4SWIFT_FrrSend012SenderACK**</span></span>|  
    |<span data-ttu-id="f1fec-165">MT015 （DNK 或延迟的 NAK）</span><span class="sxs-lookup"><span data-stu-id="f1fec-165">MT015 (DNK, or Delayed NAK)</span></span>|<span data-ttu-id="f1fec-166">**A4SWIFT_FrrSend015DNK**</span><span class="sxs-lookup"><span data-stu-id="f1fec-166">**A4SWIFT_FrrSend015DNK**</span></span>|  
    |<span data-ttu-id="f1fec-167">MT019 （中止通知）</span><span class="sxs-lookup"><span data-stu-id="f1fec-167">MT019 (Abort Notification)</span></span>|<span data-ttu-id="f1fec-168">**A4SWIFT_FrrSend019Abort**</span><span class="sxs-lookup"><span data-stu-id="f1fec-168">**A4SWIFT_FrrSend019Abort**</span></span>|  
    |<span data-ttu-id="f1fec-169">MTS21_FIN_ACKNAK （发送由 LT (ACK) 的 FIN 消息确认</span><span class="sxs-lookup"><span data-stu-id="f1fec-169">MTS21_FIN_ACKNAK (Acknowledgment of a FIN message sent by an LT (ACK)</span></span>|<span data-ttu-id="f1fec-170">**A4SWIFT_FrrSendS21ACK**</span><span class="sxs-lookup"><span data-stu-id="f1fec-170">**A4SWIFT_FrrSendS21ACK**</span></span>|  
    |<span data-ttu-id="f1fec-171">MTS21_FIN_ACKNAK （否定确认发送由 LT (NAK) 的 FIN 消息</span><span class="sxs-lookup"><span data-stu-id="f1fec-171">MTS21_FIN_ACKNAK (Negative acknowledgment of a FIN message sent by an LT (NAK)</span></span>|<span data-ttu-id="f1fec-172">**A4SWIFT_FrrSendS21NAK**</span><span class="sxs-lookup"><span data-stu-id="f1fec-172">**A4SWIFT_FrrSendS21NAK**</span></span>|  

11. <span data-ttu-id="f1fec-173">对于未成功发送，类别 0 到 9 SWIFT FIN 消息执行以下**筛选器**窗格：</span><span class="sxs-lookup"><span data-stu-id="f1fec-173">For Category 0 to 9 SWIFT FIN messages that are not successfully sent, do the following in the **Filters** pane:</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="f1fec-174">**A4SWIFT_FRRFailedReason**应分组下面的筛选器中的属性。</span><span class="sxs-lookup"><span data-stu-id="f1fec-174">The **A4SWIFT_FRRFailedReason** properties in the following filter should be grouped.</span></span>  

    |<span data-ttu-id="f1fec-175">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f1fec-175">Use this</span></span>|<span data-ttu-id="f1fec-176">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f1fec-176">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f1fec-177">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-177">**Property**</span></span>|<span data-ttu-id="f1fec-178">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-178">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_SendingServiceType**.</span></span>|  
    |<span data-ttu-id="f1fec-179">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-179">**Operator**</span></span>|<span data-ttu-id="f1fec-180">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-180">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-181">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-181">**Value**</span></span>|<span data-ttu-id="f1fec-182">类型**A4SWIFT_FrrService**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-182">Type **A4SWIFT_FrrService**.</span></span>|  
    |<span data-ttu-id="f1fec-183">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-183">**Group**</span></span>|<span data-ttu-id="f1fec-184">**And**</span><span class="sxs-lookup"><span data-stu-id="f1fec-184">**And**</span></span>|  
    |<span data-ttu-id="f1fec-185">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-185">**Property**</span></span>|<span data-ttu-id="f1fec-186">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-186">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FrrFailed**.</span></span>|  
    |<span data-ttu-id="f1fec-187">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-187">**Operator**</span></span>|<span data-ttu-id="f1fec-188">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-188">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-189">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-189">**Value**</span></span>|<span data-ttu-id="f1fec-190">类型 **，则返回 True**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-190">Type **True**.</span></span>|  
    |<span data-ttu-id="f1fec-191">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-191">**Group**</span></span>|<span data-ttu-id="f1fec-192">**And**</span><span class="sxs-lookup"><span data-stu-id="f1fec-192">**And**</span></span>|  
    |<span data-ttu-id="f1fec-193">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-193">**Property**</span></span>|<span data-ttu-id="f1fec-194">选择**BTS。操作**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-194">Select **BTS.Operation**.</span></span>|  
    |<span data-ttu-id="f1fec-195">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-195">**Operator**</span></span>|<span data-ttu-id="f1fec-196">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-196">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-197">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-197">**Value**</span></span>|<span data-ttu-id="f1fec-198">类型**A4SWIFT_FrrSendMTMsg**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-198">Type **A4SWIFT_FrrSendMTMsg**.</span></span>|  
    |<span data-ttu-id="f1fec-199">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-199">**Group**</span></span>|<span data-ttu-id="f1fec-200">**And**</span><span class="sxs-lookup"><span data-stu-id="f1fec-200">**And**</span></span>|  
    |<span data-ttu-id="f1fec-201">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-201">**Property**</span></span>|<span data-ttu-id="f1fec-202">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-202">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f1fec-203">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-203">**Operator**</span></span>|<span data-ttu-id="f1fec-204">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-204">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-205">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-205">**Value**</span></span>|<span data-ttu-id="f1fec-206">类型 *\<NAKErrorCode\>*，如"Y01"。</span><span class="sxs-lookup"><span data-stu-id="f1fec-206">Type *\<NAKErrorCode\>*, such as "Y01".</span></span>|  
    |<span data-ttu-id="f1fec-207">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-207">**Group**</span></span>|<span data-ttu-id="f1fec-208">**Or**</span><span class="sxs-lookup"><span data-stu-id="f1fec-208">**Or**</span></span>|  
    |<span data-ttu-id="f1fec-209">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-209">**Property**</span></span>|<span data-ttu-id="f1fec-210">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-210">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f1fec-211">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-211">**Operator**</span></span>|<span data-ttu-id="f1fec-212">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-212">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-213">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-213">**Value**</span></span>|<span data-ttu-id="f1fec-214">类型**TimedOut**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-214">Type **TimedOut**.</span></span>|  
    |<span data-ttu-id="f1fec-215">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-215">**Group**</span></span>|<span data-ttu-id="f1fec-216">**Or**</span><span class="sxs-lookup"><span data-stu-id="f1fec-216">**Or**</span></span>|  
    |<span data-ttu-id="f1fec-217">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-217">**Property**</span></span>|<span data-ttu-id="f1fec-218">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-218">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f1fec-219">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-219">**Operator**</span></span>|<span data-ttu-id="f1fec-220">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-220">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-221">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-221">**Value**</span></span>|<span data-ttu-id="f1fec-222">类型**TransportError**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-222">Type **TransportError**.</span></span>|  
    |<span data-ttu-id="f1fec-223">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-223">**Group**</span></span>|<span data-ttu-id="f1fec-224">**Or**</span><span class="sxs-lookup"><span data-stu-id="f1fec-224">**Or**</span></span>|  
    |<span data-ttu-id="f1fec-225">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-225">**Property**</span></span>|<span data-ttu-id="f1fec-226">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-226">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f1fec-227">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-227">**Operator**</span></span>|<span data-ttu-id="f1fec-228">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-228">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-229">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-229">**Value**</span></span>|<span data-ttu-id="f1fec-230">类型**DelayedNAK**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-230">Type **DelayedNAK**.</span></span>|  
    |<span data-ttu-id="f1fec-231">**分组**</span><span class="sxs-lookup"><span data-stu-id="f1fec-231">**Group**</span></span>|<span data-ttu-id="f1fec-232">**Or**</span><span class="sxs-lookup"><span data-stu-id="f1fec-232">**Or**</span></span>|  
    |<span data-ttu-id="f1fec-233">**属性**</span><span class="sxs-lookup"><span data-stu-id="f1fec-233">**Property**</span></span>|<span data-ttu-id="f1fec-234">选择**Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-234">Select **Microsoft.Solutions.A4SWIFT.Property.A4SWIFT_FRRFailedReason**.</span></span>|  
    |<span data-ttu-id="f1fec-235">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="f1fec-235">**Operator**</span></span>|<span data-ttu-id="f1fec-236">选择**==**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-236">Select **==**.</span></span>|  
    |<span data-ttu-id="f1fec-237">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="f1fec-237">**Value**</span></span>|<span data-ttu-id="f1fec-238">类型**AbortMessage**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-238">Type **AbortMessage**.</span></span>|  

12. <span data-ttu-id="f1fec-239">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-239">Click **Apply**, and then click **OK**.</span></span>  

13. <span data-ttu-id="f1fec-240">右键单击该发送端口，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="f1fec-240">Right-click the send port, and then click **Start**.</span></span>  

14. <span data-ttu-id="f1fec-241">重复步骤 2 到 13，创建所需的每种消息类型的发送端口。</span><span class="sxs-lookup"><span data-stu-id="f1fec-241">Repeat steps 2 through 13 to create a send port for each message type required.</span></span>